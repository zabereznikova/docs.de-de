---
title: "x:Reference Markup Extension | Microsoft Docs"
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
  - "x:Reference markup extension [XAML Services]"
  - "XAML [XAML Services], x:Reference Markup Extension"
  - "Reference markup extension [XAML Services]"
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# x:Reference Markup Extension
Verweist auf eine Instanz, die an einer anderen Stelle in XAML\-Markup deklariert wird.  Der Verweis verweist auf das `x:Name`\-Objekt eines Elements.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object property="{x:Reference instancexName}" .../>  
```  
  
## Verwendung von XAML\-Objektelementen  
  
```  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`instancexName`|Der `x:Name`\-Wert \(bzw. der durch <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> identifizierte Eigenschaftswert\) der Instanz, auf die verwiesen wird.|  
  
## Hinweise  
 `x:Reference` bietet XAML\-Unterstützung auf Sprachebene für ein Elementverweiskonzept, das andernfalls in bestimmten Frameworks, wie z. B. WPF, implementiert wurde.  
  
## x:Reference und WPF  
 In WPF und XAML 2006 werden Elementverweise von der Funktion auf Frameworkebene der <xref:System.Windows.Data.Binding.ElementName%2A>\-Bindung behandelt.  Für die meisten WPF\-Anwendungen und \-Szenarien sollte <xref:System.Windows.Data.Binding.ElementName%2A>\-Bindung immer noch verwendet werden.  Ausnahmen von dieser allgemeinen Anleitung könnten Fälle einschließen, bei denen es Datenkontext oder andere Überlegungen zum Gültigkeitsbereich gibt, die die Datenbindung unpraktisch machen, und bei denen Markupkompilierung nicht beteiligt ist.  
  
 `x:Reference` ist ein in XAML 2009 definiertes Konstrukt.  In WPF können Sie XAML 2009\-Funktionen verwenden, jedoch nur für XAML, die nicht WPF\-markupkompiliert ist.  Markupkompilierte XAML und die BAML\-Form von XAML unterstützen derzeit nicht die XAML 2009\-Sprachschlüsselwörter und \-funktionen.