# 🎄 Advent of Code CLI

> ⚠️ **Note:** This tool is under active development. I built in in a couple hours with no automated tests. Things may change between versions!

A little CLI tool that scaffolds and runs [Advent of Code](https://advent-of-code.com) solutions in Ruby.

This project is heavily based on [advent-of-code-rust](https://github.com/arturopala/advent-of-code-rust). Go check it out!

## Installation

Add this line to your application's `Gemfile`:

```ruby
gem "advent_of_code_cli"
```

Run `bundle install`.

## Usage

### Scaffold

This command will set up the files for any day of Advent of Code. It takes a nubmer between 1 and 25 as an argument.

```bash
bundle exec aoc_cli scaffold 1
```

This will result in the following output:

```
Creating file: 01.rb...
Creating inputs directory...
Creating file: inputs/01.txt...
Creating examples directory...
Creating examples/01 directory...
```

The file `01.rb` will have the following structure:

```rb
module Day01
  class << self
    def part_one(input)
      raise NotImplementedError
    end

    def part_two(input)
      raise NotImplementedError
    end
  end
end
```

I would love to make this structure configurable in the future.

### Download

This command will download the input for a given day.

In order for this to work, you must provide your Advent of Code session cookie to the program in an environment variable:

```bash
export AOC_COOKIE=your-cookie
```

Once the environment variable is set, you can request your personal input for any day.

```bash
bundle exec aoc_cli download 1
```

This will create the following output:

```
Fetching input...
Writing input to inputs/01.txt...
Done!
```

By default, the CLI will request the input for this year, but you can request previous years' input by passing a `--year` flag.

```bash
bundle exec aoc_cli download 1 --year 2021
```

### Solve

This command will run your solution to a certain day's puzzle.

```
bundle exec aoc_cli solve 1
```

This will create the following output:

```
Reading input...
Loading solution...

Running part one...
Part one result: 10000
Took 0.000259 seconds to solve

Running part two...
Part two result: 10000
Took 0.00026 seconds to solve

Done!
```

This command expects files to be in the format provided by the `scaffold` command. Once again, I would love to make this configurable but haven't gotten around to it yet.

## Contributing

Issues and code contributions are welcome! Happy Advent of Code to all who celebrate! 🎁
