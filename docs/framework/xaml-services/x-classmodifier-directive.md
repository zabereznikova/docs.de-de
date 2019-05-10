---
title: x:ClassModifier-Anweisung
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 8f90f56a595fa175d5c48a929fc19ceb81ab0d63
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617107"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier-Anweisung
Ändert die XAML-Kompilierungsverhalten beim `x:Class` wird ebenfalls bereitgestellt. Insbesondere statt einer partiellen `class` , bei dem ein `Public` Zugriffsebene (Standard), der bereitgestellten `x:Class` wird erstellt, mit einer `NotPublic` Zugriffsebene. Dieses Verhalten wirkt sich auf die Zugriffsebene für die Klasse in der generierten Assemblys.  
  
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
 [X: Class](x-class-directive.md) muss auch angegeben werden, auf das gleiche Element, und dieses Element muss das Stammelement auf einer Seite sein. Weitere Informationen finden Sie unter [ \[MS-XAML-\] Abschnitt 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Hinweise  
 Der Wert des `x:ClassModifier` Nutzung in .NET Framework-XAML-Diensten variiert je nach Programmiersprache. Wie jede Sprache implementiert, die zu verwendende Zeichenfolge hängt die <xref:System.CodeDom.Compiler.CodeDomProvider> und der Typkonverter wird zurückgegeben, um die Bedeutung für definieren <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> und <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, und gibt an, ob die entsprechende Sprache Groß-/Kleinschreibung beachtet wird.  
  
- Für c# und die Zeichenfolge übergeben, um zu bestimmen <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist `internal`.  
  
- Für Microsoft Visual Basic .NET ist die Zeichenfolge übergeben, um zu bestimmen <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist `Friend`.  
  
- Für [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], keine Ziele vorhanden sind, die Kompilierung von XAML unterstützen; aus diesem Grund ist der zu übergebende Wert nicht angegeben.  
  
 Sie können auch angeben, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in c# `Public` in Visual Basic), aber angeben <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> selten geschieht, da <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ist bereits das Standardverhalten.  
  
 Andere Werte durch entsprechende Benutzercode Zugriffsebene Einschränkungen, z. B. `private` in c# sind nicht relevant für `x:ClassModifier` da geschachtelte Klassenverweise in XAML, nicht unterstützt werden und somit die <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Modifizierer hat dieselbe Wirkung.  
  
## <a name="security-notes"></a>Sicherheitshinweise  
 Die Zugriffsebene, die gemäß der Deklaration in `x:ClassModifier` interpretiert wird, weiterhin von bestimmten Frameworks und ihre Funktionen. WPF enthält Funktionen zum Laden und Instanziieren von Typen, in denen `x:ClassModifier` ist `internal`, wenn die Klasse aus einer WPF-Ressource über einen Paket-URI-Verweis verwiesen wird. Als Folge dieses Falls und potenziell andere wie es von anderen Frameworks implementiert, verlassen Sie sich nicht ausschließlich auf `x:ClassModifier` versucht, alle möglichen Instanziierung zu blockieren.  
  
## <a name="see-also"></a>Siehe auch

- [x:Class-Anweisung](x-class-directive.md)
- [Code-Behind und XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier-Anweisung](x-fieldmodifier-directive.md)
- [Sicherheit (WPF)](../wpf/security-wpf.md)
- [Aus WPF zu System.Xaml migrierte Typen](types-migrated-from-wpf-to-system-xaml.md)
