---
title: Benannte und optionale Argumente – C#-Programmierhandbuch
description: Benannte Argumente in C# geben Argumente nach Name und nicht nach Position an. Optionale Argumente können ausgelassen werden.
ms.date: 09/25/2020
ms.custom: contperfq1
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
ms.openlocfilehash: a0606d6acccb47347c663a9fe3ffb8ab65b0ecec
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438011"
---
# <a name="named-and-optional-arguments-c-programming-guide"></a>Benannte und optionale Argumente (C#-Programmierhandbuch)

C# 4 führt benannte und optionale Argumente ein. Mithilfe von *benannten Argumenten* können Sie ein Argument für einen Parameter angeben, indem Sie das Argument mit dem Namen des Parameters anstatt mit seiner Position in der Parameterliste abgleichen. *Optionale Argumente* ermöglichen es Ihnen, Argumente für einige Parameter auszulassen. Beide Techniken können mit Methoden, Indexern, Konstruktoren und Delegaten verwendet werden.

Wenn Sie benannte und optionale Argumente verwenden, werden die Argumente in der Reihenfolge ausgewertet, in der sie in der Argumentliste, nicht in der Parameterliste, erscheinen.

Mit benannten und optionalen Parametern können Sie Argumente für ausgewählte Parameter bereitstellen. Diese Funktion erleichtert den Zugriff auf COM-Schnittstellen wie etwa die Automation-APIs in Microsoft Office erheblich.

## <a name="named-arguments"></a>Benannte Argumente

Bei Verwendung benannter Argumente bleibt es Ihnen erspart, die Reihenfolge von Parametern in den Parameterlisten von aufgerufenen Methoden abzugleichen. Der Parameter für jedes Argument kann vom Parameternamen angegeben werden. Eine Funktion, die beispielsweise Details zu einer Bestellung ausgibt (z. B. Verkäufername, Bestellnummer und Produktname), kann aufgerufen werden, indem anhand der Position Argumente in der Reihenfolge gesendet werden, die von der Funktion definiert wurde.

```csharp
PrintOrderDetails("Gift Shop", 31, "Red Mug");
```

Wenn Sie sich nicht an die Reihenfolge der Parameter erinnern, aber deren Namen kennen, können Sie die Argumente in einer beliebigen Reihenfolge senden.

```csharp
PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");
PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);
```

Benannte Argumente verbessern auch die Lesbarkeit des Codes, indem sie identifizieren, was jedes Argument darstellt. In der folgenden Beispielmethode darf `sellerName` nicht NULL sein oder Leerzeichen enthalten. Da es sich bei `sellerName` und `productName` um Zeichenfolgentypen handelt, sollten Sie benannte Argumente verwenden, anstatt Argumente nach Position zu senden, um die beiden Parameter zu unterscheiden und die Leser des Codes nicht zu verwirren.
  
Benannte Argumente sind länger gültig, wenn sie mit positionellen Argumenten verwendet werden, da

- ihnen keine positionellen Argumente folgen, bzw. da

    ```csharp
    PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");
    ```

- sie _ab C# 7.2_ in der richtigen Position verwendet werden. Im folgenden Beispiel befindet sich der Parameter `orderNum` in der richtigen Position, ist jedoch nicht explizit benannt.

    ```csharp
    PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");
    ```

Positionelle Argumente, die auf fehlerhafte benannte Argumente folgen, sind ungültig.

```csharp
// This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
```

## <a name="example"></a>Beispiel

Der folgende Code implementiert die Beispiele in diesem Abschnitt sowie einige zusätzliche Beispiele.  

