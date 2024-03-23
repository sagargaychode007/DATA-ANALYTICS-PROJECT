# CUSTOMERS BANK LOAN ANALYSIS PROJECT

create database bank_analtices;
use bank_analtices;
select * from finance_1;
select * from finance_2;

# count rows
select count(*) from finance_1 as f1;

# count rows
select count(*) from finance_2 as f2;

#TOTAL LOAN AMOUNT
Select  concat("$",format(sum(Loan_amnt)/1000000,2),"M") as Total_loan_amnt from finance_1;
select sum(loan_amnt) as total_loan_amnt from finance_1;

# TOTAL LOAN ISSUCED
Select  concat ( format(count(Member_id)/1000,2),"K") as Number_of_loan_issued from finance_1;
select count(member_id) as Number_of_loan_issuced from finance_1;

# CUMULATIVE INTEREST RATE
Select concat( format(100*avg(Int_rate),2),"%") as Cumulative_interest_rate from finance_1;
select avg(int_rate) as cumulative_interest_rate from finance_1;

# TOTAL FUNDED AMOUNT
select concat("$", format(sum(funded_amnt)/1000000,2),"M" )as total_funded_amnt from finance_1 as f1;
select sum(funded_amnt) as total_funded_amnt from finance_1 as f1;

# AVG DTI (DEPARTMENT TO INCOME RATIO)
Select concat(format(avg(dti),2),"%") as Average_DTI from finance_1;
select avg(dti) as Average_DTI from finance_1;

# FIRST KPI 1
# YEAR WISE LOAN AMOUNT
Select year(Issue_d) as Year_of_issue_d,
concat("$",format(sum(Loan_amnt)/1000000,2),"M") as Total_loan_amount from Finance_1
group by Year_of_issue_d
order by Year_of_issue_d;

#KPI 2
# GRADE & SUBGRADE WISE REVOLVING BALANCE
select f1.grade,f1.sub_grade,concat("$",format(sum(f2.revol_bal)/1000000,2),"M") as revolving_balance from finance_1
as f1 inner join finance_2 as f2 on f1.id = f2.id
group by grade,sub_grade
order by grade,sub_grade;

#KPI 3
# TOATAL PAYMENT FOR VERIFIED STATUS VS NON VERIFIED STATUS
select verification_status,concat(format(sum(total_pymnt)/1000000,2),"m") as toatal_pymnt from finance_1 as f1 inner join finance_2 as f2 
on f1.id = f2.id
group by verification_status ;

select verification_status , sum(total_pymnt) as toatal_pymnt from finance_1 as f1 inner join finance_2 as f2 
on f1.id = f2.id
group by verification_status;

#KPI 4
# STATE WISE &  MONTH WISE LOAN STATUS
select addr_state as state , month(last_pymnt_d) as monthn, loan_status from finance_1 as f1 
inner join finance_2 as f2 on f1.id = f2.id
order by state, monthn;

#KPI 5
# HOME OWNERSHIP VS LAST PAYMENT DATE
select home_ownership as hm_onr , last_credit_pull_d as dt from finance_1 as 
f1 inner join finance_2 as f2 on f1.id = f2.id
order by hm_onr;





