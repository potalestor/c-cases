# Find all number in the string

```C++
string s =
      "The farm is made up of 11 rows of panels, 9 133 kW rows and 2 smaller "
      "70kW rows that were the farm’s pilot project.";
regex pattern("([[:d:]]+)");
smatch matches;
sregex_iterator reg_iter(s.cbegin(), s.cend(), pattern);
sregex_iterator reg_end;
while (reg_iter != reg_end) {
  cout << (reg_iter++)->str(1) << " ";
}

Output: 11 9 133 2 70
```
