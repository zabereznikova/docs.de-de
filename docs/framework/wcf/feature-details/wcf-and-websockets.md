---
title: WCF und WebSockets
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e84bf7a94a6a6fa980e223daf0a6c7aaf489bb6e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-and-websockets"></a>WCF und WebSockets
Mit .NET Framework 4.5 wird Unterstützung für WebSockets in Windows Communication Foundation eingeführt.  WebSockets ist eine effiziente standardbasierte Technologie, die die bidirektionale Kommunikation über die HTTP-Standardports 80 und 443 ermöglicht. Die Verwendung der standardmäßigen HTTP-Ports ermöglicht WebSockets die webbasierte Kommunikation über Vermittler.  Um die Kommunikation über einen WebSocket-Transport zu unterstützen, wurden zwei neue Standardbindungen hinzugefügt. <xref:System.ServiceModel.NetHttpBinding> und <xref:System.ServiceModel.NetHttpsBinding>. WebSockets-spezifische Einstellungen können konfiguriert werden, auf die <xref:System.ServiceModel.Channels.HttpTransportBindingElement> durch den Zugriff auf die <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> Eigenschaft.
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Verwenden von NetHttpBinding](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 Erläutert die <xref:System.ServiceModel.NetHttpBinding> und deren Konfiguration.  
  
 [Vorgehensweise: Erstellen eines WCF-Diensts, der über WebSockets kommuniziert](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 Beschreibt, wie ein WCF-Dienst erstellt wird, der über WebSockets kommuniziert.  
  
## <a name="reference"></a>Verweis  
  
## <a name="related-sections"></a>Verwandte Abschnitte
