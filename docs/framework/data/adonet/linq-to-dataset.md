---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 8a16e3fe0cea04813be50a83f906170199e78e3e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764852"
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
Mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] können Daten, die in einem <xref:System.Data.DataSet>-Objekt zwischengespeichert sind, leichter und schneller abgefragt werden. Insbesondere [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] vereinfacht, da der Entwickler Schreiben von Abfragen in der Programmiersprache selbst, anstatt eine separate Abfragesprache mit Abfragen. Dies ist besonders nützlich für Visual Studio-Entwickler, jetzt die syntaxüberprüfung der Zeitpunkt der Kompilierung, statische Typisierung und IntelliSense-Unterstützung, die von der Visual Studio in seinen Abfragen bereitgestellt nutzen können.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] kann auch für das Abfragen von Daten verwendet werden, die aus einer oder mehreren Datenquellen konsolidiert wurden. Dies ermöglicht eine Vielzahl von Szenarios, bei denen Flexibilität bei der Darstellung und Behandlung von Daten erforderlich ist, wie das Abfragen lokal aggregierter Daten und die Zwischenspeicherung auf der mittleren Ebene bei Webanwendungen. Diese Manipulationsmethode wird insbesondere bei der Erstellung von Berichterstellungs-, Analyse- und Business Intelligence-Anwendungen benötigt.  
  
 Die [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Funktionalität wird bereitgestellt, in erster Linie durch die Erweiterungsmethoden in den <xref:System.Data.DataRowExtensions> und <xref:System.Data.DataTableExtensions> Klassen. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] baut auf und verwendet die vorhandene [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] -Architektur und ist nicht vorgesehen, ersetzen Sie [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] im Anwendungscode. Der vorhandene ADO.NET 2.0-Code funktioniert auch in einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Anwendung. Die Beziehung zwischen [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] und [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] und dem Datenspeicher wird im folgenden Diagramm illustriert.  
  
 ![LINQ to DataSet basiert auf dem ADO.NET-Anbieter](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erste Schritte](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [Programmierhandbuch](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>Referenz  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ (Language Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [LINQ und ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)
