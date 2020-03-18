---
title: Ausdrucksbaumstrukturen mit Erläuterung
description: Weitere Informationen zu Ausdrucksbaumstrukturen und ihrer Verwendung für die Übersetzung von Algorithmen für die externe Ausführung und für das Überprüfen von Code vor der Ausführung.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: bbcdd339-86eb-4ae5-9911-4c214a39a92d
ms.openlocfilehash: 12093e9c9246c87cc5ea3aedaca6ba34acacce4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "73036994"
---
# <a name="expression-trees-explained"></a>Ausdrucksbaumstrukturen mit Erläuterung

[Vorheriges – 2 Übersicht](expression-trees.md)

Eine Ausdrucksbaumstruktur ist eine Datenstruktur, die Code darstellt. Sie basiert auf den gleichen Strukturen, die ein Compiler verwendet, um Code zu analysieren und die kompilierte Ausgabe zu generieren. Wenn Sie dieses Tutorial lesen, werden Sie feststellen, dass eine Ähnlichkeit zwischen Ausdrucksbaumstrukturen und den Typen in den Roslyn-APIs vorhanden ist, um [Analyzers and CodeFixes (Analyzer und CodeFixes)](https://github.com/dotnet/roslyn-analyzers) zu erstellen.
(Analyzer und CodeFixes sind NuGet-Pakete, die statische Analysen für Code ausführen und mögliche Korrekturen für einen Entwickler vorschlagen können.) Die Konzepte sind ähnlich, und das Endergebnis ist eine Datenstruktur, die eine Prüfung des Quellcodes auf sinnvolle Weise ermöglicht. Ausdrucksbaumstrukturen basieren jedoch auf einem völlig anderen Satz von Klassen und APIs als die Roslyn-APIs.

Sehen wir uns ein einfaches Beispiel an.
Hier ist eine Codezeile:

```csharp
var sum = 1 + 2;
```

Würden Sie dies als eine Ausdrucksbaumstruktur analysieren, enthält die Struktur mehrere Knoten.
Der äußerste Knoten ist eine Variablendeklaration-Anweisung mit der Zuordnung (`var sum = 1 + 2;`). Dieser äußerste Knoten enthält mehrere untergeordnete Knoten: eine Variablendeklaration, ein Zuweisungsoperator und ein Ausdruck, der die rechte Seite des Gleichheitszeichens darstellt. Dieser Ausdruck wird weiter unterteilt in Ausdrücke, die den Additionsvorgang und linken und rechten Operanden der Addition darstellen.

Lassen Sie uns die Ausdrücke etwas genauer ansehen, die die rechte Seite neben dem Gleichheitszeichen bilden.
Der Ausdruck ist `1 + 2`. Das ist ein binärer Ausdruck. Genauer gesagt ist es ein binärer Additionsausdruck. Ein binäre Additionsausdruck verfügt über zwei untergeordnete Elemente, die den linken und rechten Knoten des Additionsausdrucks darstellen. Hier sind die beiden Knoten konstante Ausdrücke: Der linke Operand ist der Wert `1`, und der rechte Operand ist der Wert `2`.

Visuell ist die gesamte Anweisung eine Struktur: Sie können beim Stammknoten beginnen und zu jedem Knoten in der Struktur navigieren, um den Code anzuzeigen, der die Anweisung bildet:

- Variablendeklaration-Anweisung mit der Zuordnung (`var sum = 1 + 2;`)
  - Implizite Typdeklaration von Variablen (`var sum`)
    - Implizites var-Schlüsselwort (`var`)
    - Namensdeklaration von Variablen (`sum`)
  - Zuweisungsoperator (`=`)
  - Binärer Additionsausdruck (`1 + 2`)
    - Linker Operand (`1`)
    - Additionsoperator (`+`)
    - Rechter Operand (`2`)

Dies mag kompliziert aussehen, aber es ist sehr leistungsfähig. Mit den gleichen Verfahren können Sie wesentlich kompliziertere Ausdrücke zerlegen. Betrachten Sie diesen Ausdruck:

```csharp
var finalAnswer = this.SecretSauceFunction(
    currentState.createInterimResult(), currentState.createSecondValue(1, 2),
    decisionServer.considerFinalOptions("hello")) +
    MoreSecretSauce('A', DateTime.Now, true);
```

Der obige Ausdruck ist auch die Variablendeklaration mit einer Zuordnung.
In dieser Instanz ist die rechte Seite der Zuordnung eine wesentlich kompliziertere Struktur.
Ich werde diesen Ausdruck nicht zerlegen, aber beachten Sie, was die verschiedenen Knoten sein könnten. Es sind Methodenaufrufe vorhanden, die das aktuelle Objekt als Empfänger verwenden, einen, der einen expliziten `this`-Empfänger hat und einen, der das nicht hat. Es sind Methodenaufrufe vorhanden, die andere Empfängerobjekte verwenden. Es sind konstante Argumente verschiedener Typen vorhanden. Und schließlich gibt es einen binären Additionsoperator. Je nach Rückgabetyp von `SecretSauceFunction()` oder `MoreSecretSauce()`, kann dieser binäre Additionsoperator ein Methodenaufruf an einen überschriebenen Additionsoperator sein, der einen statischen Methodenaufruf des binären Additionsoperators, der für eine Klasse definiert ist auflöst.

Trotz dieser spürbaren Komplexität erstellt der obige Ausdruck eine Baumstruktur, die so einfach wie das erste Beispiel navigiert werden kann. Sie können untergeordnete Knoten durchlaufen lassen, um Endknoten im Ausdruck zu finden. Übergeordnete Knoten verfügen über Verweise auf ihre untergeordneten Elemente, und jeder Knoten verfügt über eine Eigenschaft, die beschreibt, welche Art von Knoten es ist.

Die Struktur einer Ausdrucksbaumstruktur ist sehr konsistent. Sobald Sie mit den Grundlagen vertraut sind, können Sie auch den komplexesten Code verstehen, wenn er als Ausdrucksbaumstruktur dargestellt wird. Die Eleganz in der Datenstruktur erläutert, wie der C#-Compiler die komplexesten C#-Programme analysieren und eine korrekte Ausgabe aus diesem komplizierten Quellcode erstellen kann.

Sobald Sie mit der Struktur von Ausdrucksbaumstrukturen vertraut sind, werden Sie feststellen, dass dieses Wissen es Ihnen ermöglicht, mit mehr und mehr erweiterten Szenarios zu arbeiten. Dies bedeutet eine unglaubliche Leistung für Ausdrucksbaumstrukturen.

Zusätzlich zum Übersetzen von Algorithmen, die in anderen Umgebungen ausgeführt werden sollen, können Ausdrucksbaumstrukturen verwendet werden, um das Schreiben von Algorithmen zu erleichtern, der Code überprüft, bevor Sie ihn ausführen. Sie können eine Methode schreiben, deren Argumente Ausdrücke sind, und anschließend diese Ausdrücke vor dem Ausführen des Codes überprüfen. Die Ausdrucksbaumstruktur ist eine vollständige Darstellung des Codes: Sie können Werte von beliebigen Unterausdrücken sehen.
Sie können Methoden- und Eigenschaftsnamen sehen. Sie können den Wert jedes konstanten Ausdrucks sehen.
Sie können auch eine Ausdrucksbaumstruktur in einen ausführbaren Delegaten konvertieren und den Code ausführen.

Mit den APIs für Ausdrucksbaumstrukturen können Sie Strukturen erstellen, die fast jeden gültigen Codekonstrukt darstellen. Um die Dinge so einfach wie möglich zu halten, können jedoch einige C#-Ausdrücke nicht in einer Ausdrucksbaumstruktur erstellt werden. Ein Beispiel sind asynchrone Ausdrücke (mithilfe der `async`- und `await`-Schlüsselwörter). Wenn Ihre Bedürfnisse asynchrone Algorithmen erfordern, müssten Sie die `Task`-Objekte direkt bearbeiten, anstatt sich auf die Unterstützung des Compilers zu verlassen. Ein weiteres Beispiel ist die Erstellung von Schleifen. Normalerweise erstellen Sie diese mithilfe der Schleifen `for`, `foreach`, `while` oder `do`. Wie Sie [später in dieser Serie](expression-trees-building.md) sehen werden, unterstützen die APIs für Ausdrucksbaumstrukturen einen einzelnen Schleifenausdruck mit `break`- und `continue`-Ausdrücken, die die Wiederholung der Schleife steuern.

Eine Sache, die für Sie nicht möglich ist, ist die Änderung einer Ausdrucksbaumstruktur.  Ausdrucksbaumstrukturen sind unveränderliche Datenstrukturen. Wenn Sie eine Ausdrucksbaumstruktur ändern möchten, müssen Sie eine neue Struktur erstellen, die eine Kopie des Originals ist, aber mit den gewünschten Änderungen.

[Weiter – Framework-Typen, die Ausdrucksbaumstrukturen unterstützen](expression-classes.md)
