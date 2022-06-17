
texts :

[`says`](says)

`hub` `repo` `avatar_url` `offical_url` `desc_oneline`

sh :

~~~ sh
repo_say ()
{
    t ()
    {
        say_para ()
        {
            : demo:
            : say_para hub avatar_url
            : out:
            : 'local hub="$1" && shift 1 &&'
            : 'shift 1 &&'
            : 'shift 1 &&'
            : 'local avatar_url="$1" && shift 1 &&'
            : 'shift 1 &&'
            
            : :: - :: :;
            
            say_para_profile ()
            {
                echo  hub
                echo  user
                echo  repo
                echo  avatar_url
                echo  offical_url
            } &&
            
            
            
            :;
        } &&
        
        say_hub ()
        {
            : demo:
            : say_hub gh
            : should out: github.com
            
            : :: - :: :;
            
            say_hub_profile ()
            {
                echo   gh github  github.com
                echo   gl gitlab  gitlab.com
                echo   jh jihu jihulab  jihulab.com
                echo   gitee  gitee.com
            } &&
            
            say_hub_profile_caser ()
            {
                : make 'gh github  github.com'
                : to 'gh|github) echo github.com ;;'
                
                :;
                
                x_names ()
                {
                    : get: 5 'local short_name_%g="$1" && shift 1 &&' short_name_ long_name
                    : out 5 lines:
                    : 'local short_name_1="$1" && shift 1 &&'
                    : 'local short_name_2="$1" && shift 1 &&'
                    : 'local short_name_3="$1" && shift 1 &&'
                    : 'local short_name_4="$1" && shift 1 &&'
                    : 'local long_name="$1" && shift 1 &&'
                    
                    : :: :;
                    
                    local num="$1" && shift 1 &&
                    local row="$1" && shift 1 &&
                    local switches="$1" && shift 1 &&
                    local switch_to="$1" && shift 1 &&
                    
                    seq -f "$row" -- "$num" |
                        (codes="$(cat -)" && printf %s "$switch_to" | xargs -0I "${switches}${num}" -- echo "$codes") &&
                    
                    :;
                } &&
                
                local fcount="$#" &&
                eval "$(x_names "$fcount" 'local short_name_%g="$1" && shift 1 &&' short_name_ long_name) :" &&
                eval echo "$(seq -f '"${short_name_%g}"' -s "'|'" -- "$(( fcount - 1 ))")""')'" 'echo "$long_name"' "';;'" &&
                
                :;
            } &&
            
            local h="$1" && shift 1 &&
            
            eval '
                
                case "$h" in
                    
                    '"$(
                        export -f -- say_hub_profile_caser &&
                        say_hub_profile | xargs -i -- sh -c 'say_hub_profile_caser {}' )"'
                    
                    *) echo "$h" ;;
                
                esac ' &&
            
            :;
        } &&
        
        "$@" &&
        
        :;
    } &&
    
    s ()
    {
        : demo:
        : s github.com stolen pipeline ...other_something_maybe_or_nothing
        : should out: stolen pipeline
        
        : ::: - ::: :;
        
        shift 1 &&
        local user="$1" && shift 1 &&
        local repo="$1" && shift 1 &&
        
        echo "$user" "$repo" &&
        
        :;
    } &&
    
    r ()
    {
        : demo:
        : r github.com stolen pipeline ...other_something_maybe_or_nothing
        : should out: stolen/pipeline.git
        
        : ::: - ::: :;
        
        shift 1 &&
        local user="$1" && shift 1 &&
        local repo="$1" && shift 1 &&
        
        echo https://"$hub"/"$user"/"$repo".git &&
        
        :;
    } &&
    
    h ()
    {
        : demo:
        : h github.com stolen pipeline ...other_something_maybe_or_nothing
        : should out: github.com
        
        : ::: - ::: :;
        
        local hub="$1" && shift 1 &&
        shift 1 &&
        shift 1 &&
        shift 1 &&
        shift 1 &&
        
        t say_hub "$hub" &&
        
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

