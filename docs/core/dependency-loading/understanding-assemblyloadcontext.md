---
title: Grundlegendes zu AssemblyLoadContext – .NET Core
description: Wichtige Konzepte für ein besseres Verständnis von Zweck und Verhalten von AssemblyLoadContext in .NET Core.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 43fb0d792ddeb20b8a141af452a86dd50f37ba43
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523614"
---
# <a name="understanding-systemruntimeloaderassemblyloadcontext"></a>Grundlegendes zu System.Runtime.Loader.AssemblyLoadContext

Die <xref:System.Runtime.Loader.AssemblyLoadContext>-Klasse ist einzigartig in .NET Core. In diesem Artikel wird versucht, die Dokumentation der <xref:System.Runtime.Loader.AssemblyLoadContext>-API um konzeptionelle Informationen zu ergänzen.

Dieser Artikel richtet sich an Entwickler, die dynamisches Laden implementieren, insbesondere an Entwickler, die Frameworks dynamisch laden.

## <a name="what-is-the-assemblyloadcontext"></a>Was ist der AssemblyLoadContext?

Jede .NET Core-Anwendung verwendet implizit den <xref:System.Runtime.Loader.AssemblyLoadContext>.
Er stellt den Laufzeitanbieter zum Suchen und Laden von Abhängigkeiten dar. Wenn eine Abhängigkeit geladen wird, wird eine <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz aufgerufen, um sie zu suchen.

- Er stellt einen Dienst zum Suchen, Laden und Zwischenspeichern von verwalteten Assemblys und anderen Abhängigkeiten bereit.

- Um das dynamische Laden und Entladen von Code zu unterstützen, erstellt er einen isolierten Kontext für das Laden von Code und dessen zugehörigen Abhängigkeiten in einer eigenen <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz.

## <a name="when-do-you-need-multiple-assemblyloadcontext-instances"></a>Wann benötigen Sie mehrere AssemblyLoadContext-Instanzen?

Eine einzelne <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz ist auf das Laden genau einer Version einer <xref:System.Reflection.Assembly> für jeweils einen einfachen Assemblynamen (<xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>) beschränkt.

Diese Einschränkung kann problematisch werden, wenn Codemodule dynamisch geladen werden. Jedes Modul wird unabhängig kompiliert und kann von verschiedenen Versionen einer <xref:System.Reflection.Assembly> abhängen. Dieses Problem tritt häufig auf, wenn verschiedene Module von unterschiedlichen Versionen einer häufig verwendeten Bibliothek abhängen.

Um das dynamische Laden von Code zu unterstützen, ermöglicht die <xref:System.Runtime.Loader.AssemblyLoadContext>-API das Laden von in Konflikt stehenden Versionen einer <xref:System.Reflection.Assembly> in derselben Anwendung. Jede <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz stellt eine eindeutige Wörterbuchzuordnung für jede <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> einer bestimmten <xref:System.Reflection.Assembly>-Instanz bereit.

Außerdem bietet sie einen einfachen Mechanismus zum Gruppieren von Abhängigkeiten eines Codemoduls für das spätere Entladen.

## <a name="what-is-special-about-the-assemblyloadcontextdefault-instance"></a>Was ist das Besondere an der AssemblyLoadContext.Default-Instanz?

Die <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>-Instanz wird beim Start automatisch von der Runtime aufgefüllt.  Sie verwendet [Standardüberprüfungen](default-probing.md), um alle statischen Abhängigkeiten zu finden.

Damit werden die gängigsten Szenarien zum Laden von Abhängigkeiten gelöst.

## <a name="how-does-assemblyloadcontext-support-dynamic-dependencies"></a>Wie unterstützt AssemblyLoadContext dynamische Abhängigkeiten?

<xref:System.Runtime.Loader.AssemblyLoadContext> verfügt über verschiedene Ereignisse und virtuelle Funktionen, die überschrieben werden können.

Die <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>-Instanz unterstützt nur das Überschreiben der Ereignisse.

