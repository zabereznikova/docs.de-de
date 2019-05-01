---
title: Peer-to-Peer-Netzwerke
ms.date: 03/30/2017
ms.assetid: ad6cb67b-fd1c-4ca1-a767-b410da2e16ca
ms.openlocfilehash: 388f6659602276cd3f356da2af63e4d31b5e22d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046413"
---
# <a name="peer-to-peer-networking"></a><span data-ttu-id="03f01-102">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="03f01-102">Peer-to-Peer Networking</span></span>
<span data-ttu-id="03f01-103">Peerkanal ist eine mehrparteien-, Peer-zu-Peer (P2P) kommunikationstechnologie in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="03f01-103">Peer Channel is a multiparty, peer-to-peer (P2P) communication technology in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="03f01-104">Er stellt einen sicheren und skalierbaren nachrichtenbasierten P2P-Kommunikationschannel für Anwendungsentwickler bereit.</span><span class="sxs-lookup"><span data-stu-id="03f01-104">It provides a secure and scalable message-based P2P communication channel for application developers.</span></span> <span data-ttu-id="03f01-105">Ein allgemeines Beispiel einer Mehrparteienanwendung, die vom Peerkanal profitieren kann, sind gemeinschaftliche Anwendungen, wie beispielsweise Chat, in denen eine Gruppe von Benutzern direkt miteinander kommunizieren kann, ohne dass Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="03f01-105">One common example of a multiparty application that can benefit from Peer Channel is a collaborative application, such as chat, where a group of people chat with one another in a peer-to-peer manner without servers.</span></span> <span data-ttu-id="03f01-106">Peerkanal ermöglicht P2P-Zusammenarbeit, Inhaltsverteilung, Lastenausgleich und verteilte Verarbeitung sowohl bei Consumer- als auch Unternehmensszenarios.</span><span class="sxs-lookup"><span data-stu-id="03f01-106">Peer Channel enables P2P collaboration, content distribution, load balancing, and distributed processing for both consumer and enterprise scenarios.</span></span>  
  
 <span data-ttu-id="03f01-107">Peerkanal ist standardmäßig aktiviert, auf [!INCLUDE[wv](../../../../includes/wv-md.md)], da WCF.</span><span class="sxs-lookup"><span data-stu-id="03f01-107">Peer Channel is enabled by default on [!INCLUDE[wv](../../../../includes/wv-md.md)], as is all of WCF.</span></span> <span data-ttu-id="03f01-108">Fügen Sie Ihrem Projekt Verweise auf "System.ServiceModel.dll" hinzu, um auf Peerkanalklassen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="03f01-108">To access Peer Channel classes, add references to System.ServiceModel.dll to your project.</span></span>  
  
 <span data-ttu-id="03f01-109">Die folgenden Abschnitte enthalten Informationen zu Peer-to-Peer-Netzwerken und zur Verwendung von Peerkanalklassen zum Erstellen von Peer-to-Peer-fähigen Netzwerkanwendungen.</span><span class="sxs-lookup"><span data-stu-id="03f01-109">The following sections contain information about peer-to-peer networking and the use of Peer Channel classes to create peer-enabled network applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03f01-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="03f01-110">In This Section</span></span>  
 <span data-ttu-id="03f01-111">[Peerkanalszenarien](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md):  Beschreibt Entwicklungsszenarios, die von den Peerkanal-APIs, unterstützt werden, beispielsweise Veröffentlichungs-/Abonnement-messaging, Zusammenarbeit, verteilte Verarbeitung und Spiele.</span><span class="sxs-lookup"><span data-stu-id="03f01-111">[Peer Channel Scenarios](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md):  Describes development scenarios supported by the Peer Channel APIs, such as publication/subscription messaging, collaboration, distributed processing, and gaming.</span></span>  
  
 <span data-ttu-id="03f01-112">[Peerkanal-Begriffe](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md):  Beschreibt Peernetze, Peerknoten, peerkanalsicherheit und PeerResolver.</span><span class="sxs-lookup"><span data-stu-id="03f01-112">[Peer Channel Concepts](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md):  Describes Peer Meshes, Peer Nodes, Peer Channel security, and Peer Resolvers.</span></span>  
  
 <span data-ttu-id="03f01-113">[Erstellen einer Peerkanalanwendung](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md):  Enthält Anleitungen zum Entwickeln von peerkanalanwendungen.</span><span class="sxs-lookup"><span data-stu-id="03f01-113">[Building a Peer Channel Application](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md):  Provides guidance on developing Peer Channel applications.</span></span>  
  
## <a name="peer-channel-code-examples"></a><span data-ttu-id="03f01-114">Peerkanal-Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="03f01-114">Peer Channel Code Examples</span></span>  
 <span data-ttu-id="03f01-115">[Benutzerdefinierter Peerkanal-PeerResolver](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="03f01-115">[Peer Channel Custom Peer Resolver](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90))</span></span>  
  
## <a name="peer-channel-team-blog"></a><span data-ttu-id="03f01-116">Blog des Peerkanalteams</span><span class="sxs-lookup"><span data-stu-id="03f01-116">Peer Channel Team blog</span></span>  
 [<span data-ttu-id="03f01-117">Peerkanal-Team-Blog</span><span class="sxs-lookup"><span data-stu-id="03f01-117">Peer Channel Team Blog</span></span>](https://go.microsoft.com/fwlink/?LinkID=114530)
