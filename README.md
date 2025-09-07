# Insured-Assurance


 # Optional: Uploads the full dependency graph to GitHub to improve the quality of Dependabot alerts
- name: Update dependency graph
  uses: advanced-security/maven-dependency-submission-action@571e99aab1055c27a1e230b0969

- name: scp ssh pipelines
  uses: cross-the-world/ssh-scp-ssh-pipelines@latest
  with:
    host: ${{ secrets.HOST }}
    user: ${{ secrets.USERNAME }}
    pass: ${{ secrets.PASSWORD }}
    port: ${{ secrets.PORT }}
    scp: |
      ./target/*.war => /tmp/
    last_ssh: |
      ls -lart /tmp
