---
title: Tupel in Visual Basic
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
ms.openlocfilehash: 146e9c2360cea153d2f487769d5b983516861e8d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663296"
---
# <a name="tuples-visual-basic"></a>Tupel (Visual Basic)

Starten Visual Basic 2017, Visual Basic-Sprache bietet integrierte Unterstützung für Tupel, mit der, Tupel erstellen und den Zugriff auf die Elemente der Tupel einfacher. Ein Tupel ist eine einfache Datenstruktur, die eine bestimmte Anzahl und die Sequenz von Werten verfügt. Wenn Sie das Tupel instanziieren, definieren Sie die Anzahl und den Datentyp der einzelnen Wert (oder Element). Ein 2-Tupel (oder ein Paar) enthält beispielsweise zwei Elemente auf. Die erste ist möglicherweise eine `Boolean` Wert, während die zweite ist ein `String`. Da Tupel zum Speichern mehrerer Werte in einem einzelnen Objekt erleichtern, werden sie häufig als eine einfache Möglichkeit, mehrere Werte aus einer Methode zurückgeben verwendet.

> [!IMPORTANT]
> Unterstützung für Tupel erfordert die <xref:System.ValueTuple> Typ. Wenn es sich bei .NET Framework 4.7 nicht installiert ist, müssen Sie das NuGet-Paket hinzufügen `System.ValueTuple`, das im NuGet-Katalog verfügbar ist. Ohne dieses Paket erhalten Sie möglicherweise einen Kompilierungsfehler ähnelt "Vordefinierte Typ 'ValueTuple(Of,,,)' nicht definiert oder importiert werden."

## <a name="instantiating-and-using-a-tuple"></a>Instanziieren und verwenden ein Tupel

Sie instanziieren ein Tupel, indem Sie die durch Trennzeichen getrennte Werte Im Klammern einschließen. Jeder dieser Werte wird dann ein Feld des Tupels. Z. B. der folgende Code definiert eine Triple (oder 3-Tupel) mit einem `Date` als ersten Wert ein `String` als den zweiten, und ein `Boolean` als den dritten.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

Wird standardmäßig der Name der einzelnen Felder in einem Tupel besteht aus der Zeichenfolge `Item` zusammen mit 1-basierte Position der Felder im Tupel. Für diese 3-Tupel die `Date` Feld `Item1`, wird die `String` Feld ist `Item2`, und die `Boolean` Feld `Item3`. Das folgende Beispiel zeigt die Werte der Felder des Tupels in der vorherigen Codezeile instanziiert

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

Die Felder eines Tupels Visual Basic sind Lese-/ Schreibzugriff. Nachdem Sie ein Tupel instanziiert haben, können Sie die Werte ändern. Im folgenden Beispiel ändert, zwei der drei Felder des Tupels im vorherigen Beispiel erstellt und das Ergebnis wird angezeigt.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>Instanziierung und Verwendung eines benannten Tupels

Statt die Standardnamen für des Tupels Felder, instanziieren Sie ein *benannter Tupel* durch Ihre eigenen Namen zuweisen, um Elemente des Tupels. Des Tupels Felder können dann durch ihre zugewiesenen Namen zugegriffen werden *oder* durch ihre Standardnamen. Das folgende Beispiel instanziiert die gleichen 3-Tupel wie zuvor, außer dass es explizit auf das erste Feld benennt `EventDate`, die zweite `Name`, und der dritte `IsHoliday`. Klicken Sie dann die Feldwerte angezeigt, geändert und die Feldwerte erneut angezeigt.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>Abgeleitete Tupelelementnamen

Ab Visual Basic 15.3, kann Visual Basic die Namen der Elemente des Tupels ableiten, Sie müssen keinen explizit zuweisen. Abgeleitete tupelnamen sind nützlich, wenn Sie ein Tupel aus einer Reihe von Variablen initialisieren, und der tupelelementname mit den Namen der Variablen identisch sein. 

Das folgende Beispiel erstellt eine `stateInfo` Tupel, das drei explizit enthält benannte Elemente, `state`, `stateName`, und `capital`. Beachten Sie, dass bei der Benennung der Elemente, die Anweisung zum Initialisieren der Tupel einfach die benannten Elemente weist die Werte der Variablen mit dem gleichen Namen.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
Da Elemente und Variablen den gleichen Namen haben, kann von Visual Basic-Compiler den Namen der Felder, wie im folgenden Beispiel gezeigt abgeleitet werden.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

