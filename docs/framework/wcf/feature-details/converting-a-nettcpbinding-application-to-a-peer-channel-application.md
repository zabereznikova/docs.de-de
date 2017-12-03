---
title: Konvertieren einer NetTcpBinding-Anwendung in eine Peerkanalanwendung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d52b005013e9728cfcdb43ad289984018b90d27c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="1c2a4-102">Konvertieren einer NetTcpBinding-Anwendung in eine Peerkanalanwendung</span><span class="sxs-lookup"><span data-stu-id="1c2a4-102">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>
<span data-ttu-id="1c2a4-103">Sie können Verbindungen zwischen Clients mit [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] herstellen, indem Sie Bindungen verwenden, die die Verbindungsparameter beschreiben.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-103">You can create connections between clients using the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="1c2a4-104">Für das Konvertieren einer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Anwendung zum Verwenden von Peer-to-Peer-Verbindungen ist eine Bindung erforderlich, die diese Technologie beim Herstellen von Clientverbindungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-104">Converting a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="1c2a4-105">Peerkanal stellt eine Bindung mit der Bezeichnung <xref:System.ServiceModel.NetPeerTcpBinding> bereit, die auf ähnliche Weise verwendet wird wie die <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-105">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="1c2a4-106">Die wichtigsten Unterschiede bestehen im Angeben eines Auflösungsdienstes und dem Festlegen von Sicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-106">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="1c2a4-107">Wenn eine Anwendung den Standardresolver und Standardsicherheitseinstellungen verwendet, schließt das Konvertieren einer normalen client-/serverbasierten Anwendung für die Verwendung von Peerkanal das Ändern des Bindungsnamens von „NetTcpBinding“ in „NetPeerTcpBinding“ in der Konfigurationsdatei der Anwendung ein; die Codebasis der Anwendung muss nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-107">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c2a4-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c2a4-108">See Also</span></span>  
 [<span data-ttu-id="1c2a4-109">Erstellen einer Peerkanalanwendung</span><span class="sxs-lookup"><span data-stu-id="1c2a4-109">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)  
 [<span data-ttu-id="1c2a4-110">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="1c2a4-110">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
