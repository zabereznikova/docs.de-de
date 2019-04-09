---
title: Eigenschaften
description: Erfahren Sie mehr über F# Eigenschaften, die Mitglieder sind, die einem Objekt zugeordneten Werte darstellen.
ms.date: 05/16/2016
ms.openlocfilehash: bf605ee1135bd3b3561bde9a8ae66353497931b0
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675691"
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

Eigenschaften stellen die "verfügt über eine" Beziehung in der objektorientierten Programmierung datendarstellung, die Objektinstanzen oder, für statische Eigenschaften, mit dem Typ zugeordnet ist.

Sie können deklarieren, Eigenschaften, die auf zwei Arten, abhängig davon, ob Sie explizit den zugrunde liegenden Wert (auch als "Sicherungsspeicher" bezeichnet) für die Eigenschaft angeben möchten oder wenn den Compiler automatisch der Sicherungsspeicher für Sie generiert werden sollen. Im Allgemeinen sollten Sie die explizitere Weise, wenn die Eigenschaft eine nicht triviale Implementierung verfügt und die automatische Methode verwenden, wenn die Eigenschaft nur ein einfacher Wrapper für ein Wert oder eine Variable ist. Um eine Eigenschaft explizit deklarieren, verwenden die `member` Schlüsselwort. Diese deklarative Syntax folgt die Syntax, der angibt, die `get` und `set` Methoden, die auch mit dem Namen *Accessoren*. Die verschiedenen Formen der expliziten Syntax im Syntaxabschnitt dargestellt werden für Lese-/Schreibzugriff, schreibgeschützte und lesegeschützte Eigenschaften verwendet. Für schreibgeschützte Eigenschaften, definieren Sie nur eine `get` Methode für nur-schreiben-Eigenschaften, definieren Sie nur eine `set` Methode. Beachten Sie, dass, wenn eine Eigenschaft sowohl hat `get` und `set` -Accessor angeben, die alternative Syntax können Sie angeben, Attribute und Zugriffsmodifizierer, die sich für jeden Accessor, wie im folgenden Code gezeigt werden.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

Eigenschaften von Lese-/Schreibzugriff, die jeweils eine `get` und `set` -Methode, die Reihenfolge der `get` und `set` rückgängig gemacht werden kann. Alternativ können Sie die Syntax für die bereitstellen `get` nur und die Syntax für `set` nur anstelle der kombinierten Syntax. Dies macht es einfacher, kommentieren Sie die einzelnen `get` oder `set` -Methode, wenn dies etwas ist müssen Sie Sie. Diese Alternative zur Verwendung von der kombinierten Syntax ist in den folgenden Code dargestellt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

Private Werte, die Daten für Eigenschaften heißen, halten *Sicherungsspeicher*. Damit den Compiler automatisch den Sicherungsspeicher zu erstellen, verwenden Sie die Schlüsselwörter `member val`, lassen Sie die Self-ID, und geben Sie einen Ausdruck, um die Eigenschaft zu initialisieren. Wenn die Eigenschaft ist veränderlich sein müssen, schließen Sie `with get, set`. Der folgende Klassentyp enthält beispielsweise zwei automatisch implementierte Eigenschaften. `Property1` ist schreibgeschützt und wird mit dem Argument bereitgestellt, um den primären Konstruktor, initialisiert und `Property2` ist eine Eigenschaft festgelegt werden kann, die auf eine leere Zeichenfolge initialisiert:

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

Automatisch implementierte Eigenschaften sind Teil der Initialisierung eines Typs an, damit sie genau wie vor anderen Memberdefinitionen aufgenommen werden müssen `let` Bindungen und `do` Bindungen in einer Typdefinition. Beachten Sie, dass der Ausdruck, der eine automatisch implementierte Eigenschaft initialisiert nur ausgewertet wird, bei der Initialisierung und nicht jedes Mal, wenn die Eigenschaft zugegriffen wird. Dieses Verhalten unterscheidet sich das Verhalten einer explizit implementierte Eigenschaft. Was dies bedeutet, die den Code zum Initialisieren dieser Eigenschaften ist, wird an den Konstruktor einer Klasse hinzugefügt. Betrachten Sie den folgenden Code, der diese Abweichung zeigt:

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

