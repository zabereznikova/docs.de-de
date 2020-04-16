---
title: x:Reference-Markuperweiterung
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432653"
---
# <a name="xreference-markup-extension"></a>x:Reference-Markuperweiterung

Verweist auf eine Instanz, die an anderer Stelle im XAML-Markup deklariert wird. Der Verweis bezieht sich `x:Name`auf die .

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
|`instancexName`|Der `x:Name` Wert (oder <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>Wert der -identifizierten Eigenschaft) der referenzierten Instanz.|

## <a name="remarks"></a>Bemerkungen

`x:Reference`bietet XAML-Sprachunterstützung für ein Elementreferenzkonzept, das andernfalls in bestimmten Frameworks wie WPF implementiert wurde.

## <a name="xreference-and-wpf"></a>x:Referenz und WPF

In WPF und XAML 2006 werden Elementverweise durch <xref:System.Windows.Data.Binding.ElementName%2A> das Framework-Level-Feature der Bindung adressiert. Für die meisten WPF-Anwendungen und -Szenarien sollte weiterhin <xref:System.Windows.Data.Binding.ElementName%2A> die Bindung verwendet werden. Ausnahmen von dieser allgemeinen Anleitung können Fälle umfassen, in denen Datenkontexte oder andere Scoping-Überlegungen vorliegen, die die Datenbindung unpraktisch machen und bei denen die Markupkompilierung nicht erforderlich ist.

`x:Reference`ist ein in XAML 2009 definiertes Konstrukt. In WPF können Sie XAML 2009-Funktionen verwenden, jedoch nur für XAML, das nicht WPF-markupkompiliert ist. Markupkompilierte XAML und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.
