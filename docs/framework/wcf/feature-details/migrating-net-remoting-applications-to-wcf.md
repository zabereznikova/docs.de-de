---
title: Migrieren von .NET-Remoteanwendungen nach WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 4040fb0ac223f91705a49b733f6a1f42d144068e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091115"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migrieren von .NET-Remoteanwendungen nach WCF
**Dieses Thema bezieht sich auf eine veraltete Technologie, die zum Zwecke der Abwärtskompatibilität mit vorhandenen Anwendungen beibehalten wird und nicht für die neue Entwicklung empfohlen wird. Verteilte Anwendungen sollten jetzt mithilfe von WCF entwickelt werden.**  
  
 Es gibt zwei Möglichkeiten von WCF mit vorhandenen .NET Remoting-Anwendungen nutzen: Integration und Migration. Integration können Sie .NET Remoting 2.0 "und" WCF parallel ausgeführt wird, können Sie dieselben Geschäftsobjekte über beide Technologien gleichzeitig verfügbar zu machen ohne den vorhandenen .NET Remoting 2.0-Code ändern zu müssen. Voraussetzung der Integration ist, dass [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 oder höher ausgeführt wird. Wenn Sie WCF-Features nutzen möchten, und netzwerkkompatibilität mit Remoting 2.0-Systemen ist nicht erforderlich, können Sie Ihre gesamten Dienst zu WCF migrieren. Migration von .NET Remoting 2.0 nach WCF erfordert Änderungen am-Schnittstelle des Remoteobjekts und ihre Konfigurationseinstellungen. Beide der folgenden Themen finden Sie im [von Remoting zu Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).  
  
## <a name="see-also"></a>Siehe auch

- [Konzeptionelle Übersicht](../../../../docs/framework/wcf/conceptual-overview.md)
