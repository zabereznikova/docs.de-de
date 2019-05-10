---
title: 'Vorgehensweise: Verwenden von fortlaufenden Inhaltselementen'
ms.date: 03/30/2017
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
ms.openlocfilehash: f61116c0bf52ac726238d9e21c2422cedbb4716f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663331"
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="4801f-102">Vorgehensweise: Verwenden von fortlaufenden Inhaltselementen</span><span class="sxs-lookup"><span data-stu-id="4801f-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="4801f-103">Das folgende Beispiel veranschaulicht die deklarative Verwendung für verschiedene fortlaufende Inhaltselemente und zugehörige Attribute.</span><span class="sxs-lookup"><span data-stu-id="4801f-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="4801f-104">Dargestellte Elemente und Attribute enthalten:</span><span class="sxs-lookup"><span data-stu-id="4801f-104">Elements and attributes demonstrated include:</span></span>  
  
- <span data-ttu-id="4801f-105"><xref:System.Windows.Documents.Bold>-Element</span><span class="sxs-lookup"><span data-stu-id="4801f-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
- <span data-ttu-id="4801f-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> Attribut</span><span class="sxs-lookup"><span data-stu-id="4801f-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
- <span data-ttu-id="4801f-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> Attribut</span><span class="sxs-lookup"><span data-stu-id="4801f-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
- <span data-ttu-id="4801f-108"><xref:System.Windows.Documents.Italic>-Element</span><span class="sxs-lookup"><span data-stu-id="4801f-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
- <span data-ttu-id="4801f-109"><xref:System.Windows.Documents.LineBreak>-Element</span><span class="sxs-lookup"><span data-stu-id="4801f-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
- <span data-ttu-id="4801f-110"><xref:System.Windows.Documents.List>-Element</span><span class="sxs-lookup"><span data-stu-id="4801f-110"><xref:System.Windows.Documents.List> element</span></span>  
  
- <span data-ttu-id="4801f-111"><xref:System.Windows.Documents.ListItem>-Element</span><span class="sxs-lookup"><span data-stu-id="4801f-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
- <span data-ttu-id="4801f-112"><xref:System.Windows.Documents.Paragraph>-Element</span><span class="sxs-lookup"><span data-stu-id="4801f-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
- <span data-ttu-id="4801f-113"><xref:System.Windows.Documents.Run>-Element</span><span class="sxs-lookup"><span data-stu-id="4801f-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
- <span data-ttu-id="4801f-114"><xref:System.Windows.Documents.Section>-Element</span><span class="sxs-lookup"><span data-stu-id="4801f-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
- <span data-ttu-id="4801f-115"><xref:System.Windows.Documents.Span>-Element</span><span class="sxs-lookup"><span data-stu-id="4801f-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
- <span data-ttu-id="4801f-116"><xref:System.Windows.Documents.Typography.Variants%2A> -Attribut (hochgestellt und tiefgestellt)</span><span class="sxs-lookup"><span data-stu-id="4801f-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
- <span data-ttu-id="4801f-117"><xref:System.Windows.Documents.Underline>-Element</span><span class="sxs-lookup"><span data-stu-id="4801f-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="4801f-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4801f-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
