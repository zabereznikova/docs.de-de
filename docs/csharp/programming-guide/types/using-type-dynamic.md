---
title: Verwenden des Typs „dynamic“ – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic [C#], about dynamic type
- dynamic type [C#]
ms.assetid: 3828989d-c967-4a51-b948-857ebc8fdf26
ms.openlocfilehash: c5ac5b3692266010f0be8672ef744baaa32e6a03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75711856"
---
# <a name="using-type-dynamic-c-programming-guide"></a>Verwenden des Typs „dynamic“ (C#-Programmierhandbuch)

C# 4 führt einen neuen Typ ein: `dynamic`. Bei diesem Typ handelt es sich um einen statischen Typ. Ein Objekt des Typs `dynamic` umgeht aber die Überprüfung statischer Typen. In den meisten Fällen entspricht es der Funktionsweise des Typs `object`. Bei einem Element, das zur Kompilierzeit als `dynamic` typisiert wird, wird davon ausgegangen, dass es alle Vorgänge unterstützt. Daher müssen Sie sich keine Gedanken darüber machen, ob das Objekt seinen Wert von einer COM-API, einer dynamischen Sprache wie IronPython, vom HTML-DOM (Document Object Model), aus der Reflektion oder von einer anderen Quelle im Programm erhält. Wenn der Code jedoch nicht gültig ist, werden Fehler zur Laufzeit abgefangen.

Wenn z.B. die Instanzmethode `exampleMethod1` im folgenden Code nur einen Parameter hat, erkennt der Compiler, dass der erste Aufruf der Methode, `ec.exampleMethod1(10, 4)`, nicht gültig ist, da er zwei Argumente enthält. Dieser Aufruf löst einen Compilerfehler aus. Der zweite Aufruf der Methode, `dynamic_ec.exampleMethod1(10, 4)`, wird vom Compiler nicht überprüft, da der Typ von `dynamic_ec``dynamic` ist. Daher wird kein Compilerfehler gemeldet. Allerdings bleibt der Fehler nicht unbegrenzt unbemerkt. Er wird zur Laufzeit abgefangen und führt zu einer Laufzeitausnahme.

[!code-csharp[CsProgGuideTypes#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/usingdynamic.cs#50)]

[!code-csharp[CsProgGuideTypes#56](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/usingdynamic.cs#56)]

In diesen Beispielen ist es die Rolle des Compilers, Informationen darüber zusammenzustellen, was jede Anweisung für die Behandlung des Objekts oder des Ausdrucks vorschlägt, die als `dynamic` typisiert sind. Die gespeicherten Informationen werden zur Laufzeit überprüft, und jede ungültige Anweisung verursacht eine Laufzeitausnahme.

Das Ergebnis der meisten dynamischen Vorgänge ist wiederum `dynamic`. Wenn Sie z.B. den Mauszeiger im folgenden Beispiel auf die Verwendung von `testSum` halten, zeigt IntelliSense den Typ **(local variable) dynamic testSum** an.

[!code-csharp[CsProgGuideTypes#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/usingdynamic.cs#51)]

Vorgänge, in denen das Ergebnis nicht `dynamic` lautet, sind z.B.:

* Konvertierungen von `dynamic` in einen anderen Typ
* Konstruktoraufrufe, die Argumente des Typs `dynamic` enthalten

In der folgenden Deklaration ist der Typ von `testInstance` z.B. `ExampleClass`, nicht `dynamic`:

[!code-csharp[CsProgGuideTypes#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/usingdynamic.cs#52)]

Im folgenden Abschnitt „Konvertierungen“ finden Sie Konvertierungsbeispiele.

## <a name="conversions"></a>Konvertierungen

Konvertierungen zwischen dynamischen Objekten und anderen Typen sind sehr einfach. Dadurch kann der Entwickler zwischen dynamischem und nicht dynamischem Verhalten wechseln.

Jedes Objekt kann implizit zu einem dynamischen Typ konvertiert werden, wie in den folgenden Beispielen gezeigt.

[!code-csharp[CsProgGuideTypes#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/usingdynamic.cs#53)]

Umgekehrt kann eine implizite Konvertierung dynamisch auf einen Ausdruck vom Typ `dynamic` angewendet werden.

[!code-csharp[CsProgGuideTypes#54](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/usingdynamic.cs#54)]

## <a name="overload-resolution-with-arguments-of-type-dynamic"></a>Überladungsauflösung mit Argumenten vom Typ „dynamic“

Überladungsauflösung erfolgt zur Laufzeit anstatt zur Kompilierzeit, wenn eines oder mehrere der Argumente in einem Methodenaufruf vom Typ `dynamic` sind, oder wenn der Empfänger des Methodenaufrufs vom Typ `dynamic` ist. Im folgenden Beispiel wird durch das Senden von `d1` als Argument kein Compilerfehler ausgelöst, wenn die einzige zugängliche `exampleMethod2`-Methode so definiert wird, dass sie ein Zeichenfolgenargument akzeptiert. Allerdings wird eine Laufzeitausnahme ausgelöst. Die Überladungsauflösung schlägt zur Laufzeit fehl, da der Laufzeittyp von `d1``int` ist und `exampleMethod2` eine Zeichenfolge benötigt.

[!code-csharp[CsProgGuideTypes#55](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/usingdynamic.cs#55)]

## <a name="dynamic-language-runtime"></a>Dynamic Language Runtime (DLR)

Die Dynamic Language Runtime (DLR) ist eine neue API in .NET Framework 4. Sie bietet die Infrastruktur, die den Typ `dynamic` in C# und die Implementierung von dynamischen Programmiersprachen wie IronPython und IronRuby unterstützt. Weitere Informationen zur DLR finden Sie unter [Übersicht über die Dynamic Language Runtime](../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).

## <a name="com-interop"></a>COM-Interop

C# 4 enthält mehrere Features, die die Interoperabilität mit COM-APIs wie den Automatisierungs-APIs in Office verbessern. Zu diesen Verbesserungen gehören die Verwendung des Typs `dynamic` und von [benannten und optionalen Argumenten](../classes-and-structs/named-and-optional-arguments.md).

Viele COM-Methoden ermöglichen die Variation von Argument- und Rückgabetypen durch Festlegen der Typen als `object`. Dadurch wird das explizite Umwandeln der Werte für die Koordination mit stark typisierten Variablen in C# notwendig. Wenn Sie mit der Option [-link (C#-Compileroptionen)](../../language-reference/compiler-options/link-compiler-option.md) kompilieren, ermöglicht Ihnen die Einführung des Typs `dynamic`, die Vorkommen von `object` in COM-Signaturen so zu behandeln, als wären sie vom Typ `dynamic`. Dadurch können Sie einen Großteil der Umwandlung umgehen. Die folgenden Anweisungen unterscheiden z.B., wie Sie auf eine Zelle in einem Arbeitsblatt von Microsoft Office Excel mit dem Typ `dynamic` und ohne den Typ `dynamic` zugreifen.

[!code-csharp[csOfficeWalkthrough#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#12)]

[!code-csharp[csOfficeWalkthrough#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#13)]

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[dynamic](../../language-reference/builtin-types/reference-types.md)|Beschreibt die Verwendung des Schlüsselworts `dynamic`.|
|[Übersicht über die Dynamic Language Runtime](../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)|Bietet eine Übersicht über die Dynamic Language Runtime (DLR), eine Laufzeitumgebung, die der Common Language Runtime (CLR) eine Reihe von Diensten für dynamische Sprachen hinzufügt.|
|[Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](walkthrough-creating-and-using-dynamic-objects.md)|Bietet eine ausführliche Anleitung zum Erstellen eines benutzerdefinierten dynamischen Objekts und zum Erstellen eines Projekts, das auf eine `IronPython`-Bibliothek zugreift.|
|[Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen](../interop/how-to-access-office-onterop-objects.md)|Veranschaulicht, wie Sie ein Projekt erstellen, das benannte und optionale Argumente, den Typ `dynamic` und andere Verbesserungen verwendet, die den Zugriff auf Office-API-Objekte vereinfachen.|
