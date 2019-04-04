---
title: Frameworkentwurfsrichtlinien
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
author: KrzysztofCwalina
ms.openlocfilehash: c20430f9cdcd71cc2e178d38aeed48f9fa4e75c5
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2019
ms.locfileid: "56834897"
---
# <a name="framework-design-guidelines"></a>Frameworkentwurfsrichtlinien
Dieser Abschnitt enthält Richtlinien zum Entwerfen von Bibliotheken, die zu erweitern, und interagieren mit .NET Framework. Ziel ist es, sicherzustellen, dass API-Konsistenz und benutzerfreundlichkeit durch die Bereitstellung eines einheitlichen Programmiermodell, das unabhängig von der Programmiersprache, die für die Entwicklung verwendet Bibliotheks-Designer-Hilfe. Es wird empfohlen, dass Sie diese Entwurfsrichtlinien halten, bei der Entwicklung von Klassen und Komponenten, die .NET Framework zu erweitern. Inkonsistente Bibliotheksentwurf negativ wirkt sich auf Entwicklerproduktivität und ungern.  
  
 Die Richtlinien werden als einfache Empfehlungen präsentiert organisiert `Do`, `Consider`, `Avoid`, und `Do not`. Diese Richtlinien sollen Entwickler verstehen, die Kompromisse zwischen verschiedenen Lösungen helfen. Es gibt möglicherweise Situationen, in denen guten Bibliotheksentwurf erfordert, dass Sie diese Richtlinien für den Entwurf verletzt. Einem solchen Fall dürfte selten passieren, und es ist wichtig, dass einen deutliches und überzeugenden Grund für Ihre Entscheidung.  
  
 Diese Richtlinien sind ein Auszug aus dem Buch *Framework-Entwurfsrichtlinien vorgestellt: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET Bibliotheken, 2. Auflage*, indem Sie Krzysztof Cwalina und Brad Abrams.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 Enthält Richtlinien zum Benennen von Assemblys, Namespaces, Typen und Member in Klassenbibliotheken.  
  
 [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)  
 Enthält Richtlinien für die Verwendung von statischen und abstrakte Klassen, Schnittstellen, Enumerationen, Strukturen und andere Typen.  
  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
 Enthält Richtlinien zum Entwerfen und Verwenden von Eigenschaften, Methoden, Konstruktoren, Felder, Ereignisse, Operatoren und Parameter.  
  
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 Beschreibt Mechanismen zur Erweiterbarkeit wie z. B. Unterklassen, die mithilfe von Ereignissen, virtuelle Member und Rückrufe aus, und erläutert, wie auf die Mechanismen, die am besten des Frameworks Anforderungen erfüllen.  
  
 [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)  
 Beschreibt Entwurfsrichtlinien für das Entwerfen, auslösen und Abfangen von Ausnahmen.  
  
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 Enthält Richtlinien zum verwenden allgemeine Typen wie Arrays, Attribute und Sammlungen, zur Unterstützung der Serialisierung und Überladen von Gleichheitsoperatoren.  
  
 [Allgemeine Entwurfsmuster](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 Enthält Richtlinien zur Auswahl und Implementierung von Abhängigkeitseigenschaften.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht](../../../docs/framework/get-started/overview.md)
- [Entwicklungshandbuch](../../../docs/framework/development-guide.md)
