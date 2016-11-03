
in array checking
================
read opt
A=("Y" "y")
if [[ " ${A[*]} " == *" $opt "* ]]; then
    echo "YES"
else
    echo "NO"
fi
