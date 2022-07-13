CC = gcc -g -I/usr/local/include/ 
LIBS += -L/usr/lib -L/usr/local/lib/ -lprotobuf-c

msg: serialize.c deserialize.c msg.pb-c.c msg.pb-c.h
	$(CC) -c msg.pb-c.c -o msg.pb.o $(LIBS)
	$(CC) serialize.c msg.pb.o -o serialize $(LIBS)
	$(CC) deserialize.c msg.pb.o -o deserialize $(LIBS)

dnstap: test-dnstap.c dnstap.pb-c.c dnstap.pb-c.h
	$(CC) -c dnstap.pb-c.c -o dnstap.pb.o $(LIBS)
	$(CC) test-dnstap.c dnstap.pb.o -o test-dnstap $(LIBS)

clean:
	@rm *.o serialize deserialize
