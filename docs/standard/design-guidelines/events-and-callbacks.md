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
ms.openlocfilehash: 80c16e29f1d8a0653295ebc3cf25be6fb78b7dc9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709412"
---
# <a name="events-and-callbacks"></a>Ereignisse und Rückrufe
Rückrufe sind Erweiterungs Punkte, mit denen ein Framework über einen Delegaten den Benutzercode aufrufen kann. Diese Delegaten werden in der Regel über einen Parameter einer Methode an das Framework übergeben.  
  
 Ereignisse sind ein Sonderfall von Rückrufen, die eine bequeme und konsistente Syntax für die Bereitstellung des Delegaten (eines Ereignis Handlers) unterstützen. Außerdem bieten die Visual Studio-Anweisungs Vervollständigung und Designer Hilfe bei der Verwendung von ereignisbasierten APIs. (Siehe [Ereignis Entwurf](../../../docs/standard/design-guidelines/event.md).)  
  
 **✓ CONSIDER** Verwendung von Rückrufen Benutzer geben Sie benutzerdefinierten Code, der durch das Framework ausgeführt werden darf.  
  
 **✓ CONSIDER** Ereignisse verwenden, um Benutzern das Anpassen des Verhaltens von einem Framework ohne die Notwendigkeit, um zu verstehen, eines objektorientierten Entwurfs zu ermöglichen.  
  
 **✓ DO** plain Rückrufe Ereignisse vorziehen, da sie mehr zu einem breiteren Spektrum von Entwicklern vertraut sind und mit Visual Studio-Anweisungsvervollständigung integriert sind.  
  
 **X AVOID** Rückrufe in leistungsabhängigen-APIs verwenden.  
  
 **✓ DO** verwenden Sie die neue `Func<...>`, `Action<...>`, oder `Expression<...>` Typen anstelle von benutzerdefinierten Delegaten, wenn APIs mit Rückrufe zu definieren.  
  
 `Func<...>` und `Action<...>` stellen generische Delegaten dar. `Expression<...>` stellt Funktionsdefinitionen dar, die kompiliert und anschließend zur Laufzeit aufgerufen werden können, aber auch serialisiert und an Remote Prozesse weitergegeben werden können.  
  
 **✓ DO** messen und Verstehen von Auswirkungen auf die Leistung der Verwendung von `Expression<...>`, anstatt `Func<...>` und `Action<...>` Delegaten.  
  
 `Expression<...>` Typen sind in den meisten Fällen logisch äquivalent zu `Func<...>` und `Action<...>` Delegaten. Der Hauptunterschied besteht darin, dass die Delegaten in lokalen Prozess Szenarien verwendet werden sollen. Ausdrücke sind für Fälle gedacht, in denen es vorteilhaft und möglich ist, den Ausdruck in einem Remote Prozess oder-Computer auszuwerten.  
  
 **✓ DO** verstehen, dass durch den Aufruf eines Delegaten, beliebigen Code ausführen und bei denen konnte Sicherheit, Richtigkeit und Kompatibilität Verarbeitungsverhaltens.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
