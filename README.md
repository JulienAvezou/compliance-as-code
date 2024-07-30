# compliance-as-code
Notes from DevSecOps ch.20 for Compliance as Code

CIS Benchmarks: Center for Internet Security which sets internationally recognized security config recommendations & scoring for various technologies

Why?
automate manual process of compliance -> policies translate into code

How?
AWS Config for monitoring resources and config rules to comply with, setup notifications zhen resources become non-compliant + auto-remediate

### Demo
1. Define rules via AWS Config
   - check which resources are not compliant based on configured rules
<img width="1172" alt="Capture d’écran 2024-07-30 à 15 24 59" src="https://github.com/user-attachments/assets/39aa9795-b5c1-4c9d-9f68-28f905d32604">
<img width="908" alt="Capture d’écran 2024-07-30 à 15 19 21" src="https://github.com/user-attachments/assets/92809729-d656-44d8-a483-4e901bd5ff9d">

2. Set up automatic remediation
   - remediation actions based on SSM documents
   - create role for SSM with attached policy to allow automatic remediation
   - use this role to run the automatic remediation action for a specific rule
<img width="469" alt="Capture d’écran 2024-07-30 à 17 44 05" src="https://github.com/user-attachments/assets/38dd8eab-b92e-47bd-9b76-1ca7385b03e3">
<img width="1099" alt="Capture d’écran 2024-07-30 à 17 32 45" src="https://github.com/user-attachments/assets/2bd54bb7-40cc-4f2c-add6-ccdc2f53403f">
<img width="971" alt="Capture d’écran 2024-07-30 à 17 27 06" src="https://github.com/user-attachments/assets/5ef3bd0c-1307-485c-b604-3944e7ed2410">

3. Explore which rules you require based on setup
   - for example, define min version for EKS Cluster rule, check logging is enabled for Cluster rule
