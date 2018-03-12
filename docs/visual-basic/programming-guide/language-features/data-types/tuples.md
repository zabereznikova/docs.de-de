---
title: Tupel in Visual Basic
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf26b7ce58c1e20fbbe5043cbd2acfd5712837fa
ms.sourcegitcommit: d95a91d685565f4d95c8773b558752864a6a3d7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2018
---
# <a name="tuples-visual-basic"></a>Tupel (Visual Basic)

Visual Basic 2017 ab, die Sprache Visual Basic bietet integrierte Unterstützung für Tupel, mit der, Tupel erstellen und den Zugriff auf die Elemente von Tupeln einfacher. Ein Tupel ist ein Lightweight-Datenstruktur, die eine bestimmte Anzahl und die Sequenz von Werten aufweist. Wenn Sie das Tupel instanziieren, definieren Sie die Anzahl und den Datentyp der einzelnen Wert (oder Element). Ein 2-Tupel (oder ein Paar) hat beispielsweise zwei Elemente auf. Die erste ist möglicherweise eine `Boolean` Wert, während die zweite ist eine `String`. Da Tupel mehrere Werte in ein einzelnes Objekt speichern erleichtern, werden sie häufig als einfache Möglichkeit, mehrere Werte zurückgegeben werden, von einer Methode verwendet.

> [!IMPORTANT]
> Tupel unterstützt wird, muss die <xref:System.ValueTuple> Typ. Wenn der .NET Framework-4.7 nicht installiert ist, müssen Sie das NuGet-Paket hinzufügen `System.ValueTuple`, die auf der NuGet Gallery verfügbar ist. Ohne dieses Paket können Sie erhalten einen Kompilierungsfehler wie "Vordefinierte Typ 'ValueTuple(Of,,,)' nicht definiert oder importiert wird."

## <a name="instantiating-and-using-a-tuple"></a>Instanziieren und verwenden ein Tupel

Instanziieren Sie ein Tupel durch die Werte durch Kommas getrennte Instant Messaging-Diensten Klammern einschließen. Jeder dieser Werte wird dann ein Feld des Tupels. Z. B. der folgende Code definiert eine Triple (oder 3-Tupel) mit einem `Date` als ersten Wert ein `String` als den zweiten und eine `Boolean` als den dritten.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

Wird standardmäßig der Name jedes Felds in einem Tupel besteht aus der Zeichenfolge `Item` zusammen mit dem Feld einsbasierte Positionen im Tupel. Für diese 3-Tupel die `Date` Feld ist `Item1`, `String` Feld ist `Item2`, und die `Boolean` Feld ist `Item3`. Das folgende Beispiel zeigt die Werte der Felder des Tupels in der vorherigen Codezeile instanziiert

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

Die Felder eines Visual Basic-Tupels sind Lese-/ Schreibzugriff. Nachdem Sie ein Tupel instanziiert haben, können Sie dessen Werte ändern. Im folgende Beispiel ändert zwei der drei Felder des Tupels im vorherigen Beispiel erstellt und das Ergebnis wird angezeigt.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>Instanziieren und verwenden eine benannte Tupel

Statt die Standardnamen für ein Tupel Felder, instanziieren Sie ein *mit dem Namen Tupel* durch das Tupel-Elementen mit Ihren eigenen Namen zugewiesen. Das Tupel-Felder können dann durch ihre zugewiesenen Namen zugegriffen werden *oder* durch ihre Standardnamen. Das folgende Beispiel instanziiert die gleiche 3-Tupel als zuvor mit dem Unterschied, dass es das erste Feld explizit benannt `EventDate`, das zweite `Name`, und der dritte `IsHoliday`. Es dann zeigt die Feldwerte, ändert sie und die Feldwerte erneut angezeigt.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>Abgeleitete Tupel Elementnamen

Beginnend mit Visual Basic 15.3, kann Visual Basic die Namen der Tupelelemente ableiten; Sie müssen keinen explizit zuweisen. Abgeleitete Tupel Namen sind hilfreich, wenn Sie ein Tupel aus einem Satz von Variablen initialisieren, und der Elementname Tupel mit dem Variablennamen identisch sein sollen. 

Das folgende Beispiel erstellt eine `stateInfo` Tupel, das drei explizit enthält benannten Elementen, `state`, `stateName`, und `capital`. Beachten Sie, dass bei der Benennung der Elemente, Tupel Initialisierung die Anweisung einfach benannten Elemente der Werte von gleichnamigen Variablen weist.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
Da Elemente und Variablen, die denselben Namen haben, kann die Visual Basic-Compiler die Namen der Felder, wie im folgenden Beispiel gezeigt ableiten.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

