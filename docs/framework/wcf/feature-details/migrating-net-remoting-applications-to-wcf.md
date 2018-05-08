---
title: Migrieren von .NET-Remoteanwendungen nach WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 53f63352503a48ee849580e676b5fe98f3dcf2cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migrieren von .NET-Remoteanwendungen nach WCF
**Dieses Thema bezieht sich auf eine veraltete Technologie, die zum Zwecke der Abwärtskompatibilität mit vorhandenen Anwendungen beibehalten wird und nicht für die neue Entwicklung empfohlen wird. Verteilte Anwendungen sollte jetzt mithilfe von WCF entwickelt werden.**  
  
 Es gibt zwei Möglichkeiten, die von WCF mit vorhandenen .NET Remoting-Anwendungen nutzen: Integration und Migration. Integration kann .net Remoting 2.0 und WCF ausgeführt parallel, da Sie dieselben Geschäftsobjekte über beide Technologien gleichzeitig verfügbar zu machen ohne so ändern Sie den vorhandenen .net Remoting 2.0-Code. Voraussetzung der Integration ist, dass [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 oder höher ausgeführt wird. Wenn Sie WCF-Funktionen nutzen möchten, und über das Netzwerk Kompatibilität mit Remoting 2.0-Systemen ist nicht erforderlich, können Sie den gesamten Dienst zu WCF migrieren. Migration von .NET Remoting 2.0 nach WCF erfordert Änderungen auf das Remoteobjekt Schnittstellen und ihre Konfigurationseinstellungen. Beide der folgenden Themen werden behandelt, [von Remoting zu Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).  
  
## <a name="see-also"></a>Siehe auch  
 [Konzeptionelle Übersicht](../../../../docs/framework/wcf/conceptual-overview.md)
