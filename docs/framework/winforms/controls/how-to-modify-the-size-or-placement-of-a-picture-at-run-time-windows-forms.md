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
ms.openlocfilehash: fea813d7b9fe585e35b729b8b64e3a5f414ef76d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141965"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="26837-102">Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="26837-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="26837-103">Wenn Sie das <xref:System.Windows.Forms.PictureBox> Windows Forms-Steuerelement in einem <xref:System.Windows.Forms.PictureBox.SizeMode%2A> Formular verwenden, können Sie die Eigenschaft darauf auf:</span><span class="sxs-lookup"><span data-stu-id="26837-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="26837-104">Richten Sie die obere linke Ecke des Bildes mit der oberen linken Ecke des Steuerelements aus.</span><span class="sxs-lookup"><span data-stu-id="26837-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="26837-105">Zentrieren Sie das Bild innerhalb des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="26837-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="26837-106">Passen Sie die Größe des Steuerelements an das angezeigte Bild an</span><span class="sxs-lookup"><span data-stu-id="26837-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="26837-107">Dehnen Sie jedes angezeigte Bild, um es an das Steuerelement anzupassen</span><span class="sxs-lookup"><span data-stu-id="26837-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="26837-108">Das Dehnen eines Bildes (insbesondere eines im Bitmap-Format) kann zu einem Verlust der Bildqualität führen.</span><span class="sxs-lookup"><span data-stu-id="26837-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="26837-109">Metadateien, die Listen von Grafikanweisungen zum Zeichnen von Bildern zur Laufzeit sind, eignen sich besser zum Dehnen als Bitmaps.</span><span class="sxs-lookup"><span data-stu-id="26837-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="26837-110">So legen Sie die SizeMode-Eigenschaft zur Laufzeit fest</span><span class="sxs-lookup"><span data-stu-id="26837-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="26837-111">Wird <xref:System.Windows.Forms.PictureBox.SizeMode%2A> <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> auf (Standardeinstellung), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>oder <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>festgelegt.</span><span class="sxs-lookup"><span data-stu-id="26837-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="26837-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal>bedeutet, dass das Bild in der oberen linken Ecke des Steuerelements platziert wird; Wenn das Bild größer als das Steuerelement ist, werden die unteren und rechten Ränder abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="26837-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="26837-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>bedeutet, dass das Bild innerhalb des Steuerelements zentriert ist; Wenn das Bild größer als das Steuerelement ist, werden die Außenkanten des Bildes abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="26837-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="26837-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>bedeutet, dass die Größe des Steuerelements an die Größe des Bildes angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="26837-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="26837-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>ist die Rückseite und bedeutet, dass die Größe des Bildes an die Größe des Steuerelements angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="26837-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="26837-116">Im folgenden Beispiel ist der Pfad, der für den Speicherort des Bildes festgelegt ist, der Ordner Eigene Dokumente.</span><span class="sxs-lookup"><span data-stu-id="26837-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="26837-117">Dies ist der Grund, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, dieses Verzeichnis enthalten.</span><span class="sxs-lookup"><span data-stu-id="26837-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="26837-118">Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="26837-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="26837-119">Im folgenden Beispiel wird <xref:System.Windows.Forms.PictureBox> ein Formular mit einem bereits hinzugefügten Steuerelement angenommen.</span><span class="sxs-lookup"><span data-stu-id="26837-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="26837-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26837-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="26837-121">Gewusst wie: Laden eines Bilds mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="26837-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="26837-122">Übersicht über das PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="26837-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="26837-123">Gewusst wie: Festlegen von Bildern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="26837-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="26837-124">PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="26837-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
