---
title: Konvertieren einer NetTcpBinding-Anwendung in eine Peerkanalanwendung
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 930d5ed4f3adfb8e539cea5e84aa5e5c352e5018
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742905"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>Konvertieren einer NetTcpBinding-Anwendung in eine Peerkanalanwendung
Sie können Verbindungen zwischen Clients mit [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] herstellen, indem Sie Bindungen verwenden, die die Verbindungsparameter beschreiben. Für das Konvertieren einer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Anwendung zum Verwenden von Peer-to-Peer-Verbindungen ist eine Bindung erforderlich, die diese Technologie beim Herstellen von Clientverbindungen unterstützt. Peerkanal stellt eine Bindung mit der Bezeichnung <xref:System.ServiceModel.NetPeerTcpBinding> bereit, die auf ähnliche Weise verwendet wird wie die <xref:System.ServiceModel.NetTcpBinding>. Die wichtigsten Unterschiede bestehen im Angeben eines Auflösungsdienstes und dem Festlegen von Sicherheitseinstellungen.  
  
 Wenn eine Anwendung den Standardresolver und Standardsicherheitseinstellungen verwendet, schließt das Konvertieren einer normalen client-/serverbasierten Anwendung für die Verwendung von Peerkanal das Ändern des Bindungsnamens von „NetTcpBinding“ in „NetPeerTcpBinding“ in der Konfigurationsdatei der Anwendung ein; die Codebasis der Anwendung muss nicht geändert werden.  
  
## <a name="see-also"></a>Siehe auch
- [Erstellen einer Peerkanalanwendung](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md)
