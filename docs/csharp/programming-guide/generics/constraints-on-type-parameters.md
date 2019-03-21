---
title: Einschränkungen für Typparameter – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 04/12/2018
helpviewer_keywords:
- generics [C#], type constraints
- type constraints [C#]
- type parameters [C#], constraints
- unbound type parameter [C#]
ms.openlocfilehash: 08863e677413c27461d621c7126c64f2b76c33a8
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57202599"
---
# <a name="constraints-on-type-parameters-c-programming-guide"></a>Einschränkungen für Typparameter (C#-Programmierhandbuch)

Einschränkungen informieren den Compiler über die Funktionen, über die ein Typargument verfügen muss. Ohne Einschränkungen könnte das Typargument jedes beliebige Argument sein. Der Compiler kann nur die <xref:System.Object?displayProperty=nameWithType>-Elemente annehmen. Dies ist die übergeordnete Basisklasse für jeden beliebigen .NET-Typ. Weitere Informationen finden Sie unter [Weshalb Einschränkungen?](#why-use-constraints). Wenn Clientcode versucht, Ihre Klasse zu instanziieren, indem er einen Typ verwendet, der durch Ihre Einschränkung nicht erlaubt ist, kommt es zu einem Kompilierzeitfehler. Constraints werden mit dem kontextuellen Schlüsselwort `where` angegeben. In der folgenden Tabelle werden die sieben verschiedenen Einschränkungstypen aufgelistet:

|Constraint|Beschreibung|
|----------------|-----------------|
|`where T : struct`|Das Typargument muss ein Werttyp sein. Jeder Werttyp außer <xref:System.Nullable%601> kann angegeben werden. Weitere Informationen zu Typen, die NULL-Werte zulassen, finden Sie unter [Nullable-Typen (C#-Programmierhandbuch)](../nullable-types/index.md).|
|`where T : class`|Das Typargument muss ein Verweistyp sein. Diese Einschränkung gilt auch für jede Klasse, Schnittstelle, jeden Delegaten oder Arraytyp.|
|`where T : unmanaged`|Das Typargument darf kein Verweistyp sein und darf keine Verweistypmitglieder auf einer Schachtelungsebene enthalten.|
|`where T : new()`|Das Typargument muss einen öffentlichen, parameterlosen Konstruktor aufweisen. Beim gemeinsamen Verwenden anderen Constraints muss der `new()`-Constraint zuletzt angegeben werden.|
|`where T :` *\<Basisklassenname>*|Das Typargument muss die angegebene Basisklasse sein oder von dieser abgeleitet werden.|
|`where T :` *\<Schnittstellenname>*|Das Typargument muss die angegebene Schnittstelle sein oder diese implementieren. Es können mehrere Schnittstelleneinschränkungen angegeben werden. Die einschränkende Schnittstelle kann auch generisch sein.|
|`where T : U`|Das Typargument, das für T angegeben wurde, muss das für T angegebene Argument sein oder von diesem abgeleitet werden.|

Einige der Einschränkungen schließen einander aus. Alle Werttypen müssen einen zugänglichen, parameterlosen Konstruktor haben. Die `struct`-Einschränkung impliziert die `new()`-Einschränkung, und die `new()`-Einschränkung kann nicht mit der `struct`-Einschränkung kombiniert werden. Die `unmanaged`-Einschränkung impliziert die `struct`-Einschränkung. Die `unmanaged`-Einschränkung kann nicht mit der `struct`- oder `new()`-Einschränkung kombiniert werden.

## <a name="why-use-constraints"></a>Weshalb Einschränkungen?

Indem Sie den Typparameter einschränken, erhöhen Sie die Zahl an zulässigen Vorgängen und Methodenaufrufen von denjenigen, die vom einschränkenden Typ und allen Typen in dessen Vererbungshierarchie unterstützt werden. Beim Entwerfen generischer Klassen und Methoden müssen Sie Einschränkungen auf den Typparameter anwenden, wenn Sie Vorgänge mit den generischen Membern durchführen möchten, die über das einfache Zuweisen und Aufrufen von Methoden hinausgehen, die nicht von <xref:System.Object?displayProperty=nameWithType> unterstützt werden. Der Basisklassenconstraint sagt dem Compiler z.B., dass nur Objekte dieses Typs oder Objekte, die von diesem Typ abgeleitet werden, als Typargumente verwendet werden. Sobald der Compiler diese Garantie hat, kann er erlauben, dass Methoden dieses Typs in der generischen Klasse aufgerufen werden können. Im folgenden Codebeispiel wird die Funktionalität veranschaulicht, die der `GenericList<T>`-Klasse durch das Anwenden einer Basisklasseneinschränkung hinzugefügt werden kann (in [Einführung in Generics](introduction-to-generics.md)).

[!code-csharp[using the class and struct constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#9)]

Die Einschränkung ermöglicht der generischen Klasse, die `Employee.Name`-Eigenschaft zu verwenden. Die Einschränkung gibt an, dass alle Elemente des Typs `T` entweder ein `Employee`-Objekt oder ein Objekt sind, das von `Employee` erbt.

Mehrere Constraints können wie folgt auf den gleichen Typenparameter angewendet werden, und die Contraints können selbst generische Typen sein:

[!code-csharp[using the class and struct constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#10)]

Wenn Sie den Constraint `where T : class` anwenden, vermeiden Sie das Verwenden der Operatoren `==` und `!=` mit dem Typparameter, da diese nur auf Verweisidentität und nicht auf Wertgleichheit prüfen. Dieses Verhalten tritt auch auf, wenn diese Operatoren in einem Typ überladen werden, der als Argument verwendet wird. Der folgende Code veranschaulicht diesen Aspekt. Die Ausgabe ist FALSE, obwohl die <xref:System.String>-Klasse den `==`-Operator überlädt.

[!code-csharp[using the class and struct constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#11)]

Der Compiler weiß zur Kompilierzeit nur, dass T ein Verweistyp ist, und er deshalb die Standardoperatoren verwenden muss, die für alle Verweistypen zulässig sind. Wenn Sie auf Wertgleichheit prüfen müssen, wird empfohlen, dass Sie die `where T : IEquatable<T>`- oder `where T : IComparable<T>`-Einschränkung anwenden und die Schnittstelle in jeder Klasse implementieren, die verwendet wird, um die generische Klasse zu erstellen.

## <a name="constraining-multiple-parameters"></a>Einschränken mehrerer Parameter

Sie können wie im folgenden Beispiel gezeigt Constraints auf mehrere Parameter und mehrere Constraints auf einen einzelnen Parameter anwenden:

[!code-csharp[using the class and struct constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#12)]

## <a name="unbounded-type-parameters"></a>Ungebundene Typparameter

 Typparameter, auf die keine Constraints angewendet wurden, wie z.B. T in der öffentlichen Klasse `SampleClass<T>{}`, werden als ungebundene Typparameter bezeichnet. Für ungebundene Typparameter gelten die folgenden Regeln:

- Die Operatoren `!=` und `==` können nicht verwendet werden, weil es keine Garantie gibt, dass das jeweilige Typargument diese auch unterstützt.
- Sie können in und aus `System.Object` oder implizit in einen Schnittstellentyp konvertiert werden.
- Sie können sie mit [NULL](../../language-reference/keywords/null.md) vergleichen. Wenn ein ungebundener Parameter mit `null` verglichen wird, gibt der Vergleich immer FALSE zurück, wenn das Typargument ein Werttyp ist.

## <a name="type-parameters-as-constraints"></a>Typparameter als Einschränkungen

Es ist nützlich, einen Typparameter wie in folgendem Beispiel gezeigt als Constraint zu verwenden, wenn eine Memberfunktion mit ihren eigenen Typparametern diesen Parameter auf den Typparameter des enthaltenden Typs einschränken muss:

[!code-csharp[using the class and struct constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#13)]

Im vorherigen Beispiel ist `T` ein Typconstraint im Kontext der `Add`-Methode und ein ungebundener Typparameter im Kontext der `List`-Klasse.

Typparameter können auch in generischen Klassendefinitionen als Constraints verwendet werden. Der Typparameter in spitzen Klammern muss zusammen mit allen anderen Typparametern deklariert werden:

[!code-csharp[using the class and struct constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#14)]

Das Verwenden von Typparametern als Einschränkungen für generische Klassen ist nur bis zu einem gewissen Punkt nützlich, da der Compiler keine Informationen über den Typparameter annehmen kann, nur dass er von `System.Object` abgeleitet ist. Sie sollten Typparameter als Constraints dann verwenden, wenn Sie eine Vererbungsbeziehung zwischen zwei Typparametern erzwingen möchten.

## <a name="unmanaged-constraint"></a>Nicht verwaltete Einschränkungen

Ab C# 7.3 können Sie die `unmanaged`-Einschränkung nutzen, um anzugeben, dass der Typparameter ein **nicht verwalteter Typ** sein muss. Ein **nicht verwalteter Typ** ist ein Typ, der kein Verweistyp ist, und keine Verweistypfelder auf Schachtelungsebene aufweist. Die `unmanaged`-Einschränkung ermöglicht Ihnen das Schreiben von wiederverwendbarer Routinen zum Arbeiten mit Typen, die als Speicherblöcke bearbeitet werden können, wie im folgenden Beispiel gezeigt:

[!code-csharp[using the unmanaged constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#15)]

Die vorherige Methode muss in einen `unsafe`-Kontext kompiliert werden, da sie den `sizeof`-Operator für einen nicht bekannten Typ verwendet, der ein integrierter Typ ist. Ohne die `unmanaged`-Einschränkung ist der `sizeof`-Operator nicht verfügbar.

## <a name="delegate-constraints"></a>Delegieren von Einschränkungen

Ab C# 7.3 können Sie auch <xref:System.Delegate?displayProperty=nameWithType> oder <xref:System.MulticastDelegate?displayProperty=nameWithType> als Basisklasseneinschränkung verwenden. Die CLR lässt diese Einschränkung immer zu, aber die C#-Sprache lässt sie nicht zu. Die `System.Delegate`-Einschränkung ermöglicht es Ihnen, Code zu schreiben, der mit Delegaten in einer typsicheren Weise funktioniert. Der folgende Code definiert eine Erweiterungsmethode, die zwei Delegaten kombiniert, sofern diese vom gleichen Typ sind:

[!code-csharp[using the delegate constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#16)]

Sie können die oben dargestellte Methode verwenden, um Delegaten vom selben Typ zu kombinieren:

[!code-csharp[using the unmanaged constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#17)]

Wenn Sie den Kommentar der letzten Zeile entfernen, findet die Kompilation nicht statt. `first` und `test` sind beides Delegattypen, aber sie sind unterschiedliche Delegattypen.

## <a name="enum-constraints"></a>Enumerationseinschränkungen

Ab C# 7.3 können Sie auch den <xref:System.Enum?displayProperty=nameWithType>-Typ als Basisklasseneinschränkung angeben. Die CLR lässt diese Einschränkung immer zu, aber die C#-Sprache lässt sie nicht zu. Generics, die `System.Enum` verwenden, bieten typsichere Programmierung zum Zwischenspeichern von Ergebnissen aus der Verwendung der statischen Methoden in `System.Enum`. Im folgenden Beispiel werden alle gültigen Werte für einen Enumerationstyp gefunden, und dann ein Wörterbuch erstellt, das diese Werte ihrer Zeichenfolgendarstellung zuordnet.

[!code-csharp[using the unmanaged constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#18)]

Die verwendeten Methoden nutzen die Reflektion, die Auswirkungen auf die Leistung hat. Sie können diese Methode aufrufen, um eine Sammlung zu erstellen, die zwischengespeichert und wiederverwendet wird, anstatt die Aufrufe zu wiederholen, die eine Reflektion erfordern.

Sie könnten dies wie im folgenden Beispiel gezeigt verwenden, um eine Enumeration und ein Wörterbuch der Werte und Namen zu erstellen:

[!code-csharp[using the unmanaged constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#19)]

[!code-csharp[using the unmanaged constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#20)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic>
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Einführung in Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md)
- [Generische Klassen](../../../csharp/programming-guide/generics/generic-classes.md)
- [new-Einschränkung](../../../csharp/language-reference/keywords/new-constraint.md)
