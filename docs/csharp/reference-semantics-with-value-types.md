---
title: Verweissemantik mit Werttypen
description: Verstehen der Sprachfunktionen, die kopieren-Strukturen problemlos minimieren
author: billwagner
ms.author: wiwagn
ms.date: 11/10/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 9eeaf201c1f5a58044db62e356199b609c4c035a
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="reference-semantics-with-value-types"></a>Verweissemantik mit Werttypen

Ein Vorteil der Verwendung von Werttypen ist, dass sie häufig Heapzuordnungen vermeiden.
Der entsprechende Nachteil ist, dass sie nach Wert kopiert werden. Dieser Nachteil erschwert die Algorithmen optimieren, die auf große Mengen an Daten ausgeführt werden. Neue Sprachfeatures in c# 7.2 Geben Mechanismen, mit denen Pass-Verweissemantik mit Werttypen. Bei Verwendung dieser Funktionen mit Bedacht können Sie minimieren beide Zuordnungen und Kopiervorgänge. In diesem Artikel wird erklärt, diese neuen Features.

Ein Großteil der Beispielcode in diesem Artikel werden die Funktionen, die in c# 7.2 hinzugefügt veranschaulicht. Um diese Funktionen verwenden zu können, müssen Sie das Projekt zur Verwendung von C#-7.2 oder höher in Ihrem Projekt zu konfigurieren. Sie können Visual Studio verwenden, um es auszuwählen. Wählen Sie für jedes Projekt **Projekt** aus dem Menü **Eigenschaften**. Wählen Sie die **erstellen** Registerkarte, und klicken Sie auf **erweitert**. Von dort aus können Sie die Sprachversion konfigurieren. Wählen Sie entweder "7.2" oder "Letzter".  Alternativ können Sie bearbeiten die *Csproj* Datei, und fügen Sie den folgenden Knoten:

```XML
  <PropertyGroup>
    <LangVersion>7.2</LangVersion>
  </PropertyGroup>
```

Sie können entweder "7,2" oder "Letzter" für den Wert verwenden.

## <a name="specifying-in-parameters"></a>Angeben von `in` Parameter

7.2 c# fügt der `in` Schlüsselwort, um die vorhandene ergänzen `ref` und `out` Schlüsselwörter, wenn Sie eine Methode schreiben, die Argumente als Verweis übergibt. Die `in` -Schlüsselwort Gibt an, dass den Parameter als Verweis übergeben und die aufgerufene Methode nicht den Wert übergeben wird ändert. 

Diese Ergänzung enthält vollständige Vokabular um Ihre Entwurfsabsicht auszudrücken. Werttypen werden kopiert, wenn für eine aufgerufene Methode übergeben wird, wenn Sie keinen der folgenden Modifizierer angeben. Jedes dieser Modifizierer anzugeben, dass ein Werttyp als Verweis übergeben wird, vermeiden die Kopie. Jeder Modifizierer gibt eine andere Absicht:

- `out`: Diese Methode wird der Wert des Arguments als dieser Parameter verwendet.
- `ref`: Diese Methode kann den Wert des Arguments als dieser Parameter festgelegt.
- `in`: Diese Methode ändert nicht den Wert des Arguments als dieser Parameter verwendet.

Beim Hinzufügen der `in` Modifizierer, um ein Argument als Verweis übergeben werden, Argumente zu übergeben, als Verweis auf das vermeiden Sie unnötige Kopieren Ihrer Entwurfsabsicht deklarieren. Nicht führen Sie beabsichtigen, so ändern Sie das Objekt als Argument verwendet. Der folgende Code zeigt ein Beispiel für eine Methode, die den Abstand zwischen zwei Punkten in einem 3D-Bereich berechnet. 

