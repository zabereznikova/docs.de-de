---
title: 'Verwenden von Mustern in Objekten: Tutorial zu C#'
description: In diesem Tutorial lernen Sie Techniken zur Verwendung des Musterabgleichs in Klassenmembern kennen, um bessere Modelle für das Objektverhalten zu erstellen.
ms.date: 11/05/2020
ms.openlocfilehash: 072f6f57696504c2d691473e3a43c1cda53f227f
ms.sourcegitcommit: 6bef8abde346c59771a35f4f76bf037ff61c5ba3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2020
ms.locfileid: "94332174"
---
# <a name="use-pattern-matching-to-build-your-class-behavior-for-better-code"></a>Verwenden des Musterabgleichs zum Gestalten des Verhaltens von Klassen für besseren Code

Die Features für den Musterabgleich in C# stellen die Syntax zum Ausdrücken Ihrer Algorithmen bereit. Mithilfe dieser Techniken können Sie das Verhalten in Ihren Klassen implementieren. Sie können einen objektorientierten Klassenentwurf mit einer datenorientierten Implementierung kombinieren, um bei der Modellierung von Objekten aus der realen Welt präzisen Code bereitzustellen.

In diesem Tutorial lernen Sie Folgendes:

> [!div class="checklist"]
>
> - Ausdrücken Ihrer objektorientierten Klassen mithilfe von Datenmustern
> - Implementieren dieser Muster mithilfe der C#-Features zum Musterabgleich
> - Nutzen der Compilerdiagnose zum Überprüfen Ihrer Implementierung

## <a name="prerequisites"></a>Voraussetzungen

Sie müssen Ihren Computer zur Ausführung von .NET 5 einrichten, einschließlich des C# 9.0-Compilers. Der C# 9.0-Compiler steht ab [Visual Studio 2019 Version 16.8 Preview](https://visualstudio.microsoft.com/vs/preview/) oder [.NET 5.0 SDK Preview](https://dotnet.microsoft.com/download/dotnet/5.0) zur Verfügung.

## <a name="build-a-simulation-of-a-canal-lock"></a>Erstellen einer Simulation einer Kanalschleuse

In diesem Tutorial erstellen Sie eine C#-Klasse, die eine [Kanalschleuse](https://en.wikipedia.org/wiki/Lock_(water_navigation)) simuliert. Eine Kanalschleuse ist, kurz gesagt, eine Anlage, die Schiffe hebt und senkt, wenn sie sich zwischen zwei unterschiedlich hohen Wasserständen bewegen. Eine Schleuse hat zwei Tore und einen Mechanismus zur Änderung des Wasserstands.

Im Normalbetrieb fährt ein Schiff in eines der Tore ein, wenn der Wasserstand in der Schleuse dem Wasserstand auf der Seite entspricht, auf der das Schiff hineinfährt. Einmal in der Schleuse wird der Wasserstand entsprechend dem Wasserstand geändert, bei dem das Boot die Schleuse verlässt. Sobald der Wasserstand mit dieser Seite übereinstimmt, öffnet sich das Tor auf der Ausfahrtseite. Sicherheitsmaßnahmen stellen sicher, dass ein Schiffsführer keine gefährliche Situation im Kanal herbeiführen kann. Der Wasserstand kann nur geändert werden, wenn beide Tore geschlossen sind. Es darf höchstens ein Tor geöffnet sein. Um ein Tor zu öffnen, muss der Wasserstand in der Schleuse mit dem Wasserstand außerhalb des zu öffnenden Tores übereinstimmen.

Sie können eine C#-Klasse erstellen, um dieses Verhalten zu modellieren. Eine `CanalLock`-Klasse muss Befehle zum Öffnen oder Schließen eines der Tore bieten. Sie muss andere Befehle aufweisen, mit denen sich der Wasserstand heben oder senken lässt. Die Klasse muss auch Eigenschaften zum Lesen der aktuellen Stellung der beiden Tore und des Wasserstands unterstützen. Sicherheitsmaßnahmen werden mithilfe Ihrer Methoden implementiert.

## <a name="define-a-class"></a>Definieren einer Klasse

Sie erstellen eine Konsolenanwendung, um Ihre `CanalLock`-Klasse zu testen. Erstellen Sie entweder in Visual Studio oder mit der .NET CLI ein neues Konsolenprojekt für .NET 5. Fügen Sie dann eine neue Klasse hinzu, und nennen Sie sie `CanalLock`. Als Nächstes entwerfen Sie Ihre öffentliche API, ohne jedoch die Methoden zu implementieren:

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="APIDesign":::

Der vorstehende Code initialisiert das Objekt so, dass beide Tore geschlossen sind und der Wasserstand niedrig ist. Schreiben Sie als Nächstes den folgenden Testcode in Ihre `Main`-Methode, um Sie bei der Erstellung einer ersten Implementierung der Klasse zu leiten:

:::code language="csharp" source="snippets/pattern-objects/Program.cs" ID="HappyTests":::

