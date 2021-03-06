Simple contract for an amortizing loan.  Due to Solidity's lack of fixed point decimals, the amortization is computed as if the rate was multiplied by 1000.  Since this quickly leads to integer overflow, only a 24 period loan is allowed (typically 2 years).  To run tests, have truffle and testrpc installed (`npm install -g truffle` and `npm install -g testrpc`).  With testrpc running in a terminal, in a seperate terminal (in the project directory) run `truffle test`.  

Since solidity rounds down every payment had "1" added so that it amortizes faster than it should.  The last payment is a smaller payment to make the balance zero.  There is no accrual of interest for past due.  There is a reputation system to encourage on time payments.

