# usefun

Executables which I keep in `$PATH`.
I find it very handy.

## autocmd

From the shell
```sh
./autocmd ttt.tex pdflatex ttt.tex
```
would mean to wait for `ttt.tex` to be modified
and then to execute
```sh
pdflatex ttt.tex
```

Note
* Uses `inotifywait`
 	may be installed with 
	`apt install inotify-tools`

* Get out with good old `CTRL-C`

## table

From the shell
```sh
./table f.txt | gnuplot -p
```
would generate a plot.
x-axis will have values from col1.
y-axis would have values from 
* col2,
* col3,
* col4
.
.
.

Col1, col2... being the columns in `f.txt`

Possible args would be
* `save="png"`
	would save file in png format
	you could pdf or whatever gnuplot understands.
* `spec="w l"` would mean in gnuplot `with lines`
	and hence all plots would be with lines instead
	of points.

Being an `awk` script stdin works.
From the shell try this to understand.
```sh
echo "1 34 45\n2 35 46\n3 36 46" \
	| ./table spec="w l" save=png \
	| gnuplot
```
