CC = mpic++

# Flags
CFLAGS = -std=c++11 -Wall -Wextra -pedantic -O3 -fopenmp
# -Werror 

LDFLAGS = -I/usr/lib -lpthread -lrt -lnuma
BOOST_LDFLAGS = -lboost_serialization -lboost_mpi -lrt

all: test_boost_lock_free_queue test_numa_lock_free_queue test_lock_free_queue

test_boost_lock_free_queue : test_boost_lock_free_queue.cpp
	$(CC) $(CFLAGS) $< -o $@ $(BOOST_LDFLAGS)

test_numa_lock_free_queue : test_numa_lock_free_queue.cpp
	$(CC) $(CFLAGS) $< -o $@ $(LDFLAGS)

test_lock_free_queue : test_lock_free_queue.cpp
	$(CC) $(CFLAGS) $< -o $@ $(LDFLAGS)

clean:
	rm -f *.o test_lock_free_queue test_numa_lock_free_queue test_boost_lock_free_queue
