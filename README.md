git-search-and-triage
=====================

# Roadmap for initial search and triage

From a list of search vectors

* Search blob via the GitHub API
 * If that fails, use search to find the repo, clone it, grep for the vector
* Determine if it actually meets criteria (possibly keep false positives)
* (Optionally) Find the commit that contains the line/snippet (git blame)
* Extract the committer's email
* Since repos are evolving, we won't care about prior runs (unless we track commit hash/blame/history)
* Post the results to a webhook, queue, disk, somewhere

# Roadmap for service (for separate repo)

* Database repository hit + results (e.g. had vector, false positive, etc.)
* Write email template(s), possibly mapped to collections of vectors
* Alert the user by email rather than submitting issue (Mailgun)
  * This is to eliminate "following" the bot to find interesting vectors
* Track time of response/change after email posted
* On lack of response, escalate (issue)
