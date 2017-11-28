---
title: "Gewusst wie: Programmgesteuertes Ändern der FlowDirection des Inhalts"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca4c94fe073fd618ca79d08812c42550594f445d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a><span data-ttu-id="08e2a-102">Gewusst wie: Programmgesteuertes Ändern der FlowDirection des Inhalts</span><span class="sxs-lookup"><span data-stu-id="08e2a-102">How to: Change the FlowDirection of Content Programmatically</span></span>
<span data-ttu-id="08e2a-103">Dieses Beispiel zeigt, wie Sie programmgesteuert ändern die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft von einem <xref:System.Windows.Controls.FlowDocumentReader>.</span><span class="sxs-lookup"><span data-stu-id="08e2a-103">This example shows how to programmatically change the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property of a <xref:System.Windows.Controls.FlowDocumentReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08e2a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08e2a-104">Example</span></span>  
 <span data-ttu-id="08e2a-105">Zwei <xref:System.Windows.Controls.Button> Elemente erstellt werden, jeweils eine der möglichen Werte für darstellen <xref:System.Windows.FlowDirection>.</span><span class="sxs-lookup"><span data-stu-id="08e2a-105">Two <xref:System.Windows.Controls.Button> elements are created, each representing one of the possible values of <xref:System.Windows.FlowDirection>.</span></span> <span data-ttu-id="08e2a-106">Wenn eine Schaltfläche geklickt wird, wird der Wert der zugehörigen Eigenschaft mit dem Inhalt des angewendet eine <xref:System.Windows.Controls.FlowDocumentReader> mit dem Namen `tf1`.</span><span class="sxs-lookup"><span data-stu-id="08e2a-106">When a button is clicked, the associated property value is applied to the contents of a <xref:System.Windows.Controls.FlowDocumentReader> named `tf1`.</span></span>  <span data-ttu-id="08e2a-107">Der Eigenschaftswert wird auch in geschrieben eine <xref:System.Windows.Controls.TextBlock> mit dem Namen `txt1`.</span><span class="sxs-lookup"><span data-stu-id="08e2a-107">The property value is also written to a <xref:System.Windows.Controls.TextBlock> named `txt1`.</span></span>  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a><span data-ttu-id="08e2a-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08e2a-108">Example</span></span>  
 <span data-ttu-id="08e2a-109">Ereignisse im Zusammenhang mit den oben definierten Klicks auf Schaltflächen in der behandelt eine [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] Code-Behind-Datei.</span><span class="sxs-lookup"><span data-stu-id="08e2a-109">The events associated with the button clicks defined above are handled in a [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] code-behind file.</span></span>  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
