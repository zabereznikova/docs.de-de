---
title: Erstellen von Mixin-Typen mithilfe von Standardschnittstellenmethoden
description: Mithilfe von Standardschnittstellenmembern können Sie Schnittstellen mit optionalen Standardimplementierungen für Implementierungpsprogramme erweitern.
ms.technology: csharp-advanced-concepts
ms.date: 10/04/2019
ms.openlocfilehash: 798413f0071159893de39f3e190a9b2693571bb7
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039277"
---
# <a name="tutorial-mix-in-functionality-when-creating-classes-using-interfaces-with-default-interface-methods"></a>Tutorial: Mixin-Funktionen beim Erstellen von Klassen mithilfe von Schnittstellen mit Standardschnittstellenmethoden

Ab C# 8.0 können Sie in .NET Core 3.0 eine Implementierung definieren, wenn Sie einen Member einer Schnittstelle deklarieren. Dieses Feature bietet neue Funktionen, mit denen Sie Standardimplementierungen für Funktionen definieren können, die in Schnittstellen deklariert werden. Klassen können auswählen, wann die Funktionalität überschrieben werden soll, wann die Standardfunktionalität verwendet werden soll und wann keine Unterstützung für diskrete Features deklariert werden soll.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> * Erstellen von Schnittstellen mit Implementierungen, die diskrete Features beschreiben.
> * Erstellen von Klassen, die die Standardimplementierungen verwenden.
> * Erstellen von Klassen, die einige oder alle Standardimplementierungen überschreiben.

## <a name="prerequisites"></a>Erforderliche Komponenten

Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten, einschließlich des C# 8.0-Compilers. Der C# 8.0-Compiler steht ab [Visual Studio 2019, 16.3 Version 16.3.](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder mit dem [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) oder höher zur Verfügung.

## <a name="limitations-of-extension-methods"></a>Einschränkungen von Erweiterungsmethoden

Eine Möglichkeit, Verhalten zu implementieren, das als Teil einer Schnittstelle auftritt, besteht darin, [Erweiterungsmethoden](../programming-guide/classes-and-structs/extension-methods.md) zu definieren, die das Standardverhalten bereitstellen. Schnittstellen deklarieren einen minimalen Satz von Membern und bieten gleichzeitig eine größere Oberfläche für jede Klasse, die diese Schnittstelle implementiert. Die Erweiterungsmethoden in <xref:System.Linq.Enumerable> stellen beispielsweise die Implementierung für jede beliebige Sequenz als Quelle einer LINQ-Abfrage bereit.

Erweiterungsmethoden werden zur Kompilierzeit mithilfe des deklarierten Typs der Variablen aufgelöst. Klassen, die die Schnittstelle implementieren, können eine bessere Implementierung für jede beliebige Erweiterungsmethode bereitstellen. Variablendeklarationen müssen dem implementierenden Typ entsprechen, damit der Compiler diese Implementierung auswählen kann. Wenn der Kompilierzeittyp mit der Schnittstelle übereinstimmt, werden Methodenaufrufe in die Erweiterungsmethode aufgelöst. Ein weiteres Problem bei Erweiterungsmethoden ist, dass auf diese Methoden überall dort zugegriffen werden kann, wo auf die Klasse, die die Erweiterungsmethoden enthält, zugegriffen werden kann. Klassen können nichts deklarieren, wenn sie in Erweiterungsmethoden deklarierte Funktionen bereitstellen oder nicht bereitstellen sollten.

Ab C# 8.0 können Sie die Standardimplementierungen als Schnittstellenmethoden deklarieren. Anschließend verwendet jede Klasse automatisch die Standardimplementierung. Jede Klasse, die eine bessere Implementierung bereitstellen kann, kann die Definition der Schnittstellenmethode mit einem besseren Algorithmus überschreiben. In gewisser Weise klingt diese Technik ähnlich wie die Verwendung von [Erweiterungsmethoden](../programming-guide/classes-and-structs/extension-methods.md).

In diesem Artikel erfahren Sie, wie Standardschnittstellenimplementierungen neue Szenarien ermöglichen.

## <a name="design-the-application"></a>Entwerfen der Anwendung

Stellen Sie sich eine Anwendung für Smart Home-Automatisierung vor. Sie haben wahrscheinlich viele verschiedene Arten von Leuchten und Indikatoren, die im gesamten Haus verwendet werden könnten. Jede Leuchte muss APIs unterstützen, um sie ein- und auszuschalten und den aktuellen Zustand zu melden. Einige Leuchten und Indikatoren unterstützen möglicherweise andere Funktionen, beispielsweise:

- Einschalten der Leuchte und Ausschalten anhand eines Timers.
- Blinklichtfunktion der Leuchte für einen bestimmten Zeitraum.

