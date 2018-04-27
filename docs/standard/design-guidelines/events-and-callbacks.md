---
title: Ereignisse und Rückrufe
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6a6851d1be543fe356827cad67b28cafdc9e56c2
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="events-and-callbacks"></a>Ereignisse und Rückrufe
Rückrufe sind Erweiterungspunkte, mit die ein Framework zum Benutzercode über einen Delegaten erneut aufrufen können. Diese Delegaten werden in der Regel an das Framework über einen Parameter einer Methode übergeben.  
  
 Ereignisse sind ein spezieller Fall der Rückrufe, der bequeme, einheitliche Syntax unterstützt werden, für den Delegaten (einen Ereignishandler) angeben. Darüber hinaus bieten Visual Studio Anweisungsvervollständigung und Designern Hilfe zur Verwendung der ereignisbasierten-APIs. (Siehe [Ereignis Entwurf](../../../docs/standard/design-guidelines/event.md).)  
  
 **✓ GGF.** Verwendung von Rückrufen Benutzer geben Sie benutzerdefinierten Code, der durch das Framework ausgeführt werden darf.  
  
 **✓ GGF.** Ereignisse verwenden, um Benutzern das Anpassen des Verhaltens von einem Framework ohne die Notwendigkeit, um zu verstehen, eines objektorientierten Entwurfs zu ermöglichen.  
  
 **Führen Sie ✓** plain Rückrufe Ereignisse vorziehen, da sie mehr zu einem breiteren Spektrum von Entwicklern vertraut sind und mit Visual Studio-Anweisungsvervollständigung integriert sind.  
  
 **X vermeiden** Rückrufe in leistungsabhängigen-APIs verwenden.  
  
 **✓ FÜHREN** verwenden Sie die neue `Func<...>`, `Action<...>`, oder `Expression<...>` Typen anstelle von benutzerdefinierten Delegaten, wenn APIs mit Rückrufe zu definieren.  
  
 `Func<...>` und `Action<...>` generische Delegaten darstellen. `Expression<...>` Stellt Funktionsdefinitionen, die kompiliert und anschließend zur Laufzeit kann aber auch aufgerufen werden können werden serialisiert und an remote-Prozesse übergeben.  
  
 **Führen Sie ✓** messen und Verstehen von Auswirkungen auf die Leistung der Verwendung von `Expression<...>`, anstatt `Func<...>` und `Action<...>` Delegaten.  
  
 `Expression<...>` Typen sind in den meisten Fällen ist logisch äquivalent zu `Func<...>` und `Action<...>` Delegaten. Der Hauptunterschied zwischen beiden ist, dass die Delegaten in lokalen Prozess Szenarien verwendet werden sollen. Ausdrücke sind für Fälle vorgesehen, in denen es vorteilhaft und zum Auswerten des Ausdrucks in einer remote-Prozess oder Computer möglich ist.  
  
 **Führen Sie ✓** verstehen, dass durch den Aufruf eines Delegaten, beliebigen Code ausführen und bei denen konnte Sicherheit, Richtigkeit und Kompatibilität Verarbeitungsverhaltens.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
