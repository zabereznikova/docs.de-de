---
title: 'Vorgehensweise: Erstellen einer Schaltfläche mit einem Bild'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: cfebe53047531ecddde42a3a0596dfd949629ecd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682061"
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="e4aea-102">Vorgehensweise: Erstellen einer Schaltfläche mit einem Bild</span><span class="sxs-lookup"><span data-stu-id="e4aea-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="e4aea-103">Dieses Beispiel zeigt, wie Sie ein Bild enthalten, auf eine <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="e4aea-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4aea-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4aea-104">Example</span></span>  
 <span data-ttu-id="e4aea-105">Das folgende Beispiel erstellt zwei <xref:System.Windows.Controls.Button> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="e4aea-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="e4aea-106">Eine <xref:System.Windows.Controls.Button> enthält Text und das andere ein Bild.</span><span class="sxs-lookup"><span data-stu-id="e4aea-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="e4aea-107">Das Image ist in einem Ordner namens Daten, d. h. einen Unterordner des Projektordners des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="e4aea-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="e4aea-108">Wenn ein Benutzer klickt auf die <xref:System.Windows.Controls.Button> über das Image, Hintergrund und den Text der anderen verfügt <xref:System.Windows.Controls.Button> ändern.</span><span class="sxs-lookup"><span data-stu-id="e4aea-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="e4aea-109">In diesem Beispiel wird <xref:System.Windows.Controls.Button> steuert mithilfe von Markup wird jedoch Code schreiben verwendet die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="e4aea-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e4aea-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4aea-110">See also</span></span>
- [<span data-ttu-id="e4aea-111">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="e4aea-111">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)
- [<span data-ttu-id="e4aea-112">Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="e4aea-112">Control Library</span></span>](../../../../docs/framework/wpf/controls/control-library.md)
