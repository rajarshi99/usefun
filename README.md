# usefun

Executables which I keep in `$PATH`,
so that it can be accessed from anywhere.

## autocmd

From the shell the command
```sh
./autocmd ttt.tex pdflatex ttt.tex
```
would mean to wait for `ttt.tex` to be modified
to execute
```sh
pdflatex ttt.tex
```
And then go back to waiting.

Note
* Uses `inotifywait`.
* It can be installed with 
	`apt install inotify-tools`
* Get out with good old `CTRL-C`

## table

Basically we generate `gnuplot` commands,
so from the shell
```sh
./table f.txt | gnuplot -p
```
would generate a plot where the
x-axis will have values from col1.
The graph would show combined plots of
* col1 with col2,
* col1 with col3,
* col1 with col4
.
.
.

Col1, col2... being the columns in `f.txt`

Possible args can be
* `save="png"`
	would save file in png format.
	You could pdf or whatever gnuplot understands.
* `spec="w l"` would mean in gnuplot `with lines`
	and hence all plots would be with lines instead
	of points.

Being an `awk` script, stdin works.
From the shell try this to understand.
```sh
echo "1 34 45\n2 35 46\n3 36 46" \
	| ./table spec="w l" save=png \
	| gnuplot
```
