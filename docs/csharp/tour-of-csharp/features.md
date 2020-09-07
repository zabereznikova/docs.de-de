---
title: 'Einführung in C#: Wichtige Sprachbereiche'
description: Neu bei C#? Lernen Sie die Grundlagen der Sprache kennen.
ms.date: 08/06/2020
ms.openlocfilehash: e1e533982757c10085f0444197ff97ee7487391f
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414902"
---
# <a name="major-language-areas"></a>Wichtige Sprachbereiche

## <a name="arrays-collections-and-linq"></a>Arrays, Sammlungen und LINQ

C# und .NET stellen viele verschiedene Sammlungstypen bereit. Die Syntax von Arrays wird von der Sprache definiert. Generische Sammlungstypen werden im Namespace <xref:System.Collections.Generic?displayProperty=fullName> aufgeführt. Spezialisierte Sammlungen umfassen <xref:System.Span%601?displayProperty=nameWithType> für den Zugriff auf kontinuierlichen Arbeitsspeicher im Stapelrahmen und <xref:System.Memory%601?displayProperty=nameWithType> für den Zugriff auf kontinuierlichen Arbeitsspeicher im verwalteten Heap. Alle Sammlungen, einschließlich Arrays, <xref:System.Span%601> und <xref:System.Memory%601> teilen ein vereinheitlichendes Prinzip für die Iteration. Sie verwenden die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Dieses vereinheitlichende Prinzip bedeutet, dass alle Sammlungstypen mit LINQ-Abfragen oder anderen Algorithmen verwendet werden können. Diese Methoden schreiben Sie mit <xref:System.Collections.Generic.IEnumerable%601>, und die Algorithmen funktionieren mit allen Sammlungen.

### <a name="arrays"></a>Arrays

Ein [***Array***](../programming-guide/arrays/index.md) ist eine Datenstruktur, die eine Anzahl von Variablen enthält, auf die über berechnete Indizes zugegriffen wird. Die in einem Array enthaltenen Variablen, die auch als ***Elemente*** des Arrays bezeichnet werden, weisen alle denselben Typ auf. Dieser Typ wird als ***Elementtyp*** des Arrays bezeichnet.

Arraytypen sind Verweistypen, und die Deklaration einer Arrayvariablen reserviert Speicher für einen Verweis auf eine Arrayinstanz. Die tatsächlichen Arrayinstanzen werden unter Verwendung des `new`-Operators zur Laufzeit dynamisch erstellt. Der `new`-Vorgang legt die ***Länge*** der neuen Arrayinstanz fest, die dann für die Lebensdauer der Instanz beibehalten wird. Die Indizes der Arrayelemente reichen von `0` bis `Length - 1`. Der `new`-Operator initialisiert die Elemente eines Arrays automatisch mit ihren Standardwerten. Dieser lautet z.B. für alle numerischen Typen 0 und für alle Verweistypen `null`.

Im folgenden Beispiel wird ein Array aus `int`-Elementen erstellt. Anschließend wird das Array initialisiert und die Inhalte des Arrays werden gedruckt.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="ArraysSample":::

Mit diesem Beispiel wird ein ***eindimensionales Array*** erstellt und verwendet. C# unterstützt auch ***mehrdimensionale Arrays***. Die Anzahl von Dimensionen eines Arraytyps, auch als ***Rang*** des Arraytyps bezeichnet, ist 1 plus die Anzahl von Kommas, die innerhalb der eckigen Klammern des Arraytyps angegeben ist. Mit dem folgenden Beispiel wird respektive ein eindimensionales, ein zweidimensionales und ein dreidimensionales Array erstellt.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="DeclareArrays":::

Das `a1`-Array enthält 10 Elemente, das `a2`-Array umfasst 50 (10 × 5) Elemente, und das `a3`-Array enthält 100 (10 × 5 × 2) Elemente.
Ein Array kann einen beliebigen Elementtyp verwenden, einschließlich eines Arraytyps.  Ein Array mit Elementen eines Arraytyps wird auch als ***Jagged Array*** bezeichnet, weil die Länge der Elementarrays nicht identisch sein muss. Im folgenden Beispiel wird ein Array aus `int`-Arrays zugewiesen:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="ArrayOfArrays":::

In der ersten Zeile wird ein Array mit drei Elementen erstellt, das jeweils den Typ `int[]` und einen Anfangswert von `null` aufweist. In den nachfolgenden Zeilen werden die drei Elemente mit Verweisen auf einzelne Arrayinstanzen unterschiedlicher Länge initialisiert.

Der `new`-Operator erlaubt es, die Anfangswerte der Arrayelemente unter Verwendung eines ***Arrayinitialisierers*** anzugeben, bei dem es sich um eine Liste von Ausdrücken zwischen den Trennzeichen `{` und `}` handelt. Mit dem folgenden Beispiel wird ein `int[]` mit drei Elementen zugewiesen und initialisiert.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="InitializeArray":::

