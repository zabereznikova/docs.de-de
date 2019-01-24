---
title: 'Vorgehensweise: Festlegen von Bildern zur Laufzeit (Windows Forms)'
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
ms.openlocfilehash: c7a65bcc65710324a4457c17dd728b4771550c06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694073"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a><span data-ttu-id="ac4df-102">Vorgehensweise: Festlegen von Bildern zur Laufzeit (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ac4df-102">How to: Set Pictures at Run Time (Windows Forms)</span></span>
<span data-ttu-id="ac4df-103">Sie können das Bild angezeigt, die von einer Windows Forms programmgesteuert festlegen <xref:System.Windows.Forms.PictureBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ac4df-103">You can programmatically set the image displayed by a Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-set-a-picture-programmatically"></a><span data-ttu-id="ac4df-104">So legen Sie ein Bild programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="ac4df-104">To set a picture programmatically</span></span>  
  
-   <span data-ttu-id="ac4df-105">Legen Sie die <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft mithilfe der <xref:System.Drawing.Image.FromFile%2A> -Methode der der <xref:System.Drawing.Image> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ac4df-105">Set the <xref:System.Windows.Forms.PictureBox.Image%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image> class.</span></span>  
  
     <span data-ttu-id="ac4df-106">Im folgenden Beispiel wird der Pfad für den Speicherort des Bilds Ordner "Eigene Dokumente".</span><span class="sxs-lookup"><span data-stu-id="ac4df-106">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="ac4df-107">Dies geschieht, da Sie davon ausgehen können, dass die meisten Computer, die das Windows-Betriebssystem ausgeführt wird dieses Verzeichnis enthält.</span><span class="sxs-lookup"><span data-stu-id="ac4df-107">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="ac4df-108">Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="ac4df-108">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="ac4df-109">Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.PictureBox> Steuerelement bereits hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ac4df-109">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
### <a name="to-clear-a-graphic"></a><span data-ttu-id="ac4df-110">Um eine Grafik zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ac4df-110">To clear a graphic</span></span>  
  
-   <span data-ttu-id="ac4df-111">Zunächst freigegeben Sie von der Abbildung verwendeten Arbeitsspeicher, und deaktivieren Sie dann auf die Grafik.</span><span class="sxs-lookup"><span data-stu-id="ac4df-111">First, release the memory being used by the image, and then clear the graphic.</span></span> <span data-ttu-id="ac4df-112">Die automatische speicherbereinigung wird später um den Arbeitsspeicher freizugeben, wenn die Verwaltung des Arbeitsspeichers zu einem Problem wird.</span><span class="sxs-lookup"><span data-stu-id="ac4df-112">Garbage collection will free up the memory later if memory management becomes a problem.</span></span>  
  
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
    >  <span data-ttu-id="ac4df-113">Verwenden Sie für Weitere Informationen darüber, warum die <xref:System.Drawing.Image.Dispose%2A> -Methode in der auf diese Weise finden Sie unter [Bereinigen von nicht verwalteten Ressourcen](../../../../docs/standard/garbage-collection/unmanaged.md).</span><span class="sxs-lookup"><span data-stu-id="ac4df-113">For more information on why you should use the <xref:System.Drawing.Image.Dispose%2A> method in this way, see [Cleaning Up Unmanaged Resources](../../../../docs/standard/garbage-collection/unmanaged.md).</span></span>  
  
     <span data-ttu-id="ac4df-114">Dieser Code wird das Image gelöscht, selbst wenn eine Grafik in das Steuerelement zur Entwurfszeit geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ac4df-114">This code will clear the image even if a graphic was loaded into the control at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac4df-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac4df-115">See also</span></span>
- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ac4df-116">Übersicht über das PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ac4df-116">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="ac4df-117">Vorgehensweise: Laden eines Bilds mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="ac4df-117">How to: Load a Picture Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="ac4df-118">Vorgehensweise: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ac4df-118">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="ac4df-119">PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ac4df-119">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
