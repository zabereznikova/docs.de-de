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
author: KrzysztofCwalina
ms.openlocfilehash: d0a2f11b53f50f2ec2f301f7b88df65e1cd7b811
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762045"
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
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
