---
title: WCF und WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: ac888db14ebd21c4aed2f717c1f71bed310b8388
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498526"
---
# <a name="wcf-and-websockets"></a>WCF und WebSockets
Mit .NET Framework 4.5 wird Unterstützung für WebSockets in Windows Communication Foundation eingeführt.  WebSockets ist eine effiziente standardbasierte Technologie, die die bidirektionale Kommunikation über die HTTP-Standardports 80 und 443 ermöglicht. Die Verwendung der standardmäßigen HTTP-Ports ermöglicht WebSockets die webbasierte Kommunikation über Vermittler.  Um die Kommunikation über einen WebSocket-Transport zu unterstützen, wurden zwei neue Standardbindungen hinzugefügt. <xref:System.ServiceModel.NetHttpBinding> und <xref:System.ServiceModel.NetHttpsBinding>. WebSockets-spezifische Einstellungen können konfiguriert werden, auf die <xref:System.ServiceModel.Channels.HttpTransportBindingElement> durch den Zugriff auf die <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> Eigenschaft.
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Verwenden von NetHttpBinding](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 Erläutert die <xref:System.ServiceModel.NetHttpBinding> und deren Konfiguration.  
  
 [Vorgehensweise: Erstellen eines WCF-Diensts, der über WebSockets kommuniziert](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 Beschreibt, wie ein WCF-Dienst erstellt wird, der über WebSockets kommuniziert.  
  
## <a name="reference"></a>Referenz  
  
## <a name="related-sections"></a>Verwandte Abschnitte
