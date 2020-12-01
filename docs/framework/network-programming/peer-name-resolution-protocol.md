---
title: Peer Name Resolution-Protokoll (PNRP)
description: Erfahren Sie mehr über das Peer Name Resolution-Protokoll (PNRP), ein sicheres, skalierbares und dynamisches Protokoll für die Namensregistrierung und -auflösung.
ms.date: 03/30/2017
ms.assetid: 11940511-c124-4d91-ae31-d4ed6e81ee58
ms.openlocfilehash: d50514569d066d04391ce65522df789ed421dbed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239392"
---
# <a name="peer-name-resolution-protocol"></a><span data-ttu-id="ffa33-103">Peer Name Resolution-Protokoll (PNRP)</span><span class="sxs-lookup"><span data-stu-id="ffa33-103">Peer Name Resolution Protocol</span></span>

<span data-ttu-id="ffa33-104">In Peer-zu-Peer-Umgebungen verwenden Peers bestimmte Namensauflösungssysteme, um Namen oder andere Arten von Bezeichner in die Netzwerkadressen des jeweils anderen Peers (Adressen, Protokolle und Ports) aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="ffa33-104">In peer-to-peer environments, peers use specific name resolution systems to resolve each other's network locations (addresses, protocols, and ports) from names or other types of identifiers.</span></span> <span data-ttu-id="ffa33-105">In der Vergangenheit ist die Peernamensauflösung durch die grundsätzlich flüchtige Konnektivität sowie andere Mängel im Domänennamenserver (DNS) erschwert worden.</span><span class="sxs-lookup"><span data-stu-id="ffa33-105">In the past, peer name resolution has been complicated by the inherently transient connectivity as well as other shortcomings within the Domain Name System (DNS).</span></span>  
  
 <span data-ttu-id="ffa33-106">Die Microsoft® Windows® Peer-zu-Peer Netwerkplattform löst dieses Problem mit dem Peer Name Resolution-Protokoll (PNRP), ein sicheres, skalierbares und dynamisches Namensregistrierungs- und Namensauflösungsprotokoll, das erstmals für Windows XP entwickelt und dann in Windows Vista™ aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ffa33-106">The Microsoft® Windows® Peer-to-Peer Networking platform solves this problem with the Peer Name Resolution Protocol (PNRP), a secure, scalable, and dynamic name registration and name resolution protocol first developed for Windows XP and then upgraded in Windows Vista™.</span></span> <span data-ttu-id="ffa33-107">Die Funktionsweise des PNRP unterscheidet sich sehr von traditionellen Auflösungssystemen und eröffnet interessante neue Möglichkeiten für Anwendungsentwickler.</span><span class="sxs-lookup"><span data-stu-id="ffa33-107">PNRP works very differently from traditional name resolution systems, opening up exciting new possibilities for application developers.</span></span>  
  
 <span data-ttu-id="ffa33-108">Mit PNRP können Peernamen auf den Computer oder auf einzelne Anwendungen oder Dienste auf dem Computer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ffa33-108">With PNRP, peer names can be applied to the machine, or individual applications or services on the machine.</span></span> <span data-ttu-id="ffa33-109">Eine Peernamensauflösung enthält eine Adresse, einen Port und möglicherweise eine erweiterte Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="ffa33-109">A peer name resolution includes an address, port, and possibly an extended payload.</span></span> <span data-ttu-id="ffa33-110">Die Vorteile dieses Systems sind Fehlertoleranz, keine Engpässe, und Namensauflösungen, die niemals veraltete Adressen zurückgeben; das Protokoll ist somit eine ausgezeichnete Lösung für die Lokalisierung mobiler Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ffa33-110">Benefits of this system include fault tolerance, no bottlenecks, and name resolutions that will never return stale addresses; making the protocol an excellent solution for locating mobile users.</span></span>  
  
 <span data-ttu-id="ffa33-111">Im Hinblick auf die Sicherheit können Peernamen als gesichert (geschützt) oder unsicher (ungeschützt) veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="ffa33-111">In terms of security, peer names can be published as secured (protected) or unsecured (unprotected).</span></span> <span data-ttu-id="ffa33-112">PNRP verwendet die Kryptografie mit öffentlichem Schlüssel, um Peernamen gegen Spoofing zu schützen. Computer sowie Dienste können mit PNRP benannt werden.</span><span class="sxs-lookup"><span data-stu-id="ffa33-112">PNRP uses public key cryptography to protect secure peer names against spoofing; both computers and services can be named with PNRP.</span></span>  
  
<span data-ttu-id="ffa33-113">Das Peer Name Resolution-Protokoll hat die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ffa33-113">The Peer Name Resolution Protocol demonstrates the following properties:</span></span>  
  
- <span data-ttu-id="ffa33-114">Verteilt und nahezu serverlos.</span><span class="sxs-lookup"><span data-stu-id="ffa33-114">Distributed and almost entirely serverless.</span></span> <span data-ttu-id="ffa33-115">Server werden nur in der Bootstrapping-Phase benötigt.</span><span class="sxs-lookup"><span data-stu-id="ffa33-115">Servers are only required for the bootstrapping process.</span></span>  
  
- <span data-ttu-id="ffa33-116">Speichern Sie die Namensveröffentlichung ohne die Beteiligung Dritter.</span><span class="sxs-lookup"><span data-stu-id="ffa33-116">Secure name publication without the involvement of third parties.</span></span> <span data-ttu-id="ffa33-117">Im Gegensatz zur DNS-Namensveröffentlichung ist die PNRP-Namensveröffentlichung ohne Verzögerung und kostenlos.</span><span class="sxs-lookup"><span data-stu-id="ffa33-117">Unlike DNS name publication, PNRP name publication is instantaneous and without financial cost.</span></span>  
  
