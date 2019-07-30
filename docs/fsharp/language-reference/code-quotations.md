---
title: Zitieren von Code
description: Erfahren Sie mehr über F# Codezitate, eine Sprachfunktion, die Ihnen zum Generieren von und arbeiten programmgesteuert mit F#-Codeausdrücken ermöglicht.
ms.date: 05/16/2016
ms.openlocfilehash: c6ec0078c685a6452f49edd289b01491dd62e3db
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630415"
---
# <a name="code-quotations"></a>Zitieren von Code

> [!NOTE]
> Mit dem API-Referenz-Link gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

In diesem Thema werden *Code Zitate*beschrieben, eine Sprachfunktion, die es Ihnen ermöglicht, F# Code Ausdrücke Programm gesteuert zu generieren und mit Ihnen zu arbeiten. Diese Funktion ermöglicht es Ihnen, eine abstrakte Syntax Struktur zu F# generieren, die Code darstellt. Die abstrakte Syntax Struktur kann dann nach den Anforderungen Ihrer Anwendung durchlaufen und verarbeitet werden. Beispielsweise können Sie die-Struktur verwenden, um F# Code zu generieren oder Code in einer anderen Sprache zu generieren.

## <a name="quoted-expressions"></a>Ausdrücke in Anführungszeichen

Ein *Ausdruck* in Anführungszeichen F# ist ein Ausdruck im Code, der so begrenzt ist, dass er nicht als Teil des Programms kompiliert wird, sondern in ein Objekt kompiliert wird, das einen F# Ausdruck darstellt. Sie können einen Ausdruck in Anführungszeichen auf eine von zwei Arten markieren: entweder mit Typinformationen oder ohne Typinformationen. Wenn Sie Typinformationen einschließen möchten, verwenden Sie die Symbole `<@` und `@>` , um den Ausdruck in Anführungszeichen zu begrenzen. Wenn Sie keine Typinformationen benötigen, verwenden Sie die Symbole `<@@` und. `@@>` Der folgende Code zeigt typisierte und nicht typisierte Anführungszeichen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

Das Durchlaufen eines großen Ausdrucks Baums ist schneller, wenn Sie keine Typinformationen einschließen. Der resultierende Typ eines Ausdrucks, der mit den typisierten Symbolen `Expr<'T>`angegeben wird, ist, wobei der Typparameter den Typ des Ausdrucks hat, F# der vom Typrückschluss Algorithmus des Compilers bestimmt wird. Wenn Sie Code Anführungszeichen ohne Typinformationen verwenden, handelt es sich bei dem Typ des Ausdrucks in Anführungszeichen um den nicht generischen Typ [expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65). Sie können die [RAW](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) -Eigenschaft für die typisierte `Expr` Klasse aufzurufen, um das nicht typisierte `Expr` Objekt zu erhalten.

Es gibt eine Reihe von statischen Methoden, die es Ihnen ermöglichen F# , Ausdrucks Objekte Programm gesteuert in `Expr` der-Klasse zu generieren, ohne Ausdrücke in Anführungszeichen zu verwenden.

Beachten Sie, dass ein Code Zitat einen Complete-Ausdruck enthalten muss. Für eine `let` Bindung benötigen Sie z. b. sowohl die Definition des gebundenen namens als auch einen zusätzlichen Ausdruck, der die Bindung verwendet. In der ausführlichen Syntax ist dies ein Ausdruck, der auf das `in` -Schlüsselwort folgt. Auf der obersten Ebene eines Moduls ist dies nur der nächste Ausdruck im Modul, aber in einem Anführungszeichen ist es explizit erforderlich.

Daher ist der folgende Ausdruck ungültig.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

Die folgenden Ausdrücke sind jedoch gültig.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

Zum Auswerten F# von Anführungszeichen müssen Sie die [ F# Anführungs](https://github.com/fsprojects/FSharp.Quotations.Evaluator)Zeichen Auswertung verwenden. Sie bietet Unterstützung für das Auswerten F# und Ausführen von Ausdrucks Objekten.

## <a name="expr-type"></a>Expr-Typ

Eine Instanz von der `Expr` Typ stellt ein F#-Ausdrucks dar. Sowohl die generischen als auch die nicht `Expr` generischen Typen sind in F# der Bibliotheksdokumentation dokumentiert. Weitere Informationen finden Sie unter [Microsoft. FSharp. notinamespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) und [Noti. expr Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).

## <a name="splicing-operators"></a>Splicing-Operatoren

