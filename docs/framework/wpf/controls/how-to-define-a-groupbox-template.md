---
title: 'Gewusst wie: Definieren einer GroupBox-Vorlage'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: a47ce896be4d1c38147584dd80b1bc841737d526
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43537384"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="d239a-102">Gewusst wie: Definieren einer GroupBox-Vorlage</span><span class="sxs-lookup"><span data-stu-id="d239a-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="d239a-103">Dieses Beispiel zeigt, wie Sie eine Vorlage zum Erstellen einer <xref:System.Windows.Controls.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d239a-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d239a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d239a-104">Example</span></span>  
 <span data-ttu-id="d239a-105">Das folgende Beispiel definiert eine <xref:System.Windows.Controls.GroupBox> Steuerelementvorlage mit einem <xref:System.Windows.Controls.Grid> Steuerelement für das Layout.</span><span class="sxs-lookup"><span data-stu-id="d239a-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="d239a-106">Die Vorlage verwendet eine <xref:System.Windows.Controls.BorderGapMaskConverter> definieren den Rahmen der <xref:System.Windows.Controls.GroupBox> , damit die Rahmen nicht verdeckt die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> Inhalt.</span><span class="sxs-lookup"><span data-stu-id="d239a-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="d239a-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d239a-107">See Also</span></span>  
 <xref:System.Windows.Controls.GroupBox>  
 [<span data-ttu-id="d239a-108">GroupBox Gewusst-wie-Themen</span><span class="sxs-lookup"><span data-stu-id="d239a-108">GroupBox How-to Topics</span></span>](https://msdn.microsoft.com/library/7692e155-a4c6-428c-b7e0-64b3740daca7)
