---
title: Entwurf statischer Klassen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3a0a51fc6055190f9a0189de2e17d98f88036ea
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46697645"
---
# <a name="static-class-design"></a>Entwurf statischer Klassen
Eine statische Klasse als eine Klasse, nur statische Member enthält, definiert ist (natürlich als Instanzmember vererbt <xref:System.Object?displayProperty=nameWithType> und möglicherweise einen privaten Konstruktor). Einige Sprachen bieten integrierte Unterstützung für statische Klassen. In c# 2.0 und höher, wenn eine Klasse statisch deklariert wird, es ist versiegelt, "abstract", und keine Instanzmember deklariert oder außer Kraft gesetzt werden können.  
  
 Statische Klassen sind ein Kompromiss zwischen rein objektorientiertes Design und Einfachheit. Sie werden häufig verwendet, um Verknüpfungen zu anderen Vorgängen bereitzustellen (z. B. <xref:System.IO.File?displayProperty=nameWithType>), werden Erweiterungsmethoden oder Funktionen, die für die ein vollständig objektorientierten Wrapper ungerechtfertigten ist (z. B. <xref:System.Environment?displayProperty=nameWithType>).  
  
 **✓ DO** statische Klassen nur selten zu verwenden.  
  
 Statische Klassen sollten nur als Klassen zur Unterstützung für objektorientierte Core Framework verwendet werden.  
  
 **X DO NOT** statische Klassen als Bucket für verschiedene Elemente behandeln.  
  
 **X DO NOT** deklarieren oder Instanzmember in statischen Klassen zu überschreiben.  
  
 **✓ DO** deklarieren Sie statische Klassen als versiegelt, "abstract", und fügen Sie eine private Instanzkonstruktor hinzu, wenn Ihre Programmiersprache keine integrierten Unterstützung für statische Klassen.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
