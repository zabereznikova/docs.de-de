---
title: "x:FieldModifier Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "FieldModifier attribute in XAML [XAML Services]"
  - "x:FieldModifier attribute [XAML Services]"
  - "XAML [XAML Services], x:FieldModifier attribute"
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
caps.latest.revision: 15
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 14
---
# x:FieldModifier Directive
Ändert das XAML\-Kompilierverhalten so, dass Felder für benannte Objektverweise mit <xref:System.Reflection.TypeAttributes?displayProperty=fullName>\-Zugriff statt mit dem <xref:System.Reflection.TypeAttributes?displayProperty=fullName>\-Standardverhalten definiert werden.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object x:FieldModifier="Public".../>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|*Public*|Welche Zeichenfolge genau zum Festlegen von <xref:System.Reflection.TypeAttributes?displayProperty=fullName> im Vergleich zu <xref:System.Reflection.TypeAttributes?displayProperty=fullName> übergeben wird, ist unterschiedlich und hängt von der verwendeten Code\-Behind\-Programmiersprache ab.  Siehe Hinweise.|  
  
## Abhängigkeiten  
 Wenn eine XAML\-Produktion irgendwo `x:FieldModifier` verwendet, muss das Stammelement dieser XAML\-Produktion einen [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) deklarieren.  
  
## Hinweise  
 `x:FieldModifier` ist nicht relevant zum Deklarieren der allgemeinen Zugriffsebene einer Klasse oder ihrer Member.  Es ist nur für das XAML\-Verarbeitungsverhalten relevant, wenn ein bestimmtes XAML\-Objekt, das Teil einer XAML\-Produktion ist, verarbeitet wird und ein Objekt wird, auf das potenziell im Objektdiagramm einer Anwendung zugegriffen werden kann.  Standardmäßig wird der Feldverweis für ein solches Objekt als privat beibehalten. So wird verhindert, dass Steuerelementconsumer das Objektdiagramm direkt ändern.  Stattdessen wird erwartet, dass Steuerelementconsumer das Objektdiagramm mit Standardmustern ändern, die durch Programmierungsmodelle aktiviert werden, z. B. Abrufen des Layoutstamms, der untergeordneten Elementauflistungen, der dedizierten öffentlichen Eigenschaften usw.  
  
 Der Wert des `x:FieldModifier`\-Attributs variiert je nach Programmiersprache, und sein Zweck kann in bestimmten Frameworks abweichen.  Die zu verwendende Zeichenfolge hängt davon ab, wie die jeweilige Sprache ihren <xref:System.CodeDom.Compiler.CodeDomProvider> implementiert, sowie von den Typkonvertern, die zum Definieren der Bedeutungen für <xref:System.Reflection.TypeAttributes?displayProperty=fullName> und <xref:System.Reflection.TypeAttributes?displayProperty=fullName> zurückgegeben werden, und ob bei der Sprache die Groß\- und Kleinschreibung beachtet werden muss.  
  
-   In [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)] lautet die zum Festlegen von <xref:System.Reflection.TypeAttributes?displayProperty=fullName> zu übergebende Zeichenfolge `public`.  
  
-   In [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)] lautet die zum Festlegen von <xref:System.Reflection.TypeAttributes?displayProperty=fullName> zu übergebende Zeichenfolge `Public`.  
  
-   Für [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)] sind gegenwärtig keine Ziele für XAML vorhanden. Daher ist die zu übergebenden Zeichenfolge nicht definiert.  
  
 Sie können auch <xref:System.Reflection.TypeAttributes?displayProperty=fullName> \(`internal` in [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Friend` in [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]\) festlegen, das Angeben von <xref:System.Reflection.TypeAttributes?displayProperty=fullName> ist unüblich, da `NotPublic`als Verhalten bereits die Standardeinstellung darstellt.  
  
 <xref:System.Reflection.TypeAttributes?displayProperty=fullName> ist das Standardverhalten, da nur selten Code außerhalb der Assembly, die das XAML kompilierte, auf ein XAML\-erstelltes Element zugreifen muss.  WPF\-Sicherheitsarchitektur zusammen mit XAML\-Kompilierungsverhalten deklariert keine Felder, die Elementinstanzen als öffentlich speichern, es sei denn, Sie legen den `x:FieldModifier` ausdrücklich zum Zulassen öffentlichen Zugriffs fest.  
  
 `x:FieldModifier` ist nur für Elemente mit einem [x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md) relevant, da der Name zum Verweis auf das Feld verwendet wird, nachdem es öffentlich ist.  
  
 Standardmäßig ist die partielle Klasse für das Stammelement öffentlich. Allerdings können Sie sie nicht öffentlich machen, indem Sie [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md) verwenden.  Das [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md) wirkt sich auch auf die Zugriffsebene der Instanz der Stammelementklasse aus.  Sie können sowohl `x:Name` als auch `x:FieldModifier` im Stammelement platzieren, wobei hierdurch jedoch nur eine Kopie des öffentlichen Felds des Stammelements erstellt wird und die Zugriffsebene der eigentlichen Stammelementklasse weiterhin vom [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md) gesteuert wird.  
  
## Siehe auch  
 [XAML\- und benutzerdefinierte Klassen für WPF](../../../ocs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [Code\-Behind und XAML in WPF](../../../ocs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)   
 [x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md)   
 [Erstellen einer WPF\-Anwendung \(WPF\)](../../../ocs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md)