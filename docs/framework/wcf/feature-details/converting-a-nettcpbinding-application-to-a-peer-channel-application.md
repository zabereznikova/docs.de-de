---
title: Konvertieren einer NetTcpBinding-Anwendung in eine Peerkanalanwendung
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 42266d8c7c04e2d8f3f1e4734d9a05181c3f1ea3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595556"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="46e54-102">Konvertieren einer NetTcpBinding-Anwendung in eine Peerkanalanwendung</span><span class="sxs-lookup"><span data-stu-id="46e54-102">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>
<span data-ttu-id="46e54-103">Sie können Verbindungen zwischen Clients mithilfe von WinFX mithilfe von Bindungen erstellen, die die Parameter der Verbindung beschreiben.</span><span class="sxs-lookup"><span data-stu-id="46e54-103">You can create connections between clients using the WinFX by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="46e54-104">Zum umrechnen einer .NET Framework Anwendung für die Verwendung von Peer-zu-Peer-Verbindungen ist eine Bindung erforderlich, die diese Technologie beim Herstellen von Clientverbindungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="46e54-104">Converting a .NET Framework application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="46e54-105">Peerkanal stellt eine Bindung mit der Bezeichnung <xref:System.ServiceModel.NetPeerTcpBinding> bereit, die auf ähnliche Weise verwendet wird wie die <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="46e54-105">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="46e54-106">Die wichtigsten Unterschiede bestehen im Angeben eines Auflösungsdienstes und dem Festlegen von Sicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="46e54-106">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="46e54-107">Wenn eine Anwendung den Standardresolver und Standardsicherheitseinstellungen verwendet, schließt das Konvertieren einer normalen client-/serverbasierten Anwendung für die Verwendung von Peerkanal das Ändern des Bindungsnamens von "NetTcpBinding" in "NetPeerTcpBinding" in der Konfigurationsdatei der Anwendung ein; die Codebasis der Anwendung muss nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="46e54-107">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e54-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46e54-108">See also</span></span>

- [<span data-ttu-id="46e54-109">Erstellen einer Peerkanalanwendung</span><span class="sxs-lookup"><span data-stu-id="46e54-109">Building a Peer Channel Application</span></span>](building-a-peer-channel-application.md)
- [<span data-ttu-id="46e54-110">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="46e54-110">System-Provided Bindings</span></span>](../system-provided-bindings.md)
