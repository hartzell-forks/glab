- I generally want to run this "freestyle", not from within a clone of
  a particular project's repository.

  I'd also like to do some bulk work that doesn't give me easy access
  to human readable project names, e.g. using an api call to find all
  of the issues that don't have weights set:

  ```
  env GITLAB_TOKEN=$(cat GITLAB_TOKEN) GITLAB_URI=gitlab.techsci.sana.com glab api --paginate '/groups/6/issues?weight=none' | jq '.[] | "\(.project_id) \(.id)"'
  ```

  and then set them.

  So, I need to extend the `--repo` flag to take a numeric project id
  in addition to user/project or group/namespace/proj.