Die Ausgabe des obigen Codes zeigt, dass der Wert der AutoProperty unverändert ist, wenn er wiederholt aufgerufen wird, während die ExplicitProperty sich jedes Mal ändert, wenn sie aufgerufen wird. Dies zeigt, dass der Ausdruck für eine automatisch implementierte Eigenschaft nicht jedes Mal ausgewertet wird, wie die Gettermethode für die explizite Eigenschaft.

>[!WARNING]
>Es gibt einige Bibliotheken, z. B. Entity Framework (`System.Data.Entity`), benutzerdefinierte Vorgänge ausführen, in den Konstruktoren, die auch mit der Initialisierung des automatisch implementierte Eigenschaften nicht funktionieren. Verwenden Sie in diesen Fällen explizite Eigenschaften.

Eigenschaften können Mitglieder der Klassen, Strukturen, Unterscheidungs-Unions, Datensätze, Schnittstellen und Erweiterungen des Typs sein, und es können auch in Object-Ausdrücke definiert werden.

Attribute können auf Eigenschaften angewendet werden. Schreiben Sie zum Anwenden eines Attributs auf eine Eigenschaft des Attributs in einer separaten Zeile vor der Eigenschaft ein. Weitere Informationen finden Sie unter [Attribute](../attributes.md).

Werden standardmäßig sind öffentlich Eigenschaften. Zugriffsmodifizierer können auch auf Eigenschaften angewendet werden. Zum Anwenden eines Zugriffsmodifizierers hinzufügen unmittelbar vor den Namen der Eigenschaft, wenn es für beide gelten sollen, ist die `get` und `set` Methoden vor dem Hinzufügen der `get` und `set` -Schlüsselwörter verwenden, wenn ein anderer Zugriff ist für jeden Accessor erforderlich. Die *Zugriffsmodifizierer* kann einen der folgenden sein: `public`, `private`, `internal`. Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-control.md).

Eigenschaft-Implementierungen werden jedes Mal ausgeführt, die eine Eigenschaft zugegriffen wird.

## <a name="static-and-instance-properties"></a>Statische und -Instanzeigenschaften

Eigenschaften können statisch sein oder Instanzeigenschaften. Statische Eigenschaften aufgerufen werden können, ohne eine Instanz und werden für Werte, die dem Typ, nicht mit einzelnen Objekten zugeordnet. Lassen Sie für statische Eigenschaften die Self-ID ein. Die Self-ID ist für Instanzeigenschaften erforderlich.

Die folgende Definition für die statische Eigenschaft basiert darauf, dass ein Szenario in dem Sie ein statisches Feld `myStaticValue` d. h. der Sicherungsspeicher für die Eigenschaft.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

Eigenschaften können auch arrayähnlichen, in diesem Fall werden sie aufgerufen werden *indizierte Eigenschaften*. Weitere Informationen finden Sie unter [indizierte Eigenschaften](indexed-properties.md).

## <a name="type-annotation-for-properties"></a>Typ-Anmerkung für Eigenschaften

In vielen Fällen der Compiler verfügt über genügend Informationen, um den Typ einer Eigenschaft vom Typ des Sicherungsspeichers ableiten, aber Sie können den Typ explizit festlegen, durch das Hinzufügen einer Typ-Anmerkung.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a>Set-Accessoren mit der Eigenschaft

Sie Eigenschaften festlegen, die bieten `set` Accessoren mit der `<-` Operator.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

Die Ausgabe ist **20**.

## <a name="abstract-properties"></a>Abstrakte Eigenschaften

Eigenschaften können abstrakt sein. Wie bei Methoden `abstract` bedeutet lediglich, dass ein virtueller Dispatch, die der Eigenschaft zugeordnet ist. Abstrakte Eigenschaften können tatsächlich abstrakt sein, d. h. ohne Definition in der gleichen Klasse sein. Klasse, die diese Eigenschaft enthält, ist daher eine abstrakte Klasse. Alternativ kann nur abstrakt bedeuten, dass eine Eigenschaft virtuell ist und in diesem Fall muss eine Definition in der gleichen Klasse vorhanden sein. Beachten Sie, dass abstrakte Eigenschaften müssen nicht privat sein, wenn ein Accessor abstrakt ist, die andere auch muss sein abstrakt. Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a>Siehe auch

- [Mitglieder](index.md)
- [Methoden](methods.md)
