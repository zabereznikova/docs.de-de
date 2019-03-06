---
title: 'Vorgehensweise: Definieren einer GroupBox-Vorlage'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: 6b4ad4a588aab93f5445cda962af890bfcd41c14
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377663"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="f3fb1-102">Vorgehensweise: Definieren einer GroupBox-Vorlage</span><span class="sxs-lookup"><span data-stu-id="f3fb1-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="f3fb1-103">Dieses Beispiel zeigt, wie Sie eine Vorlage zum Erstellen einer <xref:System.Windows.Controls.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f3fb1-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3fb1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f3fb1-104">Example</span></span>  
 <span data-ttu-id="f3fb1-105">Das folgende Beispiel definiert eine <xref:System.Windows.Controls.GroupBox> Steuerelementvorlage mit einem <xref:System.Windows.Controls.Grid> Steuerelement für das Layout.</span><span class="sxs-lookup"><span data-stu-id="f3fb1-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="f3fb1-106">Die Vorlage verwendet eine <xref:System.Windows.Controls.BorderGapMaskConverter> definieren den Rahmen der <xref:System.Windows.Controls.GroupBox> , damit die Rahmen nicht verdeckt die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> Inhalt.</span><span class="sxs-lookup"><span data-stu-id="f3fb1-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="f3fb1-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3fb1-107">See also</span></span>
- <xref:System.Windows.Controls.GroupBox>
- <span data-ttu-id="f3fb1-108">[Vorgehensweise: Erstellen Sie ein GroupBox-Steuerelement](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f3fb1-108">[How to: Create a GroupBox](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span></span>
