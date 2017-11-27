---
title: x:Reference-Markuperweiterung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 06e59e7686004f8fd44473bd9572ed07a0118d1f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xreference-markup-extension"></a>x:Reference-Markuperweiterung
Verweist auf eine Instanz, die an anderer Stelle im XAML-Markup deklariert wird. Der Verweis auf ein Element verweist `x:Name`.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`instancexName`|Die `x:Name` Wert (oder des Werts der <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-Eigenschaft identifiziert) der Instanz auf die verwiesen wird.|  
  
## <a name="remarks"></a>Hinweise  
 `x:Reference`bietet Unterstützung für XAML-Sprachebene für ein Konzept der Element-Referenz, die andernfalls in bestimmten Frameworks wie z. B. WPF implementiert wurde.  
  
## <a name="xreference-and-wpf"></a>X: Reference-als auch für WPF  
 In WPF und XAML 2006 können Elementverweise adressiert werden, indem die Frameworkebene-Funktion von <xref:System.Windows.Data.Binding.ElementName%2A> Bindung. Für die meisten WPF-Anwendungen und Szenarien <xref:System.Windows.Data.Binding.ElementName%2A> Bindung sollte weiterhin verwendet werden. Ausnahmen von dieser allgemeinen Leitfaden möglicherweise Fällen gehört der, in denen Datenkontext oder andere Bereichsdefinition Aspekte, die die Datenbindung alleine nicht durchführbar vornehmen vorhanden sind und nicht Markupkompilierung beteiligt ist.  
  
 `x:Reference`in XAML 2009 ist ein Konstrukt definiert werden. In WPF können Sie XAML 2009-Funktionen verwenden, jedoch nur für XAML, das nicht WPF-markupkompiliert ist. Markupkompilierte XAML und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.
