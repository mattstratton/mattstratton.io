+++
date = "2015-08-28T02:20:39-05:00"
Tags = ["chef"]
title = "iterating through word arrays is your friend in chef"

+++

Often times, when you're installing a set of packages or Windows Features, for example, in Chef, you have a long list of items you want to install. Here's one way to do it:

```
package 'nginx' do
  action :install
end

package 'mysql' do
  action :install
end

package 'git' do
  action :install
end
```

Pretty cumbersome, no? But with the magic of array iteration, we can knock this out much more simply:

```
%[nginx mysql git].each do |package|
  package package do
    action :install
  end
end
```

The `%w` portion says "split this array based on whitespace (or by 'word')". Then for each of those items, shove the value into the variable `package`, which we can then loop through.

Magic!
