---
title: Strukturentwurf
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1566d2b67e1dda5b0b221a2c10affb6bdaea888
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="struct-design"></a>Strukturentwurf
Der allgemeine Typ wird am häufigsten als eine Struktur, die C#-Schlüsselwort bezeichnet. Dieser Abschnitt enthält Richtlinien für den Entwurf der allgemeinen Struktur.  
  
 **X nicht** einen Standardkonstruktor für eine Struktur bereitstellen.  
  
 Befolgen diese Richtlinie können Arrays von Strukturen erstellt werden, ohne dass den Konstruktor für jedes Element des Arrays ausgeführt. Beachten Sie, dass c# über Standardkonstruktoren verfügen Strukturen nicht zulässt.  
  
 **X nicht** änderbaren Werts Typen definieren.  
  
 Änderbare Werttypen sind mehrere Probleme. Z. B. wenn einen Werttyp in ein Eigenschaften-Getter zurückgegeben wird, erhält der Aufrufer eine Kopie. Da die Kopie implizit erstellt wird, können Entwickler nicht bewusst sein, dass sie die Kopie und nicht den ursprünglichen Wert veränderliche sind. Für einige Sprachen (insbesondere dynamischen Sprachen) müssen außerdem Probleme änderbare Werttypen verwenden, da dies gilt auch für lokale Variablen, beim Dereferenzieren, dazu führen, dass eine Kopie erstellt werden.  
  
 **Führen Sie ✓** stellen Sie sicher, dass ein Zustand, in dem alle Instanzdaten, auf 0 (null) festgelegt ist, false oder null (nach Bedarf) ist ungültig.  
  
 Dies verhindert die versehentliche Erstellung Ungültiger Instanzen, wenn ein Array von Strukturen erstellt wird.  
  
 **Führen Sie ✓** implementieren <xref:System.IEquatable%601> für Werttypen.  
  
 Die <xref:System.Object.Equals%2A?displayProperty=nameWithType> -Methode für Werttypen wird der Boxing, und die standardmäßige Implementierung ist nicht sehr effizient, da Reflektion verwendet wird. <xref:System.IEquatable%601.Equals%2A>können viel bessere Leistung und können implementiert werden, damit er keine Boxing entstehen.  
  
 **X nicht** explizit erweitern <xref:System.ValueType>. Tatsächlich werden in den meisten Sprachen dies verhindern.  
  
 Im Allgemeinen Strukturen können sehr nützlich sein, jedoch sollte nur verwendet werden, für kleine, einzelne, unveränderliche Werte, die nicht häufig geschachtelt werden.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Typ-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/type.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Auswählen zwischen Klassen und Strukturen](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
