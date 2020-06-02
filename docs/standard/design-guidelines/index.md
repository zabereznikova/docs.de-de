---
title: Frameworkentwurfsrichtlinien
titleSuffix: ''
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
ms.openlocfilehash: 5a4edca70844a2b2a3972381b34efe85664f353d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276035"
---
# <a name="framework-design-guidelines"></a>Frameworkentwurfsrichtlinien
Dieser Abschnitt enthält Richtlinien zum Entwerfen von Bibliotheken, die die .NET Framework erweitern und mit ihnen interagieren. Ziel ist es, Bibliotheks-Designern zu helfen, die API-Konsistenz und Benutzerfreundlichkeit sicherzustellen, indem Sie ein einheitliches Programmiermodell bereitstellen, das von der für die Entwicklung verwendeten Programmiersprache unabhängig ist. Es wird empfohlen, dass Sie diese Entwurfs Richtlinien befolgen, wenn Sie Klassen und Komponenten entwickeln, mit denen die .NET Framework erweitert wird. Inkonsistentes Bibliotheks Design wirkt sich negativ auf die Produktivität von Entwicklern aus und verhindert die Übernahme  
  
 Die Richtlinien sind als einfache Empfehlungen organisiert, die die Begriffe,, und als Präfix haben `Do` `Consider` `Avoid` `Do not` . Diese Richtlinien sollen Entwicklern von Klassenbibliotheken helfen, die Kompromisse zwischen verschiedenen Lösungen nachzuvollziehen. Es kann Situationen geben, in denen ein guter Bibliotheks Entwurf erfordert, dass Sie diese Entwurfs Richtlinien verletzen. Solche Fälle sollten selten auftreten, und es ist wichtig, dass Sie einen klaren und überzeugenden Grund für Ihre Entscheidung haben.  
  
 Diese Richtlinien werden aus den Buch Framework- *Entwurfs Richtlinien entnommen: Konventionen, Idioms und Muster für wiederverwendbare .NET-Bibliotheken, 2. Edition*, von Krzysztof Cwalina und Brad Abrams.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Benennungs Richtlinien](naming-guidelines.md)  
 Enthält Richtlinien zum Benennen von Assemblys, Namespaces, Typen und Membern in Klassenbibliotheken.  
  
 [Typentwurfs Richtlinien](type.md)  
 Stellt Richtlinien für die Verwendung statischer und abstrakter Klassen, Schnittstellen, Enumerationen, Strukturen und anderer Typen bereit.  
  
 [Entwurfs Richtlinien für Member](member.md)  
 Stellt Richtlinien zum Entwerfen und Verwenden von Eigenschaften, Methoden, Konstruktoren, Feldern, Ereignissen, Operatoren und Parametern bereit.  
  
 [Entwerfen für Erweiterbarkeit](designing-for-extensibility.md)  
 Erläutert Erweiterungs Mechanismen, wie z. b. Unterklassen, using-Ereignisse, Virtual Members und Rückrufe, und erläutert, wie Sie die Mechanismen auswählen, die die Anforderungen Ihres Frameworks am besten erfüllen.  
  
 [Entwurfsrichtlinien für Ausnahmen](exceptions.md)  
 Beschreibt Entwurfs Richtlinien zum Entwerfen, auslösen und Abfangen von Ausnahmen.  
  
 [Verwendungs Richtlinien](usage-guidelines.md)  
 Beschreibt Richtlinien für die Verwendung allgemeiner Typen wie Arrays, Attribute und Auflistungen, unterstützen der Serialisierung und Überladen von Gleichheits Operatoren.  
  
 [Allgemeine Entwurfsmuster](common-design-patterns.md)  
 Stellt Richtlinien für das auswählen und Implementieren von Abhängigkeits Eigenschaften bereit.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht](../../framework/get-started/overview.md)
- [Entwicklungshandbuch](../../framework/development-guide.md)
