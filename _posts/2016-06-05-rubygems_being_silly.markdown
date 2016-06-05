I was having the following issue today:

``` /home/markitoxs/.rbenv/versions/2.3.0/lib/ruby/site_ruby/2.3.0/rubygems/specification.rb:2278:in `check_version_conflict': can't activate json-1.8.2, already activated json-1.8.3 (Gem::LoadError)
  from /home/markitoxs/.rbenv/versions/2.3.0/lib/ruby/site_ruby/2.3.0/rubygems/specification.rb:1404:in `activate'
    from /home/markitoxs/.rbenv/versions/2.3.0/lib/ruby/site_ruby/2.3.0/rubygems/core_ext/kernel_require.rb:89:in `block in require'
      from /home/markitoxs/.rbenv/versions/2.3.0/lib/ruby/site_ruby/2.3.0/rubygems/core_ext/kernel_require.rb:88:in `each'
        from /home/markitoxs/.rbenv/versions/2.3.0/lib/ruby/site_ruby/2.3.0/rubygems/core_ext/kernel_require.rb:88:in `require'
          from /home/markitoxs/.rbenv/versions/2.3.0/lib/ruby/gems/2.3.0/gems/right_chimp-2.1.16/lib/right_chimp.rb:12:in `<top (required)>'
            from /home/markitoxs/.rbenv/versions/2.3.0/lib/ruby/site_ruby/2.3.0/rubygems/core_ext/kernel_require.rb:68:in `require'
            ```

It turns out it was a rubygems issue, so all I had to do was:

```gem update --system```
followed by:
```gem cleanup```
