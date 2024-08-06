# Introduction

This is an experient to demonstrate use of at `git` as tool for document control.

<dl>
<dt>StateCouncil6.2.md</dt>
<dd>This the formal proccess considered by SC this year.</dd>
<dt>CurrentPolicies.md</dt>
<dd> This is the wording of the current policies, reorderd to match, as closely as possible the proposal.</dd>
<dt>NewPolicies.md</dt>
<dd>This is snapshot of the "live" proposal from the [Google doc](https://docs.google.com/document/d/1CU6ridrMg2Ymvm2ZnpvSpxG0urKiswnQ).
</dd>
</dl>

Suggested formatting for keeping the editing simple:

1. Stick to simple heading using a prefix of `#`, `##`, `###` etc for title, section and subsection.
1. Forget number tracking in numbered lists. Simply start each numbered item with `1.`, and indent four spaces for each level of indendation.
1. Avoid "reordering" without considering the massive burden you are placing on the many, many people that will need to look at things.
1. Markdown is a very simple way to format documents, but just be aware that some of powerful features may end up tripping us.

### Notes on importing docs into markdown

You can save a Google doc in [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) format. If you've kept it simple the docs don't need much work after this.

Handy commands to refomat numbered lists from Google docs:

        %s/^\d\+\.\d\+\.\d\j\.*/        1./
        %s/^\d\+\.\d\+\.*/    1./
        %s/^\d\+\./1./

### Preparing "diffs"

The web-interface of various tools generally provide simplified methods to see what has changed, and it is also possible to use simple word processes to do version comparison.

For the technically minded and adventourous, some simple commands to compare two files in your terminal:

    diff CurrentPolicies.md NewPolicies.md -udiw --color=always | less -r

    wdiff CurrentPolicies.md NewPolicies.md -li | less

    diff NewPolicies.md -CurrentPolicies.md diw --color=always | less -r

    wdiff  -w '\<em>' -x '\</em>' -y '\<strike>' -z '\</strike>' NewPolicies.md CurrentPolicies.md > diff.md

    wdiff NewPolicies.md StateCouncil6.2.md | sed '/---/d' | grep '[{}/[]'

    git diff | wdiff -d | grep '[{}/[]'
