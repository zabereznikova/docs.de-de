---
title: Verwenden von Indexern – C#-Programmierhandbuch
ms.date: 10/03/2018
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: 17162a0dc959a85c03a5cb5757e2b91fe10b0ab3
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628162"
---
# <a name="using-indexers-c-programming-guide"></a>Verwenden von Indexern (C#-Programmierhandbuch)

Indexer sind ein syntaktisches Hilfsmittel, um Ihnen die Erstellung einer [Klasse](../../language-reference/keywords/class.md), einer [Struktur](../../language-reference/builtin-types/struct.md), oder einer [Schnittstelle](../../language-reference/keywords/interface.md) zu ermöglichen, auf die Clientanwendungen wie auf ein Array zugreifen können. Indexer werden am häufigsten in Typen implementiert, deren Hauptzweck darin besteht, eine interne Auflistung oder ein Array zu kapseln. Ein Beispiel: Sie verfügen über eine Klasse namens `TempRecord` zur Darstellung der Temperatur in Fahrenheit zu 10 verschiedenen Zeitpunkten während eines 24-stündigen Zeitraums. Die Klasse enthält das Array `temps` des Typs `float[]`, um die Temperaturwerte zu speichern. Durch die Implementierung eines Indexers in dieser Klasse können Clients auf die Temperaturen in einer `TempRecord`-Instanz als `float temp = tr[4]` zugreifen, statt als `float temp = tr.temps[4]`. Die Angabe des Indexers vereinfacht nicht nur die Syntax für Clientanwendungen; die Klasse und Ihr Zweck können außerdem intuitiver von anderen Entwicklern verstanden werden.  
  
Um einen Indexer in einer Klasse oder Struktur zu deklarieren, verwenden Sie das [this](../../language-reference/keywords/this.md) -Schlüsselwort, wie im folgenden Beispiel gezeigt:

```csharp
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
```

## <a name="remarks"></a>Hinweise

Der Typ eines Indexers und der Typ seiner Parameter müssen zumindest dieselben Zugriffsmöglichkeiten bieten wie der Indexer selbst. Weitere Informationen zu den Zugriffsebenen finden Sie unter [Zugriffsmodifizierer](../../language-reference/keywords/access-modifiers.md).  
  
 Weitere Informationen zum Verwenden von Indexern mit einer Schnittstelle finden Sie unter [Schnittstellenindexer](./indexers-in-interfaces.md).  
  
 Die Signatur eines Indexers besteht aus der Anzahl und den Typen seiner formalen Parameter. Sie umfasst weder den Indexertyp noch die Namen der formalen Parameter. Wenn Sie mehrere Indexer in derselben Klasse deklarieren, müssen sie verschiedene Signaturen aufweisen.  
  
 Ein Indexerwert wird nicht als Variable klassifiziert. Aus diesem Grund können Sie keinen Indexerwert als [Ref](../../language-reference/keywords/ref.md)- oder [out](../../language-reference/keywords/out-parameter-modifier.md)-Parameter übergeben.  
  
 Um für den Indexer einen Namen anzugeben, den andere Sprachen verwenden können, verwenden Sie <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, wie im folgenden Beispiel gezeigt:  

```csharp
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this[int index]   // Indexer declaration  
{
    // get and set accessors  
}  
```

Dieser Indexer hat den Namen `TheItem`. Wird kein Namensattribut bereitgestellt, wird `Item` zum Standardnamen.  
  
## <a name="example-1"></a>Beispiel 1  
  
Im folgenden Beispiel wird die Deklaration eines öffentlichen Arrayfelds, `temps`, und eines Indexers dargestellt. Der Indexer ermöglicht den direkten Zugriff auf die Instanz `tempRecord[i]`. Als Alternative zur Verwendung des Indexers, kann das Array als [öffentliches](../../language-reference/keywords/public.md) Mitglied deklariert und direkt auf dessen Mitglieder, `tempRecord.temps[i]`, zugegriffen werden.  
  
 Beachten Sie, dass, wenn der Zugriff eines Indexers, z.B. in einer `Console.Write`-Anweisung ausgewertet wird, der [get](../../language-reference/keywords/get.md)-Accessor aufgerufen wird. Wenn kein `get`-Accessor vorhanden ist, tritt deshalb ein Kompilierzeitfehler auf.  
  
 [!code-csharp[csProgGuideIndexers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#1)]  
  
## <a name="indexing-using-other-values"></a>Indizieren mit anderen Werten

C# beschränkt den Indexer-Parametertyp nicht auf Integer. Beispielsweise kann es sinnvoll sein, eine Zeichenfolge mit einem Indexer zu verwenden. Ein solcher Indexer kann implementiert werden, indem die Zeichenfolge in der Auflistung gesucht und der richtige Wert zurückgegeben wird. Da Accessoren überladen werden können, können die Zeichenfolge- und die Integer-Version zusammen verwendet werden.  
  
## <a name="example-2"></a>Beispiel 2  
  
Das folgende Beispiel deklariert eine Klasse, die die Wochentage speichert. Ein `get`-Accessor akzeptiert eine Zeichenfolge – den Namen eines Tages – und gibt den entsprechenden Integer-Wert zurück. „Sunday“ gibt beispielsweise 0 zurück, „Monday“ 1 usw.  
  
 [!code-csharp[csProgGuideIndexers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#2)]  
  
## <a name="robust-programming"></a>Stabile Programmierung

 Es gibt zwei grundlegende Möglichkeiten, mit denen die Sicherheit und die Zuverlässigkeit von Indexern verbessert werden kann:  
  
- Integrieren Sie irgendeine Form von Fehlerbehandlungsstrategie, für den Fall, dass Clientcode in einem ungültigen Indexwert übergeben wird. Im ersten Beispiel weiter oben in diesem Thema stellt die TempRecord-Klasse eine Length-Eigenschaft bereit, die dem Clientcode ermöglicht, die Eingabe vor der Übergabe an den Indexer zu überprüfen. Sie können den Fehlerbehandlungscode auch in den Indexer selbst einfügen. Achten Sie darauf alle Ausnahmen, die Sie innerhalb eines Indexeraccessors auslösen, für Benutzer zu dokumentieren.  
  
- Schränken Sie den Zugriff auf die [get](../../language-reference/keywords/get.md)- und [set](../../language-reference/keywords/set.md)-Accessors so weit wie möglich ein. Dies ist insbesondere wichtig für den `set`-Accessor. Weitere Informationen finden Sie unter [Einschränken des Accessorzugriffs](../classes-and-structs/restricting-accessor-accessibility.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Indexer](./index.md)
- [Eigenschaften](../classes-and-structs/properties.md)
