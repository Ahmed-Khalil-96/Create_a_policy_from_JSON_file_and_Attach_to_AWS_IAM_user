# Create_a_policy_from_JSON_file_and_Attach_to_AWS_IAM_user
# AWS IAM Ansible Automation

This project automates the creation of a customer-managed IAM policy in AWS and assigns it directly to an IAM user using Ansible. 

## Repository Structure

* **`create_a_policy_from_json_attach_to_user/tasks/main.yml`** - The Ansible playbook that manages the IAM policy and handles user assignment.
* **`MyEC2ReadPolicy.json`** - The standalone AWS IAM JSON file containing EC2 read permissions.

## Prerequisites

Before executing the playbook, ensure your local system meets the following requirements:

1. **Ansible & AWS Collection:** Install the official Amazon AWS collection:
   ```bash
   ansible-galaxy collection install amazon.aws
   ```
2. **Python Dependencies:** Install the required AWS SDK libraries:
   ```bash
   pip install boto3 || apt install python3-boto3
   ```
3. **AWS Credentials:** Configure your AWS authentication environment variables or ensure your active profile exists in `~/.aws/credentials`.

## Configuration & Usage

1. Open **`MyEC2ReadPolicy.json`** and adjust the permissions inside the `Statement` block if necessary.
2. Open **`create_a_policy_from_json_attach_to_usertasks/main.yml`** and change the value of `name: "Your_User"` to match your target IAM username.
3. Run the playbook from your terminal:
   ```bash
   ansible-playbook policy.yml 
   ```

*Tip: If you are using a named AWS CLI profile other than default, run the playbook like this:*
```bash
AWS_PROFILE=your-profile-name ansible-playbook policy.yml
```
