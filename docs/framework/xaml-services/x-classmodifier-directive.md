---
title: x:ClassModifier-Anweisung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
caps.latest.revision: "22"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a4918e23a915ee07eace388ea2cea512c2e479d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier-Anweisung
Ändert die XAML-Kompilierungsverhalten beim `x:Class` ebenfalls bereitgestellt wird. Speziell, statt eine partielle `class` , besitzt eine `Public` Zugriffsebene (Standardeinstellung), bereitgestellten `x:Class` wird erstellt, mit einer `NotPublic` Zugriffsebene. Dieses Verhalten wirkt sich auf die Zugriffsebene für die Klasse in die generierten Assemblys.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|*NotPublic*|Die genaue Zeichenfolge übergeben, um anzugeben, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> im Vergleich zu <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> variiert in Abhängigkeit von der Code-Behind-Programmiersprache, die Sie verwenden. Siehe Hinweise.|  
  
## <a name="dependencies"></a>Abhängigkeiten  
 [X: Class](../../../docs/framework/xaml-services/x-class-directive.md) muss ebenfalls für dasselbe Element bereitgestellt werden, und dieses Element muss das Stammelement auf einer Seite sein. Weitere Informationen finden Sie unter [ \[MS-XAML-\] Abschnitt 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Hinweise  
 Der Wert des `x:ClassModifier` Verwendung in .NET Framework XAML Services variiert je nach Programmiersprache. Die zu verwendende Zeichenfolge hängt von verschiedenen Sprachen wie implementiert die <xref:System.CodeDom.Compiler.CodeDomProvider> und -Typkonverter, die zurückgegeben wird, um die Bedeutung für definieren <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> und <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, und gibt an, ob diese Sprache Groß-/Kleinschreibung beachtet wird.  
  
-   Für [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], die Zeichenfolge übergeben, um zu bestimmen <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist `internal`.  
  
-   Für [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)], die Zeichenfolge übergeben, um zu bestimmen <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist `Friend`.  
  
-   Für [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], keine Ziele vorhanden sind, die das Kompilieren von XAML unterstützen; daher ist der Wert zur Übergabe nicht angegeben.  
  
 Sie können auch angeben, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Public` in [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]); allerdings angeben <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> selten geschieht, da ein <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ist bereits das Standardverhalten.  
  
 Andere Werte durch entsprechende Benutzercode Zugriffsebene Einschränkungen, wie z. B. `private` in [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], sind nicht relevant für `x:ClassModifier` da geschachtelte Klassenverweise in XAML wird nicht unterstützt werden und daher die <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Modifizierer hat die gleiche Auswirkung.  
  
## <a name="security-notes"></a>Sicherheitshinweise  
 Die Zugriffsebene, die gemäß der Deklaration in `x:ClassModifier` unterliegt Interpretation von bestimmten Frameworks und ihre Funktionen nach wie vor. WPF enthält Funktionen zum Laden und Instanziieren von Typen, in denen `x:ClassModifier` ist `internal`, sofern dieser Klasse aus einer WPF-Ressource über einen URI-Verweis-Paket verwiesen wird. Als Folge dieser Groß-/Kleinschreibung und potenziell andere wie er von anderen Frameworks implementiert, verlassen Sie sich nicht ausschließlich auf `x:ClassModifier` versucht, alle möglichen Instanziierung zu blockieren.  
  
## <a name="see-also"></a>Siehe auch  
 [x:Class-Anweisung](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Code-Behind und XAML in WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [x:FieldModifier-Anweisung](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)  
 [Sicherheit (WPF)](../../../docs/framework/wpf/security-wpf.md)  
 [Aus WPF zu System.Xaml migrierte Typen](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
