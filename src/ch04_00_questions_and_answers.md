# Questions and Answers (as of 9-14-2020)
## How popular is Rust? 
According to the Stack Overflow's 2020 Developer Survey, only [5.1% of developers are currently using Rust](https://insights.stackoverflow.com/survey/2020#technology). So **currently** not very popular.

It is worthy to note though, for the 5th year in a row, Rust has been voted [the most beloved language](https://insights.stackoverflow.com/survey/2020#technology-most-loved-dreaded-and-wanted-languages-loved). Meaning the percentage of Rust developers who wanted to continue to use Rust exceeded any other language.

## How is the interoperability of Rust with other tools?
Good.

Rust gets compiled down to a binary just like C\C++. If you have a tool that requires a binary as input (ex. gdb) then chances are high it should just work with Rust. 

## How is the Interoperability of Rust with other languages?
It depends what language you are trying to interopt with.

Interoperability between Rust and C is okay. You can directly call Rust functions from C and vice versa.

Interopting with C and Rust should be planned carefully to avoid liberal use of the unsafe keyword.  Below are the current guidelines.
- Use only basic types (`char` or `u8`, `int` or `i32`, `bool`, ect.)
- Avoid passing pointers from C to Rust. One of the primary reasons we want to use Rust is to guarantee that dereferencing a pointer will be valid. The Rust Compiler is not able to check that the pointers passed from C are safe to dereference.
- If a pointer to an array must be passed to Rust, transform the array to a slice using [std::slice::from_raw_parts](https://doc.rust-lang.org/std/slice/fn.from_raw_parts.html)

Interopting directly with C++ and Rust are not easily achievable. In general, for Rust to interopt with C++, a C interface must exist.

In general, Interopting between Rust and C can be a great way to pull a library off the shelf that you otherwise could not, but you should avoid interopting when you can because it adds complexity and negates some of Rust's safety guarantees.

Additional Resources: [Embedded Rust Book - Interoperability](https://docs.rust-embedded.org/book/interoperability/)

## Who owns Rust?
No one. Rust is 100% open source under the [APACHE](https://choosealicense.com/licenses/apache-2.0/) and [MIT](https://choosealicense.com/licenses/mit/) licenses.

Rust was originally shepherded by Mozilla, but contributors of the language vary from hobbyists to big name companies such as Google and Facebook.

Rust is governed by the open source community. See <https://www.rust-lang.org/governance>.

Additional Resources: [Individual Contributors](https://thanks.rust-lang.org/), [Corporate sponsors](https://www.rust-lang.org/sponsors), [Growing the Rust Community](https://youtu.be/duv0tuPAnO0?t=236)

## What platforms does Rust support? 
The platform support for Rust is pretty good. See <https://doc.rust-lang.org/nightly/rustc/platform-support.html> for an updated list of supported platforms.

## Who uses Rust?
 A lot of companies. See <https://www.rust-lang.org/production/users> for a list of companies using Rust in production.