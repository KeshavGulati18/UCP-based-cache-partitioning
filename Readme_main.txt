group members :
	1: Jemee Butani(2020csb1091)
	2: Vaibhav(2020csb1215)
	3: Keshav(2020csb1095)
	4: Kapil(2020csb1093)

we have done the UCP for 2 core and try to apply it on 4 and 6 core but got some basic errors and we are not able to ractify it , so we keep it to 2 core.
the changes done on
	1: src (cache.cc)
	2: inc	(cache.h)
	3: replacement (base_replacement.cc,lru.llc_repl,llc_replacement.cc)
	4: run_2core.sh
	
the main logic consist of 
	1: we have done the static partition of cache in replacement file in find_victim 
	2: we implement ATD with 32 set as DSS in cahce.cc and there only we calculate the omptimal partition of cache and supply it to LRU
	3: after every 5M clock cycle partition change as per the UCP 

command - 
2 core -------------->
$ chmod +x build_champsim.sh
$ sed -i -e 's/\r$/\n/' build_champsim.sh
$ ./build_champsim.sh bimodal no no no no lru 2
$ ./run_2core.sh bimodal-no-no-no-no-lru-2core 1 10 trace1 trace2

4 core --------------->
$ chmod +x build_champsim.sh
$ sed -i -e 's/\r$/\n/' build_champsim.sh
$ ./build_champsim.sh bimodal no no no no lru 4
$ ./run_4core.sh bimodal-no-no-no-no-lru-4core 1 10 trace1 trace2 trace3 trace4

8 core --------------->
$ chmod +x build_champsim.sh
$ sed -i -e 's/\r$/\n/' build_champsim.sh
$ ./build_champsim.sh bimodal no no no no lru 8
$ ./run_8core.sh bimodal-no-no-no-no-lru-8core 1 10 trace1 trace2 trace3 trace4 trace5 trace6 trace6 trace7 trace8


