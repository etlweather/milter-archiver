Why a milter archiver?

If you are required to also log source and destination IPs and BCCs (additional rcpt to's not in a CC field communicated at the SMTP protocol level), then the only option is do this in the MTA, or in a milter application that has hooks in the MTA process (which is exactly why milter was invented).

It uses a simple regex file that can be used with several source target-mailbox rules to define what gets mirrored where. The archiver tries to be as quiet as possible.

The possible methods to archive are SMTP, sendmail inject / Postfix inject, IMAP delivery, and milter-add recipient.

It was build as a replacement for a Postfix BCC setup: (sender\_bcc\_maps = regexp:/etc/postfix/archive; recipient\_bcc\_maps = regexp:/etc/postfix/archive).