---
title: Eigenschaften (F#)
description: Informationen Sie zu F#-Eigenschaften, die Elemente sind, die einem Objekt zugeordneten Werte darstellen.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 98b363a5-ee6a-4b7b-b8ae-b244f2a0b316
ms.openlocfilehash: 53b93b20310c557ad9c30226bc08f85cbf2f3010
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="properties"></a>Eigenschaften

*Eigenschaften* angehören, die einem Objekt zugeordneten Werte darstellen.


## <a name="syntax"></a>Syntax

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a>Hinweise
Eigenschaften stellen die "hat eine" Beziehung in einer objektorientierten Programmierung darstellen von Daten, die mit der Objekt-Instanzen oder für statische Eigenschaften, mit dem Typ zugeordnet ist.

Sie können Deklarieren von Eigenschaften in zwei Möglichkeiten, je nachdem, ob Sie den zugrunde liegenden Wert (auch als "Sicherungsspeicher" bezeichnet) für die Eigenschaft explizit angeben möchten oder wenn den Compiler den Sicherungsspeicher für Sie automatisch generiert werden sollen. Im Allgemeinen sollten Sie die expliziter-Methode, wenn die Eigenschaft eine nicht triviale Implementierung hat und die automatische Methode verwenden, wenn die Eigenschaft nur einen einfachen Wrapper für einen Wert oder eine Variable ist. Um eine Eigenschaft explizit zu deklarieren, verwenden die `member` Schlüsselwort. Diese deklarative Syntax wird gefolgt von der Syntax, der angibt, die `get` und `set` Methoden, die auch als *Accessoren*. Für Lese-/Schreibzugriff, schreibgeschützte und lesegeschützte Eigenschaften werden die verschiedenen Formen von explicit-Syntax im Syntaxabschnitt gezeigt verwendet. Für schreibgeschützte Eigenschaften definieren Sie nur eine `get` Methode für nur-schreiben Eigenschaften definieren Sie nur eine `set` Methode. Beachten Sie, dass, wenn eine Eigenschaft sowohl hat `get` und `set` Accessoren, die alternative Syntax können Sie angeben, Attribute und Zugriffsmodifizierer, die für jeden Accessor unterschiedlich, wie im folgenden Code gezeigt wird.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

Für Lese-/Schreibeigenschaften, die beide verfügen über eine `get` und `set` -Methode, die Reihenfolge der `get` und `set` können rückgängig gemacht werden kann. Alternativ können Sie die Syntax für bereitstellen `get` nur und die Syntax für `set` nur anstelle der kombinierten Syntax. Dies macht es einfacher, kommentieren Sie die einzelnen `get` oder `set` -Methode, wenn etwas ist Sie möglicherweise erforderlich. Diese Alternative zum Verwenden der kombinierten Syntax wird im folgenden Code dargestellt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

Private Werte, die Daten für Eigenschaften heißen, Aufbewahrungspflicht *Sicherungsspeicher*. Damit den Compiler den Sicherungsspeicher automatisch zu erstellen, verwenden Sie die Schlüsselwörter `member val`, lassen Sie die Self-Bezeichner, und geben Sie einen Ausdruck, um die Eigenschaft zu initialisieren. Wenn die Eigenschaft auf änderbare werden, enthalten `with get, set`. Beispielsweise enthält die folgenden Klassentyp zwei automatisch implementierte Eigenschaften. `Property1`ist schreibgeschützt und wird an das Argument bereitgestellt, um den primären Konstruktor initialisiert und `Property2` eine festlegbare Eigenschaft auf eine leere Zeichenfolge initialisiert wird:

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

Automatisch implementierte Eigenschaften sind Teil die Initialisierung eines Typs aus, damit sie ebenso wie vor anderen Memberdefinitionen enthalten sein müssen `let` Bindungen und `do` Bindungen in einer Typdefinition. Beachten Sie, dass der Ausdruck, der eine automatisch implementierte Eigenschaft initialisiert nur ausgewertet wird, bei der Initialisierung und nicht jedes Mal, wenn die Eigenschaft zugegriffen wird. Dieses Verhalten ist im Gegensatz zu das Verhalten einer explizit implementierte Eigenschaft. Was dies bedeutet, die der Code zum Initialisieren dieser Eigenschaften ist, wird an den Konstruktor der Klasse hinzugefügt. Betrachten Sie den folgenden Code, der diesen Unterschied verdeutlicht:

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
```

**Ausgabe**

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

Die Ausgabe des vorhergehenden Codes zeigt, dass der Wert des AutoProperty unverändert bei wird wiederholt aufgerufen, während die ExplicitProperty jedes Mal ändert, wenn er aufgerufen wird. Dadurch wird bewiesen, dass der Ausdruck für eine automatisch implementierte Eigenschaft nicht in jedem Fall ausgewertet wird, wie die Gettermethode für die explizite-Eigenschaft ist.


>[!WARNING]
Es gibt einige Bibliotheken, wie das Entity Framework (`System.Data.Entity`) führen Sie benutzerdefinierte Operationen, die in den Konstruktoren, die auch bei der Initialisierung von automatisch implementierten Eigenschaften nicht unterstützt. Verwenden Sie in diesen Fällen explizite Eigenschaften.

Eigenschaften können Mitglieder der Klassen, Strukturen, Unterscheidungs-Unions, Datensätze, Schnittstellen und typerweiterungen sein und können auch im Objektausdrücke definiert werden.

Attribute können auf Eigenschaften angewendet werden. Um ein Attribut auf eine Eigenschaft anwenden möchten, Schreiben Sie das Attribut in einer separaten Zeile vor der Eigenschaft. Weitere Informationen finden Sie unter [Attribute](../attributes.md).

Standardmäßig sind die Eigenschaften öffentlich. Eigenschaften können auch Zugriffsmodifizierer angewendet werden. Zum Anwenden eines Zugriffsmodifizierers hinzufügen unmittelbar vor dem Namen der Eigenschaft vorgesehen ist, gelten für beide die `get` und `set` Methoden; fügen Sie ihn ein, bevor die `get` und `set` Schlüsselwörter, wenn unterschiedliche zugriffsmöglichkeiten ist für jeden Accessor erforderlich. Die *Zugriffsmodifizierer* kann eines der folgenden sein: `public`, `private`, `internal`. Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-control.md).

Eigenschaft Implementierungen werden jedes Mal ausgeführt, wenn eine Eigenschaft zugegriffen wird.


## <a name="static-and-instance-properties"></a>Statische und Instanzeigenschaften
Eigenschaften können statisch sein oder Instanzeigenschaften. Statische Eigenschaften können ohne Instanz aufgerufen werden und dienen zur Werte, die dem Typ, nicht für einzelne Objekte zugeordnet. Lassen Sie für statische Eigenschaften den Self-Bezeichner. Der Self-Bezeichner ist für Instanzeigenschaften erforderlich.

Die folgende Definition für die statische Eigenschaft basiert auf ein Szenario, in dem Sie ein statisches Feld `myStaticValue` also der Sicherungsspeicher für die Eigenschaft.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

Eigenschaften können auch sein arrayähnlichen, in diesem Fall werden sie aufgerufen *indizierte Eigenschaften*. Weitere Informationen finden Sie unter [indizierten Eigenschaften](indexed-properties.md).


## <a name="type-annotation-for-properties"></a>Typanmerkung für Eigenschaften
In vielen Fällen wird der Compiler verfügt über genügend Informationen, um den Typ einer Eigenschaft vom Typ des Sicherungsspeichers abgeleitet werden, aber Sie können den Typ explizit festlegen, indem eine typanmerkung hinzufügen.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a>Set-Accessoren mit der Eigenschaft
Einstellbaren Eigenschaften bereit `set` Accessoren mithilfe der `<-` Operator.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

Die Ausgabe lautet **20**.


## <a name="abstract-properties"></a>Abstrakte Eigenschaften
Eigenschaften können abstrakt sein. Wie bei Methoden, `abstract` bedeutet lediglich, dass ein virtueller Dispatch der Eigenschaft zugeordnet ist. Abstrakte Eigenschaften können tatsächlich abstrakt ist, d. h. ohne Definition in der gleichen Klasse sein. Die Klasse enthält eine solche Eigenschaft ist daher eine abstrakte Klasse. Alternativ kann nur abstrakte bedeuten, dass eine Eigenschaft virtuell ist und in diesem Fall muss eine Definition in der gleichen Klasse vorhanden sein. Beachten Sie, dass abstrakte Eigenschaften nicht privat sein, wenn ein Accessor abstrakt ist, der andere auch muss sein abstrakt. Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a>Siehe auch
[Mitglieder](index.md)

[Methoden](methods.md)
