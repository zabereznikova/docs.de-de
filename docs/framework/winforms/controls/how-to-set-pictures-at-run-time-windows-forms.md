---
title: "Gewusst wie: Festlegen von Bildern zur Laufzeit (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 429c0c928d8bff4f837186040288d9447fc18687
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a><span data-ttu-id="9df58-102">Gewusst wie: Festlegen von Bildern zur Laufzeit (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9df58-102">How to: Set Pictures at Run Time (Windows Forms)</span></span>
<span data-ttu-id="9df58-103">Bild von einer Windows Forms angezeigt können programmgesteuert festgelegt werden <xref:System.Windows.Forms.PictureBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9df58-103">You can programmatically set the image displayed by a Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-set-a-picture-programmatically"></a><span data-ttu-id="9df58-104">So legen Sie ein Bild programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="9df58-104">To set a picture programmatically</span></span>  
  
-   <span data-ttu-id="9df58-105">Legen Sie die <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft mit der <xref:System.Drawing.Image.FromFile%2A> Methode der <xref:System.Drawing.Image> Klasse.</span><span class="sxs-lookup"><span data-stu-id="9df58-105">Set the <xref:System.Windows.Forms.PictureBox.Image%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image> class.</span></span>  
  
     <span data-ttu-id="9df58-106">Im folgenden Beispiel wird der Pfad für den Speicherort des Bilds Festlegen der Ordner "Eigene Dokumente".</span><span class="sxs-lookup"><span data-stu-id="9df58-106">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="9df58-107">Dies geschieht, da Sie davon ausgehen können, die meisten Computer das Windows-Betriebssystem ausgeführt werden, dieses Verzeichnis enthält.</span><span class="sxs-lookup"><span data-stu-id="9df58-107">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="9df58-108">Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="9df58-108">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="9df58-109">Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.PictureBox> Steuerelement bereits hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9df58-109">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
### <a name="to-clear-a-graphic"></a><span data-ttu-id="9df58-110">So löschen Sie eine Grafik</span><span class="sxs-lookup"><span data-stu-id="9df58-110">To clear a graphic</span></span>  
  
-   <span data-ttu-id="9df58-111">Zunächst freigegeben Sie vom Image verwendeten Speicherplatz, und deaktivieren Sie dann auf die Grafik.</span><span class="sxs-lookup"><span data-stu-id="9df58-111">First, release the memory being used by the image, and then clear the graphic.</span></span> <span data-ttu-id="9df58-112">Garbagecollection wird später um den Arbeitsspeicher freizugeben, wenn die Verwaltung des Arbeitsspeichers ein Problem aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9df58-112">Garbage collection will free up the memory later if memory management becomes a problem.</span></span>  
  
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
    >  <span data-ttu-id="9df58-113">Weitere Informationen dazu, warum sollten Sie verwenden die <xref:System.Drawing.Image.Dispose%2A> Methode auf diese Weise finden Sie unter [Bereinigen von nicht verwalteten Ressourcen](../../../../docs/standard/garbage-collection/unmanaged.md).</span><span class="sxs-lookup"><span data-stu-id="9df58-113">For more information on why you should use the <xref:System.Drawing.Image.Dispose%2A> method in this way, see [Cleaning Up Unmanaged Resources](../../../../docs/standard/garbage-collection/unmanaged.md).</span></span>  
  
     <span data-ttu-id="9df58-114">Mit diesem Code wird das Bild gelöscht, selbst wenn das Steuerelement zur Entwurfszeit eine Grafik geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="9df58-114">This code will clear the image even if a graphic was loaded into the control at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9df58-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9df58-115">See Also</span></span>  
 <xref:System.Windows.Forms.PictureBox>  
 <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="9df58-116">Übersicht über das PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9df58-116">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [<span data-ttu-id="9df58-117">Gewusst wie: Laden eines Bilds mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="9df58-117">How to: Load a Picture Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [<span data-ttu-id="9df58-118">Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="9df58-118">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [<span data-ttu-id="9df58-119">PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9df58-119">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