Durch das Splicing können Sie literalcode-Anführungszeichen mit Ausdrücken kombinieren, die Sie Programm gesteuert erstellt haben, oder aus einem anderen Code Anführungszeichen. Mit `%` den `%%` Operatoren und können Sie einem F# Code Anführungszeichen ein Ausdrucks Objekt hinzufügen. Sie verwenden den `%` -Operator, um ein typisiertes Ausdrucks Objekt in ein typisiertes Anführungszeichen `%%` einzufügen. Sie verwenden den-Operator, um ein nicht typisiertes Expression-Objekt in ein nicht typisiertes Anführungszeichen einzufügen. Beide Operatoren sind unäre Präfix Operatoren. Wenn `expr` daher ein nicht typisierter Ausdruck vom Typ `Expr`ist, ist der folgende Code gültig.

```fsharp
<@@ 1 + %%expr @@>
```

Wenn `expr` ein typisiertes Anführungszeichen vom Typ `Expr<int>`ist, ist der folgende Code gültig.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Beispiel veranschaulicht die Verwendung von Zitieren von Code zum F#-Code in ein Datenquellenausdrucks-Objekt und klicken Sie dann die F#-Code, der den Ausdruck darstellt, zu drucken. Eine Funktion `println` ist definiert, die eine rekursive `print` Funktion enthält, F# die ein Ausdrucks Objekt ( `Expr`vom Typ) in einem benutzerfreundlichen Format anzeigt. Es gibt mehrere aktive Muster in den Modulen " [Microsoft. FSharp. Noti. Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) " und " [Microsoft. FSharp. Noti. DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) ", die zum Analysieren von Ausdrucks Objekten verwendet werden können. In diesem Beispiel sind nicht alle möglichen Muster enthalten, die in einem F# Ausdruck vorkommen können. Alle nicht erkannten Muster lösen eine Entsprechung für das Platz`_`Halter Muster () aus und werden `ToString` mithilfe der-Methode gerendert, die auf dem `Expr` -Typ das aktive Muster kennt, das Sie dem Match-Ausdruck hinzufügen können.

### <a name="code"></a>Code

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a>Output

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Sie können auch die drei aktiven Muster im [ExprShape-Modul](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) verwenden, um Ausdrucks Baumstrukturen mit weniger aktiven Mustern zu durchlaufen. Diese aktiven Muster können nützlich sein, wenn Sie eine Struktur durchlaufen möchten, Sie jedoch nicht alle Informationen in den meisten Knoten benötigen. Wenn Sie diese Muster verwenden, alle F#-Ausdruck entspricht einem der folgenden drei Muster: `ShapeVar` ist der Ausdruck einer Variablen, `ShapeLambda` der Ausdruck ist ein Lambda-Ausdruck oder `ShapeCombination` nichts ist der Ausdruck. Wenn Sie eine Ausdrucksbaumstruktur durchlaufen, indem Sie die aktive Muster wie im vorherigen Codebeispiel, müssen Sie viele weitere Muster verwenden, um alle möglichen F# Ausdruckstypen verarbeiten, und Code komplexer sein wird. Weitere Informationen finden Sie unter " [ExprShape. shapevar&#124;shapelambda&#124;shapekombination aktives Muster](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d)".

Das folgende Codebeispiel kann als Grundlage für komplexere Traversale verwendet werden. In diesem Code wird eine Ausdrucks Baumstruktur für einen Ausdruck erstellt, der einen Funktions aufzurufen `add`,, umfasst. Mit dem aktiven [specificcall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) -Muster wird ein beliebiger Aufrufe `add` von in der Ausdrucks Baumstruktur erkannt. Dieses aktive Muster weist die Argumente des Aufrufes dem `exprList` -Wert zu. In diesem Fall gibt es nur zwei, sodass diese abgerufen werden und die Funktion rekursiv für die Argumente aufgerufen wird. Die Ergebnisse werden in ein Code Zitat eingefügt, das einen-aufrufbefehl `mul` mithilfe des Splice-Operators (`%%`) darstellt. Die `println` Funktion aus dem vorherigen Beispiel wird verwendet, um die Ergebnisse anzuzeigen.

Der Code in den anderen aktiven Muster Verzweigungen generiert einfach dieselbe Ausdrucks Baumstruktur, sodass die einzige Änderung im resultierenden Ausdruck die Änderung von `add` in `mul`ist.

### <a name="code"></a>Code

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a>Output

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
