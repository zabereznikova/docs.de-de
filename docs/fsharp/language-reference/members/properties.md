---
title: Eigenschaften
description: 'Erfahren Sie mehr über die F #-Eigenschaften, die Elemente darstellen, die einem Objekt zugeordneten Werten entsprechen.'
ms.date: 05/16/2016
ms.openlocfilehash: a2a4fbfc88831dcb5cad7a2da701969b2e98b2e3
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740197"
---
# <a name="properties"></a>Eigenschaften

*Eigenschaften* sind Elemente, die mit einem Objekt verknüpfte Werte darstellen.

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

## <a name="remarks"></a>Bemerkungen

Eigenschaften stellen die Beziehung "hat eine" in der objektorientierten Programmierung dar, die Daten darstellen, die Objektinstanzen zugeordnet sind, oder für statische Eigenschaften mit dem Typ.

Sie können Eigenschaften auf zwei Arten deklarieren, je nachdem, ob Sie den zugrunde liegenden Wert (auch als Sicherungs Speicher bezeichnet) für die Eigenschaft explizit angeben möchten, oder wenn Sie zulassen möchten, dass der Compiler automatisch den Sicherungs Speicher für Sie generiert. Im Allgemeinen sollten Sie die explizitere Methode verwenden, wenn die Eigenschaft eine nicht triviale Implementierung hat, und die automatische Methode, wenn die Eigenschaft nur ein einfacher Wrapper für einen Wert oder eine Variable ist. Verwenden Sie das-Schlüsselwort, um eine Eigenschaft explizit zu deklarieren `member` . Auf diese deklarative Syntax folgt die Syntax, die die `get` -Methode und die- `set` Methode angibt, auch namens *Accessoren*. Die verschiedenen Formen der expliziten Syntax, die im Syntax Abschnitt angezeigt werden, werden für Lese-/Schreib-, schreibgeschützte und Lese geschützte Eigenschaften verwendet. Für schreibgeschützte Eigenschaften definieren Sie nur eine- `get` Methode. bei schreibgeschützten Eigenschaften definieren Sie nur eine- `set` Methode. Beachten Sie, dass `get` `set` die alternative Syntax es Ihnen ermöglicht, Attribute und Zugriffsmodifizierer anzugeben, die für jeden Accessor unterschiedlich sind, wie im folgenden Code gezeigt, wenn eine Eigenschaft sowohl-als auch-Accessoren aufweist.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

Für Lese-/Schreibeigenschaften, die sowohl die-als auch die- `get` `set` Methode aufweisen, kann die Reihenfolge von `get` und `set` umgekehrt werden. Alternativ können Sie die nur für angezeigte Syntax `get` und die Syntax angeben, die nur für angezeigt wird, `set` anstatt die kombinierte Syntax zu verwenden. Dies erleichtert das Auskommentieren der einzelnen-oder- `get` `set` Methode, wenn dies etwas ist, was Sie möglicherweise tun müssen. Diese Alternative zur Verwendung der kombinierten Syntax wird im folgenden Code dargestellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

Private Werte, die die Daten für Eigenschaften enthalten, werden als *Sicherungs Speicher* bezeichnet. Damit der Compiler den Sicherungs Speicher automatisch erstellen kann, verwenden Sie die Schlüsselwörter `member val` , lassen Sie den Self-Identifier aus, und geben Sie dann einen Ausdruck an, um die Eigenschaft zu initialisieren. Wenn die Eigenschaft änderbar sein soll, fügen Sie ein `with get, set` . Der folgende Klassentyp enthält z. b. zwei automatisch implementierte Eigenschaften. `Property1` ist schreibgeschützt und wird mit dem-Argument initialisiert, das für den primären Konstruktor bereitgestellt wird, und `Property2` ist eine festleg Bare Eigenschaft, die auf eine leere Zeichenfolge initialisiert wird:

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

Automatisch implementierte Eigenschaften sind Teil der Initialisierung eines Typs, sodass Sie vor allen anderen Element Definitionen eingeschlossen werden müssen, genauso wie `let` Bindungen und `do` Bindungen in einer Typdefinition. Beachten Sie, dass der Ausdruck, der eine automatisch implementierte Eigenschaft initialisiert, nur bei der Initialisierung ausgewertet wird und nicht jedes Mal, wenn auf die Eigenschaft zugegriffen wird. Dieses Verhalten steht im Gegensatz zum Verhalten einer explizit implementierten Eigenschaft. Dies bedeutet, dass der Code zum Initialisieren dieser Eigenschaften dem Konstruktor einer Klasse hinzugefügt wird. Sehen Sie sich den folgenden Code an, der diesen Unterschied zeigt:

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn $"class1.AutoProperty = %d{class1.AutoProperty}"
printfn $"class1.ExplicitProperty = %d{class1.ExplicitProperty}"
```

**Ausgabe**

```console
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

