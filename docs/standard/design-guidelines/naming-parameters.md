---
title: Benennen von Parametern
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: KrzysztofCwalina
ms.openlocfilehash: 0e5b33839372e303b96bd6b84949f9a82da2f689
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026305"
---
# <a name="naming-parameters"></a>Benennen von Parametern
Nach der naheliegende Grund für lesbaren Code ist es wichtig, die Richtlinien für Parameternamen zu befolgen, da der Parameter in der Dokumentation und im Designer angezeigt werden, wenn visuellen Entwurfstools Intellisense und die Klasse, die Durchsuchen-Funktionalität bereitstellt.  
  
 **✓ DO** CamelCasing Parameternamen verwenden.  
  
 **✓ DO** beschreibende Parameternamen verwenden.  
  
 **✓ CONSIDER** mit Namen basierend auf den Typ des Parameters, anstatt die Bedeutung eines Parameters.  
  
### <a name="naming-operator-overload-parameters"></a>Benennen von Parametern für Operator-Überladung  
 **✓ DO** verwenden `left` und `right` für binären Operator Überladung Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.  
  
 **✓ DO** verwenden `value` für unäre Operator überladen Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.  
  
 **✓ CONSIDER** aussagekräftige Namen für den Operator überladen Parameter aus, wenn dies also erheblichem Wert hinzugefügt.  
  
 **X DO NOT** verwenden Abkürzungen oder numerischen Indizes für Operator überladen Parameternamen.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
