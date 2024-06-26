# JJ-cookbook

Here I will talk about using the tool FFUF(Fuzz faster u fool).
It is a fast web fuzzer written in go language and it can be downloaded from below given github:
https://github.com/ffuf/ffuf

Many of the command line flags of ffuf are the same than in curl so in case you are an avid curl user, you should feel right at home with many ffuf commands.

To configure a ffuf run, two things are mandatory:
Having a wordlist, or a command that provides different inputs, Setting up a FUZZ keyword in some part of the request


We can perform directory discovery with ffuf along with tasks like virtual host discovery.
We can use the following syntax for directory discovery:

ffuf -c -w /path/to/wordlist -u https://target/FUZZ
![WhatsApp Image 2024-06-26 at 10 51 16_952479b3](https://github.com/jiteshjn6/JJ-cookbook/assets/76043839/716d674c-5edf-4588-9616-dc1071f32900)



We can fuzz host headers by using the following:

ffuf -w hosts.txt -u https://example.org/ -H "Host: FUZZ" -mc 200

We can enumerate files and can tell ffuf to look only for files with certain extensions:

ffuf -w wordlist.txt -u https://target/FUZZ -e .PHP,.HTML,.txt
![WhatsApp Image 2024-06-26 at 11 11 43_89122782](https://github.com/jiteshjn6/JJ-cookbook/assets/76043839/5141e079-3ec5-45dd-9a12-ae80c549c3cd)

