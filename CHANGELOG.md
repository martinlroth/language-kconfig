## 0.1.0 - First Release

* Known issues
  - Help blocks are not being parsed correctly. This is due to the way they are
    calculated. The line AFTER the 'help' keyword controls the indentation of
    the help block. As this line isn't available in the lexer for the keyword,
    it makes doing this correctly very difficult. As a substitute, the help
    block could be ended on the next line that has indentation equal to or less
    than the line containing the 'help' or '---help---' keyword that isn't an
    empty line. Right now, the keyword is highlighted, but if the block
    contains a valid keyword at the start of one of the lines, that would look
    to the lexer like a new keyword block.
 - The 'config' keyword block is not being parsed correctly. The block should
    end on any keyword that isn't valid within a config block. When it was
    initially configured that way, the end regex would eat the first keyword
    of the next block, messing things up.
 - Keyword lines continued to the next line with a backslash are not handled.
 - Missing some keywords that aren't used in the coreboot project.
