---
title: Strukturentwurf
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3879dc3f0270a56132b44882a74c50d05914ff89
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862483"
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
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Auswählen zwischen Klasse und Struktur](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
