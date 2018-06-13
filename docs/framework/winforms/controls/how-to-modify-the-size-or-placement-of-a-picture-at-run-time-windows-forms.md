---
title: 'Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit (Windows Forms)'
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
ms.openlocfilehash: 9e6e114e0a9d7e5e9c17ba21ef941703cd108784
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534773"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="9c99d-102">Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9c99d-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="9c99d-103">Bei Verwendung von Windows Forms <xref:System.Windows.Forms.PictureBox> Steuerelement eines Formulars, können Sie festlegen der <xref:System.Windows.Forms.PictureBox.SizeMode%2A> Eigenschaft darauf:</span><span class="sxs-lookup"><span data-stu-id="9c99d-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
-   <span data-ttu-id="9c99d-104">Richten Sie das Bild oben links mit der linken oberen Ecke des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="9c99d-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
-   <span data-ttu-id="9c99d-105">Zentrieren Sie das Bild innerhalb des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="9c99d-105">Center the picture within the control</span></span>  
  
-   <span data-ttu-id="9c99d-106">Passen Sie die Größe des Steuerelements auf dem Bild anzupassen, die angezeigt</span><span class="sxs-lookup"><span data-stu-id="9c99d-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
-   <span data-ttu-id="9c99d-107">Stretch-Bild angezeigt wird, um das Steuerelement eingepasst werden</span><span class="sxs-lookup"><span data-stu-id="9c99d-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="9c99d-108">Strecken ein Bild (vor allem eine Bitmap-Format), kann ein Verlust Bildqualität erzeugen.</span><span class="sxs-lookup"><span data-stu-id="9c99d-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="9c99d-109">Metadateien, die Listen von Graphics-Anweisungen zum Darstellen von Bildern zur Laufzeit sind, sind besser geeignet als Bitmaps sind Strecken.</span><span class="sxs-lookup"><span data-stu-id="9c99d-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="9c99d-110">Die SizeMode-Eigenschaft zur Laufzeit festgelegt</span><span class="sxs-lookup"><span data-stu-id="9c99d-110">To set the SizeMode property at run time</span></span>  
  
1.  <span data-ttu-id="9c99d-111">Legen Sie <xref:System.Windows.Forms.PictureBox.SizeMode%2A> auf <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (Standard), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, oder <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span><span class="sxs-lookup"><span data-stu-id="9c99d-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="9c99d-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> bedeutet, dass das Bild in der linken oberen Ecke befindet. Wenn das Bild größer als das Steuerelement ist, werden die unteren und rechten Rand abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="9c99d-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="9c99d-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> bedeutet, dass das Bild im Steuerelement zentriert wird. Wenn das Bild größer als das Steuerelement ist, werden das Bild äußeren Kanten abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="9c99d-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="9c99d-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> bedeutet, dass die Größe des Steuerelements auf die Größe des Bilds angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="9c99d-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="9c99d-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> ist das Gegenteil und bedeutet, dass die Größe des Bilds an die Größe des Steuerelements angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="9c99d-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="9c99d-116">Im folgenden Beispiel wird der Pfad für den Speicherort des Bilds Festlegen der Ordner "Eigene Dokumente".</span><span class="sxs-lookup"><span data-stu-id="9c99d-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="9c99d-117">Dies geschieht, da Sie davon ausgehen können, die meisten Computer das Windows-Betriebssystem ausgeführt werden, dieses Verzeichnis enthält.</span><span class="sxs-lookup"><span data-stu-id="9c99d-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="9c99d-118">Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="9c99d-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="9c99d-119">Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.PictureBox> Steuerelement bereits hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9c99d-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c99d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c99d-120">See Also</span></span>  
 <xref:System.Windows.Forms.PictureBox>  
 [<span data-ttu-id="9c99d-121">Gewusst wie: Laden eines Bilds mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="9c99d-121">How to: Load a Picture Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [<span data-ttu-id="9c99d-122">Übersicht über das PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9c99d-122">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [<span data-ttu-id="9c99d-123">Gewusst wie: Festlegen von Bildern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="9c99d-123">How to: Set Pictures at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [<span data-ttu-id="9c99d-124">PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9c99d-124">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
