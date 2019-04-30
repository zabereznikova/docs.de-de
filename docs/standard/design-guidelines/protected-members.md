---
title: Geschützte Member
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: KrzysztofCwalina
ms.openlocfilehash: 7d940f10799df2efc6c6d031781e1ef7cf777dd6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937396"
---
# <a name="protected-members"></a>Geschützte Member
Geschützte Member selbst bieten keine Erweiterungen, jedoch können sie Erweiterbarkeit durch Unterklassen leistungsfähiger machen. Sie können verwendet werden, um erweiterte Anpassungsoptionen verfügbar zu machen, ohne unnötig verkompliziert die wichtigsten öffentliche Schnittstelle.  
  
 Framework-Entwickler müssen mit geschützten Elementen vorsichtig sein, da ein falsches Gefühl der Sicherheit mit der Namen "geschützt" gesetzt werden kann. Jeder Benutzer kann Unterklasse einer unversiegelten Klasse und den Zugriff auf geschützte Member, und daher die gleichen defensive Praktiken zur codeerstellung öffentliche Member zum gelten für geschützte Member.  
  
 **✓ CONSIDER** mit geschützte Member für die erweiterte Anpassung.  
  
 **✓ DO** geschützte Member in nicht versiegelten Klassen als öffentlich für die Sicherheit, Dokumentation und Kompatibilität Analyse zu behandeln.  
  
 Jeder kann von einer Klasse erben und die geschützten Member zuzugreifen.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
