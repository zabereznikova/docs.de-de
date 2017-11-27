---
title: Frameworkentwurfsrichtlinien
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a812207fb58e6c87c263966081060d02f8038963
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="framework-design-guidelines"></a>Frameworkentwurfsrichtlinien
Dieser Abschnitt enthält Richtlinien zum Entwerfen von Bibliotheken, die erweitert und interagieren mit .NET Framework. Ziel ist es, Hilfe Bibliotheksentwickler sicherzustellen API Konsistenz und einfache Verwendung durch die Bereitstellung eines einheitlichen Programmiermodell, das unabhängig von der Programmiersprache ab, die für die Entwicklung verwendet wird. Es wird empfohlen, dass Sie diese Entwurfsrichtlinien befolgen, bei der Entwicklung von Klassen und Komponenten, die .NET Framework zu erweitern. Inkonsistente Bibliotheksentwurf wirkt sich auf die Produktivität der Entwickler negativ und ungern.  
  
 Die Richtlinien werden als einfache Empfehlungen, die mit den Begriffen vorangestellt organisiert `Do`, `Consider`, `Avoid`, und `Do not`. Diese Richtlinien dienen dem Schutz von Klassenbibliotheken, die die vor-und Nachteile zwischen verschiedenen-Lösungen zu verstehen. Es gibt möglicherweise Situationen, in denen gute Bibliotheksentwurf erfordert, dass Sie diese Richtlinien für den Entwurf verletzt. Solchen Fällen dürfte selten passieren, und es ist wichtig, dass Sie einen klare und überzeugenden Grund für Ihre Entscheidung haben.  
  
 Diese Richtlinien sind ein Auszug aus dem Buch *Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition*, indem Sie Krzysztof Cwalina und Brad Abrams.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Benennungsrichtlinien](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 Enthält Richtlinien zum Benennen von Assemblys, Namespaces, Typen und Member in Klassenbibliotheken.  
  
 [Typ-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/type.md)  
 Enthält Richtlinien für die Verwendung von statischen und abstrakten Klassen, Schnittstellen, Enumerationen, Strukturen und andere Typen.  
  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
 Enthält Richtlinien zum Entwerfen und Verwenden von Eigenschaften, Methoden, Konstruktoren, Felder, Ereignisse, Operatoren und Parameter.  
  
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 Erweiterungsmechanismen z. B. Erstellen von Unterklassen von Ereignissen, virtuelle Member und Rückrufe erläutert und wird erläutert, wie die Mechanismen auswählen, die am besten für Ihr Framework erfüllen.  
  
 [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)  
 Beschreibt Entwurfsrichtlinien für das Entwerfen, auslösen und Abfangen von Ausnahmen.  
  
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 Enthält Richtlinien für allgemeine Typen wie z. B. Arrays, Attribute und Sammlungen verwenden, unterstützen die Serialisierung und Überladen von Gleichheitsoperatoren.  
  
 [Allgemeiner Entwurfsmuster](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 Enthält Richtlinien zum auswählen und Implementieren von Abhängigkeitseigenschaften und das Dispose-Muster.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht](../../../docs/framework/get-started/overview.md)  
 [Roadmap für .NET Framework](http://msdn.microsoft.com/en-us/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)  
 [Entwicklungshandbuch](../../../docs/framework/development-guide.md)