[!code-csharp[csProgGuideNamedAndOptional#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/program.cs#1)]

## <a name="optional-arguments"></a>Optionale Argumente

Die Definition einer Methode, eines Konstruktors, eines Indexers oder eines Delegaten kann angeben, dass deren Parameter benötigt werden oder optional sind. Jeder Aufruf muss Argumente für alle benötigten Parameter bereitstellen, kann aber Argumente für optionale Parameter auslassen.

Jeder optionale Parameter hat einen Standardwert als Teil seiner Definition. Wenn für diesen Parameter kein Argument gesendet wird, wird der Standardwert verwendet. Ein Standardwert muss einer der folgenden Typen von Ausdrücken sein:
  
- Ein konstanter Ausdruck  
- Ein Ausdruck der Form `new ValType()`, wobei `ValType` ein Werttyp wie [enum](../../language-reference/builtin-types/enum.md) oder [struct](../../language-reference/builtin-types/struct.md) ist
- Ein Ausdruck in Form von [default(ValType)](../../language-reference/operators/default.md), wobei `ValType` ein Werttyp ist

Optionale Parameter werden am Ende der Parameterliste nach den erforderlichen Parametern definiert. Wenn der Aufrufer ein Argument für einen beliebigen Parameter aus einer Folge von optionalen Parametern bereitstellt, muss er Argumente für alle vorherigen optionalen Parameter bereitstellen. Durch Trennzeichen getrennte Lücken in der Argumentliste werden nicht unterstützt. Im folgenden Code wird z.B. die Instanzmethode `ExampleMethod` mit einem erforderlichen und zwei optionalen Parametern definiert.

[!code-csharp[csProgGuideNamedAndOptional#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#15)]

Der folgende Aufruf von `ExampleMethod` verursacht einen Compilerfehler, da ein Argument für den dritten Parameter, aber nicht für den zweiten, bereitgestellt wird.

```csharp
//anExample.ExampleMethod(3, ,4);
```

Wenn Sie den Namen des dritten Parameters kennen, können Sie ein benanntes Argument zum Ausführen der Aufgabe verwenden.

```csharp
anExample.ExampleMethod(3, optionalint: 4);
```

IntelliSense verwendet wie in der folgenden Abbildung gezeigt zum Anzeigen von optionalen Parametern Klammern:

![Screenshot der IntelliSense-QuickInfo für die Methode „ExampleMethod“](./media/named-and-optional-arguments/optional-examplemethod-parameters.png)

> [!NOTE]
> Sie können auch optionale Parameter mit der .NET-Klasse <xref:System.Runtime.InteropServices.OptionalAttribute> deklarieren. `OptionalAttribute`-Parameter erfordern keinen Standardwert.

## <a name="example"></a>Beispiel

Im folgenden Beispiel hat der Konstruktor für `ExampleClass` einen Parameter, der optional ist. Instanzmethode `ExampleMethod` hat einen erforderlichen Parameter (`required`) und zwei optionale Parameter (`optionalstr` und `optionalint`). Der Code in `Main` veranschaulicht die unterschiedlichen Methoden, in denen der Konstruktor und die Methode aufgerufen werden können.

[!code-csharp[csProgGuideNamedAndOptional#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#2)]

Der obige Code zeigt eine Reihe von Beispielen, in denen optionale Parameter nicht ordnungsgemäß angewendet werden. Das erste Beispiel veranschaulicht, dass für den ersten Parameter, der erforderlich ist, ein Argument angegeben werden muss.
  
## <a name="com-interfaces"></a>COM-Schnittstellen

Benannte und optionale Argumente verbessern zusammen mit der Unterstützung von dynamischen Objekten deutlich die Interoperabilität mit COM-APIs wie Office Automation-APIs.

Beispielsweise verfügt die Methode <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> in der <xref:Microsoft.Office.Interop.Excel.Range>-Schnittstelle von Microsoft Office Excel über sieben Parameter, von denen alle optional sind. Diese Parameter sind in der folgenden Abbildung dargestellt:

![Screenshot der IntelliSense-QuickInfo für die Methode „AutoFormat“](./media/named-and-optional-arguments/autoformat-method-parameters.png)

In C# 3.0 und früheren Versionen wird ein Argument für jeden Parameter benötigt, wie im folgenden Beispiel gezeigt wird.

[!code-csharp[csProgGuideNamedAndOptional#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#3)]

Sie können jedoch den Aufruf an `AutoFormat` erheblich vereinfachen, indem Sie benannte und optionale Argumente verwenden, die in C# 4.0 eingeführt wurden. Benannte und optionale Parameter helfen Ihnen dabei, das Argument für einen optionalen Parameter auszulassen, wenn Sie den Standardwert des Parameters nicht ändern möchten. Im folgenden Aufruf wird ein Wert für nur einen der sieben Parameter angegeben.

[!code-csharp[csProgGuideNamedAndOptional#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#13)]

Weitere Informationen und Beispiele finden Sie unter [Vorgehensweise: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung](./how-to-use-named-and-optional-arguments-in-office-programming.md) und [Vorgehensweise: Zugreifen auf Office Interop-Objekte mithilfe von C#-Funktionen](../interop/how-to-access-office-onterop-objects.md).
  
## <a name="overload-resolution"></a>Overload Resolution

Das Verwenden von benannten und optionalen Argumenten wirkt sich auf die Überladungsauflösung folgendermaßen aus:

- Eine Methode, ein Indexer oder ein Konstruktor ist ein Kandidat für die Ausführung, wenn jeder der Parameter entweder optional ist oder über Namen oder Position auf ein einzelnes Argument in der aufrufenden Anweisung reagiert. Dieses Argument kann in dem Typ des Parameters konvertiert werden.  
- Wenn mehr als ein Kandidat gefunden wird, werden die Regeln der Überladungsauflösung als bevorzugte Konvertierungen auf die Argumente angewandt, die ausdrücklich angegeben sind. Ausgelassene Argumente für optionale Parameter werden ignoriert.
- Wenn zwei Kandidaten gleich gut geeignet sind, wird ein Kandidat bevorzugt, der keine optionalen Parameter besitzt, für die Argumente im Aufruf ausgelassen wurden. Bei der Überladungsauflösung werden normalerweise Kandidaten mit weniger Parametern bevorzugt.
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
