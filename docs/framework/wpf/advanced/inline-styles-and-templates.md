---
title: Inlinestile und -vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: 6225e1abd2b6bb8c3598b08bb2a717340c435e77
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373386"
---
# <a name="inline-styles-and-templates"></a>Inlinestile und -vorlagen
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet <xref:System.Windows.Style> Objekte und die Vorlagenobjekte (<xref:System.Windows.FrameworkTemplate> Unterklassen) als eine Möglichkeit, um die visuelle Darstellung eines Elements in den Ressourcen zu definieren, sodass sie verwendet werden können mehrmals. Aus diesem Grund Attribute [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , die die Typen nehmen <xref:System.Windows.Style> und <xref:System.Windows.FrameworkTemplate> fast immer Verweise auf vorhandene Stile und Vorlagen, anstatt neue zu definieren.  
  
## <a name="limitations-of-inline-styles-and-templates"></a>Einschränkungen von Inlinestile und-Vorlagen  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Stil- und Vorlageneigenschaften können technisch auf zwei Arten festgelegt werden. Sie können die Attributsyntax verwenden, auf einen Stil verweisen, die in eine Ressource, z. B. definiert wurde `<` *Objekt*`Style="{StaticResource`*MyResourceKey*`}" .../>`. Oder Sie können Eigenschaftenelement-Syntax verwenden, z. B. einen Inlinestil zu definieren:  
  
 `<` *Objekt* `>`  
  
 `<` *Objekt* `.Style>`  
  
 `<` `Style`  `.../>`  
  
 `</` *Objekt* `.Style>`  
  
 `</` *Objekt* `>`  
  
 Die Verwendung von Attributen ist sehr viel häufiger. Ein Format, das Inline definiert und nicht in Ressourcen definiert ist unbedingt auf das enthaltende Element ausgerichtet ist, und kann nicht erneut verwendet werden so einfach, da sie keine Ressourcenschlüssel besitzt. Im Allgemeinen ein definierten Stil vielseitiger und nützlicher und weitere in Übereinstimmung mit den allgemeinen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Prinzip der Trennung von Programmlogik in Code vom Entwurf im Markup-Programmierung.  
  
 In der Regel besteht kein Grund eine Inline Stil oder Vorlage festlegen, auch wenn Sie nur an diesem Speicherort Stil oder die Vorlage verwenden möchten. Die meisten Elemente, die einen Stil oder Vorlage können unterstützen auch eine Content-Eigenschaft und einem Inhaltsmodell. Wenn Sie nur den logischen Struktur verwenden, werden Sie über Stile oder Vorlagen einmal erstellen, wäre es sogar noch einfacher zu Inhaltseigenschaft nur mit der entsprechenden untergeordneten Elemente in direkten Markup zu füllen. Dies würde die Stil- und Vorlagenressourcen Mechanismen vollständig umgehen.  
  
 Andere Syntax aktiviert, indem Markuperweiterungen, die ein Objekt zurückzugeben sind auch möglich, dass die Stile und Vorlagen. Zwei für diese Szenarien, in denen Erweiterungen umfassen [TemplateBinding](templatebinding-markup-extension.md) und <xref:System.Windows.Data.Binding>.  
  
## <a name="see-also"></a>Siehe auch
- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
