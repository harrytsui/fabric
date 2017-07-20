Introduction 简介
============
Hyperledger Fabric is a platform for distributed ledger solutions underpinned
by a modular architecture delivering high degrees of confidentiality,
resiliency, flexibility and scalability. It is designed to support pluggable
implementations of different components and accommodate the complexity and
intricacies that exist across the economic ecosystem.

Hyperledger Fabric是一个提供了高机密性，弹性，灵活性和可扩展性的模块化分布式账本平台。它设计为了能支持不同组件
的插件化实现和适应经济体系的错综复杂。

Hyperledger Fabric delivers a uniquely elastic and extensible architecture, distinguishing
it from alternative blockchain solutions. Planning for the future of enterprise
blockchain requires building on top of a fully vetted, open-source architecture;
Hyperledger Fabric is your starting point.

区别于其他区块链所不同的是，Hyperledger Fabric传达了一种特有的弹性和可扩展的架构。针对于企业级的区块链需要建立在
完全能通过审查，开源的架构。Hyperledger Fabric会是你的起点。

We recommended first-time users begin by going through the rest of the
introduction below in order to gain familiarity with how blockchains work
and with the specific features and components of Hyperledger Fabric.

Once comfortable -- or if you're already familiar with blockchain and
Hyperledger Fabric -- go to :doc:`getting_started` and from there explore the
demos, technical specifications, APIs, etc.

What is blockchain 什么是区块链
---------------------
**distributed ledger 分布式账本**

At the heart of a blockchain network is a distributed ledger that records all
the transactions that take place on the network.

区块链网络的核心是分布式账本，这个账本记录了在网络上发生的所有交易。

A blockchain ledger is often described as **decentralized** because it is replicated
across many network participants, each of whom **collaborate** in its maintenance.
We’ll see that decentralization and collaboration are powerful attributes that
mirror the way businesses exchange goods and services in the real world.

一个区块链账本通常被描述为 **去中心化的** ，因为在众多网络参与者中账本是重复的，每个参与者都**协作**账本的维护。
我们会发现去中心化和协作性，正反映了在真实商业世界中交换商品和服务的强大属性。

.. image:: images/basic_network.png

In addition to being decentralized and collaborative, the information recorded
to a blockchain is append-only, using cryptographic techniques that guarantee
that once a transaction has been added
to the ledger it cannot be modified. This property of immutability makes it
simple to determine the provenance of information because participants can be
sure information has not been changed after the fact. It’s why blockchains
are sometimes described as **systems of proof**.

 **Smart Contracts 智能合约**

To support the consistent update of information – and to enable a whole host of
ledger functions (transacting, querying, etc) – a blockchain network uses **smart
contracts** to provide controlled access to the ledger.

为了支持信息的一致更新 - 实现大量的账本功能（交易，查询等）- 区块链网络用 **智能合约** 来提供账本的受限访问。

.. image:: images/Smart_Contract.png

Smart contracts are not only a key mechanism for encapsulating information
and keeping it simple across the network, they can also be written to allow
participants to execute certain aspects of transactions automatically.

智能合约不仅是封装和简化信息的关键原理，而且它还能写入来让参与者自动执行特定的交易。

A smart contract can, for example, be written to stipulate the cost of shipping
an item that changes depending on when it arrives. With the terms agreed to
by both parties and written to the ledger, the appropriate funds change hands
automatically when the item is received.

例如，智能合约可以写入按照商品到达的时间，来规定商品运输的成本。根据双方固定和写入账本的条款，当商品到达时，
适当的资金将自动转手。

**Consensus 共识**

The process of keeping the ledger transactions synchronized across the network –
to ensure that ledgers only update when transactions are approved by the appropriate
participants, and that when ledgers do update, they update with the
same transactions in the same order – is called **consensus**.

共识，是保持网络内账本中交易同步的过程 - 确保只有当交易被适当的参与者批准时，账本才会更新；并且当账本更新时，
账本会以相同的次序更新相同的交易。

