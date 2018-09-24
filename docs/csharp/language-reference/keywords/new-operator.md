---
title: new-Operator (C#-Referenz)
ms.date: 03/15/2018
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 362217b247bd2ab7a2eec2f86cbaaf1a0652a3ad
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2018
ms.locfileid: "46706475"
---
# <a name="new-operator-c-reference"></a>new-Operator (C#-Referenz)

Wird zum Erstellen von Objekten und zum Aufrufen von Konstruktoren verwendet. Zum Beispiel:

```csharp
Class1 obj  = new Class1();
```

Er wird auch verwendet, um Instanzen von anonymen Typen zu erstellen:

```csharp
var query = from cust in customers
            select new { Name = cust.Name, Address = cust.PrimaryAddress };
```

Der `new`-Operator wird auch verwendet, um den Standardkonstruktor für Werttypen aufzurufen. Zum Beispiel:

```csharp
int i = new int();
```

In der vorherigen Anweisung wird `i` auf `0` initialisiert, dem Standardwert für den `int`-Typ. Die Anweisung hat den gleichen Effekt wie die Folgende:

```csharp
int i = 0;
```

Eine vollständige Liste der Standardwerte finden Sie in der [Tabelle für Standardwerte](default-values-table.md).

Beachten Sie, dass das Deklarieren eines Standardkonstruktors für eine [Struktur](struct.md) ein Fehler ist, da jeder Werttyp implizit einen öffentlichen Standardkonstruktor besitzt. Es ist möglich, parametrisierte Konstruktoren auf einem Strukturtyp zu deklarieren, um seine Standardwerte festzulegen. Dies ist aber nur notwendig, wenn andere Werte als der Standardwert erforderlich sind.

Werttypobjekte wie Strukturen und Verweistypobjekte wie Klassen werden automatisch zerstört. Werttypobjekte werden jedoch zerstört, wenn der sie enthaltende Kontext zerstört wird, während Verweistypobjekte zu einem unbestimmten Zeitpunkt nach dem Entfernen der letzten Verweise auf diese Dateien durch die Garbage Collection zerstört werden. Bei Typen, die Ressourcen wie Dateihandles oder Netzwerkverbindungen enthalten, ist eine deterministische Bereinigung empfehlenswert, um sicherzustellen, dass die darin enthaltenen Ressourcen so bald wie möglich freigegeben werden. Weitere Informationen finden Sie unter [using-Anweisung](using-statement.md).

Operator `new` kann nicht überladen werden.

Wenn der `new`-Operator bei der Zuweisung von Arbeitsspeicher scheitert, löst er die Ausnahme <xref:System.OutOfMemoryException> aus.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden ein `struct`-Objekt und ein Klassenobjekt mithilfe des `new`-Operators erstellt und initialisiert. Anschließend werden ihnen Werte zugewiesen. Die Standardwerte und die zugewiesenen Werte werden angezeigt.

[!code-csharp[csrefKeywordsOperator#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#7)]

Beachten Sie im Beispiel, dass der Standardwert einer Zeichenfolge `null` ist. Daher wird er nicht angezeigt.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../language-reference/index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Operatorschlüsselwörter](operator-keywords.md)
- [new](new.md)
- [Anonyme Typen](../../programming-guide/classes-and-structs/anonymous-types.md)