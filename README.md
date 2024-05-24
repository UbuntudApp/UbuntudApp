- # Ubuntu_dApps: Ubuntu Accounting dApp
## Overview
This repository contains a Proof of Concept (PoC) for an accounting decentralized application (dApp) and credit rating system for small and medium-sized enterprises (MSMEs) on the Cardano blockchain. The application allows users to perform triple-entry bookkeeping and automatically generates credit ratings based on financial transactions.
-
## Features
- **Triple-Entry Bookkeeping**: Track assets, liabilities, and equity.
- **Credit Rating**: Automatically calculate credit ratings based on transaction history.
- **Blockchain Integration**: Record transactions securely on the Cardano blockchain using Plutus smart contracts.
- **Access To Credit**: Give soft loans to small businesses.
## Project Structure

## Prerequisites

- Haskell Platform
- Cabal
- Plutus Playground (for testing smart contracts)

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/ubuntudApp/accounting-dapp.git
cd accounting-dapp
cabal update
cabal build

Usage
Recording a Transaction
The recordTransaction function in AccountingContract.hs is used to record a transaction. The transaction includes an ID, an account type (Asset, Liability, Equity), and an amount.

Groups (ID_User)
3 member group, 5 member group, 7 member group

Calculating Credit Rating
The calculateCreditRating function in CreditRating.hs evaluates the creditworthiness of a user based on their transaction history. The credit rating can be Excellent, Good, Average, or Poor.
module Main where

import           AccountingContract (recordTransaction)
import           CreditRating       (calculateCreditRating)
import           Ledger             (pubKeyHash)
import           Plutus.Prelude     hiding (record)
import           Wallet.Emulator    (Wallet)

-- | Main function
main :: IO ()
main = do
    -- Example usage of accounting contract
    recordTransaction (Transaction 1 Asset 100)
    recordTransaction (Transaction 2 Liability 50)

    -- Example usage of credit rating calculation
    let transactions = [Transaction 1 Asset 100, Transaction 2 Liability 50]
        creditRating = calculateCreditRating transactions
    putStrLn $ "Credit rating: " ++ show creditRating

Contributing
Contributions are welcome! Please follow these steps to contribute:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Make your changes.
Commit your changes (git commit -am 'Add new feature').
Push to the branch (git push origin feature-branch).
Create a new Pull Request.

License
This project is licensed under the MIT License

Contact
ubuntuorigin@gmail.com




