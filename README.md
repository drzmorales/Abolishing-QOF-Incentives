# Abolishing-QOF-Incentives

#### STATA code for running the multiple group analysis

tsset country year
itsa y, treatid(1) trperiod(2017) figure(legend(position(6)) xlabel(2014(1)2019,  ///
labsize(2.5)) ylabel(0(20)100, labsize(2.5)) title("CHD02")) posttrend

addplot: function y=_b[_cons] + _b[_z] + (_b[_t] + _b[_z_t])*(x-2014) + (_b[_x_t2017]*(x-2014)), range (2017 2019) lpattern (longdash) lcolor(gs10) yla(0(10)100, nogrid) ///
legend(rows(2) order(1 "Scotland observed" 4 "England observed" 2 "Scotland model" 5 "England model" 7 "Scotland counterfact.") symxsize(*0.8))

#### Please refer to the following article for full details about the itsa command:
https://www.stata-journal.com/article.html?article=st0389
