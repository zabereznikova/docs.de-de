---
title: Tupel
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
ms.openlocfilehash: 378ee4e7d3a3b106b719e5da819b09f336ff218e
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226659"
---
# <a name="tuples-visual-basic"></a>Tupel (Visual Basic)

Ab Visual Basic 2017 bietet die Visual Basic Sprache integrierte Unterstützung für Tupel, die das Erstellen von Tupeln und den Zugriff auf die Elemente von Tupeln vereinfachen. Ein Tupel ist eine vereinfachte Datenstruktur, die über eine bestimmte Anzahl und Sequenz von Werten verfügt. Wenn Sie das Tupel instanziieren, definieren Sie die Zahl und den Datentyp der einzelnen Werte (oder Elemente). Ein 2-Tupel (oder-Paar) verfügt beispielsweise über zwei-Elemente. Der erste Wert ist möglicherweise ein- `Boolean` Wert, während der zweite ein-Wert ist `String` . Da Tupel die Speicherung mehrerer Werte in einem einzelnen Objekt vereinfachen, werden diese häufig als einfache Methode zum Zurückgeben mehrerer Werte aus einer Methode verwendet.

> [!IMPORTANT]
> Tupelunterstützung erfordert den- <xref:System.ValueTuple> Typ. Wenn die .NET Framework 4,7 nicht installiert ist, müssen Sie das nuget-Paket hinzufügen `System.ValueTuple` , das im nuget-Katalog verfügbar ist. Ohne dieses Paket erhalten Sie möglicherweise einen Kompilierungsfehler ähnlich dem folgenden: "der vordefinierte Typ" valuetuple (of,,,) "ist nicht definiert oder importiert."

## <a name="instantiating-and-using-a-tuple"></a>Instanziieren und Verwenden eines Tupels

Sie instanziieren ein Tupel durch das Einschließen der durch Trennzeichen getrennten Werte in Klammern. Jeder dieser Werte wird dann zu einem Feld des Tupels. Im folgenden Code wird z. b. ein Triple (oder ein 3-Tupel) mit einem `Date` als ersten Wert, a `String` als zweiter Wert und als `Boolean` Dritter als Dritter definiert.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

Standardmäßig besteht der Name jedes Felds in einem Tupel aus der Zeichenfolge `Item` zusammen mit der einbasierten Position des Felds im Tupel. Bei diesem 3-Tupel ist das `Date` Feld `Item1` , das `String` Feld ist `Item2` , und das `Boolean` Feld ist `Item3` . Im folgenden Beispiel werden die Werte der Felder des Tupels angezeigt, die in der vorherigen Codezeile instanziiert wurden.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

Die Felder eines Visual Basic Tupels sind Lese-/Schreibzugriff. Nachdem Sie ein Tupel instanziiert haben, können Sie seine Werte ändern. Im folgenden Beispiel werden zwei der drei Felder des Tupels geändert, das im vorherigen Beispiel erstellt wurde, und das Ergebnis wird angezeigt.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>Instanziieren und Verwenden eines benannten Tupels

Anstatt Standardnamen für die Felder eines Tupels zu verwenden, können Sie ein *benanntes Tupel* instanziieren, indem Sie den Elementen des Tupels eigene Namen zuweisen. Auf die Felder des Tupels kann dann über ihre zugewiesenen Namen *oder* über deren Standardnamen zugegriffen werden. Im folgenden Beispiel wird das gleiche 3-Tupel wie zuvor instanziiert, mit der Ausnahme, dass es explizit das erste Feld `EventDate` , das zweite `Name` und das dritte benennt `IsHoliday` . Anschließend werden die Feldwerte angezeigt, Sie werden geändert, und die Feldwerte werden erneut angezeigt.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>Abgeleitete Tupelelementnamen

Ab Visual Basic 15,3 können Visual Basic die Namen der Tupelelemente ableiten. Sie müssen Sie nicht explizit zuweisen. Abherzustellende tupelnamen sind hilfreich, wenn Sie ein Tupel aus einem Satz von Variablen initialisieren und der tupelelementname dem Variablennamen entsprechen soll.

Im folgenden Beispiel wird ein `stateInfo` Tupel erstellt, das die drei explizit benannten Elemente, `state` , `stateName` und enthält `capital` . Beachten Sie, dass die tupelinitialisierungs-Anweisung beim Benennen der Elemente einfach die benannten Elemente den Werten der identisch benannten Variablen zuweist.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]

Da Elemente und Variablen denselben Namen haben, kann der Visual Basic Compiler die Namen der Felder ableiten, wie im folgenden Beispiel gezeigt.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

Sie müssen die Version der Visual Basic-compilerin definieren, die in der Visual Basic Project- \* Datei (. vbproj) verwendet werden soll, um herabherzuordnenden tupelelementnamen zu aktivieren:

```xml
<PropertyGroup>
  <LangVersion>15.3</LangVersion>
</PropertyGroup>
```

