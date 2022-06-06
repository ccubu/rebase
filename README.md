# rebase

- Developer 1 codes feature one from main initial commit
``` 
 git checkout -b feature/one
 touch code.txt
 echo feature 1 >> code.txt
 git add .
 git commit -m "Feature 1"
 git push origin feature/one
```

- Developer 1 creates PR1

- Developer 2 codes feature two from main initial commit
``` 
git checkout -b feature/two
touch code.txt
echo feature 2 >> code.txt
git add .
git commit -m "Feature 2"
git push origin feature/two
```

- Developer 2 creates PR2

- PR2 gets merged

- Developer 1 has to fix conflicts: 

``` // Developer 1
git checkout main
git pull origin main
git checkout feature/one
git rebase main
// Fix conflicts
git add .
git rebase --continue
git push -f origin feature/one
```

- PR1 gets merged

## Result:

![Caterpillar Graph](./result.png)