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
ms.openlocfilehash: 92152600d317c04e3fef26400b11e94a549fde4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="static-class-design"></a>Entwurf statischer Klassen
Eine statische Klasse als eine Klasse, nur statische Member enthält, definiert ist (natürlich neben der Instanzmember geerbt von <xref:System.Object?displayProperty=nameWithType> und möglicherweise einen privaten Konstruktor). Für einige Sprachen bieten integrierte Unterstützung für statische Klassen. In c# 2.0 und höher, wenn eine Klasse als statisch deklariert ist, ist versiegelt, "abstract", und keine Instanzmember überschreiben oder deklariert werden können.  
  
 Statische Klassen sind, einen Kompromiss zwischen reinen eines objektorientierten Entwurfs und Einfachheit. Sie werden häufig verwendet, um Verknüpfungen zu anderen Vorgängen bereitzustellen (z. B. <xref:System.IO.File?displayProperty=nameWithType>), Inhaber von Erweiterungsmethoden [c#], oder Funktionen, die für die ein vollständige objektorientierten Wrapper unbefugten ist (z. B. <xref:System.Environment?displayProperty=nameWithType>).  
  
 **Führen Sie ✓** statische Klassen nur selten zu verwenden.  
  
 Statische Klassen sollte nur als unterstützende Klassen für den objektorientierten Kern des Frameworks verwendet werden.  
  
 **X nicht** statische Klassen als Bucket für verschiedene Elemente behandeln.  
  
 **X nicht** deklarieren oder Instanzmember in statischen Klassen zu überschreiben.  
  
 **Führen Sie ✓** deklarieren Sie statische Klassen als versiegelt, "abstract", und fügen Sie eine private Instanzkonstruktor hinzu, wenn Ihre Programmiersprache keine integrierten Unterstützung für statische Klassen.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
