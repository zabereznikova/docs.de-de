---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: c4069ef760877935c4ce194144d131d0dc58b4d3
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504366"
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
LINQ to DataSet erleichtert Ihnen schneller zur Abfrage von Daten und zwischengespeichert, und einem <xref:System.Data.DataSet> Objekt. Genauer gesagt, vereinfacht die LINQ to DataSet, Abfragen, da der Entwickler Schreiben von Abfragen von der Programmiersprache selbst, anstatt eine separate Abfragesprache mit. Dies ist besonders nützlich für Visual Studio-Entwickler, die nun die syntaxüberprüfung für während der Kompilierung, statische Typisierung und IntelliSense-Unterstützung, die von der Visual Studio in ihren Abfragen bereitgestellten nutzen können.  
  
 LINQ to DataSet kann auch verwendet werden zur Abfrage von Daten, die aus einem oder mehreren Datenquellen konsolidiert wurden. Dies ermöglicht eine Vielzahl von Szenarios, bei denen Flexibilität bei der Darstellung und Behandlung von Daten erforderlich ist, wie das Abfragen lokal aggregierter Daten und die Zwischenspeicherung auf der mittleren Ebene bei Webanwendungen. Diese Manipulationsmethode wird insbesondere bei der Erstellung von Berichterstellungs-, Analyse- und Business Intelligence-Anwendungen benötigt.  
  
 Die LINQ to DataSet-Funktionalität verfügbar gemacht wird, in erster Linie durch die Erweiterungsmethoden in den <xref:System.Data.DataRowExtensions> und <xref:System.Data.DataTableExtensions> Klassen. LINQ to DataSet basiert auf und verwendet die vorhandene ADO.NET-Architektur und ist nicht zum Ersetzen von ADO.NET in Anwendungscode vorgesehen. Vorhandene ADO.NET-Code funktionieren weiterhin in einer LINQ to DataSet-Anwendung. Die Beziehung zwischen LINQ to DataSet zu ADO.NET und dem Datenspeicher wird im folgenden Diagramm veranschaulicht.  
  
 ![Das Diagramm zeigt, dass LINQ to DataSet auf dem ADO.NET-Anbieter basiert.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erste Schritte](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [Programmierhandbuch](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>Referenz  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>Siehe auch

- [Language Integrated Query (LINQ) – C#](../../../csharp/programming-guide/concepts/linq/index.md)
- [Language Integrated Query (LINQ) – Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ und ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
