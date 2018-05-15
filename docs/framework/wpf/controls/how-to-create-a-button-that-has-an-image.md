---
title: 'Gewusst wie: Erstellen einer Schaltfläche mit einem Bild'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: 9fb871aa39461329654c0289f00bd3080a633913
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="1f598-102">Gewusst wie: Erstellen einer Schaltfläche mit einem Bild</span><span class="sxs-lookup"><span data-stu-id="1f598-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="1f598-103">In diesem Beispiel wird gezeigt, wie auf ein Bild enthalten eine <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="1f598-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f598-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f598-104">Example</span></span>  
 <span data-ttu-id="1f598-105">Das folgende Beispiel erstellt zwei <xref:System.Windows.Controls.Button> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="1f598-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="1f598-106">Eine <xref:System.Windows.Controls.Button> Text enthält und das andere ein Bild.</span><span class="sxs-lookup"><span data-stu-id="1f598-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="1f598-107">Das Bild wird in einen Ordner namens Daten, d. h. einen Unterordner des Ordners für die Beispiel-Projekt.</span><span class="sxs-lookup"><span data-stu-id="1f598-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="1f598-108">Wenn ein Benutzer klickt auf die <xref:System.Windows.Controls.Button> , besitzt das Bild, Hintergrund und den Text der anderen <xref:System.Windows.Controls.Button> ändern.</span><span class="sxs-lookup"><span data-stu-id="1f598-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="1f598-109">In diesem Beispiel wird <xref:System.Windows.Controls.Button> steuert mithilfe von Markup, aber zum Schreiben von Code verwendet die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="1f598-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="1f598-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f598-110">See Also</span></span>  
 [<span data-ttu-id="1f598-111">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="1f598-111">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
 [<span data-ttu-id="1f598-112">Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="1f598-112">Control Library</span></span>](../../../../docs/framework/wpf/controls/control-library.md)
