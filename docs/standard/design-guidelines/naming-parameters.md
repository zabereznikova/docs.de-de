---
title: Benennen von Parametern
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3e5dfe35fd4f2939898acee44764535c6de5fe9e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="naming-parameters"></a>Benennen von Parametern
Über die offensichtlichen Grund der Lesbarkeit ist es wichtig, die Richtlinien für Parameternamen zu folgen, da der Parameter in der Dokumentation und im Designer angezeigt werden, wenn visuellen Entwurfstools Intellisense und Funktionen durchsuchen Klasse bereitzustellen.  
  
 **Führen Sie ✓** CamelCasing Parameternamen verwenden.  
  
 **Führen Sie ✓** beschreibende Parameternamen verwenden.  
  
 **✓ GGF.** mit Namen basierend auf den Typ des Parameters, anstatt die Bedeutung eines Parameters.  
  
### <a name="naming-operator-overload-parameters"></a>Benennen der-Operator Überladung Parameter  
 **Führen Sie ✓** verwenden `left` und `right` für binären Operator Überladung Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.  
  
 **Führen Sie ✓** verwenden `value` für unäre Operator überladen Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.  
  
 **✓ GGF.** aussagekräftige Namen für den Operator überladen Parameter aus, wenn dies also erheblichem Wert hinzugefügt.  
  
 **X nicht** verwenden Abkürzungen oder numerischen Indizes für Operator überladen Parameternamen.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
