---
title: Entwurf statischer Klassen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 35bcf1d403c78cdfcbb476b2eb5de2251a564b9a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709061"
---
# <a name="static-class-design"></a>Entwurf statischer Klassen
Eine statische Klasse wird als Klasse definiert, die nur statische Member enthält (natürlich neben den Instanzmembern, die von <xref:System.Object?displayProperty=nameWithType> und möglicherweise einem privaten Konstruktor geerbt werden). Einige Sprachen bieten integrierte Unterstützung für statische Klassen. In C# 2,0 und höher, wenn eine Klasse als statisch deklariert wird, ist Sie versiegelt, abstrakt, und keine Instanzmember können überschrieben oder deklariert werden.  
  
 Statische Klassen stellen einen Kompromiss zwischen dem reinen objektorientierten Design und der Einfachheit dar. Sie werden häufig verwendet, um Verknüpfungen zu anderen Vorgängen (z. b. <xref:System.IO.File?displayProperty=nameWithType>), Inhaber von Erweiterungs Methoden oder Funktionen, für die ein vollständiger objektorientierter Wrapper nicht gerechtfertigt ist (z. b. <xref:System.Environment?displayProperty=nameWithType>), bereitzustellen.  
  
 **✓ DO** statische Klassen nur selten zu verwenden.  
  
 Statische Klassen sollten nur als unterstützende Klassen für den objektorientierten Kern des Frameworks verwendet werden.  
  
 **X DO NOT** statische Klassen als Bucket für verschiedene Elemente behandeln.  
  
 **X DO NOT** deklarieren oder Instanzmember in statischen Klassen zu überschreiben.  
  
 **✓ DO** deklarieren Sie statische Klassen als versiegelt, "abstract", und fügen Sie eine private Instanzkonstruktor hinzu, wenn Ihre Programmiersprache keine integrierten Unterstützung für statische Klassen.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
