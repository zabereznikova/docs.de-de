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
ms.openlocfilehash: e46d8561b62d9137d4fed4df447338a97fc0577b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938910"
---
# <a name="xnull-markup-extension"></a>x:Null-Markuperweiterung
Gibt an, `null` als Wert für ein XAML-Element.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Schlüsselwort für ein null-Verweis in C# und [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] ist null. Das Microsoft Visual Basic-Schlüsselwort für ein null-Verweis ist `Nothing`, aber Sie verwenden immer `{x:Null}` wie die XAML-Nutzung unabhängig davon, welcher Code-Behind-Sprache, die Sie mit der XAML verknüpfen.  
  
 Die `x:Null` Markuperweiterung hat keine festlegbaren Eigenschaften.  
  
 Eine null-Verwendung ist häufig die XAML-Member-Offenlegung von CLR zugeordnet <xref:System.Nullable%601> Wert.  
  
 Die `x:Null` Markuperweiterung, z. B. alle Markuperweiterungen für XAML, verwendet die geschweiften Klammern (`{,}`) für die Behandlung von Attributwerten als Literale oder Ereignishandler-Verweise werden Escapezeichen. Die Attributsyntax ist die Syntax, die mit dieser Markuperweiterung am häufigsten verwendet. Ein Objektelement-Syntax `<x:Null />` ist technisch möglich, jedoch wird nur selten verwendet werden, da die `x:Null` Markuperweiterung verfügt über keine Positionsparameter oder Konstruktionsargumente.  
  
 Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 In .NET Framework-XAML-Dienste, wird die Handhabung dieser Markuperweiterung durch definiert die <xref:System.Windows.Markup.NullExtension> Klasse.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Beachten Sie, dass `null` ist nicht unbedingt der Anfangswert für eine Abhängigkeitseigenschaft vom Verweistyp nicht festgelegte. Der anfängliche Standardwert kann für jede Abhängigkeitseigenschaft unterschiedlich sein und kann basierend auf Metadaten. Viele Abhängigkeitseigenschaften akzeptieren keine `null` als Wert entweder über Markup oder Code aufgrund ihrer rückrufimplementierungen Überprüfung. Weitere Informationen zu Abhängigkeitseigenschaften finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Übersicht über XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
- [Markuperweiterungen und WPF-XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