Um abgeleitete tupelelementnamen zu aktivieren, müssen Sie die Version von Visual Basic-Compiler in Visual Basic-Projekt mit definieren (\*.vbproj) Datei: 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 
```

Die Versionsnummer kann jede Version von Visual Basic-Compiler ab Version 15.3 sein. Sie können anstatt einer hartcodierung einer bestimmten Compilerversion, auch "Latest" angeben, als der Wert des `LangVersion` kompilieren Sie mit der neuesten Version von Visual Basic-Compiler auf Ihrem System installiert.

Weitere Informationen finden Sie unter [Festlegen der Sprache Visual Basic-Version](../../../language-reference/configure-language-version.md).

In einigen Fällen kann Visual Basic-Compiler nicht ableiten der tupelelementname vom Namen Kandidaten aus, und das tupelfeld darf nur verwiesen werden mit den Standardnamen wie `Item1`, `Item2`usw. Dazu gehören:

- Namen des Kandidaten ist identisch mit den Namen eines Members Tupel, z. B. `Item3`, `Rest`, oder `ToString`.

- Namen des Kandidaten wird in das Tupel dupliziert.
 
Feld die Ableitung von Namen schlägt fehl, Visual Basic generiert einen Compilerfehler keine, noch ist eine Ausnahme, die zur Laufzeit ausgelöst. Stattdessen Tupelfeldern müssen verwiesen werden durch ihre vordefinierten Namen, z. B. `Item1` und `Item2`. 
  
## <a name="tuples-versus-structures"></a>Tupel im Vergleich zu Strukturen

Ein Visual Basic-Tupel ist ein Werttyp, der eine Instanz einer von der eine **System.ValueTuple** generische Typen. Z. B. die `holiday` im vorherigen Beispiel definierte Tupel ist eine Instanz der <xref:System.ValueTuple%603> Struktur. Es ist ein einfacher Container für Daten werden soll. Da das Tupel zielt darauf ab, um ein Objekt mit mehreren Datenelementen erstellen erleichtern, verfügt nicht über die sie einige der Features, die möglicherweise eine benutzerdefinierte Struktur. Dazu gehören:

- Benutzerdefinierte Elemente. Sie können keine eigenen Eigenschaften, Methoden oder Ereignisse für ein Tupel definieren.

- Die Überprüfung. Sie können nicht Feldern zugewiesenen Daten überprüfen.

- Unveränderlichkeit. Visual Basic-Tupel sind änderbar. Im Gegensatz dazu kann eine benutzerdefinierte Struktur Sie steuern, ob eine Instanz änderbare oder unveränderlich ist.

Wenn Sie benutzerdefinierte Elemente, die Eigenschaft und die Überprüfung oder die Unveränderlichkeit wichtig sind, verwenden Sie die Visual Basic [Struktur](../../../language-reference/statements/structure-statement.md) Anweisung, um einen benutzerdefinierten Typ definieren.

Ein Visual Basic-Tupel erbt die Member der **ValueTuple** Typ. Zusätzlich zu den Feldern gehören die folgenden Methoden:

| Member | Beschreibung |
| ---|---|
| CompareTo | Vergleicht das aktuelle Tupel in einer anderen Tupel mit der gleichen Anzahl von Elementen an. |
| gleich | Bestimmt, ob das aktuelle Tupel gleich einem anderen Tupel oder ein Objekt ist. |
| GetHashCode | Berechnet den Hashcode für die aktuelle Instanz. |
| ToString | Gibt eine Zeichenfolgendarstellung dieses Tupels, im Format `(Item1, Item2...)`, wobei `Item1` und `Item2` stellen die Werte des Tupels Felder. |

Darüber hinaus die **ValueTuple** Typen implementieren <xref:System.Collections.IStructuralComparable> und <xref:System.Collections.IStructuralEquatable> Schnittstellen, die Sie definieren Kunden vergleichen können.

## <a name="assignment-and-tuples"></a>Zuweisung und Tupel

Visual Basic unterstützt die Zuweisung zwischen Tupeltypen, die die gleiche Anzahl von Feldern aufweisen. Die Feldtypen können konvertiert werden, wenn eine der folgenden Aussagen zutrifft:

- Die Quelle und Ziel-Feld sind vom gleichen Typ.

- Eine erweiternde (oder implizite) Konvertierung des Quelltyps in den Zieltyp definiert ist. 

- `Option Strict` ist `On`, und eine einschränkende (oder explizite) Konvertierung des Quelltyps in den Zieltyp definiert ist. Diese Konvertierung kann eine Ausnahme auslösen, wenn der Quellwert außerhalb des Bereichs des Zieltyps liegt.

Andere Konvertierungen gelten nicht für Zuordnungen. Sehen wir uns die Arten von Zuweisungen an, die zwischen Tupeltypen zulässig sind.

Berücksichtigen Sie diese Variablen, die in den folgenden Beispielen verwendet werden:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

Die ersten zwei Variablen, `unnamed` und `anonymous`, haben keine semantische Namen für die Felder bereitgestellt. Die Feldnamen werden standardmäßig `Item1` und `Item2`. Die letzten zwei Variablen, `named` und `differentName` semantische Namen haben. Beachten Sie, dass diese zwei Tupel unterschiedliche Namen für die Felder besitzen.

Alle vier dieser Tupel haben die gleiche Anzahl von Feldern (als "Arity" bezeichnet), und die Typen dieser Felder sind identisch. Daher funktionieren alle Zuweisungen:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Beachten Sie, dass die Namen der Tupel nicht zugewiesen sind. Die Werte der Felder werden nach der Reihenfolge der Felder im Tupel zugewiesen.

Beachten Sie außerdem, dass wir zuweisen können die `named` das Tupel mit den `conversion` Tupel, obwohl das erste Feld der `named` ist ein `Integer`, und das erste Feld der `conversion` ist eine `Long`. Diese Zuweisung ist erfolgreich, da es sich bei Konvertierung einer `Integer` auf eine `Long` eine erweiternde Konvertierung ist.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tupel mit einer unterschiedlichen Anzahl von Feldern sind nicht zuweisbar:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>Tupel als Methodenrückgabewert

Eine Methode kann nur einen einzelnen Wert zurückgeben. In vielen Fällen jedoch, soll den Aufruf einer Methode mehrere Werte zurückgeben. Es gibt mehrere Möglichkeiten, diese Einschränkung zu umgehen:

- Sie können eine benutzerdefinierte Klasse oder Struktur, dessen Eigenschaften oder Felder darstellen, von der Methode zurückgegebenen Werte. Daher ist eine schwierige Lösung. Es ist erforderlich, dass Sie einen benutzerdefinierten Typ definieren, deren einziger Zweck ist, um Werte aus einem Methodenaufruf abzurufen.

- Sie können einen einzelnen Wert zurückgeben, von der Methode und die verbleibenden Werte durch Übergabe als Verweis auf die Methode zurück. Dies umfasst den Aufwand für das Instanziieren einer Variablen und Risiken, die unabsichtlich überschrieben den Wert der Variablen, die Sie als Verweis übergeben.

- Sie können ein Tupel, bietet eine einfache Lösung für das Abrufen von mehreren Rückgabewerten.

Z. B. die **TryParse** Methoden in .NET Rückgabe einer `Boolean` Wert, der angibt, ob der Analysevorgang erfolgreich war. Das Ergebnis des Analysevorgangs wird in einer Variablen, die als Verweis an die Methode übergeben wird zurückgegeben. In der Regel einen Aufruf der einer Analysemethode, z. B. <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> sieht wie folgt aus:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

Wir können ein Tupel in den Analysevorgang zurückgeben, wenn wir den Aufruf umschließen der <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> -Methode in unserer eigenen Methode. Im folgenden Beispiel `NumericLibrary.ParseInteger` Aufrufe der <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> Methode und gibt Sie einen benannten Tupel mit zwei Elementen zurück. 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

Sie können dann die Methode mit Code wie folgt aufrufen:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Visual Basic-Tupel und Tupel in .NET Framework

Ein Visual Basic-Tupel ist eine Instanz einer von der **System.ValueTuple** generischen Typen, die in .NET Framework 4.7 eingeführt wurden. .NET Framework enthält auch eine Reihe von generischen **System.Tuple** Klassen. Diese Klassen, unterscheiden sich jedoch von Visual Basic-Tupeln und **System.ValueTuple** generische Typen in eine Reihe von Möglichkeiten:

- Die Elemente der **Tupel** Klassen sind Eigenschaften, die mit dem Namen `Item1`, `Item2`und so weiter. In Visual Basic-Tupeln und **ValueTuple** Typen, Elemente des Tupels Felder sind.

- Sie können keine aussagekräftige Namen zuweisen, auf die Elemente der ein **Tupel** Instanz oder eine **ValueTuple** Instanz. Visual Basic können Sie Namen zuweisen, die die Bedeutung der Felder zu kommunizieren.

- Die Eigenschaften einer **Tupel** Instanz schreibgeschützt sind, die Tupel sind unveränderlich. In Visual Basic-Tupeln und **ValueTuple** Typen Tupelfeldern sind Lese-/ Schreibzugriff; die Tupel sind änderbar.

- Die generische **Tupel** -Typen sind Referenztypen. Mit diesen **Tupel** -Typen bedeutet, dass Objekte. Auf dem langsamsten Pfad kann das einen messbaren Einfluss auf die Leistung Ihrer Anwendungen haben. Visual Basic-Tupel und dem **ValueTuple** Typen sind Werttypen.

Erweiterungsmethoden in den <xref:System.TupleExtensions> Klasse erleichtern Ihnen die Konvertierung zwischen Tupel von Visual Basic und .NET **Tupel** Objekte. Die **ToTuple** -Methode konvertiert ein Visual Basic-Tupel in einer .NET **Tupel** -Objekt, und die **ToValueTuple** -Methode konvertiert ein .NET **Tupel** ein Visual Basic-Tupel-Objekt.

Das folgende Beispiel erstellt ein Tupel, konvertiert es in einer .NET **Tupel** -Objekt, und konvertiert sie in ein Visual Basic-Tupel zurück. Das Beispiel vergleicht dann dieses Tupels mit der ursprünglichen um sicherzustellen, dass sie gleich sind.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>Siehe auch

- [Sprachreferenz zu Visual Basic](index.md)
