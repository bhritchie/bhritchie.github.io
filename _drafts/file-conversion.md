
Not greedily find a citation with some page number and get them as backreferences
\v(\@\a{-}\d{4}\a{-})\s{1}\[pp?[.].(\d+(–\d+)?)]

replacement maybe:
\{% cite \1 -l \2 %\}

s/\v\@(\a{-}\d{4}\a{-})\s{1}\[pp?[.].(\d+(–\d+)?)]/\{% cite \1 -l \2 %\}


Get the ones without page references

/\v\@\a+\d{4}\a+ 

backreferences:

/\v\@(\a+\d{4}\a+)

substitute: 

%s/\v\@(\a+\d{4}\a+)/\{% cite \1 %\}/g

still need to replace citations with form @key; might also be keys with text and date but no following text eg @taber1990..