In den Artikeln [Ladealgorithmus für verwaltete Assemblys](loading-managed.md), [Ladealgorithmus für Satellitenassemblys](loading-resources.md) und [Ladealgorithmus für nicht verwaltete (native) Bibliotheken](loading-unmanaged.md) werden alle verfügbaren Ereignisse und virtuellen Funktionen beschrieben.  In den Artikeln werden die relativen Positionen der einzelnen Ereignisse und Funktionen in den Ladealgorithmen veranschaulicht. Diese Informationen werden in diesem Artikel nicht wiederholt.

In diesem Abschnitt werden die allgemeinen Prinzipien der relevanten Ereignisse und Funktionen behandelt.

- **Wiederholbarkeit**. Eine Abfrage für eine bestimmte Abhängigkeit muss immer zu derselben Antwort führen. Es muss dieselbe geladene Abhängigkeitsinstanz zurückgegeben werden. Diese Anforderung ist grundlegend für die Cachekonsistenz. Wir haben speziell für verwaltete Assemblys einen <xref:System.Reflection.Assembly>-Cache erstellt. Der Cacheschlüssel ist ein einfacher Assemblyname: <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>.
- **Normalerweise keine Fehlerauslösung**.  Es wird erwartet, dass diese Funktionen `null` zurückgeben, anstatt einen Fehler auszulösen, dass die angeforderte Abhängigkeit nicht gefunden werden kann. Durch das Auslösen wird die Suche vorzeitig beendet und eine Ausnahme an den Aufrufer zurückgegeben. Die Auslösung sollte auf unerwartete Fehler wie eine beschädigte Assembly oder Fälle mit nicht genügend Arbeitsspeicher beschränkt sein.
- **Vermeidung von Rekursion.** Beachten Sie, dass diese Funktionen und Handler die Laderegeln für die Suche nach Abhängigkeiten implementieren. Ihre Implementierung sollte keine APIs aufrufen, die Rekursion auslösen. Ihr Code sollte in der Regel Ladefunktionen von **AssemblyLoadContext** aufrufen, die ein bestimmtes Pfad- oder Speicherverweisargument erfordern.
- **Laden in den richtigen AssemblyLoadContext.** Die Wahl des richtigen Orts für das Laden von Abhängigkeiten ist anwendungsspezifisch.  Die Auswahl wird durch diese Ereignisse und Funktionen implementiert. Wenn Ihr Code **AssemblyLoadContext**-Funktionen vom Typ „Laden nach Pfad“ aufruft, sollten Sie dafür die Instanz verwenden, in die der Code geladen werden soll. In einigen Fällen besteht die einfachste Lösung darin, `null` zurückzugeben und das Laden <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> zu überlassen.
- **Berücksichtigung von Thread-Races**. Das Laden kann von mehreren Threads ausgelöst werden. Der AssemblyLoadContext verarbeitet Thread-Races, indem er die Assemblys einzeln im Cache hinzufügt. Die Instanz des letztes Threads wird dann verworfen. Fügen Sie in Ihrer Implementierungslogik keine zusätzliche Logik hinzu, die nicht ordnungsgemäß mehrere Threads verarbeiten kann.

## <a name="how-are-dynamic-dependencies-isolated"></a>Wie werden dynamische Abhängigkeiten isoliert?

Jede <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz stellt einen eindeutigen Geltungsbereich für <xref:System.Reflection.Assembly>-Instanzen und <xref:System.Type>-Definitionen dar.

Es gibt keine binäre Isolation zwischen diesen Abhängigkeiten. Sie werden nur isoliert, da sie sich gegenseitig nicht anhand des Namens finden können.

In jedem <xref:System.Runtime.Loader.AssemblyLoadContext> gilt Folgendes:

- <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> kann auf eine andere <xref:System.Reflection.Assembly>-Instanz verweisen.
- <xref:System.Type.GetType%2A?displayProperty=nameWithType> gibt möglicherweise eine andere Typinstanz für denselben Typ-`name` zurück.

## <a name="how-are-dependencies-shared"></a>Wie werden Abhängigkeiten gemeinsam genutzt?

Abhängigkeiten können problemlos von mehreren <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanzen gemeinsam genutzt werden. Im allgemeinen Modell lädt ein <xref:System.Runtime.Loader.AssemblyLoadContext> eine Abhängigkeit.  Der andere verwendet die Abhängigkeit über einen Verweis auf die geladene Assembly.

