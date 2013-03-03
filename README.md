# FFI::Aspell

FFI::Aspell is an FFI binding for the Aspell library. It was mainly written as
[Raspell][raspell], a C binding for Aspell, is buggy and no longer maintained by
the main author as of April 2012.

## Requirements

* FFI: `gem install ffi`
* Dutch and Greek language packs for Aspell (only when testing the code)

## Installing Aspell

* Arch Linux: `sudo pacman -S aspell` 
* OS X: (`brew install aspell --lang=en` 

## Usage

Install the gem:

    $ gem install ffi-aspell

Load it:

    require 'ffi/aspell'

The primary class is `FFI::Aspell::Speller`, this class can be used to check for
spelling errors and the like:

    speller = FFI::Aspell::Speller.new('en_US')

    if speller.correct?('cookie')
      puts 'The word "cookie" is correct'
    else
      puts 'The word "cookie" is incorrect'
    end

For more information see the YARD documentation.

## Hacking & Contributing

1. Make sure that Aspell and the English and Dutch dictionaries for it are
   installed as well. On Arch Linux this can be done by running `sudo pacman -S
   aspell aspell-en aspell-nl`.
2. Install the gems: `bundle install`
3. Run the tests to see if everything is working: `rake test`
4. Hack away!

## Coding Standards

* FFI functions go in FFI::Aspell
* Attached function names should resemble the C function names as much as
  possible.
* No more than 80 characters per line of code.
* Document your code, pull requests with big changes but without documentation
  will be rejected.
* Git commits should be signed off, this can be done by running `git commit
  --sign`. Commits that are not signed off will be rejected.
* Follow the Git commit standards are described here:
  <http://ramaze.net/documentation/file.contributing.html#Commit_Messages>.
* Test your code! Pull requests without tests will not be accepted.

## License

The code in this repository is licensed under the MIT license. A copy of this
license can be found in the file "LICENSE" in the root directory of this
repository.

[raspell]: https://github.com/evan/raspell
