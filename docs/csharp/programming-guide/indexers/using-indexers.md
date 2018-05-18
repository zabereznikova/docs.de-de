---
title: Verwenden von Indexern (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: 82de2841a74f58905d3089bb0b320e7501a77045
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-indexers-c-programming-guide"></a>Verwenden von Indexern (C#-Programmierhandbuch)
Indexer sind ein syntaktisches Hilfsmittel, um Ihnen die Erstellung einer [Klasse](../../../csharp/language-reference/keywords/class.md), einer [Struktur](../../../csharp/language-reference/keywords/struct.md), oder einer [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) zu ermöglichen, auf die Clientanwendungen wie auf ein Array zugreifen können. Indexer werden am häufigsten in Typen implementiert, deren Hauptzweck darin besteht, eine interne Auflistung oder ein Array zu kapseln. Angenommen Sie verfügen über eine Klasse mit dem Namen .TempRecord, zur Darstellung der Temperatur in Fahrenheit zu 10 verschiedenen Zeitpunkten während eines 24-stündigen Zeitraums. Die Klasse enthält ein Array mit dem Namen "Temps" vom "float"-Datentyp, um die Temperaturen darzustellen, und einen <xref:System.DateTime>, der das Datum darstellt, an welchem die Temperaturen erfasst wurden. Durch die Implementierung eines Indexers in dieser Klasse, können Clients auf die Temperaturen in einer TempRecord-Instanz als `float temp = tr[4]` zugreifen, statt als `float temp = tr.temps[4]`. Die Angabe des Indexers vereinfacht nicht nur die Syntax für Clientanwendungen; die Klasse und Ihr Zweck können außerdem intuitiver von anderen Entwicklern verstanden werden.  
  
 Um einen Indexer auf eine Klasse oder Struktur zu deklarieren, verwenden Sie das [this](../../../csharp/language-reference/keywords/this.md) -Schlüsselwort, wie im folgenden Beispiel:  
  
```  
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Typ eines Indexers und der Typ seiner Parameter müssen zumindest dieselben Zugriffsmöglichkeiten bieten wie der Indexer selbst. Weitere Informationen zu den Zugriffsebenen finden Sie unter [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 Weitere Informationen zum Verwenden von Indexern mit einer Schnittstelle finden Sie unter [Schnittstellenindexer](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md).  
  
 Die Signatur eines Indexers besteht aus der Anzahl und den Typen seiner formalen Parameter. Sie umfasst nicht den Indexertyp oder die Namen der formalen Parameter. Wenn Sie mehrere Indexer in derselben Klasse deklarieren, müssen sie verschiedene Signaturen aufweisen.  
  
 Ein Indexerwert wird nicht als Variable klassifiziert. Aus diesem Grund können Sie keinen Indexerwert als [Ref](../../../csharp/language-reference/keywords/ref.md)- oder [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)-Parameter übergeben.  
  
 Um dem Indexer einen Namen zu geben, den andere Sprachen verwenden können, verwenden Sie ein `name`-Attribut in der Deklaration. Zum Beispiel:  
  
```  
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this [int index]   // Indexer declaration  
{  
}  
```  
  
 Dieser Indexer hat den Namen `TheItem`. Wird kein Namensattribut bereitgestellt, wird `Item` zum Standardnamen.  
  
## <a name="example-1"></a>Beispiel 1  
  
### <a name="description"></a>description  
 Im folgenden Beispiel wird die Deklaration eines öffentlichen Arrayfelds, `temps`, und eines Indexers dargestellt. Der Indexer ermöglicht den direkten Zugriff auf die Instanz `tempRecord[i]`. Als Alternative zur Verwendung des Indexers, kann das Array als [öffentliches](../../../csharp/language-reference/keywords/public.md) Mitglied deklariert und direkt auf dessen Mitglieder, `tempRecord.temps[i]`, zugegriffen werden.  
  
 Beachten Sie, dass, wenn der Zugriff eines Indexers, z.B. in einer `Console.Write`-Anweisung ausgewertet wird, der [get](../../../csharp/language-reference/keywords/get.md)-Accessor aufgerufen wird. Wenn kein `get`-Accessor vorhanden ist, tritt deshalb ein Kompilierzeitfehler auf.  
  
### <a name="code"></a>Code  
 [!code-csharp[csProgGuideIndexers#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_1.cs)]  
  
## <a name="indexing-using-other-values"></a>Indizieren mit anderen Werten  
 C# beschränkt den Typ des Indexes nicht auf Integer. Beispielsweise kann es sinnvoll sein, eine Zeichenfolge mit einem Indexer zu verwenden. Ein solcher Indexer kann implementiert werden, indem die Zeichenfolge in der Auflistung gesucht und der richtige Wert zurückgegeben wird. Da Accessoren überladen werden können, können die Zeichenfolge- und die Integer-Version zusammen verwendet werden.  
  
## <a name="example-2"></a>Beispiel 2  
  
### <a name="description"></a>description  
 In diesem Beispiel wird eine Klasse deklariert, die die Wochentage speichert. Ein `get`-Accessor wird deklariert, der eine Zeichenfolge und den Namen eines Tages annimmt, und den entsprechenden Integer zurückgibt. Z.B. gibt Sonntag 0 zurück, Montag gibt 1 zurück, usw.  
  
### <a name="code"></a>Code  
 [!code-csharp[csProgGuideIndexers#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_2.cs)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Es gibt zwei grundlegende Möglichkeiten, mit denen die Sicherheit und die Zuverlässigkeit von Indexern verbessert werden kann:  
  
-   Integrieren Sie irgendeine Form von Fehlerbehandlungsstrategie, für den Fall, dass Clientcode in einem ungültigen Indexwert übergeben wird. Im ersten Beispiel weiter oben in diesem Thema stellt die TempRecord-Klasse eine Length-Eigenschaft bereit, die dem Clientcode ermöglicht, die Eingabe vor der Übergabe an den Indexer zu überprüfen. Sie können den Fehlerbehandlungscode auch in den Indexer selbst einfügen. Achten Sie darauf alle Ausnahmen, die Sie innerhalb eines Indexeraccessors auslösen, für Benutzer zu dokumentieren.  
  
-   Schränken Sie den Zugriff auf den `get`- und [set](../../../csharp/language-reference/keywords/set.md)-Accessor so ein, dass die Beschränkung angemessen ist. Dies ist insbesondere wichtig für den `set`-Accessor. Weitere Informationen finden Sie unter [Einschränken des Accessorzugriffs](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Indexer](../../../csharp/programming-guide/indexers/index.md)  
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)
