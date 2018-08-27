---
title: dynamic (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- dynamic_CSharpKeyword
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
ms.openlocfilehash: bddcb8890ef7312047d05794ccef0b638de4ed78
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930250"
---
# <a name="dynamic-c-reference"></a>dynamic (C#-Referenz)

Der `dynamic`-Typ ermöglicht die Vorgänge, in denen er auftritt, um die Typüberprüfung zur Kompilierzeit zu umgehen. Stattdessen werden diese Vorgänge zur Laufzeit aufgelöst. Der `dynamic`-Typ vereinfacht den Zugriff auf COM-APIs, z.B. die Office Automation-APIs, und auch auf dynamische APIs, beispielsweise IronPython-Bibliotheken und auf das HTML-Dokumentobjektmodell (Document Object Model, DOM).

Der Typ `dynamic` verhält sich in den meisten Fällen wie Typ `object`. Jedoch werden Vorgänge, die Ausdrücke des Typs `dynamic` enthalten, nicht aufgelöst oder durch den Compiler typgeprüft. Der Compiler packt Informationen über den Vorgang. Diese Informationen werden später zur Evaluierung des Vorgangs zur Laufzeit verwendet. Als Teil dieses Prozesses werden Variablen des Typs `dynamic` in Variablen des Typs `object` kompiliert. Deshalb existiert der Typ `dynamic` nur zur Kompilierzeit und nicht zur Laufzeit.

Das folgende Beispiel vergleicht den Unterschied einer Variable des Typs `dynamic` mit einer Variable des Typs `object`. Um den Typ jeder Variable zur Kompilierzeit zu überprüfen, zeigen Sie mit dem Mauszeiger auf `dyn` oder `obj` in den `WriteLine`-Anweisungen. IntelliSense zeigt **dynamic** für `dyn` und **object** für `obj`.

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

Die `WriteLine`-Anweisungen zeigen die Laufzeittypen von `dyn` und `obj`. Zu diesem Zeitpunkt verfügen beide denselben Typ, Integer. Es wird die folgende Ausgabe generiert:

`System.Int32`

`System.Int32`

Um den Unterschied zwischen `dyn` und `obj` zur Kompilierzeit anzuzeigen, fügen Sie die folgenden zwei Zeilen zwischen die Deklarationen und die `WriteLine`-Anweisungen im vorherigen Beispiel ein.

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 Es wird ein Kompilierfehler für den Versuch, einen Integer und ein Objekt im Ausdruck `obj + 3` einzufügen, ausgegeben. Es wird jedoch kein Fehler für `dyn + 3` gemeldet. Der Ausdruck, der `dyn` enthält, wird nicht zur Kompilierzeit überprüft, da der Typ von `dyn` `dynamic` ist.

## <a name="context"></a>Kontext

Das Schlüsselwort `dynamic` kann direkt oder als Komponente eines konstruierten Typs in den folgenden Situationen erscheinen:

- In Deklarationen, als Typ einer Eigenschaft, als Feld, Indexer, Parameter, Rückgabewert, lokale Variable oder Typeinschränkung. Die folgende Klassendefinition verwendet `dynamic` in einigen unterschiedlichen Deklarationen.

    [!code-csharp[csrefKeywordsTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#22)]

- In expliziten Typkonvertierungen als Zieltyp einer Konversion.

    [!code-csharp[csrefKeywordsTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#23)]

- In jedem Kontext, in dem Typen als Werte, z.B. auf der rechten Seite eines `is`-Operators oder eines `as`-Operators oder als Argument für `typeof` als Teil eines konstruierten Typs dienen. Zum Beispiel kann `dynamic` in den folgenden Ausdrücken verwendet werden.

    [!code-csharp[csrefKeywordsTypes#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#24)]

## <a name="example"></a>Beispiel

Das folgende Beispiel verwendet `dynamic` in einigen Deklarationen. Die `Main`-Methode unterscheidet auch die Typüberprüfung zur Kompilierzeit und die Laufzeittypüberprüfung.

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

Weitere Informationen und Beispiele finden Sie unter [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Dynamic.ExpandoObject?displayProperty=nameWithType>  
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>  
- [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md)  
- [object](../../../csharp/language-reference/keywords/object.md)  
- [is](../../../csharp/language-reference/keywords/is.md)  
- [as](../../../csharp/language-reference/keywords/as.md)  
- [typeof](../../../csharp/language-reference/keywords/typeof.md)  
- [Gewusst wie: Sichere Umwandlung mit den Operatoren "as" und "is"](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)  
- [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
