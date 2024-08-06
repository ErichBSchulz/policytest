# policytest


diff CurrentPolicies.md NewPolicies.md -udiw --color=always | less -r

wdiff CurrentPolicies.md NewPolicies.md -li | less

diff CurrentPolicies.md NewPolicies.md -diw --color=always | less -r

wdiff  -w '<em>' -x '</em>' -y '<strike>' -z '</strike>' CurrentPolicies.md NewPolicies.md > diff.md
