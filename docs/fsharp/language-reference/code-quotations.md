---
title: Zitieren von Code (F#)
description: Erfahren Sie mehr über f# Zitieren von Code, eine Sprachfunktion, die zum Generieren von und Arbeiten mit f#-Code-Ausdrücke programmgesteuert ermöglicht.
ms.date: 05/16/2016
ms.openlocfilehash: a6fab0364cadef1f45276267a59c694140b24a9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564533"
---
# <a name="code-quotations"></a>Zitieren von Code

> [!NOTE]
Mit dem API-Referenz-Link gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

In diesem Thema wird beschrieben, *Codezitate*, eine Sprachfunktion, die zum Generieren von und Arbeiten mit f#-Code-Ausdrücke programmgesteuert ermöglicht. Mit diesem Feature können Sie eine abstrakte Syntaxstruktur zu generieren, die f#-Code darstellt. Die abstrakte Syntaxstruktur kann durchlaufen und entsprechend den Anforderungen der Anwendung verarbeitet werden. Beispielsweise können Sie die Struktur zum Generieren von f#-Code oder Code in einer anderen Sprache zu generieren.


## <a name="quoted-expressions"></a>Ausdrücke in Anführungszeichen
Ein *in Anführungszeichen Ausdruck* ist ein Ausdruck F#-Code, der begrenzt wird, auf eine Weise, dass er nicht als Teil des Programms kompiliert wird, sondern stattdessen in ein Objekt, das einen f#-Ausdruck darstellt. Sie können einen Ausdruck in Anführungszeichen in zweierlei kennzeichnen: entweder mit oder ohne Typinformationen. Wenn Sie Typinformationen einschließen möchten, verwenden Sie die Symbole `<@` und `@>` auf den zitierten Ausdruck. Wenn Sie Typinformationen nicht benötigen, verwenden Sie die Symbole `<@@` und `@@>`. Der folgende Code zeigt, typisierte und nicht typisierte angeboten wird.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

Durchlaufen einer großen Ausdrucksbaumstruktur ist schneller, wenn Sie keine Typinformationen enthalten. Der resultierende Typ eines Ausdrucks mit den typisierten Symbolen in Anführungszeichen ist `Expr<'T>`, in dem der Typparameter den Typ des Ausdrucks wie vom f#-Compiler den Typ mithilfe eines Rückschlusses Algorithmus bestimmt wurde. Bei Verwendung von Zitieren von Code ohne Typinformationen ist der Typ des zitierten Ausdrucks die nichtgenerischen Typ [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65). Sie erreichen die [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) Eigenschaft für die typisierte `Expr` Klasse zum Abrufen der nicht typisierte `Expr` Objekt.

Es gibt eine Vielzahl von statischen Methoden, die Ihnen ermöglichen, Generieren von F#-Ausdrucksobjekte programmgesteuert in die `Expr` Klasse ohne zitierte Ausdrücke.

Beachten Sie, dass eine codequotation einen vollständigen Ausdruck enthalten muss. Für eine `let` binden, z. B. benötigen Sie sowohl die Definition der gebundenen Namens und einen zusätzlichen Ausdruck, der Bindung verwendet. In ausführlicher Syntax ist dies ein Ausdruck, der folgt die `in` Schlüsselwort. Auf der obersten Ebene in einem Modul Dies ist nur für den nächsten Ausdruck im Modul, aber in ein Zitat es unbedingt erforderlich ist.

Der folgende Ausdruck ist daher ungültig.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

Die folgenden Ausdrücke sind jedoch gültig.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

Zum Zitieren von Code verwenden zu können, müssen Sie eine Importdeklaration hinzufügen (mithilfe der `open` Schlüsselwort), öffnet der [Microsoft.FSharp.Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2) Namespace.

F#-PowerPack bietet Unterstützung für auszuwerten und f#-Ausdrucksobjekte auszuführen.


## <a name="expr-type"></a>Expr-Typ
Eine Instanz von der `Expr` Typ einen f#-Ausdruck darstellt. Der generische und nicht-generische `Expr` Typen sind in der F#-Bibliothek-Dokumentation dokumentiert. Weitere Informationen finden Sie unter [Microsoft.FSharp.Quotations-Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) und [Quotations.Expr-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).


## <a name="splicing-operators"></a>Wird beim Splicing von Operatoren
Splicing ermöglicht es Ihnen, literale Codezitate mit Ausdrücken kombinieren, die Sie programmgesteuert oder über eine andere codequotation erstellt haben. Die `%` und `%%` Operatoren ermöglichen es Ihnen, ein F#-Ausdrucksobjekt ein Codezitat hinzuzufügen. Verwenden Sie die `%` Operator zum Einfügen einer typisierten Ausdruck-Objekts in ein typisiertes Zitat; Sie verwenden die `%%` Operator, um eine nicht typisierte Expression-Objekt in eine nicht typisierte Anführungszeichen eingefügt. Beide Operatoren sind unäre Präfixoperatoren. Also wenn `expr` ist ein nicht typisierter Ausdruck des Typs `Expr`, der folgende Code ist ungültig.

```fsharp
<@@ 1 + %%expr @@>
```

Und wenn `expr` ist eine typisierte Angebot des Typs `Expr<int>`, der folgende Code ist ungültig.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung
Das folgende Beispiel veranschaulicht die Verwendung von Zitieren von Code f#-Code in einem Expression-Objekt und drucken Sie anschließend die f#-Code, der den Ausdruck darstellt. Eine Funktion `println` definiert ist, enthält eine rekursive Funktion `print` , die ein f#-Ausdrucksobjekt anzeigt (des Typs `Expr`) in einem benutzerfreundlichen Format. Es gibt mehrere aktive Muster in den [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) und [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) Module, die zum Analysieren von Ausdrucksobjekten verwendet werden können. Dieses Beispiel umfasst nicht alle möglichen Muster, die angezeigt werden in einem f#-Ausdruck. Jedes nicht erkannte Muster löst eine Übereinstimmung mit dem Platzhaltermuster (`_`) und gerendert wird, indem Sie die `ToString` Methode, die auf die `Expr` eingeben, können Sie wissen, dass die aktive Muster, um Ihre Vergleichsausdruck hinzufügen.


### <a name="code"></a>Code
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet601.fs)]
    
