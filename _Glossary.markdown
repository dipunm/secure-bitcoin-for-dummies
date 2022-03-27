---
template: page
---
# Glossary

{% capture glossary_raw %}
Mnemonic code:
A mnemonic code is a set of 12 to 24 words picked from the official 
<a href="https://github.com/bitcoin/bips/blob/master/bip-0039/english.txt">BIP 32 wordlist</a>.

A mnemonic code should be generated randomly, a mnemonic code picked by hand will 
produce a weak master key.

---

Master key:
A very long secret code used in a heirarchical deterministic wallet to derive 
multiple receive addresses and to spend from them.
{% endcapture %}


{{ glossary_raw }}

<dl>
{% assign glossary = glossary_raw | split: '---' | sort %}
{% for item in glossary %}
    {% assign title = item | split: ':' | first %}
    {% assign description = item | split: ':' | slice: 1, 1000 | join: ':' %}
    <dt>{{ title }}</dt>
    <dd>{{ description }}</dd>
{% endfor %}
</dl>