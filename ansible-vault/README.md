<div align="center">

![Project Logo](https://webuxlab-static.s3.ca-central-1.amazonaws.com/logoAmpoule.svg)

<h2>Vault Generator</h2>

<p align="center">
  <a href="https://github.com/yet-another-tool/copy-paste/issues">Report Bug</a>
  ·
  <a href="https://github.com/yet-another-tool/copy-paste/issues">Request Feature</a>
</p>
</div>

---

<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about">About</a>
      <ul>
        <li><a href="#technologies">Technologies</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>

---

<a href="https://badge.fury.io/js/@yetanothertool%2Fvault"><img src="https://badge.fury.io/js/@yetanothertool%2Fvault.svg" alt="npm version" height="18"></a>

---

## About

Simple YAML Generator using local saved JSON template to facilitate and speed up the creation of new vaults within a project.

### Technologies

This section covers the tools and packages used for the project,

- NodeJS
- `inquirer`
  - For interactive shell
- `js-yaml`
  - To convert the generated JSON to YAML
- `ansible-vault`
  - To encrypt the strings

## Getting Started

### Prerequisites

- NodeJS

### Installation

```bash
npm install -g @yetanothertool/vault
```

## Usage

### The template

You can look at `tests/vault.json` for a template example.
and the `tests/decrypt.yml` contains an example to unvault the values when using the string approach.

Documentation regarding the YAML Format generated: https://docs.ansible.com/ansible/latest/collections/community/aws/aws_ssm_parameter_store_module.html

**For Version > 1.3.0**:
- Added new option for the templates (`type`)
- Support new types with inquirer
  - input
  - editor
  - list
  - checkbox
  - password

### Create new template

This command let you attach a `.json` template to an alias.

```bash
yat-vault create
```

![Create Template](https://github.com/yet-another-tool/copy-paste/raw/main/ansible-vault/docs/example-create.png)

### Generate vault from template

#### To prepare the whole file 

The data is generated unecrypted, it is up to you to encrypt the whole file.

```bash
yat-vault generate
```

![Ansible Vault File](https://github.com/yet-another-tool/copy-paste/raw/main/ansible-vault/docs/example-generated-vault-file.png)

#### To encrypt the value as string

It uses the `ansible-vault` npm package to encrypt each values.

```bash
yat-vault generate-string
```

![Ansible Vault String](https://github.com/yet-another-tool/copy-paste/raw/main/ansible-vault/docs/example-generated-vault-string.png)
![Ansible Vault String v1.3.0](https://github.com/yet-another-tool/copy-paste/raw/main/ansible-vault/docs/example-generate-vault-string.png)

#### Passing the vault password with environment variable

```bash
export VAULT_PASS="12345"
```

---

## Contributing

1. Create a Feature Branch
2. Commit your changes
3. Push your changes
4. Create a PR

<details>
<summary>Working with your local branch</summary>

**Branch Checkout:**

```bash
git checkout -b <feature|fix|release|chore|hotfix>/prefix-name
```

> Your branch name must starts with [feature|fix|release|chore|hotfix] and use a / before the name; 
> Use hyphens as separator;
> The prefix correspond to your Kanban tool id (e.g. abc-123)

**Keep your branch synced:**

```bash
git fetch origin
git rebase origin/master
```

**Commit your changes:**

```bash
git add .
git commit -m "<feat|ci|test|docs|build|chore|style|refactor|perf|BREAKING CHANGE>: commit message"
```

> Follow this convention commitlint for your commit message structure

**Push your changes:**

```bash
git push origin <feature|fix|release|chore|hotfix>/prefix-name
```

**Examples:**

```bash
git checkout -b release/v1.15.5
git checkout -b feature/abc-123-something-awesome
git checkout -b hotfix/abc-432-something-bad-to-fix
```

```bash
git commit -m "docs: added awesome documentation"
git commit -m "feat: added new feature"
git commit -m "test: added tests"
```

</details>

## License

Distributed under the MIT License. See LICENSE for more information.

## Contact

- Tommy Gingras @ tommy@studiowebux.com
