https://explore.skillbuilder.aws/learn/course/35/play/463/understanding-cidr-notation

    • CIDR = classless internet domain routing
    • We use that in ACL, and network spec
    • 0 means don’t care
    • IP4 addressing is a 32 bit binary number
        ○ CIDR  10.10.101.5   > 00001010      00001010      0110010      00001101      
        ○ It has 4 octets for each of those 4 numbers in IPv4
        ○ Each one ranging from 0 to 255 as far as the number goes 
    • When we describe a CIDR range - we want to describe it as a range of number and not as a single number
    • In an example like this 10.10.0.0/16
        ○ We want to freeze the first 2 octets or the first 16 bits and then wild card the rest
        ○ Which gives all the of the IP numbers that begin with 10.10 and then wild carding the rest of them
    • /16 is the most common freezing range we see on VPC CIDR block. It is also the most you are allowed to do
        ○ You can certainly go smaller than 16 - like 17,18,19 and so on  and you can go as small as /28
        ○ /28 can possibly give you 12 addresses (which is 16 address minus the 4 AWS takes away)
        ○ /16 can give you about 65 K possible addresses
    • If /16 is the CIDR block of my main VPC, we then sub divide that for our subnets
        ○ Which need to be a subset of the /16. So, they can start with a 10.10. If I want multiple subnets I then don’t want them to have any collisions. 
        ○ Commonly we see them as /24 - which is - freezing the first 3 octets or the first 24 bits
        ○ Example
            § If my VPC is /16  with 10.10.0.0/16
            § My database subnet can be as 10.10.101.0/24  -- here I can have any ip address beginning form 0 to 55
    • To specify a single specific address - which means Im not wild card anything - then that is 
        ○ Example 10.10.101.5/32
        ○ Use case - used on security group definitions to allow traffic only from one ip address
        ○ To authorize traffic from any ip or from any internet
0.0.0.0/0