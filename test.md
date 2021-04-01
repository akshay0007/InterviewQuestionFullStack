Java--
cpu intesive- number of cores
io intensive- 

cache thread-->if they are idel for 60 sec. then kill that thread--



single thread--> create single thread and life cycle create new thread if in case it dies, and ensure that task run one after 
another


schedule
scheduleAtFixedRate
scheduleAtFixedDelay


parms-- corepoolsize,maxpoolsize,keepalivetime,workqueue,threadfactory,handler.

hadler(RejectionHandler)-->it's callback which ensure when task submitted and rejected and provide call back macanism


RejectionPolicy--
abortpolicy-->throw exc. RejectionHandlerException
discardpolicy-->submitted new task sliently discard abort thread
discardoldestpolicy-->addnew task and reject oldest one
callerunspolicy-->

Spring security---



Java
====================================
====================================
creat.
singleton---lazy-->double locking
factory
builder

beh.
temp
poroto
starategy

structural-
fligweight
structural
adapter
======================================

ExecutorService
LinkedList
BLockingQueue
