---
title: Ereignisse und Rückrufe
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
ms.openlocfilehash: 7dab759ba48104530fc41e46f6f2bba18d6c4456
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741656"
---
# <a name="events-and-callbacks"></a>Ereignisse und Rückrufe
Rückrufe sind Erweiterungs Punkte, mit denen ein Framework über einen Delegaten den Benutzercode aufrufen kann. Diese Delegaten werden in der Regel über einen Parameter einer Methode an das Framework übergeben.

 Ereignisse sind ein Sonderfall von Rückrufen, die eine bequeme und konsistente Syntax für die Bereitstellung des Delegaten (eines Ereignis Handlers) unterstützen. Außerdem bieten die Visual Studio-Anweisungs Vervollständigung und Designer Hilfe bei der Verwendung von ereignisbasierten APIs. (Siehe [Ereignis Entwurf](../../../docs/standard/design-guidelines/event.md).)

 ✔️ sollten die Verwendung von Rückrufen in Erwägung gezogen werden, damit Benutzer benutzerdefinierten Code bereitstellen können, der vom Framework ausgeführt werden kann

 ✔️ sollten Sie die Verwendung von Ereignissen in Erwägung gezogen, um Benutzern das Anpassen des Verhaltens eines Frameworks zu ermöglichen, ohne den objektorientierten Entwurf verstehen zu müssen.

 ✔️ bevorzugen Ereignisse über einfache Rückrufe, da Sie einer breiteren Palette von Entwicklern vertraut sind und in die Visual Studio-Anweisungs Vervollständigung integriert sind.

 ❌ sollten keine Rückrufe in Leistungs sensiblen APIs verwenden.

 beim Definieren von APIs mit Rückrufen ✔️ die neuen `Func<...>`, `Action<...>`oder `Expression<...>` Typen anstelle von benutzerdefinierten Delegaten verwenden.

 `Func<...>` und `Action<...>` stellen generische Delegaten dar. `Expression<...>` stellt Funktionsdefinitionen dar, die kompiliert und anschließend zur Laufzeit aufgerufen werden können, aber auch serialisiert und an Remote Prozesse weitergegeben werden können.

 ✔️ können die Leistungseinbußen bei der Verwendung von `Expression<...>`Messen und verstehen, anstatt `Func<...>` und `Action<...>` Delegaten zu verwenden.

 `Expression<...>` Typen sind in den meisten Fällen logisch äquivalent zu `Func<...>` und `Action<...>` Delegaten. Der Hauptunterschied besteht darin, dass die Delegaten in lokalen Prozess Szenarien verwendet werden sollen. Ausdrücke sind für Fälle gedacht, in denen es vorteilhaft und möglich ist, den Ausdruck in einem Remote Prozess oder-Computer auszuwerten.

 ✔️ verstehen, dass Sie durch Aufrufen eines Delegaten beliebigen Code ausführen, der Sicherheits-, Richtigkeit-und Kompatibilitäts Auswirkungen haben kann.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
