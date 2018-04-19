# Merge Conflicts

This is a guided exercise for a pair of students to work through together. It will walk you through resolving merge conflicts. You will have to follow each step exactly and in order.

With your pair, decide who will play the role of Student 1 and Student 2!

## Setting up the Repository

**Student 1**

- Create a new repository on GitHub named "emergency_compliment". Don't select the "Initialize this repository with a README" option on GitHub!
- Add the second student as a collaborator to your repo by going to the Settings tab then selecting "Collaborators & Teams" on the left.

Once the repository is created on GitHub, follow these steps:

1. `git clone <repo>`
2. `cd emergency_compliment`
3. `rails new ./ -d postgresql`
4. `git add .`
5. `git commit -m "initial commit"`
6. `git push origin master`
7. `sublime .`

**Student 2**

Once Student 1 has added you as a collaborator, you will receive and email to confirm you as a collaborator to the repo Student 1 created. Check your email (it could take a few minutes to come through) and click the confirmation link. 

After Student 1 has pushed their code:

1. `git clone <url>`
2. `cd emergency_compliment`
3. `bundle install`
7. `sublime .`

## Making Your First Contributions

**Both Students (pair program on one computer)**

* Check out a new feature branch and create a fruits model.

```
rails g model fruit name weight:integer
rails db:create
rails db:migrate
```
* make a method in the model
```
class Fruit < ApplicationRecord
  def standard_weight
    weight * 2.2
  end
end
```

* Commit your changes and push them to the remote repo using this command `git push origin <branch name>`. Open a pull request on Github to merge the changes from your feature branch into `master`.

* Each student should add a comment to the PR! It should be an inline comment asking a question about the code, a suggestion or just adding an observation!

* If there are no conflicts, merge your pull request and delete your feature branches!

* If there are merge conflicts resolve them through github. You will then need to `git pull` the latest changes, resolve any conflicts locally, then `commit` and push again.


### Creating A Merge Conflict

**Both Students**

* First, make sure all remote `PRs` and branches have been merged together. Once your changes are successfully merged, delete your feature branches from GitHub and your local machines.

> to delete a git branch:

> on github:

> `git push origin --delete <the-remote-branch-name>`

> on your computer:

> `git branch -D <the-local-branch-name>`

* **Locally**, make sure you are checked out to our `master` branch.

* Then, do a `git pull origin master` to receive the latest changes.

* **Note** If you encounter a merge conflict, work together to resolve it before continuing. Then push up the changes!

**Both Students( pair program on one computer)**
* Check out a new feature branch
```
git checkout -b <your-feature-branch-name>
```
* create a new model method `tax`.
```
def tax( price )
  price * 7.5
end
```

* Push your branch and make a PR. Merge your changes in to `master` together. Both of you should then pull `master` to get the latest changes

**Both Students (individually)**

* Check out a feature branch locally.
```
git checkout -b <your-feature-name>
```

**Student 1**

* Rename the `tax` method to `fruits_taxes`.

**Student 2**

* Add param `tax_percent` to the method. Change the calculation. 

**Student 1**

* Commit your changes and push them to the remote repo. Open a pull request on Github, and merge the changes on your feature branch into `master`.

**Student 2**

* Commit your change to your feature branch. Checkout `master` and pull the latest changes. Check out your `feature` branch and merge `master` to get the changes from GitHub.

**Both Students**

On Student 2's computer, look over the merge conflicts, resolve them locally and commit.

**Student 2**

Push your feature branch to GitHub using `git push origin <branch>`. Then create a PR, and merge your branch into master.

**Both Students (individually)**

Pull down the changes to `master`.
