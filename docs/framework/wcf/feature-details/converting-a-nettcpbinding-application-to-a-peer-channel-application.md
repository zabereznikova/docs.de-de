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
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>Konvertieren einer NetTcpBinding-Anwendung in eine Peerkanalanwendung
Sie können Verbindungen zwischen Clients mit den WinFX mit Bindungen, die beschreiben, die Parameter der Verbindung erstellen. Konvertieren von einer .NET Framework-Anwendung zur Verwendung von Peer-zu-Peer-Verbindungen erfordert eine Bindung, die diese Technologie beim Herstellen von Clientverbindungen zu unterstützen. Peerkanal stellt eine Bindung mit der Bezeichnung <xref:System.ServiceModel.NetPeerTcpBinding> bereit, die auf ähnliche Weise verwendet wird wie die <xref:System.ServiceModel.NetTcpBinding>. Die wichtigsten Unterschiede bestehen im Angeben eines Auflösungsdienstes und dem Festlegen von Sicherheitseinstellungen.  
  
 Wenn eine Anwendung den Standardresolver und Standardsicherheitseinstellungen verwendet, schließt das Konvertieren einer normalen client-/serverbasierten Anwendung für die Verwendung von Peerkanal das Ändern des Bindungsnamens von "NetTcpBinding" in "NetPeerTcpBinding" in der Konfigurationsdatei der Anwendung ein; die Codebasis der Anwendung muss nicht geändert werden.  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen einer Peerkanalanwendung](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md)