.. image:: images/consensus.png

We’ll learn a lot more about ledgers, smart contracts and consensus later. For
now, it’s enough to think of a blockchain as a shared, replicated transaction
system which is updated via smart contracts and kept consistently
synchronized through a collaborative process called consensus.

Why is a Blockchain useful?
---------------------------

**Today’s Systems of Record**

The transactional networks of today are little more than slightly updated
versions of networks that have existed since business records have been kept.
The members of a **Business Network** transact with each other, but they maintain
separate records of their transactions. And the things they’re transacting –
whether it’s Flemish tapestries in the 16th century or the securities of today
– must have their provenance established each time they’re sold to ensure that
the business selling an item possesses a chain of title verifying their
ownership of it.

What you’re left with is a business network that looks like this:

.. image:: images/current_network.png

Modern technology has taken this process from stone tablets and paper folders
to hard drives and cloud platforms, but the underlying structure is the same.
Unified systems for managing the identity of network participants do not exist,
establishing provenance is so laborious it takes days to clear securities
transactions (the world volume of which is numbered in the many trillions of
dollars), contracts must be signed and executed manually, and every database in
the system contains unique information and therefore represents a single point
of failure.

It’s impossible with today’s fractured approach to information and
process sharing to build a system of record that spans a business network, even
though the needs of visibility and trust are clear.

**The Blockchain Difference**

What if instead of the rat’s nest of inefficiencies represented by the “modern”
system of transactions, business networks had standard methods for establishing
identity on the network, executing transactions, and storing data? What
if establishing the provenance of an asset could be determined by looking
through a list of transactions that, once written, cannot be changed, and can
therefore be trusted?

That business network would look more like this:

.. image:: images/future_net.png

This is a blockchain network. Every participant in it has their own replicated
copy of the ledger. In addition to ledger information being shared, the processes
which update the ledger are also shared. Unlike today’s systems, where a
participant’s **private** programs are used to update their **private** ledgers,
a blockchain system has **shared** programs to update **shared** ledgers.

With the ability to coordinate their business network through a shared ledger,
blockchain networks can reduce the time, cost, and risk associated with private information and
processing while improving trust and visibility.

You now know what blockchain is and why it’s useful. There are a lot of other
details that are important, but they all relate to these fundamental ideas of
the sharing of information and processes.

What is Hyperledger Fabric?
---------------------------

The Linux Foundation founded Hyperledger in 2015 to advance
cross-industry blockchain technologies. Rather than declaring a single
blockchain standard, it encourages a collaborative approach to developing
blockchain technologies via a community process, with intellectual property
rights that encourage open development and the adoption of key standards over
time.

Hyperledger Fabric is a one of the blockchain projects within Hyperledger.
Like other blockchain technologies, it has a ledger, uses smart contracts,
and is a system by which participants manage their transactions.

Where Hyperledger Fabric breaks from some other blockchain systems is that
it is **private** and **permissioned**. Rather than the “proof of work” some
blockchain networks use to verify identity (allowing anyone who meets those
criteria to join the network), the members of a Hyperledger Fabric network
enroll through a **membership services provider**.

Hyperledger Fabric also offers several pluggable options. Ledger data can be
stored in multiple formats, consensus mechanisms can be switched in and out,
and different MSPs are supported.

Hyperledger Fabric also offers the ability to create **channels**, allowing a group of
participants to create a separate ledger of transactions. This is an especially
important option for networks where some participants might be competitors and not
want every transaction they make - a special price they're offering to some participants
and not others, for example - known to every participant. If two
participants form a channel, then those participants – and no others – have copies
of the ledger for that channel.

**Shared Ledger 共享账本**

Hyperledger Fabric has a ledger subsystem comprising two components: the **world
state** and the **transaction log**. Each participant has a copy of the ledger to
every Hyperledger Fabric network they belong to.

Hyperledger Fabric有一账本子系统，由两部分组成：**全局状态**和**交易日志**。每一个参与者持有任一他所属
Hyperledger Fabric网络的账本的副本。

