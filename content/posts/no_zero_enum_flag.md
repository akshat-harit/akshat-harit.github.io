---
title: "Bit flips with Enums/flags"
date: 2022-01-22T16:47:32-08:00
# weight: 1
# aliases: ["/first"]
tags: ["computer science"]
author: "Akshat Harit"
showToc: false
TocOpen: false
draft: false
hidemeta: false
comments: true
description: ""
canonicalURL: "https://akshat-harit.github.io/posts/no_zero_enum_flag/"
disableShare: false
disableHLJS: true
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShareButtons: ["reddit", "ycombinator", "facebook"]

cover:
    image: "<image path/url>" # image path/url
    alt: "Bit flips with Enum Flag"
    caption: "Bit flips with Enum Flag"
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/akshat-harit/akshat-harit.github.io/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

## TLDR

If you can avoid code where an if else flag variable differ by a single bit, **do it**.

Or at least make sure that your code is better at error handling. The following is a hypothetical situation that didn't happen anywhere and caused no live sites.

## Details

The code was similar to

{{< highlight python >}}
if (str[0] == '0')
    do_part1(str[1:])
else if (str[0] == '1'):
    do_part2(str[1:])
else:
    do_error_handling()
{{< /highlight>}}

If you think '0' and '1' are icky, replace it with an enum flag.

We were generating string x as either a base64 encoded representation of a structure or a json representation. Then sending it to a cache and retrieving it as needed.

The problem is that code under do_part1 and do_part2 is not doing any error handling. As it trusts the input based on the check above. And the only source of input is the same process.

You could argue that the function should have done better error checks, but at some level in the stack, you have to trust the input. Here string length would have helped, but it could well have been a memory address where we get expected length based on first byte. And this could easily trigger a crash due to access violation.

If instead we had
{{< highlight python >}}
if (str[0] == '0')
    do_part(str[1:])
else if (str[0] == '.'):
    do_part(str[1:])
else:
    do_error_handling()
{{< /highlight >}}
We probably would have gone into the error handling code, since it is much harder to bit flip from '0' i.e. 0b110001 to '.' i.e. 0b101110.

I think general guidance would be to add 3 to get guaranteed two bit difference. I originally had above code comparing to 'A' but realized that A's binary representation 0b1000001 is actually also one bit flip away from '0' 0b110001.

Of course, ideal case would be to have better error handling, but I have to admit, that when I am writing code, I am not usually thinking of bit flips. Perhaps that'll change after seeing this case in the service.

Worrisome is that we frequently use enum to go into different branching paths. The enum values frequently differ by a single bit.
