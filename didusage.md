命令：
\$ registerdid
Usage: mvs-cli registerdid [-h][--fee value] ACCOUNTNAME ACCOUNTAUTH  
ADDRESS SYMBOL

Info: registerdid

Options (named):

-h [--help] Get a description and instructions for this command.
-f [--fee] The fee of tx. defaults to 1 etp.

Arguments (positional):

ACCOUNTNAME Account name required.  
ACCOUNTAUTH Account password(authorization) required.  
ADDRESS The address will be bound to, can change to other  
 addresses later.  
SYMBOL The symbol of global unique MVS Digital Identity  
 Destination/Index, supports  
 alphabets/numbers/(“@”, “.”, “\_”,  
 “-“), case-sensitive, maximum length is 64.

规则：
ADDRESS 属于当前账户;
SYMBOL 由字母、数字和特殊字符("@",".","\_","-")组成，大小写敏感，最大长度不能超过 64;
SYMBOL 不能为有效地址并且在链上不能重复;
SYMBOL 不能为关键字"BLACKHOLE"。"BLACKHOLE"大小写不敏感，即"BLACKHOLE","blockhole","BlockHole"等形式都是无效的 SYMBOL;
SYMBOL 不能为政治相关的敏感词;
注册 did 至少需要 1 个 etp