Um interred Tupel Elementnamen zu aktivieren, müssen Sie die Version von Visual Basic-Compiler in Visual Basic-Projekt verwendet definieren (\*.vbproj) Datei: 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 
```

Die Versionsnummer kann eine beliebige Version von Visual Basic-Compiler 15.3 ab. Anstatt eine feste Programmierung einer bestimmten Compilerversion, können Sie auch "Letzten" angeben, als Wert des `LangVersion` , kompilieren Sie mit der neuesten Version von Visual Basic-Compiler, die auf Ihrem System installiert.

In einigen Fällen der Visual Basic-Compiler nicht ableiten der Elementname Tupel aus dem Namen der Kandidat, und das Tupel Feld kann nur mit dem Standardnamen wie verwiesen werden `Item1`, `Item2`usw. Dazu gehören:

- Der Kandidat-Name ist identisch mit den Namen eines Members Tupel wie `Item3`, `Rest`, oder `ToString`.

- Der Name der Kandidat ist im Tupel dupliziert.
 
Feld die Ableitung von Namen schlägt fehl, Visual Basic wird nicht generiert einen Compilerfehler, noch ist eine Ausnahme, die zur Laufzeit ausgelöst. Stattdessen Tupel Felder müssen verwiesen werden durch ihre vordefinierten Namen, z. B. `Item1` und `Item2`. 
  
## <a name="tuples-versus-structures"></a>Tupel im Vergleich zu Strukturen

Ein Visual Basic-Tupel ist ein Werttyp, der eine Instanz einer von der eine **System.ValueTuple** generische Typen. Z. B. die `holiday` im vorherigen Beispiel definierte Tupel ist eine Instanz der <xref:System.ValueTuple%603> Struktur. Es wurde entwickelt, um einen einfachen Container für Daten werden. Da das Tupel zielt darauf ab, um es einfach, um ein Objekt mit mehreren Datenelementen erstellen können, fehlen einige der Funktionen, die möglicherweise eine benutzerdefinierte Struktur. Dazu gehören:

- Kundenelemente. Sie können nicht Ihre eigenen Eigenschaften, Methoden oder Ereignisse für ein Tupel definieren.

- Überprüfung. Die Daten, die Felder zugewiesen sind, kann nicht überprüft werden.

- Unveränderlichkeit. Visual Basic-Tupeln sind änderbar. Im Gegensatz dazu kann eine benutzerdefinierte Struktur Sie steuern, ob eine Instanz änderbare oder unveränderlich ist.

Wenn Sie benutzerdefinierte Elemente, die Eigenschaft und die feldvalidierung oder die Unveränderlichkeit wichtig sind, verwenden Sie das Visual Basic [Struktur](../../../language-reference/statements/structure-statement.md) Anweisung, um einen benutzerdefinierten Typ definieren.

Ein Visual Basic-Tupel Unterstützungsobjekt für Datenobjekte erbt Member seiner **ValueTuple** Typ. Zusätzlich zu den zugehörigen Felder gehören dazu die folgenden Methoden:

| Member | Beschreibung |
| ---|---|
| CompareTo | Vergleicht das aktuelle Tupel in einer anderen Tupel mit derselben Anzahl von Elementen an. |
| gleich | Bestimmt, ob das aktuelle Tupel an eine andere Tupel oder Objekt entspricht. |
| GetHashCode | Berechnet den Hashcode für die aktuelle Instanz. |
| ToString | Gibt die Zeichenfolgendarstellung dieses Tupel, im Format `(Item1, Item2...)`, wobei `Item1` und `Item2` die Werte der Felder für das Tupel darstellen. |

Darüber hinaus die **ValueTuple** Typen implementieren <xref:System.Collections.IStructuralComparable> und <xref:System.Collections.IStructuralEquatable> Schnittstellen, die Ihnen ermöglichen, die Kunden vergleichen zu definieren.

## <a name="assignment-and-tuples"></a>Zuweisung und Tupel

Visual Basic unterstützt die Zuordnung zwischen Tupeltypen, die die gleiche Anzahl von Feldern verfügen. Die Feldtypen können konvertiert werden, wenn eine der folgenden Aussagen zutrifft:

- Die Quell- und Ziel-Feld sind vom gleichen Typ.

- Eine Konvertierung erweiternde (oder implizite) des Quelltyps in den Zieltyp definiert ist. 

- `Option Strict` ist `On`, und eine (oder explizite) einschränkende Konvertierung des Quelltyps in den Zieltyp definiert ist. Diese Konvertierung kann eine Ausnahme ausgelöst, wenn der Quellwert außerhalb des Bereichs des Zieltyps liegt.

Andere Konvertierungen gelten nicht für Zuordnungen. Sehen wir uns die Arten von Zuweisungen an, die zwischen Tupeltypen zulässig sind.

Berücksichtigen Sie diese Variablen, die in den folgenden Beispielen verwendet werden:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

Die ersten beiden Variablen `unnamed` und `anonymous`, haben keine semantische Namen für die Felder angegeben. Die Feldnamen werden standardmäßig `Item1` und `Item2`. Die letzten beiden Variablen `named` und `differentName` semantische Feldnamen haben. Beachten Sie, dass diese zwei Tupel unterschiedliche Namen für die Felder besitzen.

Alle vier diese Tupel haben die gleiche Anzahl von Feldern (bezeichnet als "Stelligkeit"), und die Datentypen dieser Felder identisch sind. Daher funktionieren alle Zuweisungen:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Beachten Sie, dass die Namen der Tupel nicht zugewiesen sind. Die Werte der Felder werden nach der Reihenfolge der Felder im Tupel zugewiesen.

Beachten Sie, dass wir zuweisen können die `named` Tupel für die `conversion` Tupel, obwohl das erste Feld der `named` ist ein `Integer`, und das erste Feld der `conversion` ist eine `Long`. Diese Zuweisung ist erfolgreich, da es sich bei Konvertierung einer `Integer` auf eine `Long` ist eine erweiternde Konvertierung.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tupel mit verschiedenen Anzahlen von Felder sind nicht zugeordnet werden kann:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>Tupel als Methodenrückgabewert

Eine Methode kann nur einen einzelnen Wert zurückgeben. In vielen Fällen jedoch soll einen Methodenaufruf an mehrere Werte zurückgegeben werden. Es gibt mehrere Möglichkeiten, diese Einschränkung zu umgehen:

- Sie können eine benutzerdefinierte Klasse oder Struktur erstellen, dessen Eigenschaften oder Felder darstellen, von der Methode zurückgegebenen Werte. Daher ist eine Heavyweight-Lösung. Es erfordert, dass Sie einen benutzerdefinierten Typ definieren, deren einzige zum Abrufen der Werte aus einem Methodenaufruf dient.

- Sie können einen einzelnen Wert zurückgeben, von der Methode und die verbleibenden Werte zurück, durch die sie als Verweis an die Methode übergeben werden. Führen Sie dazu den Aufwand für das Instanziieren einer Variablen und Risiken, die den Wert der Variablen, die Sie als Verweis übergeben versehentlich überschrieben.

- Sie können ein Tupel, eine einfache Lösung bietet für das Abrufen von mehreren Rückgabewerten.

Z. B. die **TryParse** Methoden in .NET Rückgabe einer `Boolean` Wert, der angibt, ob der Analysevorgang erfolgreich war. Das Ergebnis des Analysevorgangs wird in einer Variablen als Verweis an die Methode übergebene zurückgegeben. In der Regel wird ein Aufruf der einer Analysemethode, z. B. <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> sieht wie folgt:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

Wir können ein Tupel aus der Analysevorgang zurückgeben, wenn es den Aufruf zum Umschließen der <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> Methode in eigenen-Methode. Im folgenden Beispiel `NumericLibrary.ParseInteger` Aufrufe der <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> Methode und eine benannte Tupel mit zwei Elementen zurück. 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

Sie können dann die Methode mit Code wie folgt aufrufen:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Visual Basic-Tupel und Tupel in .NET Framework

Ein Visual Basic-Tupel ist eine Instanz einer von der **System.ValueTuple** generischen Typen, die in der .NET Framework-4.7 eingeführt wurden. .NET Framework enthält auch eine Reihe von generischen **System.Tuple** Klassen. Diese Klassen unterscheiden sich jedoch von Visual Basic-Tupeln und **System.ValueTuple** generische Typen, die eine Reihe von Möglichkeiten:

- Die Elemente der **Tupel** Klassen sind Eigenschaften, die mit dem Namen `Item1`, `Item2`und so weiter. In Visual Basic-Tupeln und **ValueTuple** Tupelelementen-Datentypen sind Felder.

- Sie können keine Elemente des aussagekräftige Namen zuweisen eine **Tupel** Instanz oder eine **ValueTuple** Instanz. Visual Basic können Sie Namen zuweisen, die die Bedeutung der Felder zu kommunizieren.

- Die Eigenschaften einer **Tupel** Instanz schreibgeschützt sind, die Tupel sind unveränderlich. In Visual Basic-Tupeln und **ValueTuple** Typen Tupel Felder sind Lese-/ Schreibzugriff; die Tupel sind änderbar.

- Die generische **Tupel** -Typen sind Referenztypen. Mit diesen **Tupel** Typen bedeutet, dass das Zuordnen von Objekten. Auf dem langsamsten Pfad kann das einen messbaren Einfluss auf die Leistung Ihrer Anwendungen haben. Visual Basic-Tupeln und **ValueTuple** Typen sind Werttypen.

Erweiterungsmethoden in den <xref:System.TupleExtensions> Klasse erleichtern das Konvertieren zwischen Tupel Visual Basic und .NET **Tupel** Objekte. Die **ToTuple** Methode konvertiert ein Visual Basic-Tupel in einer .NET **Tupel** -Objekt, und die **ToValueTuple** Methode konvertiert ein .NET **Tupel** Um ein Visual Basic-Tupel-Objekt.

Das folgende Beispiel erstellt ein Tupel, konvertiert es in einer .NET **Tupel** Objekt und konvertiert sie zurück in ein Visual Basic-Tupel. Im Beispiel vergleicht dieses Tupel mit dem ursprünglichen Stellen Sie sicher, dass sie gleich sind.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>Siehe auch

[Sprachreferenz zu Visual Basic](index.md)  