Fügen Sie als Nächstes der `CanalLock`-Klasse eine erste Implementierung jeder Methode hinzu. Der folgende Code implementiert die Methoden der Klasse, ohne dass die Sicherheitsregeln berücksichtigt werden. Sicherheitstests fügen Sie später hinzu:

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="FirstImplementation":::

Die Tests, die Sie bisher geschrieben haben, werden bestanden. Sie haben die Grundlagen implementiert. Schreiben Sie nun einen Test für die erste Fehlerbedingung. Am Ende der vorherigen Tests sind beide Tore geschlossen, und der Wasserstand ist auf niedrig festgelegt. Fügen Sie einen Test hinzu, um zu versuchen, das obere Tor zu öffnen:

:::code language="csharp" source="snippets/pattern-objects/Program.cs" ID="HighGateSafetyTest":::

Dieser Test schlägt fehl, da das Tor geöffnet wird. Als erste Implementierung können Sie dies mit dem folgendem Code beheben:

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="SecondImplementation":::

Die Tests werden bestanden. Aber je mehr Tests Sie hinzufügen, desto mehr `if`-Klauseln werden Sie hinzufügen und verschiedene Eigenschaften testen. Schon bald werden diese Methoden zu kompliziert, je mehr Bedingungen Sie hinzufügen.

## <a name="implement-the-commands-with-patterns"></a>Implementieren der Befehle mit Mustern

Eine bessere Möglichkeit bieten *Muster* , um festzustellen, ob sich das Objekt in einem gültigen Zustand zur Ausführung eines Befehls befindet. Sie können ausdrücken, ob ein Befehl in Abhängigkeit von drei Variablen erlaubt ist: Stellung des Tores, Wasserstand und die neue Einstellung:

| Neue Einstellung | Stellung des Tores | Wasserstand | Ergebnis             |
| ----------- | ---------- | ----------- | ------------------ |
| Geschlossen      | Geschlossen     | Hoch        | Geschlossen             |
| Geschlossen      | Geschlossen     | Niedrig         | Geschlossen             |
| Geschlossen      | Geöffnet       | Hoch        | Geöffnet               |
| ~~Geschlossen~~  | ~~Geöffnet~~   | ~~Niedrig~~     | ~~Geschlossen~~         |
| Öffnen        | Geschlossen     | Hoch        | Geöffnet               |
| Geöffnet        | Geschlossen     | Niedrig         | Geschlossen (Fehler)     |
| Geöffnet        | Geöffnet       | Hoch        | Geöffnet               |
| ~~Geöffnet~~    | ~~Geöffnet~~   | ~~Niedrig~~     | ~~Geschlossen (Fehler)~~ |

In der vierten und letzten Zeile der Tabelle ist der Text durchgestrichen, weil sie ungültig ist. Der Code, den Sie jetzt hinzufügen, muss sicherstellen, dass das Hochwassertor niemals bei niedrigem Wasserstand geöffnet wird.  Diese Zustände können als ein einziger Switch-Ausdruck programmiert werden (denken Sie daran, dass `false` „Geschlossen“ bedeutet):

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="ThirdImplementation":::

Versuchen Sie diese Version. Die Tests werden bestanden und der Code bestätigt. Die vollständige Tabelle zeigt die möglichen Kombinationen von Eingaben und Ergebnissen. Das bedeutet, dass Sie und andere Entwickler schnell einen Blick auf die Tabelle werfen können, um festzustellen, dass Sie alle möglichen Eingaben abgedeckt haben. Zur Vereinfachung kann auch der Compiler beitragen. Nachdem Sie den vorherigen Code hinzugefügt haben, sehen Sie, dass der Compiler eine Warnung generiert: *CS8524* bedeutet, dass der Switch-Ausdruck nicht alle möglichen Eingaben abdeckt. Der Grund für diese Warnung ist, dass eine der Eingaben den Typ `enum` hat. Der Compiler interpretiert „alle möglichen Eingaben“ als alle Eingaben des zugrunde liegenden Typs, typischerweise `int`. Dieser `switch`-Ausdruck prüft nur die in `enum` deklarierten Werte. Um die Warnung zu entfernen, können Sie für den letzten Teil des Ausdrucks ein Muster des Typs „Alle abfangen und entsorgen“ hinzufügen. Diese Bedingung löst eine Ausnahme aus, da sie eine ungültige Eingabe angibt:

```csharp
_  => throw new InvalidOperationException("Invalid internal state"),
```

Der vorherige Switch-Arm muss der letzte in Ihrem `switch`-Ausdruck sein, da er mit allen Eingaben übereinstimmt. Experimentieren Sie, indem Sie ihn in der Reihenfolge nach vorn verschieben. Dies verursacht den Compilerfehler *CS8510* für nicht erreichbaren Code in einem Muster.  Die natürliche Struktur von Switch-Ausdrücken ermöglicht es dem Compiler, Fehler und Warnungen für mögliche Fehlersituationen zu generieren. Das „Sicherheitsnetz“ des Compilers erleichtert Ihnen, fehlerfreien Code in weniger Iterationen zu erstellen, und bietet Ihnen die Möglichkeit, Switch-Arme mit Platzhaltern frei zu kombinieren. Der Compiler löst Fehler aus, wenn Ihre Kombination zu unerreichbaren Armen führt, mit denen Sie nicht gerechnet haben, und Warnungen, wenn Sie einen benötigten Arm entfernen.