Die Länge des Arrays wird von der Anzahl der Ausdrücke zwischen `{` und `}` abgeleitet. Deklarationen lokaler Variablen und Felder können weiter verkürzt werden, sodass der Arraytyp nicht erneut aufgeführt werden muss.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="InitializeShortened":::

Die zwei vorherigen Beispiele entsprechen dem folgenden Code:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="InitializeGenerated":::

Die `foreach`-Anweisung kann für die Enumeration der Elemente von beliebigen Sammlungen verwendet werden. Mit dem folgenden Code wird das Array aus dem vorherigen Beispiel aufgezählt:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="EnumerateArray":::

Die `foreach`-Anweisung nutzt die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle und kann daher mit jeder Sammlung funktionieren.

## <a name="string-interpolation"></a>Zeichenfolgeninterpolierung

Die [***Zeichenfolgeninterpolation***](../language-reference/tokens/interpolated.md) von C# ermöglicht Ihnen das Formatieren von Zeichenfolgen durch Definieren von Ausdrücken, deren Ergebnisse in eine Formatzeichenfolge platziert werden. Im folgenden Beispiel wird die Temperatur für einen jeweiligen Tag aus Wetterdaten ausgegeben:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="StringInterpolation":::

Eine interpolierte Zeichenfolge wird mithilfe des `$`-Tokens deklariert. Die Zeichenfolgeninterpolation wertet die Ausdrücke zwischen `{` und `}` aus, konvertiert das Ergebnis in `string` und ersetzt den Text zwischen den Klammern durch das Zeichenfolgenergebnis des Ausdrucks. Mit `:` im ersten Ausdruck gibt `{weatherData.Date:MM-DD-YYYY}` die *Formatzeichenfolge* an. Im obigen Beispiel wird festgelegt, dass das Datum im Format „MM-TT-JJJJ“ ausgegeben werden soll.

## <a name="pattern-matching"></a>Musterabgleich

Die C#-Sprache stellt [***Musterabgleichsausdrücke***](../pattern-matching.md) bereit, um den Zustand eines Objekts abzufragen und Code auf Grundlage dieses Zustands auszuführen. Sie können Typen und Werte von Eigenschaften und Feldern untersuchen, um zu bestimmen, welche Aktion ausgeführt werden soll. Der `switch`-Ausdruck ist der primäre Ausdruck für den Musterabgleich.

## <a name="delegates-and-lambda-expressions"></a>Delegate und Lambdaausdrücke

Ein [***Delegattyp***](../delegates-overview.md) stellt Verweise auf Methoden mit einer bestimmten Parameterliste und dem Rückgabetyp dar. Delegate ermöglichen die Behandlung von Methoden als Entitäten, die Variablen zugewiesen und als Parameter übergeben werden können. Delegaten ähneln konzeptionell Funktionszeigern, die es in einigen anderen Sprachen gibt. Im Gegensatz zu Funktionszeigern sind Delegaten objektorientiert und typsicher.

Im folgenden Beispiel wird ein Delegattyp namens `Function` deklariert und verwendet.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="DelegateExample":::

Eine Instanz des Delegattyps `Function` kann auf jede Methode verweisen, die ein `double`-Argument und einen `double`-Wert akzeptiert. Die `Apply`-Methode wendet eine jeweilige `Function` (Funktion) auf die Elemente einer `double[]`-Methode an. Mit den Ergebnissen wird eine `double[]`-Methode zurückgegeben. In der `Main`-Methode wird `Apply` verwendet, um drei verschiedene Funktionen auf ein `double[]` anzuwenden.

Ein Delegat kann entweder auf eine statische Methode verweisen (z.B. `Square` oder `Math.Sin` im vorherigen Beispiel) oder eine Instanzmethode (z.B. `m.Multiply` im vorherigen Beispiel). Ein Delegat, der auf eine Instanzmethode verweist, verweist auch auf ein bestimmtes Objekt, und wenn die Instanzmethode durch den Delegaten aufgerufen wird, wird das Objekt `this` im Aufruf.

Delegaten können auch mithilfe anonymer Funktionen erstellt werden, bei denen es sich um „Inlinemethoden“ handelt, die bei der Deklaration erstellt werden. Anonyme Funktionen können die lokalen Variablen der umgebenden Methoden sehen. Im folgenden Beispiel wird keine Klasse erstellt:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="UseDelegate":::

Ein Delegat weiß nicht und interessiert sich nicht dafür, welche Klasse der Methode er referenziert. Wichtig ist nur, dass die referenzierte Methode über dieselben Parameter und denselben Rückgabetyp wie der Delegat verfügt.

