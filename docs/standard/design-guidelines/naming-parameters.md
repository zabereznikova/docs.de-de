---
title: Benennen von Parametern
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: 0bb67056bb39b6a5f372191a1d0b0bb0dc1fe4d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709178"
---
# <a name="naming-parameters"></a>Benennen von Parametern
Neben dem offensichtlichen Grund für die Lesbarkeit ist es wichtig, den Richtlinien für Parameternamen zu folgen, da Parameter in der-Dokumentation und im-Designer angezeigt werden, wenn visuelle Entwurfs Tools IntelliSense-und Klassen Suchfunktionen bereitstellen.  
  
 **✓ DO** CamelCasing Parameternamen verwenden.  
  
 **✓ DO** beschreibende Parameternamen verwenden.  
  
 **✓ CONSIDER** mit Namen basierend auf den Typ des Parameters, anstatt die Bedeutung eines Parameters.  
  
### <a name="naming-operator-overload-parameters"></a>Überladungs Parameter für Benennungs Operator  
 **✓ DO** verwenden `left` und `right` für binären Operator Überladung Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.  
  
 **✓ DO** verwenden `value` für unäre Operator überladen Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.  
  
 **✓ CONSIDER** aussagekräftige Namen für den Operator überladen Parameter aus, wenn dies also erheblichem Wert hinzugefügt.  
  
 **X DO NOT** verwenden Abkürzungen oder numerischen Indizes für Operator überladen Parameternamen.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
