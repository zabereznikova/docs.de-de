---
title: Konvertieren einer NetTcpBinding-Anwendung in eine Peerkanalanwendung
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 5444b53f0373a2f2b06da680a53e8e5fa77d39b7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286733"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="fe0a0-102">Konvertieren einer NetTcpBinding-Anwendung in eine Peerkanalanwendung</span><span class="sxs-lookup"><span data-stu-id="fe0a0-102">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>

<span data-ttu-id="fe0a0-103">Sie können Verbindungen zwischen Clients mithilfe von WinFX mithilfe von Bindungen erstellen, die die Parameter der Verbindung beschreiben.</span><span class="sxs-lookup"><span data-stu-id="fe0a0-103">You can create connections between clients using the WinFX by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="fe0a0-104">Zum umrechnen einer .NET Framework Anwendung für die Verwendung von Peer-zu-Peer-Verbindungen ist eine Bindung erforderlich, die diese Technologie beim Herstellen von Clientverbindungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fe0a0-104">Converting a .NET Framework application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="fe0a0-105">Peerkanal stellt eine Bindung mit der Bezeichnung <xref:System.ServiceModel.NetPeerTcpBinding> bereit, die auf ähnliche Weise verwendet wird wie die <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="fe0a0-105">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="fe0a0-106">Die wichtigsten Unterschiede bestehen im Angeben eines Auflösungsdienstes und dem Festlegen von Sicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="fe0a0-106">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="fe0a0-107">Wenn eine Anwendung den Standardresolver und Standardsicherheitseinstellungen verwendet, schließt das Konvertieren einer normalen client-/serverbasierten Anwendung für die Verwendung von Peerkanal das Ändern des Bindungsnamens von "NetTcpBinding" in "NetPeerTcpBinding" in der Konfigurationsdatei der Anwendung ein; die Codebasis der Anwendung muss nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fe0a0-107">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe0a0-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe0a0-108">See also</span></span>

- [<span data-ttu-id="fe0a0-109">Erstellen einer Peerkanalanwendung</span><span class="sxs-lookup"><span data-stu-id="fe0a0-109">Building a Peer Channel Application</span></span>](building-a-peer-channel-application.md)
- [<span data-ttu-id="fe0a0-110">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="fe0a0-110">System-Provided Bindings</span></span>](../system-provided-bindings.md)
