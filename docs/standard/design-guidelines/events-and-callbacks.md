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
author: KrzysztofCwalina
ms.openlocfilehash: 3609d6ac4847cb081740fd698869df4976f83f8f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525481"
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
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
