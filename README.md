# Zhuoran Liu's personal acdemic folio

## Jeklly Theme I Am Using

> With modifications by myself

https://github.com/alshedivat/al-folio

## Command to install

- Ruby
- gem install bundler
- gem install jekyll bundler

## Command to run

- bundle install
- bundle exec jekyll serve

## Command to build (for pure static files)

- bundle exec jekyll build

## Command to run npx prettier (format checker)

You need to install `@shopify/prettier-plugin-liquid` before first time running prettier.

- npm install --save-dev @shopify/prettier-plugin-liquid

Check only

- npx prettier --check .

Check and rewrite All files

- npx prettier --write .

## **Notice**

Require Ruby>=3.0, I am using 3.3.0(arm64) through rbenv.
