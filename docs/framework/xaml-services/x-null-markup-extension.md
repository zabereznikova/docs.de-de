---
title: x:Null-Markuperweiterung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: ''
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5b10d759a4f79eabe973a0fcd60736428e46f659
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="xnull-markup-extension"></a>x:Null-Markuperweiterung
Gibt an, `null` als Wert für ein XAML-Element.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Schlüsselwort für ein null-Verweis in [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] und [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] ist null. Die [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] Schlüsselwort für ein null-Verweis ist `Nothing`, aber Sie verwenden immer `{x:Null}` in XAML, unabhängig davon, welche Code-Behind-Sprache, die Sie mit der XAML-Code zuordnen.  
  
 Die `x:Null` Markuperweiterung verfügt über keine konfigurierbaren Eigenschaften.  
  
 Eine null-Verwendung ist häufig bei der Verwendung von XAML-Member Offenlegung von einem CLR <xref:System.Nullable%601> Wert.  
  
 Die `x:Null` Markuperweiterung, z. B. alle Markuperweiterungen für XAML, verwendet die geschweiften Klammern (`{,}`) für die Behandlung von Attributwerten als Literale oder Ereignishandler Verweise Escapezeichen. Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Eine Element-Objektsyntax `<x:Null />` ist technisch zwar möglich, jedoch wird nur selten verwendet werden, da die `x:Null` Markuperweiterung verfügt über keine Positionsparameter oder Konstruktionsargumente.  
  
 Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 In .NET Framework XAML Services wird die Handhabung dieser Markuperweiterung von definiert die <xref:System.Windows.Markup.NullExtension> Klasse.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Beachten Sie, dass `null` ist nicht unbedingt der Festlegung Anfangswert für einen Verweistyp-Abhängigkeitseigenschaft. Der anfängliche Standardwert kann für jede Abhängigkeitseigenschaft unterschiedlich und kann auf eigenschaftenspezifischen Metadaten basieren. Viele Abhängigkeitseigenschaften akzeptieren keine `null` als Wert entweder über Markup oder-Code aufgrund ihrer rückrufimplementierungen Überprüfung. Weitere Informationen über Abhängigkeitseigenschaften finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.DependencyProperty.UnsetValue>  
 [Übersicht über XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Markuperweiterungen und WPF-XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
