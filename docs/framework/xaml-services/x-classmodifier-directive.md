---
title: "x:ClassModifier Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xClassModifier"
  - "x:ClassModifier"
  - "ClassModifier"
helpviewer_keywords: 
  - "XAML [XAML Services], x:ClassModifier attribute"
  - "x:ClassModifier attribute [XAML Services]"
  - "ClassModifier attribute in XAML [XAML Services]"
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
caps.latest.revision: 22
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 21
---
# x:ClassModifier Directive
Ändert das XAML\-Kompilierungsverhalten, wenn `x:Class` ebenfalls bereitgestellt wird.  Statt eine partielle `class` mit einer `Public`\-Zugriffsebene \(Standardeinstellung\) zu erstellen, wird die bereitgestellte `x:Class` spezifisch mit einer `NotPublic`\-Zugriffsebene erstellt.  Dieses Verhalten wirkt sich auf die Zugriffsebene für die Klasse in den generierten Assemblys aus.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|*NotPublic*|Welche Zeichenfolge genau zum Festlegen von <xref:System.Reflection.TypeAttributes?displayProperty=fullName> im Vergleich zu <xref:System.Reflection.TypeAttributes?displayProperty=fullName> übergeben wird, ist unterschiedlich und hängt von der verwendeten Code\-Behind\-Programmiersprache ab.  Siehe Hinweise.|  
  
## Abhängigkeiten  
 [x:Class](../../../docs/framework/xaml-services/x-class-directive.md) muss ebenfalls für dasselbe Element bereitgestellt werden, und dieses Element muss das Stammelement auf einer Seite sein.  Weitere Informationen finden Sie unter [b\[MS\-XAML\] Abschnitt 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## Hinweise  
 Der Wert von `x:ClassModifier` in der .NET Framework\-XAML\-Diensteverwendung variiert je nach Programmiersprache.  Die zu verwendende Zeichenfolge hängt davon ab, wie die jeweilige Sprache ihren <xref:System.CodeDom.Compiler.CodeDomProvider> implementiert, sowie von den Typkonvertern, die zum Definieren der Bedeutungen für <xref:System.Reflection.TypeAttributes?displayProperty=fullName> und <xref:System.Reflection.TypeAttributes?displayProperty=fullName> zurückgegeben werden, und ob bei der Sprache die Groß\- und Kleinschreibung beachtet werden muss.  
  
-   In [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)] lautet die zum Festlegen von <xref:System.Reflection.TypeAttributes?displayProperty=fullName> zu übergebende Zeichenfolge `internal`.  
  
-   In [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)] lautet die zum Festlegen von <xref:System.Reflection.TypeAttributes?displayProperty=fullName> zu übergebende Zeichenfolge `Friend`.  
  
-   Für [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)] sind keine Ziele vorhanden, die das Kompilieren von XAML unterstützen. Daher ist der zu übergebende Wert nicht angegeben.  
  
 Sie können auch <xref:System.Reflection.TypeAttributes?displayProperty=fullName> \(`public` in [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Public` in [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]\) angeben; <xref:System.Reflection.TypeAttributes?displayProperty=fullName> wird jedoch selten angegeben, da <xref:System.Reflection.TypeAttributes?displayProperty=fullName> bereits das Standardverhalten darstellt.  
  
 Andere Werte mit entsprechenden Einschränkungen für Benutzercode\-Zugriffsebenen, z. B. `private` in [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], sind für `x:ClassModifier` nicht relevant, da geschachtelte Klassenverweise in XAML nicht unterstützt werden. Daher hat der <xref:System.Reflection.TypeAttributes?displayProperty=fullName>\-Modifizierer die gleichen Auswirkungen.  
  
## Sicherheitshinweise  
 Die Zugriffsebene, wie in `x:ClassModifier` deklariert, unterliegt immer noch der Interpretation durch bestimmte Frameworks und ihre Funktionen.  WPF enthält Funktionen zum Laden und Instanziieren von Typen, wobei `x:ClassModifier` `internal` ist, wenn auf diese Klasse von einer WPF\-Ressource durch einen Pack\-URI\-Verweis verwiesen wird.  Als Folge dieses Falls und potenziell anderer ähnlicher Fälle verlassen Sie sich nicht ausschließlich auf `x:ClassModifier`, um alle möglichen Instanziierungsversuche zu blockieren.  
  
## Siehe auch  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [Code\-Behind und XAML in WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)   
 [x:FieldModifier Directive](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)   
 [Sicherheit \(WPF\)](../../../docs/framework/wpf/security-wpf.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)