---
title: Konvertieren einer NetTcpBinding-Anwendung in eine Peerkanalanwendung
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 362945959a781fac360c42475148fee1e47a1183
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960136"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="baf98-102">Konvertieren einer NetTcpBinding-Anwendung in eine Peerkanalanwendung</span><span class="sxs-lookup"><span data-stu-id="baf98-102">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>
<span data-ttu-id="baf98-103">Sie können Verbindungen zwischen Clients mit den WinFX mit Bindungen, die beschreiben, die Parameter der Verbindung erstellen.</span><span class="sxs-lookup"><span data-stu-id="baf98-103">You can create connections between clients using the WinFX by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="baf98-104">Konvertieren von einer .NET Framework-Anwendung zur Verwendung von Peer-zu-Peer-Verbindungen erfordert eine Bindung, die diese Technologie beim Herstellen von Clientverbindungen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="baf98-104">Converting a .NET Framework application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="baf98-105">Peerkanal stellt eine Bindung mit der Bezeichnung <xref:System.ServiceModel.NetPeerTcpBinding> bereit, die auf ähnliche Weise verwendet wird wie die <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="baf98-105">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="baf98-106">Die wichtigsten Unterschiede bestehen im Angeben eines Auflösungsdienstes und dem Festlegen von Sicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="baf98-106">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="baf98-107">Wenn eine Anwendung den Standardresolver und Standardsicherheitseinstellungen verwendet, schließt das Konvertieren einer normalen client-/serverbasierten Anwendung für die Verwendung von Peerkanal das Ändern des Bindungsnamens von "NetTcpBinding" in "NetPeerTcpBinding" in der Konfigurationsdatei der Anwendung ein; die Codebasis der Anwendung muss nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="baf98-107">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf98-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="baf98-108">See also</span></span>

- [<span data-ttu-id="baf98-109">Erstellen einer Peerkanalanwendung</span><span class="sxs-lookup"><span data-stu-id="baf98-109">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [<span data-ttu-id="baf98-110">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="baf98-110">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
