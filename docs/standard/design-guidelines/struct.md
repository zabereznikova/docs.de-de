---
title: Strukturentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
author: KrzysztofCwalina
ms.openlocfilehash: cc5b8d7effda31b0236477b217bccf5cf2137f8c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646606"
---
# <a name="struct-design"></a>Strukturentwurf
Der allgemeine Typ wird meist als eine Struktur, die c#-Schlüsselwort bezeichnet. Dieser Abschnitt enthält Richtlinien für den Strukturentwurf von allgemeinen.  
  
 **X DO NOT** einen Standardkonstruktor für eine Struktur bereitstellen.  
  
 Diese Richtlinien kann Arrays von Strukturen erstellt werden, ohne dass den Konstruktor für jedes Element des Arrays ausgeführt. Beachten Sie, dass C#-Strukturen, die über Standardkonstruktoren verfügen nicht zulässt.  
  
 **X DO NOT** änderbaren Werts Typen definieren.  
  
 Änderbare Werttypen müssen mehrere Probleme. Wenn Getter für eine Eigenschaft ein Werttyps zurückgegeben wird, erhält der Aufrufer z. B. eine Kopie an. Da die Kopie implizit erstellt wird, können Entwickler nicht bedenken, dass sie die Kopie, und nicht der ursprüngliche Wert mutierende sind. Darüber hinaus verfügen einige Sprachen (dynamische Sprachen, insbesondere bei) Probleme mit Werttypen des änderbar, da lokale Variablen, sogar, wenn dereferenziert, dazu führen, dass eine Kopie an.  
  
 **✓ DO** stellen Sie sicher, dass ein Zustand, in dem alle Instanzdaten, auf 0 (null) festgelegt ist, false oder null (nach Bedarf) ist ungültig.  
  
 Dadurch wird die versehentliche Erstellung Ungültiger Instanzen verhindert, wenn ein Array von Strukturen erstellt wird.  
  
 **✓ DO** implementieren <xref:System.IEquatable%601> für Werttypen.  
  
 Die <xref:System.Object.Equals%2A?displayProperty=nameWithType> -Methode für Werttypen wird der Boxing, und der Standardimplementierung nicht sehr effizient, weil Reflexion verwendet. <xref:System.IEquatable%601.Equals%2A> kann viel bessere Leistung und können implementiert werden, damit sie keine Boxing verursacht.  
  
 **X DO NOT** explizit erweitern <xref:System.ValueType>. In der Tat verhindern dies, die meisten Sprachen.  
  
 Im Allgemeinen Strukturen können sehr nützlich sein, jedoch sollte nur verwendet werden, für kleine, einzelne, unveränderliche Werte, die nicht häufig geschachtelt werden.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Auswählen zwischen Klasse und Struktur](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
