# __*How To-Clear cached memory on linux server*__


## *_Prerequsit_*
You need root previledge on server 

### _*Steps*_

* Establish an ssh connection on server check current state of memory
    ```
    free -h
    ```

                  total    |   used    |   free   |  shared   | buffers   |  cached
        Mem:    |  15G     |    14G    |   776M   |  408K     |   127M    |   5.1G

        -/+ buffers/cache: |   9.2G    |   6.0G   |
        Swap:   |    0B     |     0B   |     0B

* change user as root.
  ```
  sudo su
  sync; echo 1 > /proc/sys/vm/drop_caches
  ```
                     total    |   used    |   free   |  shared   | buffers   |  cached
        Mem:         |  15G   |    9.4G   |    5.9G  |    408K   |   1.8M    |   272M
        -/+ buffers/cache:    |    9.1G   |    6.1G
        Swap:        |  0B    |    0B     |    0B