- <span data-ttu-id="ffa33-118">PNRP wird in Echtzeit aktualisiert. Somit wird die Auflösung veralteter Adressen verhindert.</span><span class="sxs-lookup"><span data-stu-id="ffa33-118">PNRP updates in real-time, which prevents the resolution of stale addresses.</span></span>  
  
- <span data-ttu-id="ffa33-119">Die Auflösung von Namen per PNRP erstreckt sich über Computer hinaus, indem die Namensauflösung für Dienste zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="ffa33-119">The resolution of names via PNRP extends beyond computers by also allowing name resolution for services.</span></span>  
  
## <a name="the-systemnetpeertopeer-namespace"></a><span data-ttu-id="ffa33-120">Der System.Net.PeerToPeer-Namespace</span><span class="sxs-lookup"><span data-stu-id="ffa33-120">The System.Net.PeerToPeer namespace</span></span>  
  
- <span data-ttu-id="ffa33-121">Die PNRP-Funktionalität wird durch den <xref:System.Net.PeerToPeer>-Namespace in .NET Framework, Version 3.5 definiert.</span><span class="sxs-lookup"><span data-stu-id="ffa33-121">PNRP functionality is defined by the <xref:System.Net.PeerToPeer> namespace within the .NET Framework version 3.5.</span></span> <span data-ttu-id="ffa33-122">Sie stellt eine Reihe von Typen zur Verfügung, die zum Registrieren und Auflösen von Peernamen mit einem verfügbaren PNRP-Dienst verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ffa33-122">It provides a set of types that can be used to register and resolve peer names with an available PNRP service.</span></span>  
  
- <span data-ttu-id="ffa33-123">(PNRP und benutzerdefinierte PeerResolver können mithilfe der im <xref:System.ServiceModel.PeerResolvers>-Namespace zur Verfügung gestellten Typen instanziiert und erstellt werden.)</span><span class="sxs-lookup"><span data-stu-id="ffa33-123">(PNRP and custom peer resolvers can be created and instantiated using the types provided in the <xref:System.ServiceModel.PeerResolvers> namespace.)</span></span>  
  
- <span data-ttu-id="ffa33-124">Die grundlegenden Typen, die zum Registrieren und Auflösen von Namen mit einem verfügbaren PNRP-Dienst verwendet werden, sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ffa33-124">The basic types used to register and resolve names with an available PNRP service are as follows:</span></span>  
  
- <span data-ttu-id="ffa33-125"><xref:System.Net.PeerToPeer.Cloud>: Definiert die Informationen, die eine verfügbare PNRP-Cloud, einschließlich ihres Bereichs beschreiben.</span><span class="sxs-lookup"><span data-stu-id="ffa33-125"><xref:System.Net.PeerToPeer.Cloud>: Defines the information describing an available PNRP cloud, including its scope.</span></span>  
  
- <span data-ttu-id="ffa33-126"><xref:System.Net.PeerToPeer.PeerName>: Definiert einen Peernamen, der zum Registrieren und anschließendem Auflösen von einem Peer in einer Cloud verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ffa33-126"><xref:System.Net.PeerToPeer.PeerName>: Defines a peer name that can be used to register and subsequently resolve a peer within a cloud.</span></span>  
  
- <span data-ttu-id="ffa33-127"><xref:System.Net.PeerToPeer.PeerNameRecord>: Definiert den Datensatz in der PNRP-Cloud, die die Registrierungsinformationen für einen Peer enthält, der die Netzwerk-Endpunkte mit einschließt, an denen der Peer kontaktiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ffa33-127"><xref:System.Net.PeerToPeer.PeerNameRecord>: Defines the record in PNRP cloud that contains the registration information for a peer, which includes the network endpoints at which the peer can be contacted.</span></span>  
  
- <span data-ttu-id="ffa33-128"><xref:System.Net.PeerToPeer.PeerNameRegistration>: Definiert den Registrierungsvorgang für einen Peernamen, einschließlich der Methoden, um die Peer-Namensregistrierung zu starten oder zu beenden.</span><span class="sxs-lookup"><span data-stu-id="ffa33-128"><xref:System.Net.PeerToPeer.PeerNameRegistration>: Defines the registration process for a peer name, including methods to start and stop peer name registration.</span></span>  
  
- <span data-ttu-id="ffa33-129"><xref:System.Net.PeerToPeer.PeerNameResolver>: Definiert den Prozess zum Auflösen eines Peernamens in den/die zugehörigen Netzwerk-Endpunkt(e), einschließlich der synchronen und asynchronen Methoden für die Auflösung.</span><span class="sxs-lookup"><span data-stu-id="ffa33-129"><xref:System.Net.PeerToPeer.PeerNameResolver>: Defines the process for resolving a peer name to its network endpoint(s), including both synchronous and asynchronous methods for resolution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa33-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffa33-130">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers>
- <xref:System.Net.PeerToPeer>
- [<span data-ttu-id="ffa33-131">Beispiele zur Netzwerkprogrammierung</span><span class="sxs-lookup"><span data-stu-id="ffa33-131">Network Programming Samples</span></span>](network-programming-samples.md)

<!-- to-do: review sample links
- [PeerToPeer Technology Sample](https://go.microsoft.com/fwlink/?LinkID=179571)
-->
