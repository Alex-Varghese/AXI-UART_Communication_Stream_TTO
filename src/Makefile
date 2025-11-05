QUESTA := /home/share/questa.csh
SHELL := /bin/csh

main:
	clear
	clear
	vlog -sv +acc +cover +fcover -l top.log top.sv
	vsim -vopt work.top -voptargs=+acc=npr -assertdebug -l simulation.log -coverage -c -do "coverage save -onexit -assert -directive -cvg -codeAll coverage.ucdb; run -all; exit"
	vcover report -html coverage.ucdb -htmldir covReport -details
	vim transcript
