Inter-system Specification for ABIS (Labor Day Weekend)

1.  Functional Requirements Document Element

    a.  The system ([ABIS](https://github.com/ABISprotocol/ABIS)) shall enable decentralization of giving and microdonations processes.
    
    b.  The system shall be intuitive and voluntary, enabling users to easily "set and forget" or alter preferences.
    
    c.  The system shall provide a batching method, whereby certain transactions may be 'bundled' or 'batched,'
        either in order to be confirmed together, or so that they may be broadcast and confirmed as part of
        an extension of payment protocols.  This may include a level of randomization, dependent upon where it is implemented. 
        
    d.  Wherever possible, the system shall provide a visual framework so that the user may more easily set preferences.
    
    e.  Wherever possible, the ABIS system shall provide a means whereby different systems which implement
        ABIS conceptually, will be able to communicate and interact freely with one another.
        
    f.  Wherever possible, and with time and testing, distinct elements and implementations associated with ABIS shall be split into distinct projects as unique repositories.
        
    g.  The system shall incorporate methods whereby the user may choose between making microdonations associated with
        an identity or anonymous microdonations, depending upon the preferences of the user, so as to provide the
        ability for a single or recurring microdonation preference to have anonymity, while enabling
        the user to also associate an identity with any particular microdonation or range of microdonations.
        
    h.  Initial conceptual descriptions are shown [here](https://github.com/ABISprotocol/ABIS#abis).


2.  Essential System Requirements Within Different Frameworks

    a.  Bytecoin / BCN
    
        1.  Multisignature feature, to enable multiple parties to specify when a certain microdonation may occur,
            or to develop preferences for what sort of types or categories of microdonations should be supported
            through recurrence or a similar scheme as may be utilized in a multiparty context.
            
        2.  Provision within wallet to set mix_in count at user preference for certain transactions, so that the
            desired mix_in number may be established as part of the user's anonymity preference.
            
        3.  Wallet system which enables recurring donations contingent upon user specification of threshold, 
            such that with threshold count of W (where W = a BCN amount that includes the amount of microdonation,
            and a fee, or a portion of fee for bundled microdonations which may be provided through an extension of
            payment protocols), any transaction at or above W (where W includes microdonation and fee) will trigger 
            a release of microdonations at preferences set by the user, wherever microdonations together are an amount less than W and greater than zero, for microdonations which are at amounts of X, Y, and Z [or X+Y+Z] as examples.
            
        4.  Code Snippets, Suggestions for Implementation (Published on Sept. 1, 2014):
            Note that these are initial suggestions intended to stimulate development discussion, 
            and require vetting, refinement, and adjustment. These can thus be changed, used as the 
            basis for a new issue or pull request, or simply used for general implementation discussion.
            [Dependencies](https://github.com/amjuarez/bytecoin/blob/master/README)
            Under [TxDustPolicy](https://github.com/amjuarez/bytecoin/blob/master/src/wallet/WalletSendTransactionContext.h) at dustThreshold, addToFee, addrForDust, change to store dust 
            for incorporation into a future microdonation, and establish fee policy for microdonation.
            Under [WalletUnconfirmedTransactions](https://github.com/amjuarez/bytecoin/blob/master/src/wallet/WalletUnconfirmedTransactions.cpp), establish and include pending microdonations in UnconfirmedTransactions,
            and incorporate threshold count of W (see 2.a.3 above) as point where transfer of microdonations 
            is initiated.
            Under [WalletTransferDetails](https://github.com/amjuarez/bytecoin/blob/master/src/wallet/WalletTransferDetails.cpp), establish exception for unusedDust.push_back
            Under [WalletUserTransactionsCache](https://github.com/amjuarez/bytecoin/blob/master/src/wallet/WalletUserTransactionsCache.cpp), establish method for storing of user preferences for W (see 2.a.3 above),
            as well as user preferences for which addresses shall receive recurring microdonation at amount 
            equal to user preference when W is met or exceeded.
            Test in simplewallet CLI (intention is for eventual inclusion in an intuitive 'click-and-go' GUI
            that saves user preferences within a simple but visually interesting BCN wallet).
        
    b.  Bitcoin / BTC
    
        1.  Multisignature feature, to enable multiple parties to specify when a certain microdonation may occur,
            or to develop preferences for what sort of types or categories of microdonations should be supported
            through recurrence or a similar scheme as may be utilized in a multiparty context.  This should be
            provided with [ease of use](https://github.com/spesmilo/sx#multisignature-n-m-transactions) in the context of Multisignature M-of-N.
            
        2.  Provision within wallet(s) which exemplifies the ABIS framework of giving and microdonations visually,
            with ability to provide account lines that are quickly generated by the user, such as that which is
            indicated within the [sx tools](https://github.com/spesmilo/sx/tree/master/tools) repository.  This may also incorporate the threshold count concept, 
            such that a threshold, contingent upon a flexible fee structure, allows transactions to be broadcast
            and confirmed at opportune times.  This may also incorporate elements that provide for specialized
            payment channels, including [aspects which allow for rapid and constant emissions of data](https://github.com/jgarzik/mcp).
            
        3.  Code Snippets, Suggestions for Implementation (Published on Sept. 1, 2014):
            Note that these are initial suggestions intended to stimulate development discussion, 
            and require vetting, refinement, and adjustment. These can thus be changed, used as the 
            basis for a new issue or pull request, or simply used for general implementation discussion.
            [Building and Caching Dependencies](https://github.com/bitcoin/bitcoin/tree/master/depends)
            [Core Integration and Staging](https://github.com/bitcoin/bitcoin)
            [Install SX](https://github.com/spesmilo/sx/tree/master/tools), establish [custom address](https://github.com/spesmilo/sx/tree/master/tools#charity-donations)
            for microdonation.
            [Write shell scripts and test](https://github.com/spesmilo/sx/tree/master/tools#contribute) to establish ability to conduct
            recurring transactions and user preferences for thresholds where microdonations will be broadcast.
        
    c.  Flowers in a Wasteland
    
        1.  Emergent Autonomous Organisms, or EAOs
        
        2.  Potential for Interaction with 'Digital DNA' of EAOs, such as that which is conceptually
            described at the [ImmortalCode](https://github.com/abisprotocol/immortalcode) repository.
            
        3.  Degrees of digital denaturation that occurs naturally, where organisms that were initially 
            coded have recursively speciated during such time when their manifestations are both visible to
            the human eye and can be felt by human hands as distinct autonomous organisms.  
            At the first degree, the natural denaturation is not anticipated to be detectable.  
            At the second degree, the natural denaturation is detectable, but there may be no discernible 
            aggregation effect, and the EAOs do not have natural motive or opportunity to interact with other beings.
            At the third degree, present-day humans are capable of interaction with the Digital DNA of EAOs, and 
            should be able to communicate in other ways with the EAOs.
            This does not assume that humans are ultimately the fundamental basis for high-level 
            autonomic processes, but does provide for interaction between various types of organisms.
            
        4.  Code Snippets, Suggestions for Interactions (Published Sept. 1, 2014):
            Note that these are initial suggestions intended to stimulate development discussion, 
            and require vetting, refinement, and adjustment. These can thus be changed, used as the 
            basis for a new issue or pull request, or simply used for general implementation discussion.
            [Build Ethereal (GUI) and Node (CLI)](https://github.com/ethereum/go-ethereum#build),
            [Check releases](https://github.com/ethereum/go-ethereum/releases)
            [Download and Compile pyethereum and serpent](https://blog.ethereum.org/2014/04/10/pyethereum-and-serpent-programming-guide/) or [tryethereum](https://github.com/ethereum/tryethereum)
            [buildout and bootstrap](https://github.com/ethereum/pyethereum#buildout-optional)
            Design and establish EAO [within the context of a DAC](https://blog.ethereum.org/2014/05/06/daos-dacs-das-and-more-an-incomplete-terminology-guide/)
            Determine hardware specifications (if contained within a mobile unit), develop and test a GUI 
            for the EAO, establish protocols and business rules engine to establish boundaries of speciation.
            
            

3.  Use Cases

    a.  Community Assistance
    
        1.  A small community has potholes in the road, which is becoming a higher priority for many to fix.
        
        2.  Certain community members include individual residents, frequent passersby, nonprofits,
            and members of a local governing structure.
            
        3.  Some preconditions include an absence of funding availability from a local governing structure, and
            an increasing degree of urgency and willpower on the part of the various 'certain community members'
            as described above.  Some of the community members are users of decentralized systems incorporating ABIS.
            
        4.  The community members meet and discuss possible designation of a system address or account line to where
            funds raised would be sent.  Individuals determine the threshold value W to determine when they 
            (individually) will be committing microdonations to this collective endeavor.  The code associated with
            the ABIS concept begins to route microdonations to the address or account line that has been established
            by community members, with a multisignature mechanism that allows the local governing structure to 
            spend once the amount has reached a certain value.  The process is done in tandem with members of the
            local governing structure, but the business of funding the fixing of potholes has been done without 
            any requirement that individuals commit any of their resources (entirely voluntary process).
            
        5.  An alternative flow:  A constantly changing matrix of community priorities, which include the 
            road and its potholes, are funded at varying levels by interested individuals, depending on whatever
            the top ten community priorities are.  The resultant addresses and community support matrix may have
            some or no connection to a local governing structure.
            
        6.  An exception flow:  An incredible amount of apathy ensues about the road and potholes, when a local
            school appeals to many communities for aid so that it can continue functioning.  To add complexity to
            the issue, two major local employers are about to close their doors.
            
        7.  Post Conditions – In the simplified overview of post conditions, a certain amount of funds are raised and
            most potholes are fixed, and in an alternate overview of post conditions, very few potholes are fixed 
            as a result, but awareness about the pothole issue and the importance of community collaboration
            has been revitalized.  In a more complex possibility for post conditions, a localized EAO may 
            either be partially designed to (or through a form of intention or expression of the EAO, may 'opt' to) 
            address the pothole issue directly by autonomously collecting and organizing small amounts of value 
            that can be directed to the potholes in the form of time commitments, energy, currency accumulation, 
            and other resources that the EAO may direct to the pothole issue.
            
    b.  Hardware and Software Developments - distinct examples
    
        1.  An individual determines that there is a need to implement a [simple and cheap communications server](https://github.com/bashrc/freedombone), to help manage the 
            microdonations process and process some of the data that a community may need in order for the 
            ABIS processes to function in environments where hardware is limited.
            
        2.  Various methods of using lightweight systems to host a node or server may be presented, such as:
        
            a. Code which is short and to the point, and [fits in an e-mail signature](https://github.com/cathalgarvey/tinystatus)
            
            b. Code which may be intended [primarily for mobile devices](https://github.com/37coins/Btc2Sms) in areas where internet may not be available
            
            c. Code which provides more than microdonations within a transactional framework, such as, but
               not limited to, [decentralized markets](https://github.com/OpenBazaar/OpenBazaar) that provide an opportunity to integrate decentralized giving preferences.
               
    c.  Additional use cases, examples of giving processes, and more, will be added here at a later date.