### <a name="output"></a>Ausgabe

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung
Sie können auch die drei aktive Muster in den [ExprShape-Modul](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) um Ausdrucksbaumstrukturen mit weniger aktiven Mustern zu durchlaufen. Diese mit aktiven Mustern können nützlich sein, wenn Durchlaufen einer Struktur verwendet werden sollen, aber nicht alle Informationen in den meisten Knoten erforderlich. Wenn Sie diese Muster verwenden, alle f#-Ausdruck übereinstimmt, eines der folgenden drei Muster: `ShapeVar` , wenn der Ausdruck eine Variable ist `ShapeLambda` ist der Ausdruck einen Lambda-Ausdruck oder `ShapeCombination` , wenn der Ausdruck etwas anderes ist. Wenn Sie mithilfe der aktive Muster wie im vorherigen Codebeispiel eine Ausdrucksbaumstruktur zu durchlaufen, müssen Sie viele weitere Muster verwenden, um alle möglichen f# Ausdruckstypen zu behandeln, und wird der Code komplexer sein. Weitere Informationen finden Sie unter [ExprShape.ShapeVar&#124;ShapeLambda&#124;aktives ShapeCombination-Muster](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).

Das folgende Codebeispiel kann als Grundlage für komplexere Durchläufe verwendet werden. In diesem Code wird eine Ausdrucksbaumstruktur für einen Ausdruck, der einen Funktionsaufruf umfasst erstellt `add`. Die [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) aktives Muster dient zum Erkennen von jeder Aufruf von `add` in der Ausdrucksbaumstruktur. Dieses aktive Muster weist die Argumenten des Aufrufs an die `exprList` Wert. In diesem Fall fallen nur zwei, sodass diese herausziehen und die Funktion ist für die Argumente rekursiv aufgerufen. Die Ergebnisse werden in einer codequotation, die einen Aufruf darstellt eingefügt `mul` mithilfe des Operators Splice (`%%`). Die `println` Funktion aus dem vorherigen Beispiel wird verwendet, um die Ergebnisse anzuzeigen.

Der Code in anderen Verzweigungen aktives Muster generiert nur die gleichen Ausdrucksbaumstruktur, daher ist die einzige Änderung in der sich ergebenden Ausdrucks die Änderung von `add` auf `mul`.


### <a name="code"></a>Code
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]
    
### <a name="output"></a>Ausgabe

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