## <a name="async--await"></a>async/await

C# unterstützt asynchrone Programme mit zwei Schlüsselwörtern: `async` und `await`. Sie fügen den `async`-Modifizierer zu einer Methodendeklaration hinzu, um zu deklarieren, dass die Methode asynchron ist. Der `await`-Operator weist den Compiler an, asynchron auf den Ergebnis zu warten. Die Kontrolle wird wieder dem Aufrufer überlassen, und die Methode gibt eine Struktur zurück, die den Zustand der asynchronen Arbeitet verwaltet. In der Regel handelt es sich um eine <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>-Struktur, es kann jedoch ein beliebiger Typ vorliegen, der das await-Muster unterstützt. Diese Features ermöglichen Ihnen das Schreiben von Code, der sich wie das synchrone Gegenstück liest, aber asynchron ausgeführt wird. Mit dem folgenden Code wird beispielsweise die Homepage für die [Microsoft-Dokumentation](https://docs.microsoft.com) heruntergeladen:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="AsyncExample":::

In diesem kleinen Beispiel werden die wichtigsten Features für die asynchrone Programmierung veranschaulicht:

- Die Methodendeklaration enthält den Modifizierer `async`.
- Der Text der Methode `await` enthält die Rückgabe der `GetByteArrayAsync`-Methode.
- Der in der `return`-Anweisung angegebene Typ stimmt mit dem Typargument in der `Task<T>`-Deklaration für die Methode überein. (Eine Methode, die ein `Task` zurückgibt, würde `return`-Anweisungen ohne Argumente verwenden.)

## <a name="attributes"></a>Attributes

Typen, Member und andere Entitäten in einem C#-Programm unterstützen Modifizierer, die bestimmte Aspekte ihres Verhaltens steuern. Der Zugriff auf eine Methode wird beispielsweise mithilfe der Modifizierer `public`, `protected`, `internal` und `private` kontrolliert. C# generalisiert diese Funktionalität, indem benutzerdefinierte Typen deklarativer Informationen an eine Programmentität angefügt und zur Laufzeit abgerufen werden können. Programme geben diese zusätzlichen deklarativen Informationen durch das Definieren und Verwenden von [***Attributen***](../programming-guide/concepts/attributes/index.md) an.

Im folgenden Beispiel wird ein `HelpAttribute`-Attribut deklariert, dass in Programmentitäten platziert werden kann, um Links zur zugehörigen Dokumentation bereitzustellen.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="DefineAttribute":::

Alle Attributklassen werden von der Basisklasse <xref:System.Attribute> abgeleitet, die von der .NET-Bibliothek bereitgestellt wird. Attribute können durch Angabe ihres Namens angewendet werden, zusammen mit beliebigen Argumenten. Diese müssen in eckigen Klammern genau vor der zugehörigen Deklaration eingefügt werden. Wenn ein Attributname auf `Attribute` endet, kann dieser Teil des Namens beim Verweis auf das Attribut weggelassen werden. Beispielsweise kann `HelpAttribute` wie folgt verwendet werden.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="UseAttributes":::

In diesem Beispiel wird `HelpAttribute` an die `Widget`-Klasse angefügt. Darüber hinaus wird der `Display`-Methode in der Klasse ein weiteres `HelpAttribute` hinzugefügt. Die öffentlichen Konstruktoren einer Attributklasse steuern die Informationen, die beim Anfügen des Attributs an eine Programmentität angegeben werden müssen. Zusätzliche Informationen können angegeben werden, indem auf öffentliche Eigenschaften mit Lese-/Schreibzugriff der Attributklasse verwiesen wird (z.B. wie der obige Verweis auf die `Topic`-Eigenschaft).

Die durch Attribute definierten Metadaten können zur Laufzeit mittels Reflektion gelesen und bearbeitet werden. Wenn mithilfe dieser Technik ein bestimmtes Attribut angefordert wird, wird der Konstruktor für die Attributklasse mit den in der Programmquelle angegebenen Informationen aufgerufen, und die resultierende Attributinstanz wird zurückgegeben. Wenn zusätzliche Informationen über Eigenschaften bereitgestellt wurden, werden diese Eigenschaften auf die vorgegebenen Werte festgelegt, bevor die Attributinstanz zurückgegeben wird.

Das folgende Codebeispiel zeigt, wie die der `Widget`-Klasse zugeordneten `HelpAttribute`-Instanzen und die dazugehörige `Display`-Methode abgerufen wird.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="ReadAttributes":::

## <a name="learn-more"></a>Erfahren Sie mehr

Weitere Informationen über C# finden Sie in den [Tutorials](../tutorials/index.md).

>[!div class="step-by-step"]
>[Zurück](program-building-blocks.md)
