# Rupesh Blog

## Writing New Blog command

```ruby

bundle exec jekyll compose "Cloud Security Defense In-Depth Azure Approach" --date 2023-02-25

```

## Writing new draft

`bundle exec jekyll draft "My new Draft"`

### Publishing draft

`bundle exec jekyll publish _drafts/my-new-draft.md --date 2022-06-04`



## Serve in dev

`bundle exec jekyll serve`

```
bundle exec jekyll serve --limit_posts=5
```

[![Build every day](https://github.com/rupeshtiwari/blog/actions/workflows/schedule-posts.yml/badge.svg?branch=main)](https://github.com/rupeshtiwari/blog/actions/workflows/schedule-posts.yml)