Die erste Änderung besteht darin, alle Arme zu kombinieren, bei denen der Befehl lautet, das Tor zu schließen. Das ist stets erlaubt. Fügen Sie den folgenden Code als ersten Arm in den Switch-Ausdruck ein:

```csharp
(false, _, _) => false,
```

Nachdem Sie den vorherigen Switch-Arm hinzugefügt haben, erhalten Sie vier Compilerfehler, einen in jedem der Arme, in denen der Befehl `false` ist. Diese Arme sind bereits durch den neu hinzugefügten Arm abgedeckt. Sie können diese vier Zeilen sicher entfernen. Sie wollten mit diesem neuen Switch-Arm diese Bedingungen ersetzen.

Als Nächstes können Sie die vier Arme vereinfachen, bei denen der Befehl lautet, das Tor zu öffnen. In beiden Fällen, in denen der Wasserstand hoch ist, kann das Tor geöffnet werden. (In einem ist es bereits geöffnet.) Ein Fall, in dem der Wasserstand niedrig ist, löst eine Ausnahme aus, der andere darf nicht passieren. Es sollte sicher sein, die gleiche Ausnahme auszulösen, wenn sich die Schleuse bereits in einer ungültigen Stellung befindet. Sie können die folgenden Vereinfachungen für diese Arme vornehmen:

```csharp
(true, _, WaterLevel.High) => true,
(true, false, WaterLevel.Low) => throw new InvalidOperationException("Cannot open high gate when the water is low"),
_ => throw new InvalidOperationException("Invalid internal state"),
```

Führen Sie die Tests erneut aus, die bestanden werden. Hier ist die endgültige Version der `SetHighGate`-Methode:

:::code language="csharp" source="snippets/pattern-objects/CanalLock.cs" ID="FinalImplementaton":::

## <a name="implement-patterns-yourself"></a>Eigenständiges Implementieren der Muster

Nachdem Sie die Technik kennengelernt haben, füllen Sie die Methoden `SetLowGate` und `SetWaterLevel` selbst aus.  Beginnen Sie mit dem Hinzufügen des folgenden Codes, um ungültige Vorgänge in diesen Methoden zu testen:

:::code language="csharp" source="snippets/pattern-objects/Program.cs" ID="FinalTestCode":::

Führen Sie Ihre Anwendung erneut aus. Sie erleben, wie die neuen Tests fehlschlagen und die Kanalschleuse in einen ungültigen Zustand gerät. Versuchen Sie, die restlichen Methoden selbst zu implementieren. Die Methode zur Festlegung des unteren Tores sollte ähnlich wie die Methode zur Festlegung des oberen Tores sein. Die Methode zum Ändern des Wasserstands hat unterschiedliche Prüfungen, sollte aber eine ähnliche Struktur aufweisen. Möglicherweise finden Sie es hilfreich, dasselbe Verfahren auch für die Methode zu verwenden, mit der der Wasserstand festgelegt wird. Beginnen Sie mit allen vier Eingaben: Stellung der beiden Tore, aktueller Wasserstand und geforderter neuer Wasserstand. Der Switch-Ausdruck sollte wie folgt beginnen:

```csharp
CanalLockWaterLevel = (newLevel, CanalLockWaterLevel, LowWaterGateOpen, HighWaterGateOpen) switch
{
    // elided
};
```

Es gibt insgesamt 16 auszufüllende Switch-Arme. Testen und vereinfachen Sie das Ganze im Anschluss.

Haben Sie Methoden in etwa wie folgt gestaltet?

:::code language="csharp" source="snippets/pattern-objects/CanalLock.cs" ID="FinalExercise":::

Die Tests sollten bestanden werden, und die Schleuse sollte sicher betrieben werden.

## <a name="summary"></a>Zusammenfassung

In diesem Tutorial haben Sie gelernt, mithilfe eines Musterabgleichs den internen Zustand eines Objekts zu überprüfen, ehe Änderungen an diesem Zustand vorgenommen werden. Sie können Kombinationen von Eigenschaften überprüfen. Sobald Sie Tabellen für beliebige dieser Übergänge erstellt haben, testen Sie Ihren Code, und vereinfachen ihn dann hinsichtlich Lesbarkeit und Wartbarkeit. Aus diesen anfänglichen Refactorings können sich weitere Refactorings ergeben, die den internen Zustand validieren oder andere API-Änderungen verwalten. In diesem Tutorial wurden Klassen und Objekte mit einem eher datenorientierten, musterbasierten Ansatz kombiniert, um diese Klassen zu implementieren.
