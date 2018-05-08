---
title: Inlinestile und -vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: 9c06f61bce1e17770fa0a9b9ed7a0e20625a79ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="inline-styles-and-templates"></a>Inlinestile und -vorlagen
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet <xref:System.Windows.Style> Objekte und die Vorlagenobjekte (<xref:System.Windows.FrameworkTemplate> Unterklassen) als eine Möglichkeit, um die visuelle Darstellung eines Elements in den Ressourcen zu definieren, sodass sie verwendet werden können mehrere Male auf. Aus diesem Grund Attribute im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , die anhand von den Typen <xref:System.Windows.Style> und <xref:System.Windows.FrameworkTemplate> fast immer Ressourcenverweise auf vorhandene Stile und Vorlagen, anstatt neue zu definieren.  
  
## <a name="limitations-of-inline-styles-and-templates"></a>Einschränkungen von Inlinestile und Vorlagen  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Stil- und Eigenschaften können auf zwei Arten technisch festgelegt werden. Können Sie auf um einen Stil zu verweisen, die in einer Ressource, z. B. definiert wurde Attributsyntax `<` *Objekt*`Style="{StaticResource`*MyResourceKey*`}" .../>`. Oder Sie können Eigenschaftenelementsyntax verwenden, um einen Inlinestil für die Instanz zu definieren:  
  
 `<` *Objekt* `>`  
  
 `<` *Objekt* `.Style>`  
  
 `<` `Style`  `.../>`  
  
 `</` *Objekt* `.Style>`  
  
 `</` *Objekt* `>`  
  
 Für die Attributverwendung ist sehr viel häufiger. Ein Format, das Inline definiert und nicht in Ressourcen definiert ist unbedingt auf das enthaltende Element nur begrenzt, und kann nicht erneut verwendet werden genauso einfach, da sie keine Ressourcenschlüssel besitzt. Im Allgemeinen ein Stil Ressource definiert vielseitiger und hilfreich ist, und wird in Übereinstimmung mit den allgemeinen weitere [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Programmierung Prinzip Programmlogik im Code vom Entwurf in Markup zu trennen.  
  
 In der Regel besteht kein Grund eine Inline Stil oder eine Vorlage festlegen, auch wenn Sie nur an diesem Speicherort Stil oder die Vorlage verwenden möchten. Die meisten Elemente, die einen Stil oder eine Vorlage übernehmen können unterstützen auch ein Content-Eigenschaft und einem Inhaltsmodell. Wenn Sie nur die logische Struktur verwenden Sie erstellen durch formatieren oder Datenvorlagen einmal, wäre es noch einfacher, Content-Eigenschaft nur mit den entsprechenden untergeordneten Elementen im direkten Markup zu füllen. Dies würde die Mechanismen Stil- und vollständig umgehen.  
  
 Andere Syntax aktiviert, die für Markuperweiterungen, die ein Objekt zurückgeben, sind auch für Stile und Vorlagen möglich. Zwei diese Erweiterungen, die über mögliche Szenarien umfassen [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) und <xref:System.Windows.Data.Binding>.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)
