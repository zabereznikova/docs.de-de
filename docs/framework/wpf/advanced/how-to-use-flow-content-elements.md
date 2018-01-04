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
ms.workload: dotnet
ms.openlocfilehash: e637e114187d0864afe4211a45c346c1e5a449b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="95c47-102">Gewusst wie: Verwenden von fortlaufenden Inhaltselementen</span><span class="sxs-lookup"><span data-stu-id="95c47-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="95c47-103">Das folgende Beispiel veranschaulicht die deklarative Verwendung für verschiedene fortlaufende Inhaltselemente und zugehörige Attribute.</span><span class="sxs-lookup"><span data-stu-id="95c47-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="95c47-104">Dargestellte Elemente und Attribute enthalten:</span><span class="sxs-lookup"><span data-stu-id="95c47-104">Elements and attributes demonstrated include:</span></span>  
  
-   <span data-ttu-id="95c47-105"><xref:System.Windows.Documents.Bold>-Element</span><span class="sxs-lookup"><span data-stu-id="95c47-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
-   <span data-ttu-id="95c47-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A>-Attribut</span><span class="sxs-lookup"><span data-stu-id="95c47-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
-   <span data-ttu-id="95c47-107"><xref:System.Windows.Documents.TextElement.FontSize%2A>-Attribut</span><span class="sxs-lookup"><span data-stu-id="95c47-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
-   <span data-ttu-id="95c47-108"><xref:System.Windows.Documents.Italic>-Element</span><span class="sxs-lookup"><span data-stu-id="95c47-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
-   <span data-ttu-id="95c47-109"><xref:System.Windows.Documents.LineBreak>-Element</span><span class="sxs-lookup"><span data-stu-id="95c47-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
-   <span data-ttu-id="95c47-110"><xref:System.Windows.Documents.List>-Element</span><span class="sxs-lookup"><span data-stu-id="95c47-110"><xref:System.Windows.Documents.List> element</span></span>  
  
-   <span data-ttu-id="95c47-111"><xref:System.Windows.Documents.ListItem>-Element</span><span class="sxs-lookup"><span data-stu-id="95c47-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
-   <span data-ttu-id="95c47-112"><xref:System.Windows.Documents.Paragraph>-Element</span><span class="sxs-lookup"><span data-stu-id="95c47-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
-   <span data-ttu-id="95c47-113"><xref:System.Windows.Documents.Run>-Element</span><span class="sxs-lookup"><span data-stu-id="95c47-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
-   <span data-ttu-id="95c47-114"><xref:System.Windows.Documents.Section>-Element</span><span class="sxs-lookup"><span data-stu-id="95c47-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
-   <span data-ttu-id="95c47-115"><xref:System.Windows.Documents.Span>-Element</span><span class="sxs-lookup"><span data-stu-id="95c47-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
-   <span data-ttu-id="95c47-116"><xref:System.Windows.Documents.Typography.Variants%2A>Attribut (hoch- und tiefgestellt)</span><span class="sxs-lookup"><span data-stu-id="95c47-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
-   <span data-ttu-id="95c47-117"><xref:System.Windows.Documents.Underline>-Element</span><span class="sxs-lookup"><span data-stu-id="95c47-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="95c47-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="95c47-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
