---
title: Entwurf statischer Klassen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 28fe3756a2881e8f746616f8275b505b1a01eada
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Typ-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/type.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
