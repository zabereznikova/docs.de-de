---
title: Zitieren von Code
description: Erfahren Sie mehr über F# Codezitate, eine Sprachfunktion, die Ihnen zum Generieren von und arbeiten programmgesteuert mit F#-Codeausdrücken ermöglicht.
ms.date: 05/16/2016
ms.openlocfilehash: 464df5e3fafa683c93fd5fb6e94d24c229903491
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642003"
---
# <a name="code-quotations"></a>Zitieren von Code

> [!NOTE]
> Mit dem API-Referenz-Link gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

In diesem Thema wird beschrieben, *Codezitate*, eine Sprachfunktion, mit der Sie zum Generieren von und Arbeiten mit F# Ausdrücke programmgesteuert zu codieren. Dieses Feature ermöglicht Ihnen das Generieren von einer abstrakten Syntaxstruktur, die darstellt F# Code. Die abstrakte Syntaxstruktur kann dann durchlaufen und gemäß den Anforderungen Ihrer Anwendung verarbeitet werden. Beispielsweise können Sie die Struktur zum generieren F# code oder Generieren von Code in einer anderen Sprache.

## <a name="quoted-expressions"></a>Zitierte Ausdrücke

Ein *in Anführungszeichen Ausdruck* ist ein F# Ausdrucks im Code, der getrennt wird, so, dass es nicht als Teil des Programms kompiliert wird, sondern stattdessen in ein Objekt, das darstellt ein F# Ausdruck. Sie können einen Ausdruck in Anführungszeichen in eine von zwei Arten kennzeichnen: entweder mit oder ohne Typinformationen. Wenn Sie Typinformationen einschließen möchten, verwenden Sie die Symbole `<@` und `@>` zitierten Ausdrucks zu trennen. Wenn Sie Typinformationen nicht benötigen, verwenden Sie die Symbole `<@@` und `@@>`. Der folgende Code zeigt die typisierte und nicht typisierte Angebote.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

Durchlaufen einer Ausdrucksbaumstruktur zu großen ist schneller, wenn Sie keine Typinformationen einschließen. Der resultierende Typ eines Ausdrucks für die typisierte Symbole in Anführungszeichen ist `Expr<'T>`, in dem der Typparameter den Typ des Ausdrucks gemäß hat die F# Algorithmus Typrückschluss des Compilers, Typ. Wenn Sie Zitieren von Code ohne Typinformationen verwenden, ist der Typ des zitierten Ausdrucks der nicht generischen Typ [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65). Rufen Sie die [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) Eigenschaft für die typisierte `Expr` Klasse, die nicht typisierte erhalten `Expr` Objekt.

Es gibt eine Vielzahl von statischen Methoden, die zum generieren F# Ausdruck Objekte programmgesteuert in die `Expr` Klasse ohne zitierte Ausdrücke.

Beachten Sie, dass ein Code-Angebot einen vollständigen Ausdruck enthalten muss. Für eine `let` Bindung, beispielsweise benötigen Sie sowohl die Definition der gebundenen Namens und einen zusätzlichen Ausdruck, der die Bindung verwendet. In ausführlicher Syntax ist dies ein Ausdruck, der `in` Schlüsselwort. Auf der obersten Ebene in einem Modul Dies ist nur des nächsten Ausdrucks in das Modul, aber in einem Angebot, es unbedingt erforderlich ist.

Aus diesem Grund ist der folgende Ausdruck ungültig.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

Die folgenden Ausdrücke sind jedoch gültig.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

Zum Zitieren von Code verwenden zu können, müssen Sie eine Importdeklaration hinzufügen (mithilfe der `open` Schlüsselwort), öffnet der [Microsoft.FSharp.Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2) Namespace.

Die F# PowerPack bietet Unterstützung für die Auswertung und Ausführung F# Ausdrucksobjekte.

## <a name="expr-type"></a>Expr-Typ

Eine Instanz von der `Expr` Typ stellt ein F#-Ausdrucks dar. Der generische und nicht generischen `Expr` Typen werden in dokumentiert die F# Bibliotheksdokumentation. Weitere Informationen finden Sie unter [Microsoft.FSharp.Quotations-Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) und [Quotations.Expr-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).

## <a name="splicing-operators"></a>Wird beim Splicing von Operatoren

