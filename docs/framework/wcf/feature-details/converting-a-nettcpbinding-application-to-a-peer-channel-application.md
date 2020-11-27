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
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>Konvertieren einer NetTcpBinding-Anwendung in eine Peerkanalanwendung

Sie können Verbindungen zwischen Clients mithilfe von WinFX mithilfe von Bindungen erstellen, die die Parameter der Verbindung beschreiben. Zum umrechnen einer .NET Framework Anwendung für die Verwendung von Peer-zu-Peer-Verbindungen ist eine Bindung erforderlich, die diese Technologie beim Herstellen von Clientverbindungen unterstützt. Peerkanal stellt eine Bindung mit der Bezeichnung <xref:System.ServiceModel.NetPeerTcpBinding> bereit, die auf ähnliche Weise verwendet wird wie die <xref:System.ServiceModel.NetTcpBinding>. Die wichtigsten Unterschiede bestehen im Angeben eines Auflösungsdienstes und dem Festlegen von Sicherheitseinstellungen.  
  
 Wenn eine Anwendung den Standardresolver und Standardsicherheitseinstellungen verwendet, schließt das Konvertieren einer normalen client-/serverbasierten Anwendung für die Verwendung von Peerkanal das Ändern des Bindungsnamens von "NetTcpBinding" in "NetPeerTcpBinding" in der Konfigurationsdatei der Anwendung ein; die Codebasis der Anwendung muss nicht geändert werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen einer Peerkanalanwendung](building-a-peer-channel-application.md)
- [Vom System bereitgestellte Bindungen](../system-provided-bindings.md)
