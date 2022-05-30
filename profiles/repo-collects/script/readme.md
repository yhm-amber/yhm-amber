
texts :

~~~~ text

~~~~

sh :

~~~ sh
repo_say ()
{
    s ()
    {
        echo "$@" &&
        
        :;
    } &&
    
    r ()
    {
        local prefix="$1" &&
        shift 1 &&
        
        echo "$prefix"/"$1"/"$2".git &&
        
        :;
    } &&
    
    d ()
    {
        echo "$1"."$2" &&
        
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

cat texts | xargs -i -- sh -c 'repo_tb {}'
~~~~

### head md tb

~~~~ sh
repo_hd ()
{
    echo '[![`'"$(repo_say d "$@")"'`]('"$(repo_say d "$@")"'-xxxx.png)](https://avatars.xxx/u/xxxx)'
} && export -f -- repo_say repo_hd ;

cat texts | xargs -i -- sh -c 'repo_hd {}'
~~~~

