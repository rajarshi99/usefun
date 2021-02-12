# usefun

## autocmd

On the terminal
`autocmd ttt.tex pdflatex ttt.tex`
would mean to wait for `ttt.tex` to be modified
and then to execute `pdflatex ttt.tex`.

## table

On the terminal
`table f.txt | gnuplot -p`
would generate a plot with
col1-col2, col1-col3, col1-col4...
Being an `awk` script stdin works.
Possible args would be
* save
	give the file type for output
* spec
	spec="w l" would mean in gnuplot `with lines`
	and hence all plots would be with lines instead
	of points.
