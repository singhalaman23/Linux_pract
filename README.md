# Linux_pract

3) Calculator
```
#!/bin/bash
echo "Enter first number"
read a
echo "Enter second number"
read b
echo "Press..."
echo "1 to add"
echo "2 to subtract"
echo "3 to multiply"
echo "4 to divide"
read ch
case $ch in
1)res=`echo $a + $b | bc`;;
2)res=`echo $a - $b | bc`;;
3)res=`echo $a \* $b|bc`;;
4)res=`echo "scale=2; $a/$b" | bc`;;
esac
echo "Result = $res"
```
4) Even or odd
```
#!/bin/bash
echo "enter a  number"
read a
if [ `expr $a % 2` == 0 ]
then
echo "number is even"
else
echo "number is odd"
fi
```
5) Prime number
```
#!/bin/bash
echo "enter the number"
read n
if [ $n -lt 2 ]
then
echo "number of not prime"
exit
fi

i=2
while [ $i -lt $n ]
do
if [ `expr $n % $i` == 0 ]
then
echo "number is not prime"
exit
fi
i=`expr $i + 1`
done
echo "number is prime"
```
6) Prime factorization
```
#!/bin/bash

echo "Enter a number: "
read number

echo "Prime factors of $number are:"

i=2
while [ $i -le $number ]; do
  if [ $((number % i)) -eq 0 ]; then
    is_prime=1
    for ((j = 2; j <= i / 2; j++)); do
      if [ $((i % j)) -eq 0 ]; then
        is_prime=0
        break
      fi
    done
    if [ $is_prime -eq 1 ]; then
      echo $i
    fi
    number=$((number / i))
    i=1
  fi
  ((i++))
done

```
7) Fibonacci series
```
#!/bin/bash
echo "enter number of terms u want to print"
read n

a=0
b=1

if [ $n == 0 ]
then
echo "0"
elif [ $n == 1 ]
then
echo "1"
else
echo "0"
echo "1"
for ((i=2; i <= n; i++));do
next=$((a + b))
a=$b
b=$next
echo "$next"
done
fi

```