Die Versionsnummer kann eine beliebige Version des Visual Basic Compilers sein, beginnend mit 15,3. Anstatt eine bestimmte Compilerversion hart zu codieren, können Sie auch "Latest" als Wert von angeben, `LangVersion` um mit der neuesten Version des Visual Basic Compilers zu kompilieren, die auf Ihrem System installiert ist.

Weitere Informationen finden Sie unter [Festlegen der Visual Basic Sprachversion](../../../language-reference/configure-language-version.md).

In einigen Fällen kann der Visual Basic Compiler den tupelelementnamen nicht aus dem Kandidaten Namen ableiten, und auf das tupelfeld kann nur mithilfe seines Standard namens verwiesen werden, z `Item1` . b `Item2` ., usw. Hierzu gehören:

- Der Kandidaten Name ist identisch mit dem Namen eines tupelmembers, z `Item3` . b., `Rest` oder `ToString` .

- Der Kandidaten Name wird im Tupel dupliziert.

Wenn der Rückschluss von Feld Namen fehlschlägt, generiert Visual Basic weder einen Compilerfehler noch eine Ausnahme, die zur Laufzeit ausgelöst wird. Stattdessen müssen auf tupelfelder durch ihre vordefinierten Namen, wie z. b `Item1` . und, verwiesen werden `Item2` .

## <a name="tuples-versus-structures"></a>Tupel im Vergleich zu Strukturen

Ein Visual Basic Tupel ist ein Werttyp, bei dem es sich um eine Instanz eines der generischen **System. valuetuple** -Typen handelt. Beispielsweise ist das `holiday` Tupel, das im vorherigen Beispiel definiert wurde, eine Instanz der- <xref:System.ValueTuple%603> Struktur. Es ist als Lightweight-Container für Daten konzipiert. Da das Tupel darauf abzielt, ein Objekt mit mehreren Datenelementen zu erstellen, fehlen einige der Features, die eine benutzerdefinierte Struktur aufweisen kann. Dazu gehören:

- Benutzerdefinierte Member. Sie können keine eigenen Eigenschaften, Methoden oder Ereignisse für ein Tupel definieren.

- Validierung. Die den Feldern zugewiesenen Daten können nicht überprüft werden.

- Unveränderlichkeit. Visual Basic Tupel sind änderbar. Im Gegensatz dazu können Sie mit einer benutzerdefinierten Struktur steuern, ob eine Instanz änderbar oder unveränderlich ist.

Wenn benutzerdefinierte Member, die Validierung von Eigenschaften und Feldern oder Unveränderlichkeit wichtig sind, sollten Sie die Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) -Anweisung verwenden, um einen benutzerdefinierten Werttyp zu definieren.

Ein Visual Basic Tupel erbt die Member seines **valuetuple** -Typs. Zusätzlich zu den zugehörigen Feldern umfassen diese die folgenden Methoden:

| Member | Beschreibung |
| ---|---|
| CompareTo | Vergleicht das aktuelle Tupel mit einem anderen Tupel mit der gleichen Anzahl von Elementen. |
| Ist gleich | Bestimmt, ob das aktuelle Tupel einem anderen Tupel oder Objekt entspricht. |
| GetHashCode | Berechnet den Hashcode für die aktuelle Instanz. |
| ToString | Gibt die Zeichen folgen Darstellung dieses Tupels zurück, die das Formular annimmt `(Item1, Item2...)` , wobei `Item1` und `Item2` die Werte der Felder des Tupels darstellen. |

Außerdem implementieren die **valuetuple** <xref:System.Collections.IStructuralComparable> -Typen-und- <xref:System.Collections.IStructuralEquatable> Schnittstellen, die es Ihnen ermöglichen, Kunden Vergleiche zu definieren.

## <a name="assignment-and-tuples"></a>Zuweisung und Tupel

Visual Basic unterstützt die Zuweisung zwischen Tupeltypen, die über die gleiche Anzahl von Feldern verfügen. Die Feldtypen können konvertiert werden, wenn eine der folgenden Punkte zutrifft:

- Das Quell-und Zielfeld weisen denselben Typ auf.

- Eine erweiternde (oder implizite) Konvertierung des Quell Typs in den Zieltyp ist definiert.

- `Option Strict`ist `On` , und eine einschränkende (oder explizite) Konvertierung des Quell Typs in den Zieltyp ist definiert. Diese Konvertierung kann eine Ausnahme auslösen, wenn der Quellwert außerhalb des Bereichs des Zieltyps liegt.

Andere Konvertierungen gelten nicht für Zuordnungen. Sehen wir uns die Arten von Zuweisungen an, die zwischen Tupeltypen zulässig sind.

Berücksichtigen Sie diese Variablen, die in den folgenden Beispielen verwendet werden:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

Die ersten beiden Variablen ( `unnamed` und) `anonymous` haben keine semantischen Namen für die Felder bereitgestellt. Die Feldnamen sind die Standardwerte `Item1` und `Item2` . Die letzten zwei Variablen `named` und `differentName` haben semantische Feldnamen. Beachten Sie, dass diese zwei Tupel unterschiedliche Namen für die Felder besitzen.

