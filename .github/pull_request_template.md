[Link to the issue](https://trello.com/c/GvGCxKHP)

(Summary: What has been changed and why)

Discussion topics:

- List bullets of issues to discuss, while the PR is with WIP
- You can here also suggest squashing, or not.

---

# Developer's checklists:

### Mandatory checks

- [ ] I have read what I have written, each commit and full PR.
- [ ] TSA rule: I have myself packed my commits, they contain only my code,
      nobody has added anything to it except me.
- [ ] There is no binding.pry!
- [ ] Naming is descriptive and proper English, proper case (camel or underscore
      ) and plurality.
- [ ] This branch is rebased on current master.
- [ ] Commit messages are ready and follow the
      [6 rules](https://chris.beams.io/posts/git-commit/#seven-rules).
- [ ] Trello task is marked with both green colors and I have verified the task
      is OK.
- [ ] PR title is without WIP.
- [ ] I have tested with reasonably new DB backup.
- [ ] I have deployed and tested on Stage (options, where needed).
- [ ] I have Rubocopped the code and manually made changes the way I find best.

### General Ruby and Rails checklist

- [ ] There's enough logging with appropriate log levels
- [ ] I only use local variables where it is really needed
- [ ] I use concerns so files are not too big
- [ ] I use concerns so files are not too big
- [ ] Usage of `bang!`-methods ([Prima Donna methods](https://github.com/troessner/reek/blob/v3.0.0/docs/Prima-Donna-Method.md))
- [ ] I checked for possible exceptions and am handling them properly. Unless I
      am re-raising, there is a comment.

### ShopApp rules

- [ ] Global setup is in settings.yml and local.yml (not ony in local).
- [ ] Company specific stuff is in company.info.
- [ ] Generic code, such as helpers, is moved to Shopapp Gem.

### ActiveRecord and DB

- [ ] Transactions are in place where needed!
- [ ] I check the values of Save and Update, otherwise I use Save!
- [ ] I have created validations
- [ ] Models: do not use AR queries outside models, use scopes
- [ ] Migrations: there are null:false, default:something unless not needed and
      always for integers and booleans.
- [ ] Non trivial default values are assigned in before_create callback.
- [ ] Migrations: there are unique indexes for unique fields and field
      combinations, for example [company,object code].
- [ ] I have added seeds for new objects.

### Routes, Controllers, Jobs and Rake Tasks

- [ ] Routes are SEO and follow collection/object/subobject/action logic.
- [ ] I have sanitized parameters.
- [ ] Controllers only deal with request, all logic is in models.
- [ ] Jobs only deal with the job, all logic is in models (and if needed
      services).
- [ ] Tasks only deal with the command line parameters, all logic is in models
      (and if needed services).

### Views, Layout and Assets

- [ ] All logic is in helpers and not in views.
- [ ] Views do not use local variables!
- [ ] Partials do not use instance variables!
- [ ] Views are localized.
