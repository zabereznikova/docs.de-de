---
title: Migrieren von .NET-Remoteanwendungen nach WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: d12583904e4a025a8de1103f0fb48f4656d6855e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598774"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migrieren von .NET-Remoteanwendungen nach WCF
**Dieses Thema ist spezifisch für eine Legacy Technologie, die aus Gründen der Abwärtskompatibilität mit vorhandenen Anwendungen beibehalten wird und nicht für die neue Entwicklung empfohlen wird. Verteilte Anwendungen sollten jetzt mithilfe von WCF entwickelt werden.**  
  
 Es gibt zwei Möglichkeiten, WCF mit vorhandenen .NET Remoting-Anwendungen zu nutzen: Integration und Migration. Integration ermöglicht es Ihnen, .NET Remoting 2,0 und WCF nebeneinander auszuführen, sodass Sie dieselben Geschäftsobjekte über beide Technologien gleichzeitig verfügbar machen können, ohne Ihren vorhandenen .NET Remoting 2,0-Code ändern zu müssen. Für die Integration ist es erforderlich, dass Sie auf .NET Framework 2,0 oder höher ausführen. Wenn Sie WCF-Features nutzen und keine Netzwerkkompatibilität mit Remoting 2,0-Systemen benötigen, können Sie den gesamten Dienst zu WCF migrieren. Für die Migration von .NET Remoting 2,0 zu WCF sind Änderungen an der Schnittstelle des Remote Objekts und seinen Konfigurationseinstellungen erforderlich. Beide Themen werden unter [Remoting zum Windows Communication Foundation](https://docs.microsoft.com/previous-versions/aa730857(v=vs.80))behandelt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Konzeptionelle Übersicht](../conceptual-overview.md)
