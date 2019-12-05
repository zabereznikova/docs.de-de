---
title: Peer-to-Peer-Netzwerke
ms.date: 03/30/2017
ms.assetid: ad6cb67b-fd1c-4ca1-a767-b410da2e16ca
ms.openlocfilehash: 74566d7bc7c8d817cedb0ff6f64590ba827ed4c4
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837362"
---
# <a name="peer-to-peer-networking"></a><span data-ttu-id="3c4ff-102">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="3c4ff-102">Peer-to-Peer Networking</span></span>
<span data-ttu-id="3c4ff-103">Peerkanal ist eine mehr Parteien-, P2P-Kommunikationstechnologie (Peer-to-Peer) in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3c4ff-103">Peer Channel is a multiparty, peer-to-peer (P2P) communication technology in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="3c4ff-104">Er stellt einen sicheren und skalierbaren nachrichtenbasierten P2P-Kommunikationschannel für Anwendungsentwickler bereit.</span><span class="sxs-lookup"><span data-stu-id="3c4ff-104">It provides a secure and scalable message-based P2P communication channel for application developers.</span></span> <span data-ttu-id="3c4ff-105">Ein allgemeines Beispiel einer Mehrparteienanwendung, die vom Peerkanal profitieren kann, sind gemeinschaftliche Anwendungen, wie beispielsweise Chat, in denen eine Gruppe von Benutzern direkt miteinander kommunizieren kann, ohne dass Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3c4ff-105">One common example of a multiparty application that can benefit from Peer Channel is a collaborative application, such as chat, where a group of people chat with one another in a peer-to-peer manner without servers.</span></span> <span data-ttu-id="3c4ff-106">Peerkanal ermöglicht P2P-Zusammenarbeit, Inhaltsverteilung, Lastenausgleich und verteilte Verarbeitung sowohl bei Consumer- als auch Unternehmensszenarios.</span><span class="sxs-lookup"><span data-stu-id="3c4ff-106">Peer Channel enables P2P collaboration, content distribution, load balancing, and distributed processing for both consumer and enterprise scenarios.</span></span>  
  
 <span data-ttu-id="3c4ff-107">Peerkanal ist unter Windows Vista standardmäßig aktiviert, ebenso wie alle WCF-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="3c4ff-107">Peer Channel is enabled by default on Windows Vista, as is all of WCF.</span></span> <span data-ttu-id="3c4ff-108">Fügen Sie Ihrem Projekt Verweise auf "System.ServiceModel.dll" hinzu, um auf Peerkanalklassen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="3c4ff-108">To access Peer Channel classes, add references to System.ServiceModel.dll to your project.</span></span>  
  
 <span data-ttu-id="3c4ff-109">Die folgenden Abschnitte enthalten Informationen zu Peer-to-Peer-Netzwerken und zur Verwendung von Peerkanalklassen zum Erstellen von Peer-to-Peer-fähigen Netzwerkanwendungen.</span><span class="sxs-lookup"><span data-stu-id="3c4ff-109">The following sections contain information about peer-to-peer networking and the use of Peer Channel classes to create peer-enabled network applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c4ff-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3c4ff-110">In This Section</span></span>  
 <span data-ttu-id="3c4ff-111">[Peer Kanal Szenarios](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md): Beschreibt Entwicklungsszenarien, die von den Peerkanal-APIs unterstützt werden, z. b. Veröffentlichung/Abonnement-Messaging, Zusammenarbeit, verteilte Verarbeitung und Spiele.</span><span class="sxs-lookup"><span data-stu-id="3c4ff-111">[Peer Channel Scenarios](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md):  Describes development scenarios supported by the Peer Channel APIs, such as publication/subscription messaging, collaboration, distributed processing, and gaming.</span></span>  
  
 <span data-ttu-id="3c4ff-112">[Peerkanal-Konzepte](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md): Beschreibt Peer-Meshes, Peer Knoten, Peer Kanal Sicherheit und Peerresolver.</span><span class="sxs-lookup"><span data-stu-id="3c4ff-112">[Peer Channel Concepts](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md):  Describes Peer Meshes, Peer Nodes, Peer Channel security, and Peer Resolvers.</span></span>  
  
 <span data-ttu-id="3c4ff-113">[Erstellung einer Peer Kanal Anwendung](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md): enthält Anleitungen zum Entwickeln von Peer Kanal Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="3c4ff-113">[Building a Peer Channel Application](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md):  Provides guidance on developing Peer Channel applications.</span></span>  
  
## <a name="peer-channel-code-examples"></a><span data-ttu-id="3c4ff-114">Peerkanal-Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="3c4ff-114">Peer Channel Code Examples</span></span>  
 <span data-ttu-id="3c4ff-115">[Benutzerdefinierter Peerkanal-Peerresolver](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3c4ff-115">[Peer Channel Custom Peer Resolver](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90))</span></span>  
  
## <a name="peer-channel-team-blog"></a><span data-ttu-id="3c4ff-116">Blog des Peerkanalteams</span><span class="sxs-lookup"><span data-stu-id="3c4ff-116">Peer Channel Team blog</span></span>  
 [<span data-ttu-id="3c4ff-117">Peer Channel-Teamblog</span><span class="sxs-lookup"><span data-stu-id="3c4ff-117">Peer Channel Team Blog</span></span>](https://go.microsoft.com/fwlink/?LinkID=114530)
