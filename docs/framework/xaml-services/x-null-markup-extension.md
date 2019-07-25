---
title: x:Null-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: 7dbea2c7d4010d8defc572dbdc14a0dfd6d7601e
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484707"
---
# <a name="xnull-markup-extension"></a>x:Null-Markuperweiterung
Gibt `null` als Wert für ein XAML-Element an.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Schlüsselwort für einen NULL- C# Verweis C++ in und ist NULL. Das Microsoft Visual Basic-Schlüsselwort für einen NULL `Nothing`-Verweis ist, Sie `{x:Null}` verwenden jedoch immer als XAML-Verwendung, unabhängig davon, welche Code Behind-Sprache Sie der XAML zuordnen.  
  
 Die `x:Null` Markup Erweiterung hat keine festleg baren Eigenschaften.  
  
 Eine null-Verwendung ist häufig dem XAML-Element zugeordnet, das einen CLR <xref:System.Nullable%601> -Wert verfügbar macht.  
  
 Die `x:Null` Markup Erweiterung verwendet, wie alle XAML-Markup Erweiterungen, die geschweiften Klammern (`{,}`), um die Behandlung von Attributwerten als Literale oder ereignishandlerverweise zu vermeiden. Die Attribut Syntax ist die Syntax, die in dieser Markup Erweiterung am häufigsten verwendet wird. Eine Objekt Element Syntax `<x:Null />` ist technisch möglich, wird jedoch nur selten verwendet, `x:Null` da die Markup Erweiterung keine Positions Parameter oder Konstruktions Argumente aufweist.  
  
 Weitere Informationen zu Markup Erweiterungen finden Sie unter [Markup Erweiterungen und WPF-XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 In .NET Framework XAML-Diensten wird die Behandlung dieser Markup Erweiterung durch die <xref:System.Windows.Markup.NullExtension> -Klasse definiert.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Beachten Sie `null` , dass nicht notwendigerweise der anfängliche nicht festgelegte Wert für eine Verweistyp-Abhängigkeits Eigenschaft ist. Der anfängliche Standardwert kann für jede Abhängigkeits Eigenschaft variieren und kann auf Eigenschafts spezifischen Metadaten basieren. Viele Abhängigkeits Eigenschaften akzeptieren `null` aufgrund ihrer Validierungs Rückruf Implementierungen nicht als Wert, entweder durch Markup oder Code. Weitere Informationen zu Abhängigkeits Eigenschaften finden Sie unter [Übersicht über Abhängigkeits Eigenschaften](../wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Übersicht über XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
- [Markuperweiterungen und WPF-XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
