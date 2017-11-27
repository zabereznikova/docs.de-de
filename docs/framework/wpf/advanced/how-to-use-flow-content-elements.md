---
title: 'Gewusst wie: Verwenden von fortlaufenden Inhaltselementen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c1350a380e97631ac290e57de64fec696535fecc
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="897e8-102">Gewusst wie: Verwenden von fortlaufenden Inhaltselementen</span><span class="sxs-lookup"><span data-stu-id="897e8-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="897e8-103">Das folgende Beispiel veranschaulicht die deklarative Verwendung für verschiedene fortlaufende Inhaltselemente und zugehörige Attribute.</span><span class="sxs-lookup"><span data-stu-id="897e8-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="897e8-104">Dargestellte Elemente und Attribute enthalten:</span><span class="sxs-lookup"><span data-stu-id="897e8-104">Elements and attributes demonstrated include:</span></span>  
  
-   <span data-ttu-id="897e8-105"><xref:System.Windows.Documents.Bold>-Element</span><span class="sxs-lookup"><span data-stu-id="897e8-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
-   <span data-ttu-id="897e8-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A>-Attribut</span><span class="sxs-lookup"><span data-stu-id="897e8-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
-   <span data-ttu-id="897e8-107"><xref:System.Windows.Documents.TextElement.FontSize%2A>-Attribut</span><span class="sxs-lookup"><span data-stu-id="897e8-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
-   <span data-ttu-id="897e8-108"><xref:System.Windows.Documents.Italic>-Element</span><span class="sxs-lookup"><span data-stu-id="897e8-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
-   <span data-ttu-id="897e8-109"><xref:System.Windows.Documents.LineBreak>-Element</span><span class="sxs-lookup"><span data-stu-id="897e8-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
-   <span data-ttu-id="897e8-110"><xref:System.Windows.Documents.List>-Element</span><span class="sxs-lookup"><span data-stu-id="897e8-110"><xref:System.Windows.Documents.List> element</span></span>  
  
-   <span data-ttu-id="897e8-111"><xref:System.Windows.Documents.ListItem>-Element</span><span class="sxs-lookup"><span data-stu-id="897e8-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
-   <span data-ttu-id="897e8-112"><xref:System.Windows.Documents.Paragraph>-Element</span><span class="sxs-lookup"><span data-stu-id="897e8-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
-   <span data-ttu-id="897e8-113"><xref:System.Windows.Documents.Run>-Element</span><span class="sxs-lookup"><span data-stu-id="897e8-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
-   <span data-ttu-id="897e8-114"><xref:System.Windows.Documents.Section>-Element</span><span class="sxs-lookup"><span data-stu-id="897e8-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
-   <span data-ttu-id="897e8-115"><xref:System.Windows.Documents.Span>-Element</span><span class="sxs-lookup"><span data-stu-id="897e8-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
-   <span data-ttu-id="897e8-116"><xref:System.Windows.Documents.Typography.Variants%2A>Attribut (hoch- und tiefgestellt)</span><span class="sxs-lookup"><span data-stu-id="897e8-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
-   <span data-ttu-id="897e8-117"><xref:System.Windows.Documents.Underline>-Element</span><span class="sxs-lookup"><span data-stu-id="897e8-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="897e8-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="897e8-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
