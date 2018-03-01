---
title: WCF Syndication
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- syndication [WCF]
ms.assetid: ebf80384-0fc9-4919-a1e8-23ca2a13e300
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1f7f5fd65fc298107a66e2049c059f3cc58b3d44
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-syndication"></a><span data-ttu-id="1684a-102">WCF Syndication</span><span class="sxs-lookup"><span data-stu-id="1684a-102">WCF Syndication</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="1684a-103"> unterstützt das problemlose Arbeiten mit Syndication-Feeds in Atom, RSS oder in anderen benutzerdefinierten Formaten. Dies ermöglicht das Lesen und Erstellen dieser Feeds sowie das Verfügbarmachen für einen Dienstendpunkt.</span><span class="sxs-lookup"><span data-stu-id="1684a-103"> provides support to easily work with syndication feeds in Atom, RSS or other custom formats, which allows you to read and create them as well as expose them on a service endpoint.</span></span> <span data-ttu-id="1684a-104">In den Themen dieses Abschnitts wird dieses Programmiermodell für Syndication genau beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1684a-104">The topics in this section describe this programming model for syndication in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1684a-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1684a-105">In This Section</span></span>  
 [<span data-ttu-id="1684a-106">Übersicht über WCF Syndication</span><span class="sxs-lookup"><span data-stu-id="1684a-106">WCF Syndication Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 <span data-ttu-id="1684a-107">Bietet eine Übersicht über Syndication-Unterstützung, die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="1684a-107">Provides an overview of syndication support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="1684a-108">Architektur von Syndication</span><span class="sxs-lookup"><span data-stu-id="1684a-108">Architecture of Syndication</span></span>](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)  
 <span data-ttu-id="1684a-109">Beschreibt die Klassen im Objektmodell und die Erweiterbarkeit von Syndication.</span><span class="sxs-lookup"><span data-stu-id="1684a-109">Describes the classes in the object model and the extensibility of syndication.</span></span>  
  
 [<span data-ttu-id="1684a-110">Zuordnung des WCF-Syndication-Objektmodells zu Atom und RSS</span><span class="sxs-lookup"><span data-stu-id="1684a-110">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 <span data-ttu-id="1684a-111">Beschreibt die Darstellung von Feeds im WCF Syndication-Objektmodell und deren Konvertierung zu RSS- und Atom-Feeds.</span><span class="sxs-lookup"><span data-stu-id="1684a-111">Describes how feeds are represented within the WCF Syndication Object Model and how they are converted to RSS and Atom feeds.</span></span>  
  
 [<span data-ttu-id="1684a-112">Vorgehensweise: Erstellen eines grundlegenden RS-Feeds</span><span class="sxs-lookup"><span data-stu-id="1684a-112">How to: Create a Basic RSS Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-rss-feed.md)  
 <span data-ttu-id="1684a-113">Erläutert die Erstellung eines Diensts, der einen grundlegenden RSS-Feed verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="1684a-113">Shows how to create a service that makes a basic RSS feed available.</span></span>  
  
 [<span data-ttu-id="1684a-114">Vorgehensweise: Erstellen eines grundlegenden Atom-Feeds</span><span class="sxs-lookup"><span data-stu-id="1684a-114">How to: Create a Basic Atom Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-atom-feed.md)  
 <span data-ttu-id="1684a-115">Erläutert die Erstellung eines Diensts, der einen grundlegenden ATOM-Feed verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="1684a-115">Shows how to create a service that makes a basic ATOM feed available.</span></span>  
  
 [<span data-ttu-id="1684a-116">Vorgehensweise: Bereitstellen eines Feeds als Atom und RSS</span><span class="sxs-lookup"><span data-stu-id="1684a-116">How to: Expose a Feed as Both Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-feed-as-both-atom-and-rss.md)  
 <span data-ttu-id="1684a-117">Erläutert die Erstellung eines Diensts, der denselben Feed mit ATOM und RSS verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="1684a-117">Shows how to create a service that makes the same feed available with ATOM and RSS.</span></span>  
  
 [<span data-ttu-id="1684a-118">Syndication-Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="1684a-118">Syndication Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md)  
 <span data-ttu-id="1684a-119">Beschreibt die Methoden zum Hinzufügen benutzerdefinierter Elemente und Attribute zu einem Syndication-Feed.</span><span class="sxs-lookup"><span data-stu-id="1684a-119">Describes the methods of adding custom elements and attributes to a syndication feed.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1684a-120">Verweis</span><span class="sxs-lookup"><span data-stu-id="1684a-120">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1684a-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1684a-121">Related Sections</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1684a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1684a-122">See Also</span></span>  
 [<span data-ttu-id="1684a-123">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="1684a-123">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="1684a-124">Teilweise Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="1684a-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)
