---
title: x:Reference-Markuperweiterung
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: 960f5c0e4192df72090c1a571dfc2fc5e3fd8ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938878"
---
# <a name="xreference-markup-extension"></a>x:Reference-Markuperweiterung
Verweist auf eine Instanz, die an anderer Stelle im XAML-Markup deklariert ist. Der Verweis bezieht sich auf ein Element des `x:Name`.  
  
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
|`instancexName`|Die `x:Name` Wert (oder den Wert der <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-Eigenschaft identifiziert) der Instanz auf die verwiesen wird.|  
  
## <a name="remarks"></a>Hinweise  
 `x:Reference` unterstützt XAML-Sprachebene ein Konzept der Element-Referenz, die andernfalls in bestimmten Frameworks wie WPF implementiert wurde.  
  
## <a name="xreference-and-wpf"></a>X: Reference und WPF  
 In WPF- und XAML 2006, werden die Elementverweise durch das Feature auf Frameworkebene des <xref:System.Windows.Data.Binding.ElementName%2A> Bindung. Für die meisten WPF-Anwendungen und Szenarien <xref:System.Windows.Data.Binding.ElementName%2A> Bindung sollte weiterhin verwendet werden. Ausnahmen von dieser allgemeinen Leitfaden können Fälle enthalten, wobei Datenkontext oder andere bereichsüberlegungen, die die Datenbindung nicht unmöglich ist vorhanden sind und Markupkompilierung nicht beteiligt ist.  
  
 `x:Reference` in XAML 2009 ist ein Konstrukt definiert werden. In WPF können Sie XAML 2009-Funktionen verwenden, jedoch nur für XAML, das nicht WPF-markupkompiliert ist. Markupkompilierte XAML und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.
