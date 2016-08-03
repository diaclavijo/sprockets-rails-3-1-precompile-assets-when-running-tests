# sprockets-rails 3.1 precompile assets when running tests

This is an small application to show that `sprockets-rails 3.1` is precompiling the assets when 
 the specs require them even having the configuration `assets.compile = true`. 
 
This application raise an exception when the precompilation of the assets is executed. This is to
proof that assets precompilation is run when running tests that require them. 

The test `spec/views/welcome/index.html.erb_spec.rb` just renders a view which calls 
`<%= stylesheet_link_tag 'index' %>` .

This test fails in `sprockets-rails 3.1` when trying to run the assets precompilation. 
[You can checkout from the commit and run specs](https://github.com/diaclavijo/sprockets-rails-3-1-precompile-assets-when-running-tests/commit/04f1939e9f4423686edcb564d43c1a3dec9ea253).

But it passes in `sprockets-rails 2.3` as it compiles the file on demand.
[You can checkout from the commit and run specs](https://github.com/diaclavijo/sprockets-rails-3-1-precompile-assets-when-running-tests/commit/203085d6a793e3253e947a3edc92d9d0e48a3089).


I expected that if you have `assets.compile = true` it will never run precompilation and always
 compile assets on demand. 
 
 Am I understanding something wrong here?