Einige dieser erweiterten Funktionen können auf Geräten emuliert werden, die den minimalen Satz unterstützen. Dies bedeutet, dass eine Standardimplementierung bereitgestellt wird. Für Geräte, die über mehr integrierte Funktionen verfügen, würde die Gerätesoftware die nativen Funktionen verwenden. Für andere Leuchten können sie sich entscheiden, die Schnittstelle zu implementieren und die Standardimplementierung zu verwenden.

Standardschnittstellenmember sind eine bessere Lösung für dieses Szenario als Erweiterungsmethoden. Klassenautoren können steuern, welche Schnittstellen sie implementieren möchten. Diese Schnittstellen, die sie auswählen, sind als Methoden verfügbar. Da Standardschnittstellenmethoden standardmäßig virtuell sind, wählt die Methodenbindung außerdem immer die Implementierung in der-Klasse aus. 

Erstellen wir den Code, um diese Unterschiede zu veranschaulichen.

## <a name="create-interfaces"></a>Erstellen von Schnittstellen

Beginnen Sie, indem Sie die Schnittstelle erstellen, die das Verhalten für alle Leuchten definiert:

[!code-csharp[Declare base interface](~/samples/csharp/tutorials/mixins-with-interfaces/UnusedExampleCode.cs?name=SnippetILightInterfaceV1)]

Eine einfache Deckenleuchte könnte diese Schnittstelle wie im folgenden Code dargestellt implementieren:

[!code-csharp[First overhead light](~/samples/csharp/tutorials/mixins-with-interfaces/UnusedExampleCode.cs?name=SnippetOverheadLightV1)]

In diesem Tutorial werden keine IoT-Geräte durch den Code gesteuert, sondern diese Aktivitäten werden emuliert, indem Nachrichten in die Konsole geschrieben werden. Sie können den Code untersuchen, ohne Ihr Haus zu automatisieren.

Definieren wir nun die Schnittstelle für eine Leuchte, die nach einem Timeout automatisch ausgeschaltet werden kann:

[!code-csharp[pure Timer interface](~/samples/csharp/tutorials/mixins-with-interfaces/UnusedExampleCode.cs?name=SnippetPureTimerInterface)]

Sie könnten eine Basisimplementierung zur Deckenleuchte hinzufügen, aber eine bessere Lösung besteht darin, diese Schnittstellendefinition zu ändern, um eine `virtual`-Standardimplementierung bereitzustellen:

[!code-csharp[Timer interface](~/samples/csharp/tutorials/mixins-with-interfaces/ITimerLight.cs?name=SnippetTimerLightFinal)]

Durch Hinzufügen dieser Änderung kann die `OverheadLight`-Klasse die Timerfunktion implementieren, indem sie Unterstützung für die Schnittstelle deklariert:

```csharp
public class OverheadLight : ITimerLight { }
```

Ein anderer Leuchtentyp unterstützt möglicherweise ein anspruchsvolleres Protokoll. Er kann seine eigene Implementierung für `TurnOnFor` bereitstellen, wie im folgenden Code gezeigt:

[!code-csharp[Override the timer function](~/samples/csharp/tutorials/mixins-with-interfaces/HalogenLight.cs?name=SnippetHalogenLight)]

Im Gegensatz zum Überschreiben von Methoden der virtuellen Klasse verwendet die Deklaration von `TurnOnFor` in der `HalogenLight`-Klasse nicht das Schlüsselwort `override`. 

## <a name="mix-and-match-capabilities"></a>Mix-und-Match-Funktionen

Die Vorteile von Standardschnittstellenmethoden werden deutlicher, wenn Sie erweiterte Funktionen einführen. Durch die Verwendung von Schnittstellen können Sie Mix-und-Match-Funktionen verwenden. Außerdem kann jeder Klassenautor zwischen der Standardimplementierung und einer benutzerdefinierten Implementierung wählen. Fügen wir eine Schnittstelle mit einer Standardimplementierung für eine blinkende Leuchte hinzu:

[!code-csharp[Define the blinking light interface](~/samples/csharp/tutorials/mixins-with-interfaces/IBlinkingLight.cs?name=SnippetBlinkingLight)]

Die Standardimplementierung ermöglicht jeder Leuchte das Blinken. Die Deckenleuchte kann sowohl Timer- als auch Blinkfunktionen mit der Standardimplementierung hinzufügen:

[!code-csharp[Use the default blink function](~/samples/csharp/tutorials/mixins-with-interfaces/OverheadLight.cs?name=SnippetOverheadLight)]

Ein neuer Leuchtentyp (`LEDLight`) unterstützt die Timerfunktion und die Blinkfunktion direkt. Dieser Leuchtenstil implementiert sowohl die `ITimerLight`- als auch die `IBlinkingLight`-Schnittstelle und überschreibt die `Blink`-Methode:

[!code-csharp[Override the blink function](~/samples/csharp/tutorials/mixins-with-interfaces/LEDLight.cs?name=SnippetLEDLight)]

Ein `ExtraFancyLight`-Element unterstützt ggf. Blink- und Timerfunktionen direkt:

[!code-csharp[Override the blink and timer function](~/samples/csharp/tutorials/mixins-with-interfaces/ExtraFancyLight.cs?name=SnippetExtraFancyLight)]

Das `HalogenLight`-Element, das Sie zuvor erstellt haben, unterstützt kein Blinken. Fügen Sie `IBlinkingLight` daher nicht der Liste der unterstützten Schnittstellen dieses Elements hinzu.

## <a name="detect-the-light-types-using-pattern-matching"></a>Erkennen der Leuchtentypen mithilfe von Musterabgleich

Schreiben wir nun etwas Testcode. Sie können das Feature [Musterabgleich](../pattern-matching.md) von C# verwenden, um die Funktionen einer Leuchte zu ermitteln, indem Sie untersuchen, welche Schnittstellen sie unterstützt.  Die folgende Methode gibt die unterstützten Fähigkeiten der einzelnen Leuchten aus:

[!code-csharp[Test a light's capabilities](~/samples/csharp/tutorials/mixins-with-interfaces/Program.cs?name=SnippetTestLightFunctions)]

Der folgende Code in der `Main`-Methode erstellt alle Leuchtentypen nacheinander und testet die einzelnen Leuchten:

[!code-csharp[Test a light's capabilities](~/samples/csharp/tutorials/mixins-with-interfaces/Program.cs?name=SnippetMainMethod)]

## <a name="how-the-compiler-determines-best-implementation"></a>So ermittelt der Compiler die beste Implementierung

Dieses Szenario zeigt eine Basisschnittstelle ohne Implementierungen. Durch das Hinzufügen einer Methode zur `ILight`-Schnittstelle werden neue Komplexitäten eingeführt. Die Sprachregeln, die für Standardschnittstellenmethoden gelten, minimieren die Auswirkungen auf die konkreten Klassen, die mehrere abgeleitete Schnittstellen implementieren. Erweitern wir die ursprüngliche Schnittstelle durch eine neue Methode, um zu zeigen, wie sich dadurch ihre Verwendung ändert. Jede Indikatorleuchte kann ihren Energiestatus als Enumerationswert melden:

[!code-csharp[Enumeration for power status](~/samples/csharp/tutorials/mixins-with-interfaces/ILight.cs?name=SnippetPowerStatus)]

Die Standardimplementierung geht von einer Wechselstromversorgung aus:

[!code-csharp[Report a default power status](~/samples/csharp/tutorials/mixins-with-interfaces/ILight.cs?name=SnippetILightInterface)]

Diese Änderungen werden ordnungsgemäß kompiliert, auch wenn `ExtraFancyLight` Unterstützung für die `ILight`-Schnittstelle und die beiden abgeleiteten Schnittstellen `ITimerLight` und `IBlinkingLight` deklariert. Es gibt nur eine „nächste“ Implementierung, die in der `ILight`-Schnittstelle deklariert ist. Jede Klasse, die eine Überschreibung deklariert hat, würde zur „nächsten“ Implementierung werden. Sie haben in den vorhergehenden Klassen Beispiele gesehen, die die Member anderer abgeleiteter Schnittstellen überschreiben.

Vermeiden Sie das Überschreiben derselben Methode in mehreren abgeleiteten Schnittstellen. Auf diese Weise wird ein mehrdeutiger Methodenaufruf erstellt, wenn eine Klasse beide abgeleiteten Schnittstellen implementiert. Der Compiler kann keine einzelne bessere Methode auswählen, sodass er einen Fehler ausgibt. Wenn z.B. sowohl `IBlinkingLight` als auch `ITimerLight` eine Überschreibung von `PowerStatus` implementiert hat, müsste `OverheadLight` eine spezifischere Überschreibung bereitstellen. Andernfalls kann der Compiler nicht zwischen den Implementierungen in den beiden abgeleiteten Schnittstellen wählen. Sie können diese Situation in der Regel vermeiden, indem Sie Schnittstellendefinitionen klein halten und sich auf eine Funktion konzentrieren. In diesem Szenario ist jede Funktion einer Leuchte eine eigene Schnittstelle. Mehrere Schnittstellen werden nur von Klassen geerbt.

Dieses Beispiel zeigt ein Szenario, in dem Sie diskrete Features definieren können, die in Klassen gemischt werden können. Sie deklarieren einen beliebigen Satz unterstützter Funktionen, indem Sie deklarieren, welche Schnittstellen eine Klasse unterstützt. Durch die Verwendung von virtuellen Standardschnittstellenmethoden können Klassen eine andere Implementierung für beliebige oder alle Schnittstellenmethoden verwenden oder definieren. Diese Sprachfunktion bietet neue Möglichkeiten zum Modellieren der realen Systeme, die Sie entwickeln. Standardschnittstellenmethoden bieten eine bessere Möglichkeit, verwandte Klassen auszudrücken, die Mix-and-Match-Funktionen verwenden, indem sie virtuelle Implementierungen dieser Funktionen verwenden.
