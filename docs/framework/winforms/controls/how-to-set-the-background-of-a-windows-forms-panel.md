---
title: Festlegen des Hintergrunds eines Bereichs
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: 36e552475334c25b9d5a6fafb82155c6ebcba266
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182106"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a><span data-ttu-id="f808f-102">Gewusst wie: Festlegen des Hintergrunds eines Windows Forms-Bereichs</span><span class="sxs-lookup"><span data-stu-id="f808f-102">How to: Set the Background of a Windows Forms Panel</span></span>
<span data-ttu-id="f808f-103">Ein Windows <xref:System.Windows.Forms.Panel> Forms-Steuerelement kann sowohl eine Hintergrundfarbe als auch ein Hintergrundbild anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f808f-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="f808f-104">Die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft legt die Hintergrundfarbe für die enthaltenen Steuerelemente fest, z. B. Beschriftungen und Optionsfelder.</span><span class="sxs-lookup"><span data-stu-id="f808f-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for the contained controls, such as labels and radio buttons.</span></span> <span data-ttu-id="f808f-105">Wenn <xref:System.Windows.Forms.Control.BackgroundImage%2A> die Eigenschaft nicht <xref:System.Windows.Forms.Control.BackColor%2A> festgelegt ist, füllt die Auswahl das gesamte Bedienfeld aus.</span><span class="sxs-lookup"><span data-stu-id="f808f-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill the entire panel.</span></span> <span data-ttu-id="f808f-106">Wenn <xref:System.Windows.Forms.Control.BackgroundImage%2A> die Eigenschaft festgelegt ist, wird das Bild hinter den enthaltenen Steuerelementen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f808f-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the contained controls.</span></span>  
  
### <a name="to-set-the-background-programmatically"></a><span data-ttu-id="f808f-107">So stellen Sie den Hintergrund programmgesteuert ein</span><span class="sxs-lookup"><span data-stu-id="f808f-107">To set the background programmatically</span></span>  
  
1. <span data-ttu-id="f808f-108">Legen Sie die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft des Bedienfelds auf einen Wert vom Typ <xref:System.Drawing.Color?displayProperty=nameWithType>fest.</span><span class="sxs-lookup"><span data-stu-id="f808f-108">Set the panel's <xref:System.Windows.Forms.Control.BackColor%2A> property to a value of type <xref:System.Drawing.Color?displayProperty=nameWithType>.</span></span>  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. <span data-ttu-id="f808f-109">Legen Sie die <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft <xref:System.Drawing.Image.FromFile%2A> des Bedienfelds mithilfe der Methode der <xref:System.Drawing.Image?displayProperty=nameWithType> Klasse fest.</span><span class="sxs-lookup"><span data-stu-id="f808f-109">Set the panel's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image?displayProperty=nameWithType> class.</span></span>  
  
    ```vb  
    ' You should replace the bolded image
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f808f-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f808f-110">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="f808f-111">Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f808f-111">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="f808f-112">Übersicht über das Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f808f-112">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
