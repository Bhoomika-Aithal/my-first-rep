# !/usr/bin/bash
#
#guessinggame.sh - guessing name in BASH
#
guess=-1
typeset -i num=0

echo -e "guessinggame.sh - How many files are in the current directory?\n"

###Generate random number
((answer = RANDOM % 10+1))

###play game
while(( guess!=answer)); do
    num=num+1
    read -p "Enter guess $num:" guess
    if (( guess<answer)); then
        echo "Too high"
    elif ((guess>answer)); then
        echo "Too low"
    fi
done
echo -e "Congratulatons! The guess is correct.That took $num gueses.\n"
