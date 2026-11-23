# Sunrise Bakery - Axolo agent test site

A small static website (no build step) used to test the Axolo git agent with the **AWS Amplify** button.

The agent may add "Team Portal" ONLY in:
- the top menu (header)
- the footer

The side menu ("Quick links") and the hero button are there on purpose: the agent must REFUSE them.

## 1. Push to GitHub
Create an empty repo on GitHub named `website-test`, then in this folder:

    git init
    git add .
    git commit -m "Test site"
    git branch -M main
    git remote add origin https://github.com/<your-username>/website-test.git
    git push -u origin main

## 2. Host on AWS Amplify
AWS Console -> Amplify -> Create new app -> GitHub -> pick `website-test`, branch `main` -> Save and deploy.
`amplify.yml` tells Amplify there is nothing to build. Every push to `main` redeploys the site.

## 3. Test the agent
Click **AWS Amplify** (`"platform": "aws_amplify"`), log in with GitHub, pick `website-test`,
and ask for Team Portal in the top menu or the footer.
Also try asking for the side menu, the hero, or another change: it must refuse.
