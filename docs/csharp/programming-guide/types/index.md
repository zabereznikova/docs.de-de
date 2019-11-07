---
title: Typen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- value types [C#]
- reference types [C#]
- types [C#]
- C# language, data types
- common type system [C#]
- data types [C#]
- C# language, types
- strong typing [C#]
ms.assetid: f782d7cc-035e-4500-b1b1-36a9881130ad
ms.openlocfilehash: 7d101e72a94ec1fecf44d4c883efb4f74e6d1d88
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739205"
---
# <a name="types-c-programming-guide"></a>Typen (C#-Programmierhandbuch)

## <a name="types-variables-and-values"></a>Typen, Variablen und Werte

C# ist eine stark typisierte Sprache. Jede Variable und jede Konstante verfügt über einen Typ, genau wie jeder Ausdruck, der zu einem Wert ausgewertet wird. Jede Methodensignatur gibt für jeden Eingabeparameter und den Rückgabewert einen Typ an. In der .NET-Klassenbibliothek werden integrierte numerische Typen und komplexe Typen definiert, die viele logische Konstrukte darstellen, z.B. das Dateisystem, Netzwerkverbindungen, Auflistungen und Arrays von Objekten sowie Datumsangaben. In einem typischen C#-Programm werden Typen aus der Klassenbibliothek sowie benutzerdefinierte Typen verwendet, die die Konzepte für das Problemfeld des Programms modellieren.

Folgende Informationen können in einem Typ gespeichert sein:

- Der Speicherplatz, den eine Variable des Typs erfordert

- Die maximalen und minimalen Werte, die diese darstellen kann

- Die enthaltenen Member (Methoden, Felder, Ereignisse usw.)

- Der Basistyp, von dem geerbt wird

- Die Position, an der der Arbeitsspeicher für Variablen zur Laufzeit belegt wird

- Die Arten von zulässigen Vorgängen

Der Compiler verwendet Typinformationen, um sicherzustellen, dass alle im Code ausgeführten Vorgänge *typsicher* sind. Wenn Sie z.B. eine Variable vom Typ [int](../../language-reference/builtin-types/integral-numeric-types.md) deklarieren, können Sie mit dem Compiler die Variable für Additions- und Subtraktionsvorgänge verwenden. Wenn Sie dieselben Vorgänge für eine Variable vom Typ [bool](../../language-reference/keywords/bool.md) ausführen möchten, generiert der Compiler einen Fehler, wie im folgenden Beispiel dargestellt:

[!code-csharp[csProgGuideTypes#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#42)]

> [!NOTE]
> C- und C++-Entwickler sollten beachten, dass in C# [bool](../../language-reference/keywords/bool.md) nicht in [int](../../language-reference/builtin-types/integral-numeric-types.md) konvertiert werden kann.

Der Compiler bettet die Typinformationen als Metadaten in die ausführbare Datei ein. Die Common Language Runtime (CLR) verwendet diese Metadaten zur Laufzeit, um die Typsicherheit zu gewährleisten, wenn Speicherplatz belegt und freigegeben wird.

### <a name="specifying-types-in-variable-declarations"></a>Angeben von Typen in Variablendeklarationen

Wenn Sie eine Variable oder Konstante in einem Programm deklarieren, müssen Sie den Typ festlegen oder das [var](../../language-reference/keywords/var.md)-Schlüsselwort verwenden, damit der Typ vom Compiler abgeleitet wird. Im folgenden Beispiel werden einige Variablendeklarationen dargestellt, die sowohl integrierte numerische Typen als auch komplexe benutzerdefinierte Typen verwenden:

[!code-csharp[csProgGuideTypes#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#36)]

Die Methodenparameter- und Rückgabewerttypen werden in der Methodensignatur angegeben. Die folgende Signatur zeigt eine Methode, für die ein [int](../../language-reference/builtin-types/integral-numeric-types.md) als Eingabeargument benötigt wird und die eine Zeichenfolge zurückgibt:

[!code-csharp[csProgGuideTypes#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#35)]

Nachdem eine Variable deklariert wurde, kann sie nicht erneut mit einem neuen Typ deklariert werden. Außerdem kann ihr kein Wert zugewiesen werden, der nicht mit dem deklarierten Typ kompatibel ist. Zum Beispiel können Sie eine [int](../../language-reference/builtin-types/integral-numeric-types.md) nicht deklarieren und dieser dann den booleschen Wert [true](../../language-reference/keywords/true-literal.md) zuweisen. Werte können jedoch in andere Typen konvertiert werden, z. B., wenn diese neuen Variablen zugewiesen oder als Methodenargumente übergeben werden. Eine *Typkonvertierung*, die keinen Datenverlust verursacht, wird automatisch vom Compiler ausgeführt. Eine Konvertierung, die möglicherweise Datenverlust verursacht, erfordert eine *Umwandlung* in den Quellcode.

Weitere Informationen finden Sie unter [Umwandlung und Typkonvertierungen](./casting-and-type-conversions.md).

## <a name="built-in-types"></a>Integrierte Typen

C# liefert einen Standardsatz mit integrierten numerischen Typen zur Darstellung von ganzen Zahlen, Gleitkommawerten, booleschen Ausdrücken, Textzeichen, Dezimalwerten und anderen Datentypen. Es gibt auch integrierte `string`-Typen und `object`-Typen. Diese können Sie in jedem C#-Programm verwenden. Weitere Informationen über die integrierten Typen finden Sie in den [Referenztabellen für integrierte Typen](../../language-reference/keywords/built-in-types-table.md).

## <a name="custom-types"></a>Benutzerdefinierte Typen

Sie verwenden die Konstrukte [struct](../../language-reference/keywords/struct.md), [class](../../language-reference/keywords/class.md), [interface](../../language-reference/keywords/interface.md) und [enum](../../language-reference/keywords/enum.md), um eigene benutzerdefinierte Typen zu erstellen. Die .NET-Klassenbibliothek ist eine Auflistung benutzerdefinierter, von Microsoft bereitgestellter Typen, die Sie in Ihren eigenen Anwendungen verwenden können. Standardmäßig sind die am häufigsten verwendeten Typen in der Klassenbibliothek in jedem C#-Programm verfügbar. Andere stehen nur zur Verfügung, wenn Sie ausdrücklich einen Projektverweis auf die Assembly hinzufügen, in der diese definiert sind. Wenn der Compiler über einen Verweis auf die Assembly verfügt, können Sie Variablen (und Konstanten) des in dieser Assembly deklarierten Typs im Quellcode deklarieren. Weitere Informationen finden Sie in der Dokumentation zur [.NET-Klassenbibliothek](../../../standard/class-library-overview.md).

## <a name="the-common-type-system"></a>Das allgemeine Typsystem

Mit zwei grundlegenden Punkten über das System der Typen in .NET sollten Sie vertraut sein:

- Es unterstützt das Prinzip der Vererbung. Typen können von anderen Typen abgeleitet werden, die als *Basistypen* bezeichnet werden. Der abgeleitete Typ erbt (mit einigen Beschränkungen) die Methoden, Eigenschaften und anderen Member des Basistyps. Der Basistyp kann wiederum von einem anderen Typ abgeleitet sein. In diesem Fall erbt der abgeleitete Typ die Member beider Basistypen in der Vererbungshierarchie. Alle Typen, einschließlich integrierter numerischer Typen, z. B. <xref:System.Int32?displayProperty=nameWithType> (C#-Schlüsselwort: [int](../../language-reference/builtin-types/integral-numeric-types.md)), werden letztendlich von einem einzelnen Basistyp abgeleitet, nämlich <xref:System.Object?displayProperty=nameWithType> (C#-Schlüsselwort: [object](../../language-reference/builtin-types/reference-types.md)). Diese einheitliche Typhierarchie wird als [Allgemeines Typsystem](../../../standard/base-types/common-type-system.md) (CTS) bezeichnet. Weitere Informationen zur Vererbung in C# finden Sie unter [Vererbung](../classes-and-structs/inheritance.md).

- Jeder Typ im CTS ist als *Werttyp* oder *Referenztyp* definiert. Dies betrifft auch alle benutzerdefinierten Typen in der .NET-Klassenbibliothek und Ihre eigenen benutzerdefinierten Typen. Typen, die Sie mithilfe des [struct](../../language-reference/keywords/struct.md)-Schlüsselworts definieren, sind Werttypen. Alle integrierten numerischen Typen sind `structs`. Typen, die Sie mithilfe des [class](../../language-reference/keywords/class.md)-Schlüsselworts definieren, sind Referenztypen. Für Referenztypen und Werttypen gelten unterschiedliche Kompilierzeitregeln und ein anderes Laufzeitverhalten.

In der folgenden Abbildung wird die Beziehung zwischen Werttypen und Referenztypen im CTS dargestellt.

Die folgende Abbildung zeigt Werttypen und Verweistypen im CTS:

![Screenshot mit CTS-Werttypen und -Verweistypen.](./media/index/value-reference-types-common-type-system.png)

> [!NOTE]
> Wie Sie sehen, sind die am häufigsten verwendeten Typen alle im <xref:System>-Namespace organisiert. Jedoch ist es für den Namespace, in dem ein Typ enthalten ist, unerheblich, ob es sich um einen Werttyp oder einen Referenztyp handelt.

### <a name="value-types"></a>Werttypen

Werttypen werden von <xref:System.ValueType?displayProperty=nameWithType> abgeleitet, was wiederum von <xref:System.Object?displayProperty=nameWithType> abgeleitet wird. Typen, die von <xref:System.ValueType?displayProperty=nameWithType> abgeleitet werden, weisen ein besonderes Verhalten in der CLR auf. Werttypvariablen enthalten die zugehörigen Werte direkt, d. h., der Speicher wird inline in dem Kontext belegt, in dem die Variable deklariert ist. Für Werttypvariablen erfolgt keine getrennte Heapzuordnung oder ein Mehraufwand für die Garbage Collection.

Zwei Kategorien von Werttypen sind verfügbar: [struct](../../language-reference/keywords/struct.md) und [enum](../../language-reference/keywords/enum.md).

Die integrierten numerischen Typen sind Strukturen und verfügen über Eigenschaften und Methoden, auf die Sie zugreifen können:

```csharp
// Static method on type byte.
byte b = byte.MaxValue;
```

Sie deklarieren diese jedoch und weisen ihnen Werte zu, als wären es einfache, nicht aggregierte Typen:

```csharp
byte num = 0xA;
int i = 5;
char c = 'Z';
```

Werttypen sind *versiegelt* (sealed). Dies bedeutet z.B., dass Sie keinen Typ von <xref:System.Int32?displayProperty=nameWithType> ableiten können und dass eine Struktur nicht von einer benutzerdefinierten Klasse oder Struktur erben kann, weil eine Struktur nur von <xref:System.ValueType?displayProperty=nameWithType> erben kann. Eine Struktur kann jedoch eine oder mehrere Schnittstellen implementieren. Sie können einen Strukturtyp in einen Schnittstellentyp umwandeln, der von diesem implementiert wird. Dadurch wird ein *Boxing*-Vorgang gestartet, mit dem die Struktur von einem Verweistypobjekt im verwalteten Heap umschlossen wird. Boxing-Vorgänge werden auch ausgeführt, wenn Sie einen Werttyp an eine Methode übergeben, die <xref:System.Object?displayProperty=nameWithType> oder einen beliebigen Schnittstellentyp als Eingabeparameter akzeptiert. Weitere Informationen finden Sie unter [Boxing und Unboxing](./boxing-and-unboxing.md).

Sie können das [struct](../../language-reference/keywords/struct.md)-Schlüsselwort verwenden, um eigene benutzerdefinierte Werttypen zu erstellen. In der Regel wird eine Struktur als Container für einen kleinen Satz verwandter Variablen verwendet, wie im folgenden Beispiel dargestellt:

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

Weitere Informationen über Strukturen finden Sie unter [Strukturen](../classes-and-structs/structs.md). Weitere Informationen über Werttypen in .NET finden Sie unter [Werttypen](../../language-reference/keywords/value-types.md).

Die andere Kategorie von Werttypen ist [enum](../../language-reference/keywords/enum.md). Eine Enumeration definiert einen Satz benannter ganzzahliger Konstanten. So enthält z.B. die <xref:System.IO.FileMode?displayProperty=nameWithType>-Enumeration in der .NET-Klassenbibliothek mehrere benannte ganzzahlige Konstanten, die festlegen, wie eine Datei geöffnet werden soll. Die Definition erfolgt wie im folgenden Beispiel:

[!code-csharp[csProgGuideTypes#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#44)]

Die `System.IO.FileMode.Create`-Konstante besitzt den Wert 2. Der Name ist jedoch für Personen, die den Quellcode lesen, viel aussagekräftiger. Aus diesem Grund ist es besser, anstelle von Konstantenliteralen Enumerationen zu verwenden. Weitere Informationen finden Sie unter <xref:System.IO.FileMode?displayProperty=nameWithType>.

Alle Enumerationen erben von <xref:System.Enum?displayProperty=nameWithType>, was wiederum von <xref:System.ValueType?displayProperty=nameWithType> erbt. Alle Regeln, die für Strukturen gelten, gelten auch für Enumerationen. Weitere Informationen über Enumerationen finden Sie unter [Enumerationstypen](../enumeration-types.md).

### <a name="reference-types"></a>Verweistypen

Ein Typ, der als [Klasse](../../language-reference/keywords/class.md), [Delegat](../../language-reference/builtin-types/reference-types.md), Array oder [Schnittstelle](../../language-reference/keywords/interface.md) definiert ist, ist ein *Referenztyp*. Wenn Sie zur Laufzeit eine Variable eines Referenztyps deklarieren, enthält die Variable zunächst den Wert [NULL](../../language-reference/keywords/null.md), bis Sie explizit ein Objekt mithilfe des Operators [new](../../language-reference/operators/new-operator.md) erstellen oder ihr ein Objekt zuweisen, das, wie im folgenden Beispiel gezeigt wird, an anderer Stelle mithilfe des Operators `new` erstellt wurde:

```csharp
MyClass mc = new MyClass();
MyClass mc2 = mc;
```

Eine Schnittstelle muss zusammen mit einem Klassenobjekt initialisiert werden, von dem sie implementiert wird. Wenn `MyClass` von `IMyInterface` implementiert wird, erstellen Sie eine Instanz von `IMyInterface`, wie im folgenden Beispiel dargestellt:

```csharp
IMyInterface iface = new MyClass();
```

Beim Erstellen des Objekts wird der Speicher im verwalteten Heap belegt. Die Variable enthält lediglich einen Verweis auf den Speicherort des Objekts. Für Typen im verwalteten Heap ist Mehraufwand erforderlich, wenn sie zugewiesen werden und wenn sie von der automatischen Speicherverwaltungsfunktion der CLR freigegeben werden, was als *Garbage Collection* bezeichnet wird. Die Garbage Collection ist jedoch auch stark optimiert. In den meisten Szenarien führt sie nicht zu einem Leistungsproblem. Weitere Informationen zur Garbage Collection finden Sie unter [Automatische Speicherverwaltung](../../../standard/automatic-memory-management.md).

Alle Arrays sind Referenztypen, selbst wenn ihre Elemente Werttypen sind. Arrays werden implizit von der <xref:System.Array?displayProperty=nameWithType>-Klasse abgeleitet. Sie deklarieren und verwenden diese jedoch mit der vereinfachten, von C# bereitgestellten Syntax, wie im folgenden Beispiel dargestellt:

[!code-csharp[csProgGuideTypes#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#45)]

Referenztypen bieten volle Vererbungsunterstützung. Wenn Sie eine Klasse erstellen, können Sie von einer anderen Schnittstelle oder Klasse erben, die nicht als [versiegelt](../../language-reference/keywords/sealed.md) definiert ist. Andere Klassen können von Ihrer Klasse erben und die virtuellen Methoden überschreiben. Weitere Informationen zum Erstellen eigener Klassen finden Sie unter [Klassen und Strukturen](../classes-and-structs/index.md). Weitere Informationen zur Vererbung und zu virtuellen Methoden finden Sie unter [Vererbung](../classes-and-structs/inheritance.md).

## <a name="types-of-literal-values"></a>Typen von Literalwerten

In C# erhalten Literalwerte einen Typ vom Compiler. Sie können festlegen, wie ein numerisches Literal eingegeben werden soll, indem Sie am Ende der Zahl einen Buchstaben anfügen. Um z. B. anzugeben, dass der Wert 4.56 als Gleitkommazahl behandelt werden soll, fügen Sie nach der Zahl `4.56f` ein "f" oder "F" an: Wenn kein Buchstabe angefügt wird, leitet der Compiler einen Typ für das Literal ab. Weitere Informationen darüber, welche Typen mit Buchstabensuffixen angegeben werden können, finden Sie auf den Referenzseiten für einzelne Typen unter [Werttypen](../../language-reference/keywords/value-types.md).

Da Literale typisiert sind und alle Typen letztlich von <xref:System.Object?displayProperty=nameWithType> abgeleitet werden, können Sie Code der folgenden Art erstellen und kompilieren:

[!code-csharp[csProgGuideTypes#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#37)]

## <a name="generic-types"></a>Generische Typen

Ein Typ kann mit einem oder mehreren *Typparametern* deklariert werden, die als Platzhalter für den eigentlichen Typ verwendet werden (den *konkreten Typ*), der vom Clientcode beim Erstellen einer Instanz des Typs bereitgestellt wird. Solche Typen werden als *generische Typen* bezeichnet. Beispielsweise besitzt der .NET-Typ <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> einen Typparameter, dem üblicherweise der Name *T* gegeben wird. Beim Erstellen einer Instanz des Typs geben Sie die Objekte an, die die Liste enthalten soll, z. B. string:

```csharp
List<string> stringList = new List<string>();
stringList.Add("String example");
// compile time error adding a type other than a string:
stringList.Add(4);
```

Die Verwendung des Typparameters ermöglicht die Wiederverwendung der Klasse für beliebige Elementtypen, ohne die einzelnen Elemente in [object](../../language-reference/builtin-types/reference-types.md) konvertieren zu müssen. Generische Auflistungsklassen werden als *stark typisierte Auflistungen* bezeichnet, weil der Compiler den jeweiligen Typ der Elemente in der Auflistung kennt und zur Kompilierzeit einen Fehler auslösen kann, wenn Sie beispielsweise versuchen, dem `stringList`-Objekt im vorherigen Beispiel eine ganze Zahl hinzuzufügen. Weitere Informationen finden Sie unter [Generics](../generics/index.md).

## <a name="implicit-types-anonymous-types-and-nullable-value-types"></a>Implizite Typen, anonyme Typen und Werttypen, die Nullwerte zulassen

Wie bereits zuvor erläutert, können Sie eine lokale Variable (jedoch keine Klassenmember) implizit eingeben, indem Sie das [var](../../language-reference/keywords/var.md)-Schlüsselwort verwenden. Die Variable erhält weiterhin zur Kompilierzeit einen Typ, aber der Typ wird vom Compiler bereitgestellt. Weitere Informationen zu finden Sie unter [Implizit typisierte lokale Variablen](../classes-and-structs/implicitly-typed-local-variables.md).

In einigen Fällen ist es unpraktisch, einen benannten Typ für einfache Sätze verwandter Werte zu erstellen, die nicht außerhalb von Methodengrenzen gespeichert oder übergeben werden sollen. Sie können für diesen Zweck *anonyme Typen* erstellen. Weitere Informationen finden Sie unter [Anonyme Typen](../classes-and-structs/anonymous-types.md).

Gewöhnliche Werttypen können den Wert [NULL](../../language-reference/keywords/null.md) nicht aufweisen. Sie können jedoch auf NULL festlegbare Werttypen erstellen, indem Sie nach dem Typ ein `?` anfügen. Zum Beispiel ist `int?` ein `int`-Typ, der auch den Wert [NULL](../../language-reference/keywords/null.md) aufweisen kann. Werttypen, die Nullwerte zulassen, sind Instanzen vom generischen Strukturtyp <xref:System.Nullable%601?displayProperty=nameWithType>. Werttypen, die Nullwerte zulassen, sind besonders hilfreich, wenn Sie Daten an und aus Datenbanken übergeben, in denen die numerischen Werte NULL sein können. Weitere Informationen finden Sie unter [Werttypen, die Nullwerte zulassen](../../language-reference/builtin-types/nullable-value-types.md).

## <a name="related-sections"></a>Verwandte Abschnitte

Weitere Informationen finden Sie unter den folgenden Themen:

- [Umwandlung und Typkonvertierungen](./casting-and-type-conversions.md)

- [Boxing und Unboxing](./boxing-and-unboxing.md)

- [Verwenden von dynamischen Typen](./using-type-dynamic.md)

- [Werttypen](../../language-reference/keywords/value-types.md)

- [Verweistypen](../../language-reference/keywords/reference-types.md)

- [Klassen und Strukturen](../classes-and-structs/index.md)

- [Anonyme Typen](../classes-and-structs/anonymous-types.md)

- [Generics](../generics/index.md)

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../language-reference/index.md)
- [C#-Programmierhandbuch](../index.md)
- [Konvertierung von XML-Datentypen](../../../standard/data/xml/conversion-of-xml-data-types.md)
- [Integrale Typen](../../language-reference/builtin-types/integral-numeric-types.md)