Diese Form der gemeinsamen Verwendung ist für die Runtimeassemblys erforderlich. Diese Assemblys können nur in den <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> geladen werden. Dasselbe gilt auch für Frameworks wie `ASP.NET`, `WPF` oder `WinForms`.

Es wird empfohlen, gemeinsam genutzte Abhängigkeiten in <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> zu laden. Diese Form der gemeinsamen Nutzung ist das gängige Entwurfsmuster.

Die gemeinsame Nutzung wird im Code der benutzerdefinierten <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz implementiert. <xref:System.Runtime.Loader.AssemblyLoadContext> verfügt über verschiedene Ereignisse und virtuelle Funktionen, die überschrieben werden können. Wenn eine dieser Funktionen einen Verweis auf eine <xref:System.Reflection.Assembly>-Instanz zurückgibt, die in einer anderen <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz geladen wurde, wird die <xref:System.Reflection.Assembly>-Instanz gemeinsam verwendet. Der Standardladealgorithmus orientiert sich für das Laden am <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>, um das Muster für die gemeinsame Nutzung zu vereinfachen.  Weitere Informationen finden Sie unter [Ladealgorithmus für verwaltete Assemblys](loading-managed.md).

## <a name="complications"></a>Komplikationen

### <a name="type-conversion-issues"></a>Probleme bei der Typkonvertierung

Wenn zwei <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanzen Typdefinitionen mit demselben `name` enthalten, sind sie nicht vom selben Typ. Sie weisen nur dann denselben Typ auf, wenn sie von derselben <xref:System.Reflection.Assembly>-Instanz stammen.

Noch komplizierter wird es, da die Meldungen zu Ausnahmen bei diesen nicht übereinstimmenden Typen verwirrend sein können. Auf die Typen wird in den Ausnahmemeldungen anhand ihrer einfachen Typnamen verwiesen. In diesem Fall hat die allgemeine Ausnahmemeldung folgende Form:

> Ein Objekt vom Typ „IsolatedType“ kann nicht in den Typ „IsolatedType“ konvertiert werden.

### <a name="debugging-type-conversion-issues"></a>Probleme bei der Konvertierung des Debugtyps

Bei einem Paar nicht übereinstimmender Typen ist es darüber hinaus wichtig, Folgendes zu wissen:

- Die <xref:System.Type.Assembly?displayProperty=nameWithType> jedes Typs
- Die <xref:System.Runtime.Loader.AssemblyLoadContext> jedes Typs, die über die <xref:System.Runtime.Loader.AssemblyLoadContext.GetLoadContext(System.Reflection.Assembly)?displayProperty=nameWithType>-Funktion abgerufen werden kann.

Bei den beiden Objekten `a` und `b` ist die Auswertung der folgenden Informationen im Debugger hilfreich:

```csharp
// In debugger look at each assembly's instance, Location, and FullName
a.GetType().Assembly
b.GetType().Assembly
// In debugger look at each AssemblyLoadContext's instance and name
System.Runtime.Loader.AssemblyLoadContext.GetLoadContext(a.GetType().Assembly)
System.Runtime.Loader.AssemblyLoadContext.GetLoadContext(b.GetType().Assembly)
```

### <a name="resolving-type-conversion-issues"></a>Beheben von Problemen bei der Typkonvertierung

Es gibt zwei Entwurfsmuster für das Beheben dieser Typkonvertierungsprobleme.

1. Verwenden Sie allgemeine freigegebene Typen. Der jeweilige freigegebene Typ kann ein primitiver Runtimetyp sein, oder Sie können einen neuen freigegebenen Typ in einer freigegebenen Assembly erstellen.  Häufig handelt es sich bei dem freigegebenen Typ um eine [Schnittstelle](../../csharp/language-reference/keywords/interface.md), die in einer Anwendungsassembly definiert ist. Siehe auch: [Wie werden Abhängigkeiten gemeinsam genutzt?](#how-are-dependencies-shared)

2. Verwenden Sie Marshallingtechniken, um Typen zu konvertieren.