Alle vier dieser Tupel haben die gleiche Anzahl von Feldern (als "Stelligkeit" bezeichnet), und die Typen dieser Felder sind identisch. Daher funktionieren alle Zuweisungen:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Beachten Sie, dass die Namen der Tupel nicht zugewiesen sind. Die Werte der Felder werden nach der Reihenfolge der Felder im Tupel zugewiesen.

Beachten Sie schließlich, dass wir das `named` Tupel dem `conversion` Tupel zuweisen können, obwohl das erste Feld von `named` ein ist `Integer` und das erste Feld von `conversion` ein ist `Long` . Diese Zuweisung ist erfolgreich, da das Konvertieren `Integer` von in eine `Long` erweiternde Konvertierung ist.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tupel mit unterschiedlicher Anzahl von Feldern können nicht zugewiesen werden:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>Tupel als Methodenrückgabewert

Eine Methode kann nur einen einzelnen Wert zurückgeben. Häufig ist es jedoch ein Methoden aufzurufen, mehrere Werte zurückzugeben. Es gibt mehrere Möglichkeiten, diese Einschränkung zu umgehen:

- Sie können eine benutzerdefinierte Klasse oder Struktur erstellen, deren Eigenschaften oder Felder Werte darstellen, die von der-Methode zurückgegeben werden. Daher ist eine Lösung mit Schwergewicht. Es erfordert, dass Sie einen benutzerdefinierten Typ definieren, dessen einziger Zweck das Abrufen von Werten aus einem Methoden aufzurufen ist.

- Sie können einen einzelnen Wert aus der-Methode zurückgeben und die verbleibenden Werte zurückgeben, indem Sie Sie als Verweis an die-Methode übergeben. Dies umfasst den mehr Aufwand für die Instanziierung einer Variablen und die Risiken, die versehentlich den Wert der Variablen überschreiben, die Sie als Verweis übergeben.

- Sie können ein Tupel verwenden, das eine Lightweight-Lösung zum Abrufen mehrerer Rückgabewerte bereitstellt.

Die **tryanalyse** -Methoden in .net geben z. b `Boolean` . einen Wert zurück, der angibt, ob der Analyse Vorgang erfolgreich war. Das Ergebnis des-Vorgangs wird in einer Variablen zurückgegeben, die als Verweis an die-Methode ausgegeben wird. In der Regel sieht ein aufrufungs Methode wie <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> die folgende aus:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

Wir können ein Tupel aus dem erteilungsvorgang zurückgeben, wenn wir den Aufrufen der <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> Methode in unserer eigenen Methode einschließen. Im folgenden Beispiel `NumericLibrary.ParseInteger` Ruft die <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> -Methode auf und gibt ein benanntes Tupel mit zwei-Elementen zurück.

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

Anschließend können Sie die-Methode mit Code wie dem folgenden aufzurufen:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Visual Basic Tupel und Tupel in der .NET Framework

Ein Visual Basic Tupel ist eine Instanz eines der generischen **System. valuetuple** -Typen, die in der .NET Framework 4,7 eingeführt wurden. Die .NET Framework enthält auch einen Satz generischer **System. Tuple** -Klassen. Diese Klassen unterscheiden sich jedoch von Visual Basic Tupeln und den generischen **System. valuetuple** -Typen auf verschiedene Weise:

- Die Elemente der **tupelklassen** sind Eigenschaften namens `Item1` , `Item2` usw. In Visual Basic Tupel und den **valuetuple** -Typen sind Tupelelemente Felder.

- Sie können den Elementen einer **tupelinstanz** oder einer **valuetuple** -Instanz keine aussagekräftigen Namen zuweisen. Mit Visual Basic können Sie Namen zuweisen, die die Bedeutung der Felder übermitteln.

- Die Eigenschaften einer **tupelinstanz** sind schreibgeschützt. die Tupel sind unveränderlich. In Visual Basic Tupel und den **valuetuple** -Typen werden tupelfelder mit Lese-/Schreibzugriff. die Tupel sind änderbar.

- Die generischen **Tupeltypen** sind Verweis Typen. Die Verwendung dieser **Tupeltypen** bedeutet das Zuweisen von Objekten. Auf dem langsamsten Pfad kann das einen messbaren Einfluss auf die Leistung Ihrer Anwendungen haben. Visual Basic Tupel und die **valuetuple** -Typen sind Werttypen.

Erweiterungs Methoden in der- <xref:System.TupleExtensions> Klasse erleichtern das Konvertieren zwischen Visual Basic Tupeln und .net- **tupelobjekten** . Die Methode " **detuple** " konvertiert ein Visual Basic Tupel in ein .net- **tupelobjekt** , und die Methode " **devaluetuple** " konvertiert ein .net **Tupel** -Objekt in ein Visual Basic Tupel.

Im folgenden Beispiel wird ein Tupel erstellt, in ein .net- **tupelobjekt** konvertiert und wieder in ein Visual Basic Tupel konvertiert. Im Beispiel wird dann dieses Tupel mit dem ursprünglichen verglichen, um sicherzustellen, dass Sie gleich sind.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>Siehe auch

- [Sprachreferenz zu Visual Basic](index.md)
