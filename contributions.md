# Contribution README

## Chosen Issue

[Fix Gitlab/JsonSafeParse: ee/app/models/ai/conversation/message.rb (#586107)](https://gitlab.com/gitlab-org/gitlab/-/issues/586107)

## Problem Summary

This issue involves replacing `Gitlab::Json.parse` with `Gitlab::Json.safe_parse` in the file `ee/app/models/ai/conversation/message.rb` to comply with GitLab's internal RuboCop coding standards. The `safe_parse` method adds built-in protections against oversized and deeply nested JSON payloads, making the codebase more secure and resilient. Without this change, the code is vulnerable to potentially malicious or malformed JSON input that could cause performance or security issues. I chose this issue because it is clearly documented, provides a practical introduction to GitLab's contribution workflow and security-conscious coding conventions, and has "first timer" and "quick win" labels.

## About Me

- **Name:** Tito Garcia
- **University:** University of Florida
- **Major:** Computer Science
- **GitHub:** [github.com/Poiixen](https://github.com/Poiixen)
- **GitLab:** [gitlab.com/Poiixen](https://gitlab.com/Poiixen)