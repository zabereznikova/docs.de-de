---
title: Hosten in einer verwalteten Anwendung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1e81a8eb27725edeccf3e5c7489109ba47b70dec
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="hosting-in-a-managed-application"></a><span data-ttu-id="bb347-102">Hosten in einer verwalteten Anwendung</span><span class="sxs-lookup"><span data-stu-id="bb347-102">Hosting in a Managed Application</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="bb347-103"> -Dienste können in jeder [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Anwendung gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="bb347-103"> services can be hosted in any [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application.</span></span> <span data-ttu-id="bb347-104">Die Selbsthosting-Option ist die flexibelste Option, da sie für die Bereitstellung die geringsten Anforderungen an die Infrastruktur stellt.</span><span class="sxs-lookup"><span data-stu-id="bb347-104">Self-hosting services is the most flexible hosting option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="bb347-105">Sie ist jedoch auch die am wenigsten robuste Hostingoption, weil verwaltete Anwendungen nicht die erweiterten Hosting- und Verwaltungsfunktionen bereitstellen wie die anderen Hostingoptionen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], z.&amp;#160;B. Internetinformationsdienste (IIS) und Windows-Dienste.</span><span class="sxs-lookup"><span data-stu-id="bb347-105">However, it is also the least robust hosting option, because managed applications do not provide the advanced hosting and management features of other hosting options in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], such as Internet Information Services (IIS) and Windows services.</span></span>  
  
 <span data-ttu-id="bb347-106">Zur Erstellung eines selbst gehosteten Diensts erstellen und öffnen Sie eine Instanz von <xref:System.ServiceModel.ServiceHost>, der die Dienstüberwachung für Nachrichten startet.</span><span class="sxs-lookup"><span data-stu-id="bb347-106">To create a self-hosted service, create and open an instance of the <xref:System.ServiceModel.ServiceHost>, which starts a service listening for messages.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="bb347-107"> [Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="bb347-107"> [How to: Host a WCF Service in a Managed Application](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).</span></span>  
  
 <span data-ttu-id="bb347-108">Ein vollständiges Beispiel zum Definieren eines Dienstvertrags, den Vertrag zu implementieren und Hosten eines Diensts innerhalb einer verwalteten Anwendung finden Sie unter der [Lernprogramm für erste Schritte](../../../../docs/framework/wcf/getting-started-tutorial.md) und [Selbsthosting](../../../../docs/framework/wcf/samples/self-host.md).</span><span class="sxs-lookup"><span data-stu-id="bb347-108">For a complete example on how to define a contract, implement the contract, and host a service inside of a managed application see the [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md) and the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md).</span></span>  
  
 <span data-ttu-id="bb347-109">In den folgenden Abschnitten werden allgemeine Szenarien beschrieben, die diese Hostingoption verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb347-109">The following sections describe common scenarios that use this hosting option.</span></span>  
  
## <a name="console-applications"></a><span data-ttu-id="bb347-110">Konsolenanwendungen</span><span class="sxs-lookup"><span data-stu-id="bb347-110">Console Applications</span></span>  
 <span data-ttu-id="bb347-111">Allgemeine, für das Selbsthosting geeignete Szenarien sind [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienste, die in Konsolenanwendungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bb347-111">Common scenarios that self-hosting enables are [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services running inside console applications.</span></span> <span data-ttu-id="bb347-112">Das Hosten eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Diensts in einer Konsolenanwendung ist in der Regel während der Entwicklungsphase der Anwendung nützlich.</span><span class="sxs-lookup"><span data-stu-id="bb347-112">Hosting a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service inside a console application is typically useful during the development phase of the service.</span></span> <span data-ttu-id="bb347-113">Die Anwendung lässt sich dann einfach debuggen. Ablaufverfolgungsinformationen über die Anwendung lassen sich leichter ermitteln, um herauszufinden, was intern in der Anwendung vor sich geht. Zudem lässt sich die Anwendung dann einfacher an andere Speicherorte kopieren.</span><span class="sxs-lookup"><span data-stu-id="bb347-113">This makes them easy to debug, easy to get trace information from to find out what is happening inside of the application, and easy to move around by copying them to new locations.</span></span>  
  
## <a name="rich-client-applications"></a><span data-ttu-id="bb347-114">Rich Client-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="bb347-114">Rich Client Applications</span></span>  
 <span data-ttu-id="bb347-115">Weitere häufige Szenarien sind Selbsthosting rich Client-Anwendungen wie jene auf Grundlage von Windows Presentation Foundation (WPF) oder Windows Forms (WinForms).</span><span class="sxs-lookup"><span data-stu-id="bb347-115">Other common scenarios that self-hosting enables are rich client applications, such as those based on Windows Presentation Foundation (WPF) or Windows Forms (WinForms).</span></span> <span data-ttu-id="bb347-116">Diese Hostingoption erleichtert es Rich&amp;#160;Client-Anwendungen, wie [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] - und WinForms-Anwendungen, mit der Außenwelt zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="bb347-116">This hosting option also makes it easy for rich client applications, such as [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] and WinForms applications, to communicate with the outside world.</span></span> <span data-ttu-id="bb347-117">Ein Beispiel dafür ist ein Peer-to-Peer-Kollaborationsclient, der [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] als Benutzeroberfläche nutzt und darüber hinaus als Host für einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienst fungiert, der es anderen Clients ermöglicht, eine Verbindung mit ihm herzustellen und Daten auszutauschen.</span><span class="sxs-lookup"><span data-stu-id="bb347-117">For example, a peer-to-peer collaboration client that uses [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] for its user interface and also hosts a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that allows other clients to connect to it and share information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb347-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb347-118">See Also</span></span>  
 [<span data-ttu-id="bb347-119">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="bb347-119">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="bb347-120">Tutorial mit ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="bb347-120">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)
