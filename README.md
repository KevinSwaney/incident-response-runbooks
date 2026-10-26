# Incident Response Runbooks

Short, practical runbooks for the incidents small teams actually face. Each one starts with the first 30 minutes, then what to preserve, then what not to do.

These are generic templates. Adapt the contact names and tool names to your own environment before you need them. No client stories are included.

## Runbook 1: Compromised email account

First 30 minutes:
1. Reset the password, revoke active sessions, and turn on two-step verification.
2. Check sent mail, rules, and forwarding. Attackers often hide a rule that forwards mail out.
3. Check for password resets the attacker triggered on other services.
Preserve: full headers of suspicious messages, login history, rule changes.
Do not: delete the mailbox, or tell the user to just change the password and move on without checking rules.

## Runbook 2: Ransomware on one machine

First 30 minutes:
1. Disconnect the machine from the network, wired and wireless. Do not turn it off yet if you can preserve memory safely, but do not let it spread.
2. Check if other machines show the same ransom note or encrypted files.
3. Notify security leadership and check backup status before paying anything. Paying is a last resort, not a first step.
Preserve: ransom note, encrypted file samples, logs, and the first infected machine's image if possible.
Do not: pay from a personal account, delete logs, or reconnect the machine to "check if it works".

## Runbook 3: Business email compromise, payment fraud

First 30 minutes:
1. Stop the payment if it has not cleared. Call the bank's fraud team, not just your account manager.
2. Preserve the original message with full headers. Do not forward it as an attachment that strips headers.
3. Check who else received the same message, and whether any other payments went out.
Preserve: headers, invoice, bank details given, and any changed vendor banking information.
Do not: reply to the attacker, or quietly fix the payment without reporting it.

## Runbook 4: Stolen laptop

First 30 minutes:
1. Revoke the user's sessions and, if available, remotely lock or wipe the device.
2. Rotate any credentials stored on the device, especially VPN and email.
3. Check for sensitive data that was on the device, and whether encryption was on.
Preserve: asset record, last known location, and login attempts after the theft.
Do not: assume encryption was on. Verify it from your management console.

## Runbook 5: Exposed cloud key or secret

First 30 minutes:
1. Revoke the key immediately. Do not just rotate it later, revoke it now.
2. Check usage logs for that key: what was accessed, from where, and when.
3. Rotate any other secrets that were stored in the same place.
Preserve: key usage logs, and the commit or file where it was exposed.
Do not: delete the log, or push a new key into the same public place.

## After every incident

- Write a one-page timeline: what happened, when, what you did, what worked.
- Fix the root cause, not just the symptom: the rule, the missing control, the training gap.
- Share the lesson with the team, without naming and shaming the person who clicked.
