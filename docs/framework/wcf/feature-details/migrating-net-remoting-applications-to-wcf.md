---
title: Migrieren von .NET-Remoteanwendungen nach WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 96018b775b858e8ac0d0221135cb5109b0cd81d3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509999"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migrieren von .NET-Remoteanwendungen nach WCF
**Dieses Thema bezieht sich auf eine veraltete Technologie, die zum Zwecke der Abwärtskompatibilität mit vorhandenen Anwendungen beibehalten wird und nicht für die neue Entwicklung empfohlen wird. Verteilte Anwendungen sollten jetzt mithilfe von WCF entwickelt werden.**  
  
 Es gibt zwei Möglichkeiten von WCF mit vorhandenen .NET Remoting-Anwendungen nutzen: Integration und Migration. Integration kann .net Remoting 2.0 und mit WCF parallel, können Sie dieselben Geschäftsobjekte über beide Technologien gleichzeitig verfügbar zu machen ohne so ändern Sie den vorhandenen .net Remoting 2.0-Code. Voraussetzung der Integration ist, dass [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 oder höher ausgeführt wird. Wenn Sie WCF-Features nutzen möchten, und netzwerkkompatibilität mit Remoting 2.0-Systemen ist nicht erforderlich, können Sie Ihre gesamten Dienst zu WCF migrieren. Migration von .NET Remoting 2.0 nach WCF erfordert Änderungen am-Schnittstelle des Remoteobjekts und ihre Konfigurationseinstellungen. Beide der folgenden Themen finden Sie im [von Remoting zu Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).  
  
## <a name="see-also"></a>Siehe auch
- [Konzeptionelle Übersicht](../../../../docs/framework/wcf/conceptual-overview.md)
