---
title: "Erweiterbarkeit von Kanälen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7e0cf92edc4ec05df3e5e8c25b90bcf253e94ed6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="channels-extensibility"></a><span data-ttu-id="63c88-102">Erweiterbarkeit von Kanälen</span><span class="sxs-lookup"><span data-stu-id="63c88-102">Channels Extensibility</span></span>
<span data-ttu-id="63c88-103">Die Beispiele in diesem Abschnitt veranschaulichen benutzerdefinierte Kanäle.</span><span class="sxs-lookup"><span data-stu-id="63c88-103">This section contains samples that demonstrate custom channels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="63c88-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="63c88-104">In This Section</span></span>  
 [<span data-ttu-id="63c88-105">Lokaler Kanal</span><span class="sxs-lookup"><span data-stu-id="63c88-105">Local Channel</span></span>](../../../../docs/framework/wcf/samples/local-channel.md)  
 <span data-ttu-id="63c88-106">Veranschaulicht den lokalen Kanal, einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Transportkanal, der für die Kommunikation innerhalb derselben Anwendungsdomäne verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="63c88-106">Demonstrates the local channel, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transport channel that is used for communication within the same application domain.</span></span>  
  
 [<span data-ttu-id="63c88-107">Zuverlässige, sichere Profil</span><span class="sxs-lookup"><span data-stu-id="63c88-107">Reliable Secure Profile</span></span>](../../../../docs/framework/wcf/samples/reliable-secure-profile.md)  
 <span data-ttu-id="63c88-108">Veranschaulicht, wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und Reliable Secure Profile (RSP) verfasst werden.</span><span class="sxs-lookup"><span data-stu-id="63c88-108">Demonstrates how to compose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and Reliable Secure Profile (RSP).</span></span>  
  
 [<span data-ttu-id="63c88-109">Benutzerdefinierter Kanalverteiler</span><span class="sxs-lookup"><span data-stu-id="63c88-109">Custom Channel Dispatcher</span></span>](../../../../docs/framework/wcf/samples/custom-channel-dispatcher.md)  
 <span data-ttu-id="63c88-110">Zeigt, wie der Kanalstapel auf benutzerdefinierte Weise erstellt wird, indem <xref:System.ServiceModel.ServiceHostBase> direkt implementiert wird, und wie ein benutzerdefinierter Kanalverteiler in einer Webhostumgebung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="63c88-110">Demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span>  
  
 [<span data-ttu-id="63c88-111">Segmentierungskanal</span><span class="sxs-lookup"><span data-stu-id="63c88-111">Chunking Channel</span></span>](../../../../docs/framework/wcf/samples/chunking-channel.md)  
 <span data-ttu-id="63c88-112">Veranschaulicht, wie die Menge des Arbeitsspeichers begrenzt wird, der zur Pufferung von großen, mithilfe von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gesendeten Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="63c88-112">Demonstrates how to limit the amount of memory used to buffer large messages sent using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="63c88-113">HTTP-Bestätigungskanal</span><span class="sxs-lookup"><span data-stu-id="63c88-113">HTTP Acknowledgement Channel</span></span>](../../../../docs/framework/wcf/samples/http-acknowledgement-channel.md)  
 <span data-ttu-id="63c88-114">Veranschaulicht einen geschichteten Kanal, der das unidirektionale Nachrichtenmuster ändert.</span><span class="sxs-lookup"><span data-stu-id="63c88-114">Demonstrates a layered channel which changes the one-way messaging pattern.</span></span>  
  
 [<span data-ttu-id="63c88-115">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="63c88-115">HttpCookieSession</span></span>](../../../../docs/framework/wcf/samples/httpcookiesession.md)  
 <span data-ttu-id="63c88-116">Zeigt, wie ein benutzerdefinierter Protokollkanal zum Verwenden von HTTP-Cookies zur Sitzungsverwaltung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="63c88-116">Demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span>  
  
 [<span data-ttu-id="63c88-117">Benutzerdefinierter Nachrichteninterceptor</span><span class="sxs-lookup"><span data-stu-id="63c88-117">Custom Message Interceptor</span></span>](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)  
 <span data-ttu-id="63c88-118">Zeigt, wie ein benutzerdefiniertes Bindungselement implementiert wird, das Kanalfactorys und Kanallistener erstellt, um sämtliche ein- und ausgehenden Nachrichten an einer bestimmten Stelle im Laufzeitstapel abzufangen.</span><span class="sxs-lookup"><span data-stu-id="63c88-118">Demonstrates how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span>
