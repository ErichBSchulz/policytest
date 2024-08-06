# policytest


diff CurrentPolicies.md NewPolicies.md -udiw --color=always | less -r

wdiff CurrentPolicies.md NewPolicies.md -li | less

diff NewPolicies.md -CurrentPolicies.md diw --color=always | less -r

wdiff  -w '<em>' -x '</em>' -y '<strike>' -z '</strike>' NewPolicies.md CurrentPolicies.md > diff.md
