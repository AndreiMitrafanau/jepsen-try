# Jepsen

## Super quick start

  - step 1: go to [jepsen github](https://github.com/jepsen-io/jepsen) and check readme
  - step 2: checkout project, dependencies could be outdated don't waste your time to correct it
  - step 3: goto /docker folder and run ./up.sh as described in folder's readme
  in the end you should see something like this: ![](img/docker_script_success.png)
  - step 4: run docker ps to check the containers
  - step 5:  run test for etcd (quite easy just read the console hints)
  - step 6: run lein run serve and check docker_control node port for web interface to examine output
  ![](img/web_interface_for_test_results.png)
  - step 7: if you wandering about errors you could read this [article](https://aphyr.com/posts/316-call-me-maybe-etcd-and-consul) 
  
  Congrats! You are done with your first Jepsen test
  
  
## How to write the test

as simple as

![](img/test-example.png)

It is worth to study jepsen/etcd.clj for more understanding

so first of all you need to define main function that wraps jepsen cli 
in this case it use single-test-cmd and serve-cmd (enable results web server)
noop-test - is test stub
[r, w, cas] - means read, write and [compare and swap](https://en.wikipedia.org/wiki/Compare-and-swap) scenarios


future steps:

It's better to have cluster ready to serve state. 
 - I spend huge amount of time by checking half-working vagrant based solutions, and no success.
It should be possible to use java driver without clojure wrapper
It also could be useful to check this [repo](https://github.com/riptano/jepsen)
Tutorial on jepsen [github](https://github.com/jepsen-io/jepsen/blob/master/doc/tutorial/index.md)
 is not beginner step by step guide, more like some milestones you need to figured out how to achive
 
 
 
## Notes
 Clojure tutorial that works for me (RUS 2014) https://clojurecourse.by/ 
 I use [cursive plugin](https://cursive-ide.com/userguide/) for IntelliJ

 