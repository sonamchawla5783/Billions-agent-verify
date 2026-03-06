# Billions Verified Agent Identity – Setup Guide


This guide explains how to set up **Verified Agent Identity on Ubuntu / WSL (Ubuntu environment)**.

This guide explains how to install and run the verified-agent-identity scripts and link an agent DID with a human identity on the Billions Network.

---

# Requirements

* Node.js **v20+**
* npm **v10+**
* Linux / WSL / Ubuntu terminal

Check installation:

```
node -v
npm -v
```

---

# 1. Install the Skill

```
npx clawhub@latest install verified-agent-identity
```

The skill will be installed in:

---

# 2. Navigate to Scripts Directory

```
cd verified-agent-identity/scripts
```

Check files:

```
ls
```

Expected files:

```
createNewEthereumIdentity.js
manualLinkHumanToAgent.js
generateChallenge.js
linkHumanToAgent.js
signChallenge.js
verifySignature.js
package.json
```

---

# 3. Install Dependencies

```
npm install
```

Warnings such as deprecated packages or vulnerabilities can be ignored.

---

# 4. Create Agent Identity (DID)

Run:

```
node createNewEthereumIdentity.js
```

Example output:

```
did:iden3:billions:main:2VmAkXrihYaLk5RBTCkMrxh9h9mxrQ7UYEYvAAyJTL
```

This creates a new decentralized identity for the agent.


# 5. Link Human Identity to Agent

Run:

```
node manualLinkHumanToAgent.js --challenge '{"name":"My Agent","description":"Verified agent"}'
```
Chnage name, description according to you

Example output:

```
https://wallet.billions.network#i_m=...
```

---

# 6. Complete Verification

1. Open the generated URL in your browser.
2. The **Billions Wallet** will open.
3. Approve the request to link your identity.

After approval:

* Human identity is linked
* Agent DID becomes verified

---

# YOU ARE DONE.