The world state component describes the state of the ledger at a given point
in time. It’s the database of the ledger. The transaction log component records
all transactions which have resulted in the current value of the world state.
It’s the update history for the world state. The ledger, then, is a combination
of the world state database and the transaction log history.

全局状态描述了在一指定时间账本的状态，是账本的数据库。交易日志记录了所有致使目前全局状态的交易，是全局状态的更新历史。
所以账本是全局状态数据库和交易日志历史的组合。

The ledger has a replaceable data store for the world state. By default, this
is a LevelDB key-value store database. The transaction log does not need to be
pluggable. It simply records the before and after values of the ledger database
being used by the blockchain network.

对于全局状态，账本有一可替换的数据存储。默认情况下，是LevelDB 键-值 数据库。交易日志不一定要可插拔。它仅仅记录了在区块链网络
，使用的账本数据库之前和之后的值。

**Smart Contracts 智能合约**

Hyperledger Fabric smart contracts are written in **chaincode** and are invoked
by an application external to the blockchain when that
application needs to interact with the ledger. In most cases chaincode only
interacts with the database component of the ledger, the world state (querying
it, for example), and not the transaction log.

Hyperledger Fabric智能合约是写在**chaincode**中，只有当区块链外部的程序需要与账本进行交互时，才会调用**chaincode**。
在大部分情况下，**chaincode**只与账本的数据库进行交互，全局状态（比如查询时），而并不会与交易日志进行交互。

Chaincode can be implemented in several programming languages. The currently
supported chaincode language is `Go <https://golang.org/>`__ with support
for Java and other languages coming in future releases.

**Privacy**

Depending on the needs of a network, participants in a Business-to-Business
(B2B) network might be extremely sensitive about how much information they share.
For other networks, privacy will not be a top concern.

Hyperledger Fabric supports networks where privacy (using channels) is a key
operational requirement as well as networks that are comparatively open.

**Consensus**

Transactions must be written to the ledger in the order in which they occur,
even though they might be between different sets of participants within the
network. For this to happen, the order of transactions must be established
and a method for rejecting bad transactions that have been inserted into the
ledger in error (or maliciously) must be put into place.

交易必须按照它们发生的次序写入账本，尽管交易可能发生在网络中不同的参与者之间。为了实现这个目标，必须建立交易的次序，
并且必须实施一个可以拒绝由于错误（或者恶意）写入账本的错误交易。

This is a thoroughly researched area of computer science, and there are many
ways to achieve it, each with different trade-offs. For example, PBFT (Practical
Byzantine Fault Tolerance) can provide a mechanism for file replicas to
communicate with each other to keep each copy consistent, even in the event
of corruption. Alternatively, in Bitcoin, ordering happens through a process
called mining where competing computers race to solve a cryptographic puzzle
which defines the order that all processes subsequently build upon.

Hyperledger Fabric has been designed to allow network starters to choose a
consensus mechanism that best represents the relationships that exist between
participants. As with privacy, there is a spectrum of needs; from networks
that are highly structured in their relationships to those that are more
peer-to-peer.

We’ll learn more about the Hyperledger Fabric consensus mechanisms, which
currently include SOLO, Kafka, and will soon extend to SBFT (Simplified
Byzantine Fault Tolerance), in another document.

Where can I learn more?
-----------------------

:doc:`getting_started`

We provide a number of tutorials where you’ll be introduced to most of the
key components within a blockchain network, learn more about how they
interact with each other, and then you’ll actually get the code and run
some simple transactions against a running blockchain network. We also provide
tutorials for those of you thinking of operating a blockchain network using
Hyperledger Fabric.

:doc:`fabric_model`

A deeper look at the components and concepts brought up in this introduction as
well as a few others and describes how they work together in a sample
transaction flow.

.. Licensed under Creative Commons Attribution 4.0 International License
   https://creativecommons.org/licenses/by/4.0/
