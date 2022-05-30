
texts :

[`says`](says)

`user` `repo` `avatar_url` `offical_url`

sh :

~~~ sh
repo_say ()
{
    s ()
    {
        : demo:
        : s stolen pipeline ...other_something_maybe_or_nothing
        : should out: stolen pipeline
        
        : ::: - ::: :;
        
        local user="$1" && shift 1 &&
        local repo="$1" && shift 1 &&
        
        echo "$user" "$repo" &&
        
        :;
    } &&
    
    r ()
    {
        : demo:
        : r 'https://github.com' stolen pipeline ...other_something_maybe_or_nothing
        : should out: https://github.com/stolen/pipeline.git
        
        : ::: - ::: :;
        
        local prefix="$1" && shift 1 &&
        
        local user="$1" && shift 1 &&
        local repo="$1" && shift 1 &&
        
        echo "$prefix"/"$user"/"$repo".git &&
        
        :;
    } &&
    
    d ()
    {
        : demo:
        : d stolen pipeline ...other_something_maybe_or_nothing
        : should out: stolen.pipeline
        
        : ::: - ::: :;
        
        local user="$1" && shift 1 &&
        local repo="$1" && shift 1 &&
        
        echo "${user}.${repo}" &&
        
        :;
    } &&
    
    n ()
    {
        : demo:
        : n some_value some_value 'https://f-droid.org/repo/me.zhanghai.android.files/en-US/icon_BFY8kIAZkrB0kKwXt1uVDgghMociormUlcOIedEh2mA=.png' ...other_something_maybe_or_nothing
        : should out: https://f-droid.org/repo/me.zhanghai.android.files/en-US/icon_BFY8kIAZkrB0kKwXt1uVDgghMociormUlcOIedEh2mA=.png
        
        : ::: - ::: :;
        
        shift 1 &&
        shift 1 &&
        local avatar_url="$1" && shift 1 &&
        
        echo "$avatar_url" &&
        
        :;
    } &&
    
    w ()
    {
        : demo:
        : w some_value some_value 'some_value' 'https://kouchat.net' ...other_something_maybe_or_nothing
        : should out: https://kouchat.net
        
        : ::: - ::: :;
        
        shift 1 &&
        shift 1 &&
        shift 1 &&
        local offical_url="$1" && shift 1 &&
        
        echo "$offical_url" &&
        
        :;
    } &&
    
    "$@" ;
} ;
~~~



### repo md tb

~~~~ sh
repo_tb ()
{
    echo '|[![]()]()|`'"$(repo_say s "$@")"'`|`'"$(repo_say r https://github.com "$@")"'`|'
} && export -f -- repo_say repo_tb ;

cat says | xargs -i -- sh -c 'repo_tb {}'
~~~~

### head md tb

~~~~ sh
repo_hd ()
{
    echo '[![`'"$(repo_say d "$@")"'`]('"$(repo_say d "$@")"'-xxxx.png)]('"$(repo_say n "$@")"')'
} && export -f -- repo_say repo_hd ;

cat says | xargs -i -- sh -c 'repo_hd {}'
~~~~