[!code-csharp[InArgument](../../samples/csharp/reference-semantics/Program.cs#InArgument "Specifying an In argument")]

Die Argumente sind zwei Strukturen, die jeweils drei Doubles enthalten. Ein Double-Wert ist 8 Byte, sodass jedes Argument 24 Bytes ist. Durch Angabe der `in` Modifizierer, übergeben Sie 4-Byte- oder 8-Byte-Verweis auf diese Argumente, je nach Architektur des Computers. Der Unterschied in Größe ist klein, aber sie können schnell summieren, wenn diese Methode in einer dichten Schleife, die mit vielen unterschiedlichen Werten von Ihrer Anwendung aufgerufen.
 
Die `in` Modifizierer ergänzt `out` und `ref` auf andere Weise als auch. Sie können keine Überladungen einer Methode, die nur bei Vorhandensein der unterscheiden erstellen `in`, `out` oder `ref`. Diese neue Regeln erweitern dasselbe Verhalten, das immer für definiert worden `out` und `ref` Parameter.

Die `in` Modifizierer kann angewendet werden, um ein Element, das Parameter annimmt: Methoden, Delegaten, Lambda-Ausdrücke, lokale Funktionen, Indexer, Operatoren.

Im Gegensatz zu `ref` und `out` Argumente, Sie können Literalwerte oder Konstanten für das Argument für eine `in` Parameter. Auch, im Gegensatz zu einer `ref` oder `out` Parameter verwenden, müssen Sie nicht anwenden der `in` Modifizierer an der Aufrufsite. Der folgende Code zeigt zwei Beispiele für den Aufruf der `CalculateDistance` Methode. Die erste Klasse verwendet zweier lokale Variablen als Verweis übergeben wird. Die zweite enthält eine temporäre Variable als Teil des Methodenaufrufs erstellt. 

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#UseInArgument "Specifying an In argument")]

Es gibt mehrere Möglichkeiten, die in der der Compiler stellt, dass den nur-Lese Charakter sicher ein `in` Argument wird erzwungen.  Erstens, die aufgerufene Methode kann nicht direkt zuweisen einer `in` Parameter. Es kann nicht direkt auf jedes Feld der Zuweisen einer `in` Parameter. Darüber hinaus können keine Sie übergeben ein `in` Parameter an eine beliebige Methode verlangen die `ref` oder `out` Modifizierer.
Der Compiler erzwingt, die die `in` Argument ist eine schreibgeschützte Variable. Sie können Instanzmethode aufrufen, die Übergabe von Wertsemantik verwendet. In diesen Fällen eine Kopie der `in` wird erstellt. Da der Compiler eine temporäre Variable für eine beliebige erstellen kann `in` Parameter können auch das Angeben von Standardwerten für alle `in` Parameter. Der folgende Code verwendet, um den Ursprung (Punkt 0,0) als Standardwert für den zweiten Punkt angeben:

[!code-csharp[InArgumentDefault](../../samples/csharp/reference-semantics/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

Die `in` Parameter Bezeichnung kann auch bei Verweistypen verwendet oder in numerischen Werten erstellt. Allerdings sind die Vorteile in beiden Fällen minimal, sofern vorhanden.

## <a name="ref-readonly-returns"></a>`ref readonly`Gibt zurück

Sie sollten auch einen Werttyp als Verweis zurückgegeben, aber nicht zulassen Aufrufer aus diesen Wert ändern. Verwenden der `ref readonly` Modifizierer, um diese Entwurfsabsicht auszudrücken. Leser benachrichtigt, dass Sie einen Verweis auf die vorhandenen Daten zurückgeben, aber Änderung nicht zugelassen. 

Der Compiler erzwingt, dass der Aufrufer die Referenz ändern kann. Versucht, auf den Wert direkt zuweisen generieren einen Fehler während der Kompilierung. Der Compiler wissen nicht allerdings, wenn jeder Member-Methode den Zustand der Struktur ändert.
Um sicherzustellen, dass das Objekt nicht geändert wird, wird der Compiler erstellt eine Kopie und ruft Member verweisen, die mit dieser Kopie. Alle Änderungen werden mit dieser defensiven Kopie. 

Es ist wahrscheinlich, die die Bibliothek mit `Point3D` Ursprung im gesamten Code häufig verwenden. Jede Instanz erstellt ein neues Objekt auf dem Stapel an. Möglicherweise vorteilhaft sein, erstellen eine Konstante erstellt und als Verweis zurückgegeben. Wenn Sie einen Verweis auf die interne Speicherung zurückgeben, Sie möchten jedoch möglicherweise zu erzwingen, dass der Aufrufer den referenzierten Speicher ändern kann. Der folgende Code definiert eine schreibgeschützte Eigenschaft, die zurückgibt eine `readonly ref` auf eine `Point3D` , des Ursprungs angibt.

[!code-csharp[OriginReference](../../samples/csharp/reference-semantics/Point3D.cs#OriginReference "Creating a readonly Origin reference")]

Erstellen eine Kopie des einen schreibgeschützten Ref return ist einfach: nur eine Variable nicht mit dem Zuweisen der `ref readonly` Modifizierer. Der Compiler generiert Code, um das Objekt als Teil der Zuordnung zu kopieren. 

Wenn Sie eine Variable zum Zuweisen einer `ref readonly return`, geben Sie entweder eine `ref readonly` Variable oder ein per-Wert-Kopie des Verweises Readonly:

[!code-csharp[AssignRefReadonly](../../samples/csharp/reference-semantics/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

Die erste Zuweisung im vorangehenden Code wird eine Kopie der `Origin` Konstante und weist ihm, die kopiert werden. Die zweite weist einen Verweis. Beachten Sie, dass die `readonly` Modifizierer muss Teil der Deklaration der Variablen. Der Verweis auf dem es verweist, nicht geändert werden. Versuche, die dazu führen zu einem Fehler während der Kompilierung.

## <a name="readonly-struct-type"></a>`readonly struct`-Typ

Anwenden von `ref readonly` beim hohem Datenverkehr mithilfe einer Struktur möglicherweise nicht ausreichend.
In einigen Fällen können Sie eine unveränderliche Struktur erstellen möchten. Anschließend können Sie immer als Readonly-Verweis übergeben. Übung die Verteidigung entfernt kopiert, stattfinden beim Zugriff auf Methoden einer Struktur, die als verwendet ein `in` Parameter.

Sie können dies vornehmen, indem erstellen eine `readonly struct` Typ. Sie können hinzufügen, die `readonly` Modifizierer, um eine Strukturdeklaration. Der Compiler erzwingt, dass alle Member der Struktur `readonly`; das `struct` müssen unveränderlich sein.

Es gibt weitere Optimierungen für eine `readonly struct`. Können Sie die `in` Modifizierer an jeder Stelle, wo ein `readonly struct` ist ein Argument. Sie können darüber hinaus Zurückgeben einer `readonly struct` als eine `ref return` Wenn Sie ein Objekt, dessen Lebensdauer überschreitet den Bereich der Methode zurückgeben des Objekts, zurückgegeben werden.

Schließlich generiert der Compiler effizienter Code beim Aufrufen von Membern der eine `readonly struct`: die `this` Verweis, anstatt eine Kopie der Empfänger ist immer ein `in` Parameter als Verweis auf die Membermethode übergeben. Diese Optimierung speichert Weitere kopieren bei der Verwendung einer `readonly struct`. Die `Point3D` prädestiniert für diese Änderung ist. Der folgende Code zeigt ein aktualisiertes `ReadonlyPoint3D` Struktur:

[!code-csharp[ReadonlyOnlyPoint3D](../../samples/csharp/reference-semantics/Point3D.cs#ReadonlyOnlyPoint3D "Defining an immutable structure")]

## <a name="ref-struct-type"></a>`ref struct`-Typ

Eine andere verwandte Sprachfunktion ist die Möglichkeit, einen Werttyp deklarieren, der Stapel zugeordnet werden muss. Das heißt, können dieser Typen nie auf dem Heap als Mitglied einer anderen Klasse erstellt werden. Die primäre Motivation für dieses Feature wurde <xref:System.Span%601> und zugehörigen Strukturen. <xref:System.Span%601>einen verwalteten Zeiger enthalten als eines seiner Elemente, die andere wird die Länge der Spanne. Er ist tatsächlich ein wenig anders implementiert, da C#-Zeiger in den verwalteten Speicher außerhalb von einem unsicheren Kontext nicht unterstützt. Alle Schreibvorgänge, die ändert sich der Zeiger und die Länge ist nicht unteilbar. Das bedeutet, dass eine <xref:System.Span%601> wäre unterliegen außerhalb des gültigen Bereichsfehler oder andere Verletzungen der typsicherheit wurden sie nicht auf einen einzelnen Stapelrahmen eingeschränkt. Darüber hinaus stürzt ab, in der Regel einen verwalteten Zeiger auf den GC-Heap ablegen zur JIT-Zeit.

Möglicherweise ähnliche Anforderungen arbeiten mit Speicher mit erstellt [ `stackalloc` ](language-reference/keywords/stackalloc.md) oder bei der Verwendung von Arbeitsspeicher von Interop-APIs. Können eigene definieren `ref struct` -Typen für diese Anforderungen. In diesem Artikel finden Sie Beispiele für die Verwendung `Span<T>` aus Gründen der Einfachheit.

Die `ref struct` Deklaration deklariert, dass eine Struktur dieses Typs auf dem Stapel sein muss. Gemäß den Sprachregeln Sicherstellen der sichere Verwendung dieser Typen. Andere Typen deklariert wird, als `ref struct` enthalten <xref:System.ReadOnlySpan%601>. 

Das Ziel des durch die Beibehaltung einer `ref struct` geben, wie eine Stapel zugeordneten Variablen mehrere Regeln eingeführt, die für alle der Compiler erzwingt `ref struct` Typen.

- Sie können keine Feld eine `ref struct`. Kann nicht zugewiesen werden eine `ref struct` Typ einer Variablen des Typs `object`, `dynamic`, oder einen beliebigen anderen Schnittstellentyp.
- Sie können nicht deklariert eine `ref struct` als Member einer Klasse oder eine normale Struktur.
- Lokale Variablen, die nicht deklariert werden `ref struct` Typen in Async-Methoden. Sie deklarieren Sie diese im synchronen Methoden, mit denen `Task`, `Task<T>` oder Task-ähnlichen Typen.
- Sie können nicht deklariert werden `ref struct` lokalen Variablen in Iteratoren.
- Sie können keine erfassen `ref struct` Variablen in Lambda-Ausdrücken oder Funktionen.

Diese Einschränkungen stellen Sie sicher, dass Sie nicht versehentlich verwenden eine `ref struct` in einer Weise, die sie auf dem verwalteten Heap heraufzustufen konnte.

## <a name="conclusions"></a>Zusammenfassung

Diese Verbesserungen an der C#-Sprache sind für Leistung kritisch Algorithmen vorgesehen, in denen speicherbelegungen für die benötigte Leistung erreichen von entscheidender Bedeutung sein können. Möglicherweise, dass Sie häufig dieser Features im Code nicht verwenden, den Sie schreiben. Allerdings haben diese Verbesserungen an zahlreichen Speicherorten in .NET Framework übernommen wurde. Als weitere und weitere APIs stellen diese Funktionen nutzen möchten, sehen Sie die Leistung Ihrer eigenen Anwendungen zu verbessern.
