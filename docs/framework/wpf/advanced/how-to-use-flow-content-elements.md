---
title: 'Gewusst wie: Verwenden von fortlaufenden Inhaltselementen'
ms.date: 03/30/2017
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
ms.openlocfilehash: 146a785ef4f6da650144ed6fc47633670304bde6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544130"
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="07189-102">Gewusst wie: Verwenden von fortlaufenden Inhaltselementen</span><span class="sxs-lookup"><span data-stu-id="07189-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="07189-103">Das folgende Beispiel veranschaulicht die deklarative Verwendung für verschiedene fortlaufende Inhaltselemente und zugehörige Attribute.</span><span class="sxs-lookup"><span data-stu-id="07189-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="07189-104">Dargestellte Elemente und Attribute enthalten:</span><span class="sxs-lookup"><span data-stu-id="07189-104">Elements and attributes demonstrated include:</span></span>  
  
-   <span data-ttu-id="07189-105"><xref:System.Windows.Documents.Bold>-Element</span><span class="sxs-lookup"><span data-stu-id="07189-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
-   <span data-ttu-id="07189-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A>-Attribut</span><span class="sxs-lookup"><span data-stu-id="07189-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
-   <span data-ttu-id="07189-107"><xref:System.Windows.Documents.TextElement.FontSize%2A>-Attribut</span><span class="sxs-lookup"><span data-stu-id="07189-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
-   <span data-ttu-id="07189-108"><xref:System.Windows.Documents.Italic>-Element</span><span class="sxs-lookup"><span data-stu-id="07189-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
-   <span data-ttu-id="07189-109"><xref:System.Windows.Documents.LineBreak>-Element</span><span class="sxs-lookup"><span data-stu-id="07189-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
-   <span data-ttu-id="07189-110"><xref:System.Windows.Documents.List>-Element</span><span class="sxs-lookup"><span data-stu-id="07189-110"><xref:System.Windows.Documents.List> element</span></span>  
  
-   <span data-ttu-id="07189-111"><xref:System.Windows.Documents.ListItem>-Element</span><span class="sxs-lookup"><span data-stu-id="07189-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
-   <span data-ttu-id="07189-112"><xref:System.Windows.Documents.Paragraph>-Element</span><span class="sxs-lookup"><span data-stu-id="07189-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
-   <span data-ttu-id="07189-113"><xref:System.Windows.Documents.Run>-Element</span><span class="sxs-lookup"><span data-stu-id="07189-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
-   <span data-ttu-id="07189-114"><xref:System.Windows.Documents.Section>-Element</span><span class="sxs-lookup"><span data-stu-id="07189-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
-   <span data-ttu-id="07189-115"><xref:System.Windows.Documents.Span>-Element</span><span class="sxs-lookup"><span data-stu-id="07189-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
-   <span data-ttu-id="07189-116"><xref:System.Windows.Documents.Typography.Variants%2A> Attribut (hoch- und tiefgestellt)</span><span class="sxs-lookup"><span data-stu-id="07189-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
-   <span data-ttu-id="07189-117"><xref:System.Windows.Documents.Underline>-Element</span><span class="sxs-lookup"><span data-stu-id="07189-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="07189-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07189-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