Die Ausgabe des vorangehenden Codes zeigt, dass der Wert von autoproperty unverändert ist, wenn er wiederholt aufgerufen wird, während die explizproperty bei jedem Aufruf geändert wird. Dies zeigt, dass der Ausdruck für eine automatisch implementierte Eigenschaft nicht jedes Mal ausgewertet wird, wie dies die Getter-Methode für die explizite Eigenschaft ist.

>[!WARNING]
>Es gibt einige Bibliotheken, z. b. die Entity Framework ( `System.Data.Entity` ), die benutzerdefinierte Vorgänge in Basisklassenkonstruktoren ausführen, die nicht gut mit der Initialisierung automatisch implementierter Eigenschaften funktionieren. Versuchen Sie in diesen Fällen, explizite Eigenschaften zu verwenden.

Eigenschaften können Member von Klassen, Strukturen, Unterscheidungs-Unions, Datensätzen, Schnittstellen und Typerweiterungen sein und können auch in Objekt Ausdrücken definiert werden.

Attribute können auf Eigenschaften angewendet werden. Wenn Sie ein Attribut auf eine Eigenschaft anwenden möchten, schreiben Sie das-Attribut in einer separaten Zeile vor der-Eigenschaft. Weitere Informationen finden Sie unter [Attribute](../attributes.md).

Standardmäßig sind Eigenschaften öffentlich. Zugriffsmodifizierer können auch auf Eigenschaften angewendet werden. Wenn Sie einen Zugriffsmodifizierer anwenden möchten, fügen Sie ihn direkt vor dem Namen der Eigenschaft ein, wenn er auf die `get` -Methode und die-Methode angewendet werden soll `set` . Fügen Sie ihn vor den `get` Schlüsselwörtern und hinzu, `set` Wenn für jeden Accessor ein anderer Zugriff erforderlich Der *accessibility-modifier* Zugriffsmodifizierer kann eine der folgenden sein: `public` , `private` , `internal` . Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-control.md).

Eigenschafts Implementierungen werden jedes Mal ausgeführt, wenn auf eine Eigenschaft zugegriffen wird.

## <a name="static-and-instance-properties"></a>Statische Eigenschaften und Instanzeigenschaften

Eigenschaften können statische Eigenschaften oder Instanzeigenschaften sein. Statische Eigenschaften können ohne eine Instanz aufgerufen werden und werden für Werte verwendet, die dem Typ zugeordnet sind, nicht für einzelne Objekte. Lassen Sie für statische Eigenschaften den selbst Bezeichner aus. Der Self-Identifier ist für Instanzeigenschaften erforderlich.

Die folgende statische Eigenschafts Definition basiert auf einem Szenario, in dem Sie über ein statisches Feld verfügen `myStaticValue` , das den Sicherungs Speicher für die Eigenschaft ist.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

Eigenschaften können auch Array ähnlich sein. in diesem Fall werden Sie als *indizierte Eigenschaften* bezeichnet. Weitere Informationen finden Sie unter [indizierte Eigenschaften](indexed-properties.md).

## <a name="type-annotation-for-properties"></a>Typanmerkung für Eigenschaften

In vielen Fällen verfügt der Compiler über ausreichende Informationen, um den Typ einer Eigenschaft vom Typ des Sicherungs Speicher abzuleiten, aber Sie können den Typ explizit festlegen, indem Sie eine Typanmerkung hinzufügen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a>Verwenden von Eigenschaften Satz Accessoren

Sie können Eigenschaften festlegen, die `set` Accessoren bereitstellen, indem Sie den- `<-` Operator verwenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

Die Ausgabe beträgt **20**.

## <a name="abstract-properties"></a>Abstrakte Eigenschaften

Eigenschaften können abstrakt sein. Wie bei Methoden `abstract` bedeutet nur, dass der Eigenschaft ein virtueller Verteiler zugeordnet ist. Abstrakte Eigenschaften können wirklich abstrakt sein, d. h. ohne eine Definition in der gleichen Klasse. Die Klasse, die eine solche Eigenschaft enthält, ist daher eine abstrakte Klasse. Alternativ kann Abstract nur bedeuten, dass eine Eigenschaft virtuell ist, und in diesem Fall muss eine Definition in der gleichen Klasse vorhanden sein. Beachten Sie, dass abstrakte Eigenschaften nicht privat sein dürfen, und wenn ein Accessor abstrakt ist, muss der andere ebenfalls abstrakt sein. Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a>Weitere Informationen

- [Mitglieder](index.md)
- [Methoden](methods.md)
