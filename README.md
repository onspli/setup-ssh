# setup-ssh 
Setup SSH GitHub Action

## Example

```yaml
name: Test SSH

on:
  workflow_dispatch:
  
jobs:
  deploy:
    runs-on: ubuntu-latest
      - name: Setup SSH
        uses: onspli/setup-ssh@main
        with:
          private-key: ${{ secrets.SSH_PRIVATE_KEY }}
          host: github.com
          user: git
          port: 22

      - name: Test SSH connection
        run: ssh -T git@github.com

```