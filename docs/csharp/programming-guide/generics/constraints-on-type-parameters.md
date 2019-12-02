---
title: Einschränkungen für Typparameter – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 04/12/2018
helpviewer_keywords:
- generics [C#], type constraints
- type constraints [C#]
- type parameters [C#], constraints
- unbound type parameter [C#]
ms.openlocfilehash: d05307735506db0f0e4abab067334e4f0466ee6a
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204639"
---
# <a name="constraints-on-type-parameters-c-programming-guide"></a>Einschränkungen für Typparameter (C#-Programmierhandbuch)

Einschränkungen informieren den Compiler über die Funktionen, über die ein Typargument verfügen muss. Ohne Einschränkungen könnte das Typargument jedes beliebige Argument sein. Der Compiler kann nur die <xref:System.Object?displayProperty=nameWithType>-Elemente annehmen. Dies ist die übergeordnete Basisklasse für jeden beliebigen .NET-Typ. Weitere Informationen finden Sie unter [Weshalb Einschränkungen?](#why-use-constraints). Wenn Clientcode versucht, Ihre Klasse zu instanziieren, indem er einen Typ verwendet, der durch Ihre Einschränkung nicht erlaubt ist, kommt es zu einem Kompilierzeitfehler. Constraints werden mit dem kontextuellen Schlüsselwort `where` angegeben. In der folgenden Tabelle werden die sieben verschiedenen Einschränkungstypen aufgelistet:

|Constraint|BESCHREIBUNG|
|----------------|-----------------|
|`where T : struct`|Das Typargument muss ein Nicht-Nullable-Werttyp sein. Weitere Informationen zu Nullable-Werttypen finden Sie unter [Nullable-Werttypen](../../language-reference/builtin-types/nullable-value-types.md). Da alle Werttypen einen parameterlosen Konstruktor aufweisen, auf den zugegriffen werden kann, impliziert die `struct`-Einschränkung die `new()`-Einschränkung und kann nicht mit der `new()`-Einschränkung kombiniert werden. Ferner kann auch die `struct`-Einschränkung nicht mit der `unmanaged`-Einschränkung kombiniert werden.|
|`where T : class`|Das Typargument muss ein Verweistyp sein. Diese Einschränkung gilt auch für jede Klasse, Schnittstelle, jeden Delegaten oder Arraytyp.|
|`where T : notnull`|Das Typargument muss ein Nicht-Nullable-Typ sein. Das Argument kann ein Nicht-Nullable-Verweistyp in C# 8.0 oder höher oder ein Nicht-Nullable-Werttyp sein. Diese Einschränkung gilt auch für jede Klasse, Schnittstelle, jeden Delegaten oder Arraytyp.|
|`where T : unmanaged`|Das Typargument muss ein [nicht verwalteter Non-Nullable-Typ](../../language-reference/builtin-types/unmanaged-types.md) sein. Die `unmanaged`-Einschränkung impliziert die `struct`-Einschränkung und kann weder mit der `struct`- noch mit der `new()`-Einschränkung kombiniert werden.|
|`where T : new()`|Das Typargument muss einen öffentlichen, parameterlosen Konstruktor aufweisen. Beim gemeinsamen Verwenden anderen Constraints muss der `new()`-Constraint zuletzt angegeben werden. Die `new()`-Einschränkung kann nicht mit der `struct`- oder `unmanaged`-Einschränkung kombiniert werden.|
|`where T :` *\<Basisklassenname>*|Das Typargument muss die angegebene Basisklasse sein oder von dieser abgeleitet werden.|
|`where T :` *\<Schnittstellenname>*|Das Typargument muss die angegebene Schnittstelle sein oder diese implementieren. Es können mehrere Schnittstelleneinschränkungen angegeben werden. Die einschränkende Schnittstelle kann auch generisch sein.|
|`where T : U`|Das Typargument, das für T angegeben wurde, muss das für T angegebene Argument sein oder von diesem abgeleitet werden.|

## <a name="why-use-constraints"></a>Weshalb Einschränkungen?

Indem Sie den Typparameter einschränken, erhöhen Sie die Zahl an zulässigen Vorgängen und Methodenaufrufen von denjenigen, die vom einschränkenden Typ und allen Typen in dessen Vererbungshierarchie unterstützt werden. Beim Entwerfen generischer Klassen oder Methoden müssen Sie Einschränkungen auf den Typparameter anwenden, wenn Sie Vorgänge mit den generischen Membern durchführen möchten, die über das einfache Zuweisen und Aufrufen von Methoden hinausgehen, die nicht von <xref:System.Object?displayProperty=nameWithType> unterstützt werden. Der Basisklassenconstraint sagt dem Compiler z.B., dass nur Objekte dieses Typs oder Objekte, die von diesem Typ abgeleitet werden, als Typargumente verwendet werden. Sobald der Compiler diese Garantie hat, kann er erlauben, dass Methoden dieses Typs in der generischen Klasse aufgerufen werden können. Im folgenden Codebeispiel wird die Funktionalität veranschaulicht, die der `GenericList<T>`-Klasse durch das Anwenden einer Basisklasseneinschränkung hinzugefügt werden kann (in [Einführung in Generics](../../../standard/generics/index.md)).

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#9)]

Die Einschränkung ermöglicht der generischen Klasse, die `Employee.Name`-Eigenschaft zu verwenden. Die Einschränkung gibt an, dass alle Elemente des Typs `T` entweder ein `Employee`-Objekt oder ein Objekt sind, das von `Employee` erbt.

Mehrere Constraints können wie folgt auf den gleichen Typenparameter angewendet werden, und die Contraints können selbst generische Typen sein:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#10)]

Wenn Sie den Constraint `where T : class` anwenden, vermeiden Sie das Verwenden der Operatoren `==` und `!=` mit dem Typparameter, da diese nur auf Verweisidentität und nicht auf Wertgleichheit prüfen. Dieses Verhalten tritt auch auf, wenn diese Operatoren in einem Typ überladen werden, der als Argument verwendet wird. Der folgende Code veranschaulicht diesen Aspekt. Die Ausgabe ist FALSE, obwohl die <xref:System.String>-Klasse den `==`-Operator überlädt.

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#11)]

Der Compiler weiß erst zur Kompilierzeit, dass `T` ein Verweistyp ist und die für alle Verweistypen zulässigen Standardoperatoren verwendet werden müssen. Wenn Sie auf Wertgleichheit prüfen müssen, wird empfohlen, dass Sie die `where T : IEquatable<T>`- oder `where T : IComparable<T>`-Einschränkung anwenden und die Schnittstelle in jeder Klasse implementieren, die verwendet wird, um die generische Klasse zu erstellen.

## <a name="constraining-multiple-parameters"></a>Einschränken mehrerer Parameter

Sie können wie im folgenden Beispiel gezeigt Constraints auf mehrere Parameter und mehrere Constraints auf einen einzelnen Parameter anwenden:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#12)]

## <a name="unbounded-type-parameters"></a>Ungebundene Typparameter

 Typparameter, auf die keine Constraints angewendet wurden, wie z.B. T in der öffentlichen Klasse `SampleClass<T>{}`, werden als ungebundene Typparameter bezeichnet. Für ungebundene Typparameter gelten die folgenden Regeln:

- Die Operatoren `!=` und `==` können nicht verwendet werden, weil es keine Garantie dafür gibt, dass das jeweilige Typargument diese auch unterstützt.
- Sie können in und aus `System.Object` oder implizit in einen Schnittstellentyp konvertiert werden.
- Sie können sie mit [NULL](../../language-reference/keywords/null.md) vergleichen. Wenn ein ungebundener Parameter mit `null` verglichen wird, gibt der Vergleich immer FALSE zurück, wenn das Typargument ein Werttyp ist.

## <a name="type-parameters-as-constraints"></a>Typparameter als Einschränkungen

Es ist nützlich, einen Typparameter wie in folgendem Beispiel gezeigt als Constraint zu verwenden, wenn eine Memberfunktion mit ihren eigenen Typparametern diesen Parameter auf den Typparameter des enthaltenden Typs einschränken muss:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#13)]

Im vorherigen Beispiel ist `T` ein Typconstraint im Kontext der `Add`-Methode und ein ungebundener Typparameter im Kontext der `List`-Klasse.

Typparameter können auch in generischen Klassendefinitionen als Constraints verwendet werden. Der Typparameter in spitzen Klammern muss zusammen mit allen anderen Typparametern deklariert werden:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#14)]

Das Verwenden von Typparametern als Einschränkungen für generische Klassen ist nur bis zu einem gewissen Punkt nützlich, da der Compiler keine Informationen über den Typparameter annehmen kann, nur dass er von `System.Object` abgeleitet ist. Sie sollten Typparameter als Constraints dann verwenden, wenn Sie eine Vererbungsbeziehung zwischen zwei Typparametern erzwingen möchten.

## <a name="notnull-constraint"></a>NotNull-Einschränkung

Ab C# 8.0 können Sie die `notnull`-Einschränkung verwenden, um anzugeben, dass das Typargument ein Nicht-Nullable-Wert- oder -Verweistyp sein muss. Die `notnull`-Einschränkung kann nur in einem `nullable enable`-Kontext verwendet werden. Der Compiler generiert eine Warnung, wenn Sie die `notnull`-Einschränkung in einem Kontext hinzufügen, in dem nicht bekannt ist, ob NULL-Werte zugelassen sind. 

Im Gegensatz zu anderen Einschränkungen generiert der Compiler eine Warnung, wenn ein Typargument die `notnull`-Einschränkung verletzt und dieser Code in einem `nullable enable`-Kontext kompiliert wird. Wenn der Code in einem Kontext kompiliert wird, in dem nicht bekannt ist, ob NULL-Werte zugelassen sind, generiert der Compiler keine Warnungen oder Fehler.

## <a name="unmanaged-constraint"></a>Nicht verwaltete Einschränkungen

Ab C# 7.3 können Sie die `unmanaged`-Einschränkung nutzen, um anzugeben, dass der Typparameter ein [nicht verwalteter Non-Nullable-Typ](../../language-reference/builtin-types/unmanaged-types.md) sein muss. Die `unmanaged`-Einschränkung ermöglicht Ihnen das Schreiben von wiederverwendbarer Routinen zum Arbeiten mit Typen, die als Speicherblöcke bearbeitet werden können, wie im folgenden Beispiel gezeigt:

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#15)]

Die vorherige Methode muss in einen `unsafe`-Kontext kompiliert werden, da sie den `sizeof`-Operator für einen nicht bekannten Typ verwendet, der ein integrierter Typ ist. Ohne die `unmanaged`-Einschränkung ist der `sizeof`-Operator nicht verfügbar.

Die `unmanaged`-Einschränkung impliziert die `struct`-Einschränkung und kann nicht mit ihr kombiniert werden. Da die `struct`-Einschränkung die `new()`-Einschränkung impliziert, kann die `unmanaged`-Einschränkung ebenso wenig mit der `new()`-Einschränkung kombiniert werden.

## <a name="delegate-constraints"></a>Delegieren von Einschränkungen

Ab C# 7.3 können Sie auch <xref:System.Delegate?displayProperty=nameWithType> oder <xref:System.MulticastDelegate?displayProperty=nameWithType> als Basisklasseneinschränkung verwenden. Die CLR lässt diese Einschränkung immer zu, aber die C#-Sprache lässt sie nicht zu. Die `System.Delegate`-Einschränkung ermöglicht es Ihnen, Code zu schreiben, der mit Delegaten in einer typsicheren Weise funktioniert. Der folgende Code definiert eine Erweiterungsmethode, die zwei Delegaten kombiniert, sofern diese vom gleichen Typ sind:

[!code-csharp[using the delegate constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#16)]

Sie können die oben dargestellte Methode verwenden, um Delegaten vom selben Typ zu kombinieren:

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#17)]

Wenn Sie den Kommentar der letzten Zeile entfernen, findet die Kompilation nicht statt. Sowohl `first` als auch `test` sind Delegattypen, aber sie sind unterschiedlich.

## <a name="enum-constraints"></a>Enumerationseinschränkungen

Ab C# 7.3 können Sie auch den <xref:System.Enum?displayProperty=nameWithType>-Typ als Basisklasseneinschränkung angeben. Die CLR lässt diese Einschränkung immer zu, aber die C#-Sprache lässt sie nicht zu. Generics, die `System.Enum` verwenden, bieten typsichere Programmierung zum Zwischenspeichern von Ergebnissen aus der Verwendung der statischen Methoden in `System.Enum`. Im folgenden Beispiel werden alle gültigen Werte für einen Enumerationstyp gefunden, und dann ein Wörterbuch erstellt, das diese Werte ihrer Zeichenfolgendarstellung zuordnet.

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#18)]

Die verwendeten Methoden nutzen die Reflektion, die Auswirkungen auf die Leistung hat. Sie können diese Methode aufrufen, um eine Sammlung zu erstellen, die zwischengespeichert und wiederverwendet wird, anstatt die Aufrufe zu wiederholen, die eine Reflektion erfordern.

Sie könnten dies wie im folgenden Beispiel gezeigt verwenden, um eine Enumeration und ein Wörterbuch der Werte und Namen zu erstellen:

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#19)]

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#20)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic>
- [C#-Programmierhandbuch](../index.md)
- [Einführung in Generics](./index.md)
- [Generische Klassen](./generic-classes.md)
- [new-Einschränkung](../../language-reference/keywords/new-constraint.md)
