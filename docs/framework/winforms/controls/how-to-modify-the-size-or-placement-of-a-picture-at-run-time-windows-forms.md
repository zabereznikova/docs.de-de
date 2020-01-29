---
title: 'Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
ms.openlocfilehash: 9bb094ce0b7945f23a2e9b8614e56c9492d5f832
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736036"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="a790b-102">Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a790b-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="a790b-103">Wenn Sie die Windows Forms <xref:System.Windows.Forms.PictureBox>-Steuerelement in einem Formular verwenden, können Sie die Eigenschaft <xref:System.Windows.Forms.PictureBox.SizeMode%2A> auf Folgendes festlegen:</span><span class="sxs-lookup"><span data-stu-id="a790b-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="a790b-104">Ausrichten der oberen linken Ecke des Bilds mit der linken oberen Ecke des Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="a790b-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="a790b-105">Zentrieren des Bilds innerhalb des Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="a790b-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="a790b-106">Passen Sie die Größe des Steuer Elements an das Bild an, das es anzeigt.</span><span class="sxs-lookup"><span data-stu-id="a790b-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="a790b-107">Bildstrecken, das angezeigt wird, um das Steuerelement anzupassen</span><span class="sxs-lookup"><span data-stu-id="a790b-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="a790b-108">Das Strecken eines Bilds (insbesondere eines im Bitmapformat) kann zu einem Verlust bei der Bildqualität führen.</span><span class="sxs-lookup"><span data-stu-id="a790b-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="a790b-109">Metadatendateien, die Listen mit Grafik Anweisungen zum Zeichnen von Bildern zur Laufzeit sind, eignen sich besser für die Streckung als Bitmaps.</span><span class="sxs-lookup"><span data-stu-id="a790b-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="a790b-110">So legen Sie die SizeMode-Eigenschaft zur Laufzeit fest</span><span class="sxs-lookup"><span data-stu-id="a790b-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="a790b-111">Legen Sie <xref:System.Windows.Forms.PictureBox.SizeMode%2A> auf <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (Standardeinstellung), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>oder <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>fest.</span><span class="sxs-lookup"><span data-stu-id="a790b-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="a790b-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> bedeutet, dass das Bild in der oberen linken Ecke des Steuer Elements platziert wird. Wenn das Bild größer als das Steuerelement ist, werden die unteren und rechten Ränder abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="a790b-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="a790b-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> bedeutet, dass das Bild im Steuerelement zentriert ist. Wenn das Bild größer als das Steuerelement ist, werden die äußeren Ränder des Bilds abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="a790b-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="a790b-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> bedeutet, dass die Größe des Steuer Elements an die Größe des Bilds angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="a790b-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="a790b-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> ist die umgekehrte und bedeutet, dass die Größe des Bilds an die Größe des Steuer Elements angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="a790b-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="a790b-116">Im folgenden Beispiel ist der Pfad, der für den Speicherort des Bilds festgelegt ist, der Ordner "eigene Dateien".</span><span class="sxs-lookup"><span data-stu-id="a790b-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="a790b-117">Dies geschieht, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, dieses Verzeichnis enthalten.</span><span class="sxs-lookup"><span data-stu-id="a790b-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="a790b-118">Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="a790b-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="a790b-119">Im folgenden Beispiel wird davon ausgegangen, dass ein <xref:System.Windows.Forms.PictureBox> Formular bereits hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="a790b-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a790b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a790b-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="a790b-121">Gewusst wie: Laden eines Bilds mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="a790b-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="a790b-122">Übersicht über das PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a790b-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="a790b-123">Gewusst wie: Festlegen von Bildern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a790b-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="a790b-124">PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a790b-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
