---
title: Ereignisse und Rückrufe
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 390c12af7107bb78fc261c55ea15390cf9eaa5b7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43862948"
---
# <a name="events-and-callbacks"></a>Ereignisse und Rückrufe
Rückrufe sind Erweiterungspunkte, die ein Framework Rückruf in Benutzercode durch einen Delegaten zu ermöglichen. Diese Delegaten werden in der Regel für das Framework über einen Parameter einer Methode übergeben.  
  
 Ereignisse sind ein Sonderfall der Rückrufe, der bequeme, einheitliche Syntax unterstützt wird, für den Delegaten (ein Ereignishandler) angeben. Darüber hinaus bieten die Anweisungsvervollständigung und Designer von Visual Studio Hilfe bei der Verwendung von Ereignis-basierten APIs. (Finden Sie unter [Ereignisentwurf](../../../docs/standard/design-guidelines/event.md).)  
  
 **✓ CONSIDER** Verwendung von Rückrufen Benutzer geben Sie benutzerdefinierten Code, der durch das Framework ausgeführt werden darf.  
  
 **✓ CONSIDER** Ereignisse verwenden, um Benutzern das Anpassen des Verhaltens von einem Framework ohne die Notwendigkeit, um zu verstehen, eines objektorientierten Entwurfs zu ermöglichen.  
  
 **✓ DO** plain Rückrufe Ereignisse vorziehen, da sie mehr zu einem breiteren Spektrum von Entwicklern vertraut sind und mit Visual Studio-Anweisungsvervollständigung integriert sind.  
  
 **X AVOID** Rückrufe in leistungsabhängigen-APIs verwenden.  
  
 **✓ DO** verwenden Sie die neue `Func<...>`, `Action<...>`, oder `Expression<...>` Typen anstelle von benutzerdefinierten Delegaten, wenn APIs mit Rückrufe zu definieren.  
  
 `Func<...>` und `Action<...>` generische Delegaten darstellen. `Expression<...>` Stellt Funktionsdefinitionen, die kompiliert und anschließend zur Laufzeit kann aber auch aufgerufen werden können, serialisiert und an remote-Prozesse übergeben werden.  
  
 **✓ DO** messen und Verstehen von Auswirkungen auf die Leistung der Verwendung von `Expression<...>`, anstatt `Func<...>` und `Action<...>` Delegaten.  
  
 `Expression<...>` Typen sind in den meisten Fällen ist logisch äquivalent zur `Func<...>` und `Action<...>` Delegaten. Der Hauptunterschied zwischen diesen besteht darin, dass die Delegaten in lokalen Prozess Szenarien verwendet werden sollen; Ausdrücke werden für Fälle gedacht, bei denen es vorteilhaft und zum Auswerten des Ausdrucks in einer remote-Prozess oder Computer möglich.  
  
 **✓ DO** verstehen, dass durch den Aufruf eines Delegaten, beliebigen Code ausführen und bei denen konnte Sicherheit, Richtigkeit und Kompatibilität Verarbeitungsverhaltens.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
