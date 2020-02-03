---
title: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], removing from ImageList component
- images [Windows Forms], storing for controls
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
- images [Windows Forms], displaying with controls
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
ms.openlocfilehash: f531003377395bf219775e5ddb48ceb0822ff0ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741500"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="c9e20-102">Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9e20-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="c9e20-103">Die Windows Forms <xref:System.Windows.Forms.ImageList> Komponente wird in der Regel mit Bildern aufgefüllt, bevor Sie einem-Steuerelement zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="c9e20-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="c9e20-104">Sie können jedoch Bilder hinzufügen und entfernen, nachdem Sie die Bildliste mit einem-Steuerelement verknüpft haben.</span><span class="sxs-lookup"><span data-stu-id="c9e20-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9e20-105">Wenn Sie Bilder entfernen, vergewissern Sie sich, dass die <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A>-Eigenschaft aller zugeordneten Steuerelemente weiterhin gültig ist.</span><span class="sxs-lookup"><span data-stu-id="c9e20-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="c9e20-106">So fügen Sie Bilder Programm gesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="c9e20-106">To add images programmatically</span></span>  
  
- <span data-ttu-id="c9e20-107">Verwenden Sie die <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A>-Methode der <xref:System.Windows.Forms.ImageList.Images%2A>-Eigenschaft der Bildliste.</span><span class="sxs-lookup"><span data-stu-id="c9e20-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="c9e20-108">Im folgenden Codebeispiel ist der Pfad, der für den Speicherort des Bilds festgelegt wurde, der Ordner " **eigene** Dateien".</span><span class="sxs-lookup"><span data-stu-id="c9e20-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="c9e20-109">Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, diesen Ordner enthalten.</span><span class="sxs-lookup"><span data-stu-id="c9e20-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="c9e20-110">Wenn Sie diesen Speicherort auswählen, können Benutzer mit minimalen System Zugriffsebenen die Anwendung sicherer ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9e20-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="c9e20-111">Für das folgende Codebeispiel ist es erforderlich, dass Sie über ein Formular mit einem <xref:System.Windows.Forms.ImageList>-Steuerelement verfügen.</span><span class="sxs-lookup"><span data-stu-id="c9e20-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    End Sub  
    ```  
  
    ```csharp  
    public void addImage()  
    {  
    // Be sure that you use an appropriate escape sequence (such as the   
    // @) when specifying the location of the file.  
       System.Drawing.Image myImage =   
         Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
    }  
    ```  
  
    ```cpp  
    public:  
       void addImage()  
       {  
       // Replace the bold image in the following sample   
       // with your own icon.  
       // Be sure that you use an appropriate escape sequence (such as   
       // \\) when specifying the location of the file.  
          System::Drawing::Image ^ myImage =   
             Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
       }  
    ```  
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="c9e20-112">Zum Hinzufügen von Bildern mit einem Schlüsselwert.</span><span class="sxs-lookup"><span data-stu-id="c9e20-112">To add images with a key value.</span></span>  
  
- <span data-ttu-id="c9e20-113">Verwenden Sie eine der <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> Methoden der <xref:System.Windows.Forms.ImageList.Images%2A> Eigenschaft der Bildliste, die einen Schlüsselwert annimmt.</span><span class="sxs-lookup"><span data-stu-id="c9e20-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="c9e20-114">Im folgenden Codebeispiel ist der Pfad, der für den Speicherort des Bilds festgelegt wurde, der Ordner " **eigene** Dateien".</span><span class="sxs-lookup"><span data-stu-id="c9e20-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="c9e20-115">Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, diesen Ordner enthalten.</span><span class="sxs-lookup"><span data-stu-id="c9e20-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="c9e20-116">Wenn Sie diesen Speicherort auswählen, können Benutzer mit minimalen System Zugriffsebenen die Anwendung sicherer ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9e20-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="c9e20-117">Für das folgende Codebeispiel ist es erforderlich, dass Sie über ein Formular mit einem <xref:System.Windows.Forms.ImageList>-Steuerelement verfügen.</span><span class="sxs-lookup"><span data-stu-id="c9e20-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add("myPhoto", myImage)  
    End Sub  
    ```  
  
```csharp  
public void addImage()  
{  
// Be sure that you use an appropriate escape sequence (such as the   
// @) when specifying the location of the file.  
   System.Drawing.Image myImage =   
     Image.FromFile  
   (System.Environment.GetFolderPath  
   (System.Environment.SpecialFolder.Personal)  
   + @"\Image.gif");  
   imageList1.Images.Add("myPhoto", myImage);  
}  
```  
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="c9e20-118">So entfernen Sie alle Bilder Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="c9e20-118">To remove all images programmatically</span></span>  
  
- <span data-ttu-id="c9e20-119">Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A>-Methode zum Entfernen eines einzelnen Bilds</span><span class="sxs-lookup"><span data-stu-id="c9e20-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="c9e20-120">,-oder-</span><span class="sxs-lookup"><span data-stu-id="c9e20-120">,-or-</span></span>  
  
     <span data-ttu-id="c9e20-121">Verwenden Sie die <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A>-Methode, um alle Bilder in der Bildliste zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c9e20-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
    ```vb  
    ' Removes the first image in the image list  
    ImageList1.Images.Remove(myImage)  
    ' Clears all images in the image list  
    ImageList1.Images.Clear()  
    ```  
  
```csharp  
// Removes the first image in the image list.  
imageList1.Images.Remove(myImage);  
// Clears all images in the image list.  
imageList1.Images.Clear();  
```  
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="c9e20-122">So entfernen Sie Images nach Schlüssel</span><span class="sxs-lookup"><span data-stu-id="c9e20-122">To remove images by key</span></span>  
  
- <span data-ttu-id="c9e20-123">Verwenden Sie die <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A>-Methode, um ein einzelnes Bild anhand des Schlüssels zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c9e20-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9e20-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9e20-124">See also</span></span>

- [<span data-ttu-id="c9e20-125">ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="c9e20-125">ImageList Component</span></span>](imagelist-component-windows-forms.md)
- [<span data-ttu-id="c9e20-126">Übersicht über die ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="c9e20-126">ImageList Component Overview</span></span>](imagelist-component-overview-windows-forms.md)
- [<span data-ttu-id="c9e20-127">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="c9e20-127">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