Einfügen, können Sie literale Codezitate mit Ausdrücken kombinieren, die Sie programmgesteuert oder aus einem anderen Code-Angebot erstellt haben. Die `%` und `%%` Operatoren ermöglichen es Ihnen, Hinzufügen einer F# Datenquellenausdrucks-Objekt in ein Code-Angebot. Sie verwenden die `%` Operator zum Einfügen von einem typisierten Datenquellenausdrucks-Objekt in ein typisiertes Zitat; Sie verwenden die `%%` Operator, um eine nicht typisierte Datenquellenausdrucks-Objekt in eine nicht typisierte Anführungszeichen einfügen. Beide Operatoren sind Unäroperatoren-Präfix. Also wenn `expr` ist ein nicht typisierter Ausdruck vom Typ `Expr`, der folgende Code ist ungültig.

```fsharp
<@@ 1 + %%expr @@>
```

Und wenn `expr` ist ein typisiertes Zitat des Typs `Expr<int>`, der folgende Code ist ungültig.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Beispiel veranschaulicht die Verwendung von Zitieren von Code zum F#-Code in ein Datenquellenausdrucks-Objekt und klicken Sie dann die F#-Code, der den Ausdruck darstellt, zu drucken. Eine Funktion `println` definiert ist, die eine rekursive Funktion enthält `print` angezeigt, die ein F# Datenquellenausdrucks-Objekt (des Typs `Expr`) in einem freundlichen Format. Es gibt mehrere aktive Muster in den [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) und [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) Module, die zum Ausdrucksobjekten verwendet werden können. In diesem Beispiel enthält keine alle Muster, die in angezeigt werden, können ein F# Ausdruck. Eine nicht erkannte Muster löst eine Übereinstimmung mit dem Platzhaltermuster (`_`) und gerendert wird, indem Sie die `ToString` Methode, das auf die `Expr` eingeben, können Sie das aktive Muster der Match-Ausdruck hinzu.

### <a name="code"></a>Code

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a>Output

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Sie können auch die drei aktive Muster in den [ExprShape-Modul](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) um Ausdrucksbaumstrukturen mit weniger aktive Muster zu durchlaufen. Diese aktive Muster können hilfreich sein, wenn Sie eine Struktur zu durchlaufen möchten, aber alle Informationen in den meisten der Knoten ist nicht erforderlich. Wenn Sie diese Muster verwenden, alle F#-Ausdruck entspricht einem der folgenden drei Muster: `ShapeVar` ist der Ausdruck einer Variablen, `ShapeLambda` der Ausdruck ist ein Lambda-Ausdruck oder `ShapeCombination` nichts ist der Ausdruck. Wenn Sie eine Ausdrucksbaumstruktur durchlaufen, indem Sie die aktive Muster wie im vorherigen Codebeispiel, müssen Sie viele weitere Muster verwenden, um alle möglichen F# Ausdruckstypen verarbeiten, und Code komplexer sein wird. Weitere Informationen finden Sie unter [ExprShape.ShapeVar&#124;ShapeLambda&#124;aktives ShapeCombination-Muster](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).

Im folgenden Codebeispiel wird als Grundlage für komplexere Durchläufe dienen. In diesem Code wird eine Ausdrucksbaumstruktur erstellt wird, für einen Ausdruck, der einen Funktionsaufruf umfasst `add`. Die [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) aktives Muster verwendet, um jeden Aufruf von erkennen `add` in der Ausdrucksbaumstruktur. Dieses aktive Muster weist die Argumente des Aufrufs an die `exprList` Wert. In diesem Fall stehen nur zwei, damit diese abgerufen werden, und die Funktion rekursiv, auf den Argumenten aufgerufen wird. Die Ergebnisse werden in einem Code-Angebot, die einen Aufruf darstellt eingefügt `mul` mithilfe des Operators für die Einfügung (`%%`). Die `println` Funktion aus dem vorherigen Beispiel wird verwendet, um die Ergebnisse anzuzeigen.

Der Code in anderen Verzweigungen aktives Muster wird nur die gleichen Ausdrucksbaumstruktur generiert, ist die einzige Änderung in der sich ergebenden Ausdrucks die Änderung von `add` zu `mul`.

### <a name="code"></a>Code

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a>Output

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
