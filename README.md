# Two-Node-connection-in-Omnet-
connection of two nodes

#include<string.h>
#include<omnetpp.h>
using namespace omnetpp;

class coin : public cSimpleModule
{
protected:
    virtual void initialize() override;
    virtual void handleMessage(cMessage *msg) override;
};

Define_Module(coin);

void coin::initialize()
{
        if(strcmp("head",getName())==0)
        {
            cMessage *msg= new cMessage("hello");
            send(msg,"out");
        }
}

void coin::handleMessage(cMessage *msg)
{
    send(msg, "out");
}
