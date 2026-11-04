# Discovery

What you learn before you build: cleaned meeting transcripts, notes, and your own requirement prompt. The requirements skill reads everything here and writes `../requirements.md`.

> [!IMPORTANT]
> Everything in this folder stays on your computer. Git ignores it (see `.gitignore`), so it's never committed or pushed. Only this README is in the repository.

## What goes here

| File | What it is | Where it comes from |
|---|---|---|
| `service-introduction.md` | What you told the assistant about the service when you set up the repository | `/lbbexley:new-app` (Copilot: the lbbexley-new-app skill) |
| `transcript-1.md`, `transcript-2.md` and so on | A Teams meeting transcript with roles instead of names, and contact details and reference numbers removed | `npm run transcript:clean` |
| `requirement-prompt.md` | Your project in your own words: what, who, why, rules, what's out of scope | You, from the template below |
| Any other `.md` file | Notes from a conversation, or a summary of an existing document, with no personal data | You |

Never put an original transcript, a recording or a roles file here. The assistant can read anything in your repository's folder.

## From a Teams meeting

1. **Before the meeting**, tell everyone why you're recording and transcribing it, and when you'll delete the transcript. Ask them to talk about how the service works, not about particular residents.
2. **After the meeting**, open the meeting chat in Teams, select **Recap**, then **Transcript**, then the arrow next to **Download**, and choose **Download as .vtt**. Only the organiser and co-organisers can download it. Save it in your Downloads folder, not here.
3. **Clean it yourself**, never with the assistant. In a terminal in your repository's folder:

   ```bash
   npm run transcript:clean -- ~/Downloads/<transcript file>.vtt
   ```

   In PowerShell, write the path as `"$HOME\Downloads\<transcript file>.vtt"`.

   This writes `transcript-1.md` here, and a roles file next to the original, for example `~/Downloads/<transcript file>.roles.json`.

4. **Name the speakers by role.** Open the roles file, change `"Speaker 1"` and so on to roles such as `"Service manager"` or `"Contact centre adviser"`, save it, and run the same command again. The roles file holds names, so it stays next to the original.
5. **Read the cleaned copy from start to finish.** Remove or replace:
   - names of anyone who wasn't speaking: residents, colleagues, councillors, suppliers
   - addresses, and anything else that points to where someone lives
   - details of anyone's case or situation: health, family, money, complaints
   - opinions about named colleagues, and anything said in confidence
   - small talk

   Keep how the service works, the problems people described, volumes, deadlines, rules and decisions.

6. **Delete the original transcript and the roles file** once the requirements are agreed, unless the council's retention schedule says otherwise.

The full checklist is in the data-protection skill: `.github/skills/lbbexley-data-protection/transcripts.md`.

## In your own words

No transcript, or something the meeting didn't cover? Write a requirement prompt. Copy the template from `.github/skills/lbbexley-requirements/requirement-prompt.md` to `requirement-prompt.md` here, and fill in what you know under each heading. Make it in VS Code, on your computer, not on GitHub: a file created on GitHub is published, and the assistant only sees what's on your computer. `requirement-prompt-example.md`, in the same folder as the template, shows the level of detail that helps.

## Then

Run `/lbbexley:requirements` in Claude Code, or ask the lbbexley-plan agent in GitHub Copilot to use the lbbexley-requirements skill. It reads this folder, asks what's missing, and writes `docs/requirements.md` for the service owner to check. That file is on your computer, on your branch: open it in VS Code. It isn't on GitHub until you push.
