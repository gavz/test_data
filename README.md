# test_data
Test data for gr-gsm - files containing raw signals, gsm bursts and gsm messages

vf_call6_a725_d174_g5_Kc1EF00BAB3BAC7002.cfile - signal file that was originally published by srlabs here: https://srlabs.de/airprobe-how-to/

sudo grgsm_decode -c vf_call6_a725_d174_g5_Kc1EF00BAB3BAC7002.cfile -a 725 -s $((100000000/174)) -t 0 -m BCCH

Check timeslot and mode in immediate assignement ~= 250e frame we shunt the deciphering (doable but beyond the scope of this video) as we already know Kc is 1EF00BAB3BAC7002

timeslot is 1 and mode SDCCH8

sudo grgsm_decode -c vf_call6_a725_d174_g5_Kc1EF00BAB3BAC7002.cfile -a 725 -s $((100000000/174)) -t 1 -m SDCCH8 -k 1EF00BAB3BAC7002

Next check timeslot and mode in assignement command timeslot is 5 and mode TCHF and codec FullRate FR

sudo grgsm_decode -c vf_call6_a725_d174_g5_Kc1EF00BAB3BAC7002.cfile -a 725 -s $((100000000/174)) -t 5 -m TCHF -k 1EF00BAB3BAC7002 -o speech.au.gsm -d FR

And call is DECIPHERED !!!

decode it 

toast -d speech.au.gsm

and play !!!!
