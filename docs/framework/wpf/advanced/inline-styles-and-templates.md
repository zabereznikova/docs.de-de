---
title: Inlinestile und -vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b88ef444283f4e1e85009c59b39f3cc41965d300
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460009"
---
# <a name="inline-styles-and-templates"></a>Inlinestile und -vorlagen
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt <xref:System.Windows.Style> Objekte und Vorlagen Objekte (<xref:System.Windows.FrameworkTemplate> Unterklassen) als Möglichkeit zum Definieren des visuellen Erscheinungs Bilds eines Elements in Ressourcen bereit, sodass Sie mehrmals verwendet werden können. Aus diesem Grund machen Attribute in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], die die Typen <xref:System.Windows.Style> und <xref:System.Windows.FrameworkTemplate>, fast immer Ressourcen Verweise auf vorhandene Stile und Vorlagen, anstatt Sie neu zu definieren.  
  
## <a name="limitations-of-inline-styles-and-templates"></a>Einschränkungen für Inline Stile und-Vorlagen  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]können Stil-und Vorlagen Eigenschaften auf eine von zwei Arten festgelegt werden. Sie können die Attribut Syntax verwenden, um auf einen Stil zu verweisen, der in einer Ressource definiert wurde, z. b. `<`*Objekt*`Style="{StaticResource`*myresourcekey*`}" .../>`. Oder Sie können die Eigenschafts Element Syntax verwenden, um einen Stil inline zu definieren, z.b.:  
  
 `<` *Objekt* `>`  
  
 `<` *Objekt* `.Style>`  
  
 `<` `Style``.../>`  
  
 `</` *Objekt* `.Style>`  
  
 `</` *Objekt* `>`  
  
 Die Attribut Verwendung ist viel häufiger. Ein Stil, der Inline definiert und nicht in Ressourcen definiert ist, ist notwendigerweise auf das enthaltende Element beschränkt und kann nicht so einfach wieder verwendet werden, da er keinen Ressourcen Schlüssel aufweist. Im Allgemeinen ist ein Ressourcen definiertes Format vielseitiger und nützlicher, und es ist besser, das allgemeine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Programmiermodell-Prinzip der Trennung von Programmlogik in Code vom Design in Markup zu unterhalten.  
  
 In der Regel gibt es keinen Grund, einen Stil oder eine Vorlage Inline festzulegen, auch wenn Sie nur den Stil oder die Vorlage an dieser Stelle verwenden möchten. Die meisten Elemente, die einen Stil oder eine Vorlage annehmen können, unterstützen auch eine Inhalts Eigenschaft und ein Inhalts Modell. Wenn Sie nur eine beliebige logische Struktur verwenden, die Sie mithilfe von Formaten oder Vorlagen erstellen, ist es sogar noch einfacher, diese Inhalts Eigenschaft mit den entsprechenden untergeordneten Elementen in direktem Markup zu füllen. Dies würde den Stil und die Vorlagen Mechanismen vollständig umgehen.  
  
 Andere durch Markup Erweiterungen aktivierte Syntaxen, die ein-Objekt zurückgeben, sind auch für Stile und Vorlagen möglich. Zwei solcher Erweiterungen, die mögliche Szenarien aufweisen, sind [TemplateBinding](templatebinding-markup-extension.md) und <xref:System.Windows.Data.Binding>.  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
