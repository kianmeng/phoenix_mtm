# Phoenix MTM Helpers
[![.github/workflows/ci.yml](https://github.com/adam12/phoenix_mtm/actions/workflows/ci.yml/badge.svg)](https://github.com/adam12/phoenix_mtm/actions/workflows/ci.yml)
[![API Docs](https://img.shields.io/badge/api-docs-yellow.svg?style=flat)](https://hexdocs.pm/phoenix_mtm/)

A small collection of functions to make it easier working with `many_to_many` Ecto
associations and checkboxes to create them.

If you are familiar with Ruby on Rails, analogous to `collection_check_boxes`.

## Installation

Add phoenix_mtm to your list of dependencies in `mix.exs`:

      def deps do
        [{:phoenix_mtm, "~> 1.0.0"}]
      end

If you're still on Ecto 2, you'll want to use the pre-1.0 release:

      def deps do
        [{:phoenix_mtm, "~> 0.5.1"}]
      end

## Usage

1. Ensure your schema is setup with a `many_to_many` association. You will likely
   need to ensure the `on_delete` and `on_replace` keys are present. See the example
   in the docs for `PhoenixMTM.Changeset.cast_collection`.

2. Inside your changeset function, pipe your changeset through `PhoenixMTM.Changeset.cast_collection`,
   providing the association name, repo module, ans association module.

3. Inside your template, call `PhoenixMTM.Helpers.collection_checkboxes` where
   you want the output of checkboxes to occur. This function accepts a form,
   the association name, a keyword list of values, and a list of pre-selected values.

   You can pass along attributes directly to the generated inputs and labels by
   passing a keyword list inside both `label_opts` and `input_opts` keys.

## Contributing

I love pull requests! If you fork this project and modify it, please ping me to see
if your changes can be incorporated back into this project.

That said, if your feature idea is nontrivial, you should probably open an issue to
[discuss it](http://www.igvita.com/2011/12/19/dont-push-your-pull-requests/)
before attempting a pull request.

## License

PhoenixMTM is released under the MIT License. See [LICENSE](LICENSE.md) file for
more information.
