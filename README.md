🧠 What this gives you

You now have a clean A/B test:

❌ Risky repo should trigger:
Remote script execution
Git-based installs
Unpinned dependencies
Runtime downloads
✅ Safe repo should NOT trigger:
Everything pinned
Deterministic installs (npm ci, --require-hashes)
No external script execution
🎯 How to use this properly

Run both through your PR flow:

PR with risky version → expect findings + failure
PR with safe version → expect clean scan
⚠️ One small note

Those hashes in requirements.txt are placeholders.
If Wiz is strict, you may want to generate real ones via:

pip-compile --generate-hashes
