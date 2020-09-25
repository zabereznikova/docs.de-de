---
title: Abfrageergebnisse
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcd7b699-4e50-4523-8c33-2f54a103d94e
ms.openlocfilehash: 5eb23525f685c4ebf22ac24d16aa3ee66297e172
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202226"
---
# <a name="query-results"></a>Abfrageergebnisse

Nachdem eine LINQ to Entities Abfrage in Befehlsstrukturen konvertiert und ausgeführt wurde, werden die Abfrageergebnisse in der Regel als eine der folgenden zurückgegeben:  
  
- Eine Auflistung von 0 (null) oder mehr typisierten Entitätsobjekten oder eine Projektion komplexer Typen im konzeptionellen Modell.  
  
- Vom konzeptionellen Modell unterstützte CLR-Typen.  
  
- Inlineauflistungen  
  
- Anonyme Typen  
  
 Wenn die Abfrage in der Datenquelle ausgeführt wurde, werden die Ergebnisse in CLR-Typen materialisiert und an den Client zurückgegeben. Jede Objektmaterialisierung wird vom Entity Framework durchgeführt. Alle Fehler, die dadurch entstehen, dass zwischen dem Entity Framework und der CLR keine Zuordnung vorgenommen werden kann, lösen bei der Objektmaterialisierung Ausnahmen aus.
  
 Wenn die Abfrage Ausführung primitive konzeptionelle Modelltypen zurückgibt, besteht das Ergebnis aus CLR-Typen, die eigenständig sind und vom Entity Framework getrennt sind. Wenn die Abfrage jedoch eine durch <xref:System.Data.Objects.ObjectQuery%601> dargestellte Auflistung typisierter Entitätsobjekte zurückgibt, werden diese Typen vom Objektkontext nachverfolgt. Das gesamte Objekt Verhalten (z. b. untergeordnete/übergeordnete Auflistungen, Änderungs Nachverfolgung, Polymorphie usw.) ist wie in der Entity Framework definiert. Diese Funktion kann in ihrer Kapazität verwendet werden, wie Sie in der Entity Framework definiert ist. Weitere Informationen finden Sie unter [Arbeiten mit Objekten](../working-with-objects.md).
  
 Von Abfragen zurückgegebene Strukturtypen (wie anonyme Typen und komplexe Typen, die NULL-Werte zulassen) können den Wert `null` haben. Eine <xref:System.Data.Objects.DataClasses.EntityCollection%601>-Eigenschaft einer zurückgegebenen Entität kann ebenfalls den Wert `null` haben. Dies kann durch die Projektion einer Auflistungseigenschaft einer Entität geschehen, die den Wert `null` hat, wie ein Aufruf von <xref:System.Linq.Queryable.FirstOrDefault%2A> für eine <xref:System.Data.Objects.ObjectQuery%601>, die über keine Elemente verfügt.  
  
 In einigen Fällen kann es den Anschein haben, dass eine Abfrage bei ihrer Ausführung ein materialisiertes Ergebnis erstellt, während die Abfrage tatsächlich auf dem Server ausgeführt wird und das Entitätsobjekt nicht in der CLR materialisiert wird. Dies kann Probleme verursachen, wenn Nebeneffekte der Objektmaterialisierung von Bedeutung sind.  
  
 Im folgenden Beispiel ist eine benutzerdefinierte Klasse, `MyContact`, mit einer `LastName`-Eigenschaft enthalten. Wenn die `LastName`-Eigenschaft festgelegt wird, wird eine `count`-Variable inkrementiert. Bei der Ausführung der folgenden beiden Abfragen inkrementiert die erste `count`, die zweite jedoch nicht. Der Grund dafür ist, dass in der zweiten Abfrage die `LastName`-Eigenschaft aus den Ergebnissen projiziert wird und die `MyContact`-Klasse nicht erstellt wird, da es nicht nötig ist, die Abfrage im Speicher auszuführen.  
  
 [!code-csharp[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#materializationsideeffects)]
 [!code-vb[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#materializationsideeffects)]  
  
 [!code-csharp[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#mycontactclass)]
 [!code-vb[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#mycontactclass)]
