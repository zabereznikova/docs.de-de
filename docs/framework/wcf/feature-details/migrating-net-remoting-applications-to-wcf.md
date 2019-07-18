---
title: Migrieren von .NET-Remoteanwendungen nach WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: c0ce7c9badc8bad6eedc58827b6efe2595ab2cf8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592870"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migrieren von .NET-Remoteanwendungen nach WCF
**Dieses Thema bezieht sich auf eine veraltete Technologie, die zum Zwecke der Abwärtskompatibilität mit vorhandenen Anwendungen beibehalten wird und nicht für die neue Entwicklung empfohlen wird. Verteilte Anwendungen sollten jetzt mithilfe von WCF entwickelt werden.**  
  
 Es gibt zwei Möglichkeiten von WCF mit vorhandenen .NET Remoting-Anwendungen nutzen: Integration und Migration. Integration können Sie .NET Remoting 2.0 "und" WCF parallel ausgeführt wird, können Sie dieselben Geschäftsobjekte über beide Technologien gleichzeitig verfügbar zu machen ohne den vorhandenen .NET Remoting 2.0-Code ändern zu müssen. Integration erfordert, dass Sie auf .NET Framework 2.0 oder höher ausgeführt werden. Wenn Sie WCF-Features nutzen möchten, und netzwerkkompatibilität mit Remoting 2.0-Systemen ist nicht erforderlich, können Sie Ihre gesamten Dienst zu WCF migrieren. Migration von .NET Remoting 2.0 nach WCF erfordert Änderungen am-Schnittstelle des Remoteobjekts und ihre Konfigurationseinstellungen. Beide der folgenden Themen finden Sie im [von Remoting zu Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).  
  
## <a name="see-also"></a>Siehe auch

- [Konzeptionelle Übersicht](../../../../docs/framework/wcf/conceptual-overview.md)
