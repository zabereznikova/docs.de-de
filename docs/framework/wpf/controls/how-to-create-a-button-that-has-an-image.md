---
title: 'Vorgehensweise: Erstellen einer Schaltfläche mit einem Bild'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: fe9f35a6f83c5a839823d94c4d3c55e01b192fb1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352034"
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="81ee9-102">Vorgehensweise: Erstellen einer Schaltfläche mit einem Bild</span><span class="sxs-lookup"><span data-stu-id="81ee9-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="81ee9-103">Dieses Beispiel zeigt, wie Sie ein Bild enthalten, auf eine <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="81ee9-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81ee9-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81ee9-104">Example</span></span>  
 <span data-ttu-id="81ee9-105">Das folgende Beispiel erstellt zwei <xref:System.Windows.Controls.Button> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="81ee9-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="81ee9-106">Eine <xref:System.Windows.Controls.Button> enthält Text und das andere ein Bild.</span><span class="sxs-lookup"><span data-stu-id="81ee9-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="81ee9-107">Das Image ist in einem Ordner namens Daten, d. h. einen Unterordner des Projektordners des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="81ee9-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="81ee9-108">Wenn ein Benutzer klickt auf die <xref:System.Windows.Controls.Button> über das Image, Hintergrund und den Text der anderen verfügt <xref:System.Windows.Controls.Button> ändern.</span><span class="sxs-lookup"><span data-stu-id="81ee9-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="81ee9-109">In diesem Beispiel wird <xref:System.Windows.Controls.Button> steuert mithilfe von Markup wird jedoch Code schreiben verwendet die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="81ee9-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="81ee9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81ee9-110">See also</span></span>
- [<span data-ttu-id="81ee9-111">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="81ee9-111">Controls</span></span>](index.md)
- [<span data-ttu-id="81ee9-112">Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="81ee9-112">Control Library</span></span>](control-library.md)
