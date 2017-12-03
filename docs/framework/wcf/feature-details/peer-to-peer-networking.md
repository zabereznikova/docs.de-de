---
title: Peer-to-Peer-Netzwerke
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad6cb67b-fd1c-4ca1-a767-b410da2e16ca
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d3ef21d4ab431ea4e1e1ac0392b3f088a7053c80
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="peer-to-peer-networking"></a><span data-ttu-id="05fbb-102">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="05fbb-102">Peer-to-Peer Networking</span></span>
<span data-ttu-id="05fbb-103">Peerkanal ist eine Mehrparteien-, P2P-Kommunikationstechnologie (Peer-to-Peer) in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05fbb-103">Peer Channel is a multiparty, peer-to-peer (P2P) communication technology in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="05fbb-104">Er stellt einen sicheren und skalierbaren nachrichtenbasierten P2P-Kommunikationschannel für Anwendungsentwickler bereit.</span><span class="sxs-lookup"><span data-stu-id="05fbb-104">It provides a secure and scalable message-based P2P communication channel for application developers.</span></span> <span data-ttu-id="05fbb-105">Ein allgemeines Beispiel einer Mehrparteienanwendung, die vom Peerkanal profitieren kann, sind gemeinschaftliche Anwendungen, wie beispielsweise Chat, in denen eine Gruppe von Benutzern direkt miteinander kommunizieren kann, ohne dass Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="05fbb-105">One common example of a multiparty application that can benefit from Peer Channel is a collaborative application, such as chat, where a group of people chat with one another in a peer-to-peer manner without servers.</span></span> <span data-ttu-id="05fbb-106">Peerkanal ermöglicht P2P-Zusammenarbeit, Inhaltsverteilung, Lastenausgleich und verteilte Verarbeitung sowohl bei Consumer- als auch Unternehmensszenarios.</span><span class="sxs-lookup"><span data-stu-id="05fbb-106">Peer Channel enables P2P collaboration, content distribution, load balancing, and distributed processing for both consumer and enterprise scenarios.</span></span>  
  
 <span data-ttu-id="05fbb-107">Peerkanal ist unter [!INCLUDE[wv](../../../../includes/wv-md.md)] standardmäßig aktiviert (wie auch der Rest von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="05fbb-107">Peer Channel is enabled by default on [!INCLUDE[wv](../../../../includes/wv-md.md)], as is all of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="05fbb-108">Fügen Sie Ihrem Projekt Verweise auf "System.ServiceModel.dll" hinzu, um auf Peerkanalklassen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="05fbb-108">To access Peer Channel classes, add references to System.ServiceModel.dll to your project.</span></span>  
  
 <span data-ttu-id="05fbb-109">Die folgenden Abschnitte enthalten Informationen zu Peer-to-Peer-Netzwerken und zur Verwendung von Peerkanalklassen zum Erstellen von Peer-to-Peer-fähigen Netzwerkanwendungen.</span><span class="sxs-lookup"><span data-stu-id="05fbb-109">The following sections contain information about peer-to-peer networking and the use of Peer Channel classes to create peer-enabled network applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05fbb-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="05fbb-110">In This Section</span></span>  
 <span data-ttu-id="05fbb-111">[Peerkanalszenarien](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md): Beschreibt Entwicklungsszenarien, die von den Peerkanal-APIs, unterstützt, z. B. Veröffentlichungs-/Abonnement-messaging, Zusammenarbeit, verteilte Verarbeitung und Spiele.</span><span class="sxs-lookup"><span data-stu-id="05fbb-111">[Peer Channel Scenarios](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md):  Describes development scenarios supported by the Peer Channel APIs, such as publication/subscription messaging, collaboration, distributed processing, and gaming.</span></span>  
  
 <span data-ttu-id="05fbb-112">[Peerkanalkonzepte](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md): Beschreibt Peernetze, Peerknoten, peerkanalsicherheit und PeerResolver.</span><span class="sxs-lookup"><span data-stu-id="05fbb-112">[Peer Channel Concepts](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md):  Describes Peer Meshes, Peer Nodes, Peer Channel security, and Peer Resolvers.</span></span>  
  
 <span data-ttu-id="05fbb-113">[Erstellen einer Peerkanalanwendung](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md): enthält Hinweise zum Entwickeln von peerkanalanwendungen.</span><span class="sxs-lookup"><span data-stu-id="05fbb-113">[Building a Peer Channel Application](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md):  Provides guidance on developing Peer Channel applications.</span></span>  
  
## <a name="peer-channel-code-examples"></a><span data-ttu-id="05fbb-114">Peerkanal-Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="05fbb-114">Peer Channel Code Examples</span></span>  
 [<span data-ttu-id="05fbb-115">Benutzerdefinierter Peerkanal-PeerResolver</span><span class="sxs-lookup"><span data-stu-id="05fbb-115">Peer Channel Custom Peer Resolver</span></span>](http://msdn.microsoft.com/en-us/5b75a2bb-7ff1-4a14-abe7-3debf0537d23)  
  
## <a name="peer-channel-team-blog"></a><span data-ttu-id="05fbb-116">Blog des Peerkanalteams</span><span class="sxs-lookup"><span data-stu-id="05fbb-116">Peer Channel Team blog</span></span>  
 <span data-ttu-id="05fbb-117">[Peerkanalteams](http://go.microsoft.com/fwlink/?LinkID=114530) (http://go.microsoft.com/fwlink/?LinkID=114530)</span><span class="sxs-lookup"><span data-stu-id="05fbb-117">[Peer Channel Team Blog](http://go.microsoft.com/fwlink/?LinkID=114530) (http://go.microsoft.com/fwlink/?LinkID=114530)</span></span>
