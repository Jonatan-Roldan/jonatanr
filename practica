# We will only run this action when:
# 1. This repository isn't the template repository.
# 2. The step is currently 1.
# 3. The event is a branch.
# 4. The branch name is `my-first-branch`.
# Reference: https://docs.github.com/en/actions/learn-github-actions/contexts
# Reference: https://docs.github.com/en/actions/learn-github-actions/expressions
if: >-
  ${{ !github.event.repository.is_template
      && needs.get_current_step.outputs.current_step == 1
      && github.ref_type == 'branch'
      && github.ref_name == 'my-first-branch' }}

# We'll run Ubuntu for performance instead of Mac or Windows.
runs-on: ubuntu-latest

steps:
  # We'll need to check out the repository so that we can edit the README.
  - name: Checkout
    uses: actions/checkout@v4
    with:
      fetch-depth: 0 # Let's get all the branches.

  # In README.md, switch step 1 for step 2.
  - name: Update to step 2
    uses: skills/action-update-step@v2
    with:
      token: ${{ secrets.GITHUB_TOKEN }}
      from_step: 1
      to_step: 2
      branch_name: my-first-branch
