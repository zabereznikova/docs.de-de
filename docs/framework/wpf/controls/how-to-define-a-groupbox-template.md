---
title: 'Gewusst wie: Definieren einer GroupBox-Vorlage'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a63a79b298a45b4efd6d1cbd439d208744358ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="4cde0-102">Gewusst wie: Definieren einer GroupBox-Vorlage</span><span class="sxs-lookup"><span data-stu-id="4cde0-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="4cde0-103">In diesem Beispiel wird gezeigt, wie beim Erstellen einer Vorlage für eine <xref:System.Windows.Controls.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4cde0-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cde0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4cde0-104">Example</span></span>  
 <span data-ttu-id="4cde0-105">Das folgende Beispiel definiert eine <xref:System.Windows.Controls.GroupBox> Steuerelementvorlage mithilfe einer <xref:System.Windows.Controls.Grid> Steuerelement für das Layout.</span><span class="sxs-lookup"><span data-stu-id="4cde0-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="4cde0-106">Die Vorlage verwendet eine <xref:System.Windows.Controls.BorderGapMaskConverter> definieren den Rahmen der <xref:System.Windows.Controls.GroupBox> , damit die Rahmen nicht verdeckt die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> Inhalt.</span><span class="sxs-lookup"><span data-stu-id="4cde0-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="4cde0-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cde0-107">See Also</span></span>  
 <xref:System.Windows.Controls.GroupBox>  
 [<span data-ttu-id="4cde0-108">GroupBox Gewusst-wie-Themen</span><span class="sxs-lookup"><span data-stu-id="4cde0-108">GroupBox How-to Topics</span></span>](http://msdn.microsoft.com/en-us/7692e155-a4c6-428c-b7e0-64b3740daca7)
