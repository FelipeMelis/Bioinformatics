## GitHub

**Create a Branch**
```
git pull origin master
git checkout -b branchname
```

**Commit changes**
```
git add -A (or ./file.fl)
git commit -m 'this change is for rucula'
git push origin branchname (or master (never do master))
```

**Solution when you push something to big to GitHub**
```
git filter-branch --tree-filter 'rm -f file-too.big' HEAD

**Prokka**
Software for bacterial genome annotation

>https://github.com/tseemann/prokka

**Snippy**
Rapid SNP calling for bacterial genomes

>https://github.com/tseemann/snippy


