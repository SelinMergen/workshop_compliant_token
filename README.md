# **Aleo Workshop: Compliant Token Challenge – Earn $100!**  

## **Overview**  
This workshop is focused on exploring compliance mechanisms within the Aleo ecosystem. Participants can earn **$100 USD** by deploying a new Aleo program that introduces a **compliance rule, mechanism, or example** related to compliant tokens. The best use of pAleo/Pondo tokens will earn an additional **$150 USD** worth of the pondo token.

## **How to Participate**  
### 1. Develop & Deploy  
- Build and deploy an **Aleo program** that demonstrates a **new** compliance rule, enforcement mechanism, or regulatory example.  
- Examples include, but are not limited to:
  - KYC/AML enforcement.
  - Transfer restrictions (e.g., jurisdiction-based, whitelist/blacklist).  
  - Time-locked transactions or permissions.  
  - Privacy-preserving compliance reporting.  
  - On-chain attestations or proof-of-compliance mechanisms.

### 2. Publish Your Work  
- Push your Aleo program code to a **public GitHub repository**.  
- Include a `README.md` with:  
  - A description of the compliance feature.  
  - How it works and its intended use case.  
  - Deployment instructions.

### 3. Submit Your Entry  
- Share your project link (GitHub + deployed program) via a form we will share after this event.  
- Provide a short explanation of your compliance mechanism.  

### 4. Get Rewarded!  
- The **eligible submissions** will receive **$100 USD each**.  
- Submissions will be reviewed for originality, correctness, and adherence to the rules.

## **Rules & Eligibility**  
- Your program **must introduce a new compliance feature** (not just a fork of an existing one).  
- The program should be **functional and deployable** on Aleo.  
- Code must be **open-source** and properly documented.  
- Only **one reward per participant**.  
- We reserve the right to reject submissions that are incomplete, plagiarized, or non-functional.

## **Deadline**  
- Submissions are open from 2/27/25 to 3/1/25  

## **Questions?**  
Join our [**Discord**](https://link.leo.app/discord) or contact @coralrelief for any questions.

## **Compliant Token Implementation**

This project implements a compliant token on Aleo with the following compliance features:

## **Compliance Features**

### 1. KYC Verification Levels
- **None (0)**: No KYC verification
- **Basic (1)**: Basic KYC verification, required for standard transfers
- **Full (2)**: Full KYC verification, required for large transfers (>1,000,000 tokens)

### 2. Jurisdiction-Based Restrictions
- **None (0)**: Jurisdiction not determined
- **Allowed (1)**: User is from an allowed jurisdiction
- **Restricted (2)**: User is from a restricted jurisdiction, transfers not allowed

### 3. Blacklist Functionality
- Administrators can blacklist addresses to prevent them from receiving or sending tokens
- Blacklisted addresses cannot obtain spend limits or participate in transfers

### 4. Daily Spending Limits
- Each user has a configurable daily spending limit
- Limits are enforced on a per-epoch basis (1 epoch = 1 day)
- Current limit: 10,000,000,000 tokens per day

### 5. Large Transfer Restrictions
- Transfers exceeding 1,000,000 tokens require full KYC verification

## **How It Works**

1. **Admin Setup**:
   - Admin initializes the token and mints the supply
   - Admin sets KYC levels and jurisdiction status for users
   - Admin can blacklist addresses as needed

2. **User Onboarding**:
   - Users must complete at least basic KYC
   - Users must be from an allowed jurisdiction
   - Users receive a spend limit record after verification

3. **Transfer Process**:
   - Transfers check KYC level, jurisdiction status, and blacklist status
   - Large transfers require higher KYC levels
   - Daily spending limits are enforced

## Installation

1. Ensure [Leo is installed](https://github.com/ProvableHQ/leo)
2. Ensure the ADMIN_ADDRESS is set to an address you have

That's it!

## Building

1. `leo build`

## Deploying

1. `leo deploy` - Need some credits first

## Execution

### Admin Functions

- Initialize: `leo run initialize`
- Private Mint: `leo run mint_private`
- Set KYC Status: `leo run set_kyc_status [ADDRESS] [LEVEL]`
- Set Jurisdiction: `leo run set_jurisdiction [ADDRESS] [STATUS]`
- Set Blacklist Status: `leo run set_blacklist_status [ADDRESS] [IS_BLACKLISTED]`
- Issue Limit: `leo run issue_limit [ADDRESS]`

### User Functions

- Transfer Private: `leo run transfer_private [TOKEN_RECORD] [SPEND_LIMIT_RECORD] [AMOUNT] [RECIPIENT] [EPOCH]`

## Example Output

[Example outputs for each function as in your original README]