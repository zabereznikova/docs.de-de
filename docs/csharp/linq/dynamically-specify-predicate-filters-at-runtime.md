---
title: "Dynamisches Festlegen von Prädikatfiltern zur Laufzeit"
description: "So legen Sie Prädikatfilter zur Laufzeit dynamisch fest."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: 06bc594ac1357e7dca6c182fa28310559a79875c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a>Dynamisches Festlegen von Prädikatfiltern zur Laufzeit

In einigen Fällen wissen Sie bis zur Laufzeit nicht, wie viele Prädikate Sie für die Quellelemente in die `where`-Klausel übernehmen müssen. Eine Möglichkeit, mehrere Prädikatfilter dynamisch festzulegen, ist die Verwendung der Methode <xref:System.Linq.Enumerable.Contains%2A>, wie im folgenden Beispiel gezeigt wird. Das Beispiel wird auf zwei Arten erstellt. Zuerst wird das Projekt durch Filtern nach Werten, die im Programm bereitgestellt werden, ausgeführt. Und dann wird das Projekt mithilfe der Eingabe, die zur Laufzeit bereitgestellt wird, erneut ausgeführt.  
  
## <a name="to-filter-by-using-the-contains-method"></a>Filtern mithilfe der Contains-Methode  
  
1.  Erstellen Sie eine neue Konsolenanwendung und nennen Sie sie `PredicateFilters`.  
  
2.  Kopieren Sie die `StudentClass`-Klasse aus [Query a collection of objects (Abfragen einer Auflistung von Objekten)](query-a-collection-of-objects.md) und fügen Sie ihn in Namespace `PredicateFilters` unter Klasse `Program` ein. `StudentClass` stellt eine Liste von `Student`-Objekten bereit.  
  
3.  Kommentieren Sie die `Main`-Methode in `StudentClass` aus.  
  
4.  Ersetzen Sie die `Program`-Klasse durch den folgenden Code.  
  
     [!code-csharp[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]  
  
5.  Fügen Sie die folgende Zeile in die `Main`-Methode in Klasse `DynamicPredicates` unter der Deklaration von `ids` ein.  
  
     ```csharp
     QueryById(ids);
     ```

6.  Führen Sie das Projekt aus.  
  
7.  In einem Konsolenfenster wird die folgende Ausgabe angezeigt werden:  
  
     Garcia: 114  
  
     O'Donnell: 112  
  
     Omelchenko: 111  
  
8.  Im nächsten Schritt wird das Projekt erneut ausgeführt, dieses Mal mit der Eingabe zur Laufzeit anstelle von Array `ids`. Ändern Sie `QueryByID(ids)` zu `QueryByID(args)` in der `Main`-Methode.  
  
9. Führen Sie das Projekt mit den Befehlszeilenargumenten `122 117 120 115` aus. Wenn das Projekt ausgeführt wird, werden diese Werte Elemente von `args`, dem Parameter der `Main`-Methode.  
  
10. In einem Konsolenfenster wird die folgende Ausgabe angezeigt werden:  
  
     Adams: 120  
  
     Feng: 117  
  
     Garcia: 115  
  
     Tucker: 122  
  
## <a name="to-filter-by-using-a-switch-statement"></a>Filtern mithilfe einer Switch-Anweisung  
  
1.  Sie können eine `switch`-Anweisung zum Auswählen zwischen vordefinierten alternativen Abfragen verwenden. Im folgenden Beispiel verwendet `studentQuery` eine andere `where`-Klausel, abhängig davon, welche Klassenstufe oder welches Jahr zur Laufzeit angegeben wird.  
  
2.  Kopieren Sie die folgende Methode, und fügen Sie sie in die Klasse `DynamicPredicates` ein.  
  
     [!code-csharp[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]  
  
3.  Ersetzen Sie in der `Main`-Methode den Aufruf von `QueryByID` mit dem folgenden Aufruf, der das erste Element aus dem `args`-Array als sein Argument sendet: `QueryByYear(args[0])`.  
  
4.  Führen Sie das Projekt mit einem Befehlszeilenargument für einen ganzzahligen Wert zwischen 1 und 4 aus.  
  
 
## <a name="see-also"></a>Siehe auch  
 [LINQ-Abfrageausdrücke](index.md)  
 [where-Klausel](../language-reference/keywords/where-clause.md)
