# Rupesh Blog

## Writing New Blog command

```ruby

bundle exec jekyll compose "You Dont Know How to Use Azure Tags Effectively" --date 2022-07-30

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
