#### Create an empty file
``` touch notes.txt ``` 

#### Write the first line
```echo "Linux file I/O practice started" > notes.txt```

#### Append second line
```echo "Using echo with redirection" >> notes.txt```

#### Append third line using tee
``` echo "This line is written using tee" | tee -a notes.txt```

#### Read the full file
```cat notes.txt```

#### Read first 2 lines
```head -n 2 notes.txt```
