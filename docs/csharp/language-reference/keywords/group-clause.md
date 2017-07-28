---
title: group-Klausel (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- group
- group_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- group keyword [C#]
- group clause [C#]
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: afd32358a406b2797059cf2b8d85d897c8737222
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="group-clause-c-reference"></a>group-Klausel (C#-Referenz)
Die `group`-Klausel gibt eine Sequenz von <xref:System.Linq.IGrouping%602>-Objekten zurück, die null oder mehr Elemente enthalten, die mit dem Schlüsselwert für die Gruppe übereinstimmen. Sie können z.B. eine Sequenz von Zeichenfolgen entsprechend des ersten Buchstaben in jeder Zeichenfolge gruppieren. In diesem Fall ist der erste Buchstabe der Schlüssel, verfügt über einen Typ [char](../../../csharp/language-reference/keywords/char.md) und wird in der `Key`-Eigenschaft jedes <xref:System.Linq.IGrouping%602>-Objekts gespeichert. Der Compiler leiten den Typ des Schlüssels her.  
  
 Sie können einen Abfrageausdruck mit einer `group`-Klausel beenden, so wie in folgendem Beispiel gezeigt:  
  
 [!code-cs[cscsrefQueryKeywords#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_1.cs)]  
  
 Wenn Sie zusätzliche Abfragevorgänge für jede Gruppe ausführen möchten, können Sie einen temporären Bezeichner mithilfe des kontextuellen Schlüsselworts [into](../../../csharp/language-reference/keywords/into.md) angeben. Wenn Sie `into` verwenden, müssen Sie mit der Abfrage fortfahren und sie entweder mit einer `select`-Anweisung oder einer anderen `group`-Klausel beenden, so wie im folgenden Auszug dargestellt:  
  
 [!code-cs[cscsrefQueryKeywords#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_2.cs)]  
  
 Weitere vollständige Beispiele des Gebrauchs von `group` mit und ohne `into` stehen im Abschnitt über Beispiele in diesem Thema bereit.  
  
## <a name="enumerating-the-results-of-a-group-query"></a>Auflisten der Ergebnisse einer Gruppenabfrage  
 Da die <xref:System.Linq.IGrouping%602>-Objekte, die von einer `group`-Abfrage erstellt wurden, praktisch eine Liste von Listen sind, müssen Sie eine geschachtelte [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Schleife verwenden, um auf die Elemente in jeder Gruppe zuzugreifen. Die äußere Schleife durchläuft die Gruppenschlüssel, und die innere Schleife durchläuft jedes Element in der Gruppe selbst. Eine Gruppe kann womöglich über einen Schlüssel verfügen, jedoch nicht über Elemente. Nachstehend finden Sie die `foreach`-Schleife, die die Abfrage in den vorherigen Codebeispielen ausführen:  
  
 [!code-cs[cscsrefQueryKeywords#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_3.cs)]  
  
## <a name="key-types"></a>Schlüsseltypen  
 Gruppenschlüssel können von jedem Typ sein, z.B. eine Zeichenfolge, ein integrierter numerischer Typ oder ein benutzerdefinierter benannter oder anonymer Typ.  
  
### <a name="grouping-by-string"></a>Gruppieren nach Zeichenfolge  
 Das vorherige Codebeispiel verwendete einen `char`. Es hätte stattdessen einfach ein Zeichenfolgenschlüssel angegeben werden können, z.B. der vollständige letzte Name.  
  
 [!code-cs[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_4.cs)]  
  
### <a name="grouping-by-bool"></a>Gruppieren nach Bool  
 Das folgende Beispiel zeigt die Verwendung eines booleschen Werts für einen Schlüssel, um die Ergebnisse in zwei Gruppen zu unterteilen. Beachten Sie, dass der Wert durch einen Unterausdruck in der `group`-Klausel erstellt wird.  
  
 [!code-cs[cscsrefQueryKeywords#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_5.cs)]  
  
### <a name="grouping-by-numeric-range"></a>Gruppieren nach numerischen Bereich  
 Das nächste Beispiel verwendet einen Ausdruck, um einen nummerischen Gruppenschlüssel zu erstellen, der einen Prozentbereich darstellt. Beachten Sie den Gebrauch von [let](../../../csharp/language-reference/keywords/let-clause.md) an einer komfortablen Position zur Speicherung eines Ergebnisses eines Methodenaufrufs, damit Sie die Methode nicht zweimal in der `group`-Klausel aufrufen müssen. Beachten Sie außerdem, dass in der `group`-Klausel eine Ausnahme durch Nulldivision vermieden wird, indem der Code überprüft, dass der Student keinen Durchschnitt von 0 hat. Weitere Informationen zur sicheren Verwendung von Methoden in Abfrageausdrücken finden Sie unter [Vorgehensweise: Behandeln von Ausnahmen in Abfrageausdrücken](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md).  
  
 [!code-cs[cscsrefQueryKeywords#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_6.cs)]  
  
### <a name="grouping-by-composite-keys"></a>Gruppieren nach zusammengesetzten Schlüsseln  
 Verwenden Sie einen zusammengesetzten Schlüssel, wenn Sie Elemente gemäß mehrerer Schlüssel gruppieren möchten. Sie erstellen einen zusammengesetzten Schlüssel, indem Sie einen anonymen Typ oder einen benannten Typ verwenden, um das Schlüsselelement aufzunehmen. Im folgenden Beispiel wird davon ausgegangen, dass eine `Person`-Klasse mit Elementen namens `surname` und `city` deklariert wurde. Die `group`-Klausel bewirkt, dass eine separate Gruppe für jede Gruppe von Personen mit dem gleichen Nachnamen und der gleichen Stadt erstellt wird.  
  
```csharp  
group person by new {name = person.surname, city = person.city};  
```  
  
 Verwenden Sie einen benannten Typ, wenn Sie die Abfragevariable an eine andere Methode übergeben müssen. Erstellen Sie eine spezielle Klasse mit automatisch implementierten Eigenschaften für die Schlüssel, und setzen Sie anschließend die Methoden <xref:System.Object.Equals%2A> und <xref:System.Object.GetHashCode%2A> außer Kraft. Sie können auch eine Struktur verwenden. In diesem Fall müssen Sie diese Methoden nicht unbedingt außer Kraft setzen. Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) und [Vorgehensweise: Abfragen von Dateiduplikaten in einer Verzeichnisstruktur (LINQ)](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md). Das zweite Thema verfügt über ein Codebeispiel, das darstellt, wie ein zusammengesetzter Schlüssel mit benannten Typen verwendet wird.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Standardmuster für das Sortieren von Quelldaten in Gruppen, wenn keine zusätzliche Abfragelogik auf die Gruppen angewendet wird. Dies wird Gruppierung ohne Fortsetzung genannt. Die Elemente in einem Zeichenfolgenarray werden gemäß des ersten Buchstabens gruppiert. Das Ergebnis der Abfrage ist ein <xref:System.Linq.IGrouping%602>-Typ, der eine öffentliche `Key`-Eigenschaft des Typs `char` und eine <xref:System.Collections.Generic.IEnumerable%601>-Sammlung enthält, die jedes Element in der Gruppierung enthält.  
  
 Das Ergebnis einer `group`-Klausel ist eine Sequenz von Sequenzen. Verwenden Sie deshalb eine geschachtelte `foreach`-Schleife innerhalb der Schleife, die die Gruppenschlüssel durchläuft – so wie in folgendem Beispiel gezeigt – um auf die einzelnen Elemente innerhalb jeder zurückgegebenen Gruppe zuzugreifen.  
  
 [!code-cs[cscsrefQueryKeywords#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_7.cs)]  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, wie zusätzliche Logik auf die Gruppen ausgeführt wird, nachdem Sie diese erstellt haben, indem eine *Fortsetzung* mit `into` verwendet wird. Weitere Informationen finden Sie unter [into](../../../csharp/language-reference/keywords/into.md). Das folgende Beispiel fragt jede Gruppe ab, wobei nur die Gruppe ausgewählt werden soll, dessen Schlüsselwert ein Vokal ist.  
  
 [!code-cs[cscsrefQueryKeywords#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_8.cs)]  
  
## <a name="remarks"></a>Hinweise  
 `group`-Klauseln werden zur Kompilierzeit in Aufrufe der <xref:System.Linq.Enumerable.GroupBy%2A>-Methode übersetzt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.IGrouping%602>   
 <xref:System.Linq.Enumerable.GroupBy%2A>   
 <xref:System.Linq.Enumerable.ThenBy%2A>   
 <xref:System.Linq.Enumerable.ThenByDescending%2A>   
 [Abfrageschlüsselwörter (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Vorgehensweise: Erstellen einer geschachtelten Gruppe](../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)   
 [Vorgehensweise: Gruppieren von Abfrageergebnissen](../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)   
 [Gewusst wie: Ausführen einer Unterabfrage für eine Gruppierungsoperation](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)

