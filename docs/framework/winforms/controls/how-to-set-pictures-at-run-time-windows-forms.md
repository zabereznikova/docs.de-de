---
title: 'Gewusst wie: Festlegen von Bildern zur Laufzeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: bd0509c05fd9c1cfc0c631fcd613c64d20296f6b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746745"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a><span data-ttu-id="49806-102">Gewusst wie: Festlegen von Bildern zur Laufzeit (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="49806-102">How to: Set Pictures at Run Time (Windows Forms)</span></span>
<span data-ttu-id="49806-103">Sie können das Bild, das von einem Windows Forms <xref:System.Windows.Forms.PictureBox>-Steuerelement angezeigt wird, Programm gesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="49806-103">You can programmatically set the image displayed by a Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-set-a-picture-programmatically"></a><span data-ttu-id="49806-104">So legen Sie ein Bildprogramm gesteuert fest</span><span class="sxs-lookup"><span data-stu-id="49806-104">To set a picture programmatically</span></span>  
  
- <span data-ttu-id="49806-105">Legen Sie die <xref:System.Windows.Forms.PictureBox.Image%2A>-Eigenschaft mit der <xref:System.Drawing.Image.FromFile%2A>-Methode der <xref:System.Drawing.Image>-Klasse fest.</span><span class="sxs-lookup"><span data-stu-id="49806-105">Set the <xref:System.Windows.Forms.PictureBox.Image%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image> class.</span></span>  
  
     <span data-ttu-id="49806-106">Im folgenden Beispiel ist der Pfad, der für den Speicherort des Bilds festgelegt ist, der Ordner "eigene Dateien".</span><span class="sxs-lookup"><span data-stu-id="49806-106">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="49806-107">Dies geschieht, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, dieses Verzeichnis enthalten.</span><span class="sxs-lookup"><span data-stu-id="49806-107">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="49806-108">Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="49806-108">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="49806-109">Im folgenden Beispiel wird davon ausgegangen, dass ein <xref:System.Windows.Forms.PictureBox> Formular bereits hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="49806-109">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a><span data-ttu-id="49806-110">So löschen Sie eine Grafik</span><span class="sxs-lookup"><span data-stu-id="49806-110">To clear a graphic</span></span>  
  
- <span data-ttu-id="49806-111">Geben Sie zunächst den Speicher frei, der von dem Image verwendet wird, und löschen Sie dann die Grafik.</span><span class="sxs-lookup"><span data-stu-id="49806-111">First, release the memory being used by the image, and then clear the graphic.</span></span> <span data-ttu-id="49806-112">Durch die Garbage Collection wird der Arbeitsspeicher später freigegeben, wenn die Speicherverwaltung zu einem Problem wird.</span><span class="sxs-lookup"><span data-stu-id="49806-112">Garbage collection will free up the memory later if memory management becomes a problem.</span></span>  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)   
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="49806-113">Weitere Informationen dazu, warum Sie die <xref:System.Drawing.Image.Dispose%2A>-Methode auf diese Weise verwenden sollten, finden Sie unter [Bereinigen von nicht verwalteten Ressourcen](../../../standard/garbage-collection/unmanaged.md).</span><span class="sxs-lookup"><span data-stu-id="49806-113">For more information on why you should use the <xref:System.Drawing.Image.Dispose%2A> method in this way, see [Cleaning Up Unmanaged Resources](../../../standard/garbage-collection/unmanaged.md).</span></span>  
  
     <span data-ttu-id="49806-114">Mit diesem Code wird das Bild gelöscht, auch wenn eine Grafik zur Entwurfszeit in das Steuerelement geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="49806-114">This code will clear the image even if a graphic was loaded into the control at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49806-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="49806-115">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [<span data-ttu-id="49806-116">Übersicht über das PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="49806-116">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="49806-117">Gewusst wie: Laden eines Bilds mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="49806-117">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="49806-118">Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="49806-118">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="49806-119">PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="49806-119">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
