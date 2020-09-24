---
title: Verzögertes im Vergleich zu unmittelbarem Laden
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1d7247f-a3b7-460b-b342-5c1a2365aa1a
ms.openlocfilehash: 4e2cb7c90eb703985cbb1b8673522a9e253564d0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164297"
---
# <a name="deferred-versus-immediate-loading"></a>Verzögertes im Vergleich zu unmittelbarem Laden

Wenn Sie eine Abfrage für ein Objekt durchführen, wird nur das angeforderte Objekt abgerufen. Die *verknüpften Objekte werden* nicht automatisch gleichzeitig abgerufen. (Weitere Informationen finden Sie unter [Beziehungs übergreifende Abfragen](querying-across-relationships.md).) Die Tatsache, dass die verknüpften Objekte nicht bereits geladen sind, wird nicht angezeigt, da der Versuch, darauf zuzugreifen, eine Anforderung erzeugt, mit der Sie abgerufen werden.  
  
 Beispielsweise können Sie eine Abfrage nach einem bestimmten Satz von Bestellungen durchsuchen und dann nur gelegentlich eine e-Mail-Benachrichtigung an bestimmte Kunden senden. Sie müssen nicht notwendigerweise zunächst alle Kundendaten zu jeder Bestellung abrufen. Sie können mithilfe von verzögertem Laden weitere Informationen erst dann abrufen, wenn Sie diese benötigen. Betrachten Sie das folgende Beispiel:  
  
 [!code-csharp[DLinqQueryConcepts#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#1)]
 [!code-vb[DLinqQueryConcepts#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#1)]  
  
 Das Gegenteil könnte auch zutreffen. Möglicherweise verwenden Sie eine Anwendung, die Kunden- und Bestelldaten gleichzeitig anzeigen muss. Sie wissen, dass Sie beide Datensätze benötigen. Sie wissen, dass die Anwendung Bestellinformationen für jeden Kunden benötigt, sobald Sie die Ergebnisse abrufen. Sie möchten nicht einzelne Abfragen zu den Bestellungen jedes einzelnen Kunden übergeben. Sie möchten stattdessen die Bestelldaten zusammen mit den Kunden abrufen.  
  
 [!code-csharp[DLinqQueryConcepts#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#2)]
 [!code-vb[DLinqQueryConcepts#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#2)]  
  
 Sie können auch Kunden und Bestellungen in einer Abfrage zusammenfassen, indem Sie diese produktübergreifend gestalten und alle erforderlichen Daten in Form einer großen Projektion abrufen. Diese Ergebnisse sind jedoch keine Entitäten. (Weitere Informationen finden Sie [unter LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)). Entitäten sind Objekte, die Sie verändern können. Bei diesen Ergebnissen handelt es sich jedoch um Projektionen, die nicht verändert und erhalten werden können. Darüber hinaus würden Sie eine Menge redundanter Daten abrufen, da sich die Kunden bei jeder Bestellung in der optimierten gemeinsamen Abfrage wiederholen.  
  
 Sie benötigen stattdessen eine Möglichkeit, verwandte Objekte zur gleichen Zeit abzurufen. Dieser Satz ist ein isolierter Bereich eines Graphen, sodass Sie niemals mehr oder weniger Daten als benötigt abrufen. Zu diesem Zweck [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] stellt das <xref:System.Data.Linq.DataLoadOptions> sofortige Laden eines Bereichs des Objektmodells bereit. Die Methoden umfassen:  
  
- Die <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>-Methode zum sofortigen Laden von Daten zum Hauptziel.  
  
- Die <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A>-Methode zum Filtern abgerufener Objekte nach einer bestimmten Beziehung.  
  
## <a name="see-also"></a>Weitere Informationen

- [Abfragekonzepte](query-concepts.md)
