---
title: "Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms"
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
- images [Windows Forms], removing from ImageList component
- images [Windows Forms], storing for controls
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
- images [Windows Forms], displaying with controls
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ce13ba3413c13ced7ff9a967e23d87622309feb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="b945d-102">Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b945d-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="b945d-103">Windows Forms <xref:System.Windows.Forms.ImageList> Komponente wird in der Regel mit Bildern aufgefüllt, bevor sie ein Steuerelement zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b945d-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="b945d-104">Sie können jedoch hinzufügen und entfernen Bilder, nachdem die Bildliste mit einem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b945d-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b945d-105">Beim Entfernen von Bildern, vergewissern Sie sich, die die <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> Eigenschaft aller verknüpften Steuerelemente noch gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b945d-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="b945d-106">Programmgesteuertes Hinzufügen von Bildern</span><span class="sxs-lookup"><span data-stu-id="b945d-106">To add images programmatically</span></span>  
  
-   <span data-ttu-id="b945d-107">Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> Methode der Bildliste <xref:System.Windows.Forms.ImageList.Images%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b945d-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="b945d-108">Im folgenden Codebeispiel legen der Pfad für der Speicherort des Bilds wird die **eigene** Ordner.</span><span class="sxs-lookup"><span data-stu-id="b945d-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="b945d-109">Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass die meisten Computer, auf denen die Windows-Betriebssystem ausgeführt werden dieser Ordner enthält.</span><span class="sxs-lookup"><span data-stu-id="b945d-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="b945d-110">Dieser Speicherort kann auch Benutzer mit minimalen Zugriffsebenen Weitere sicher führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="b945d-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="b945d-111">Das folgende Codebeispiel erfordert, dass ein Formular mit einem <xref:System.Windows.Forms.ImageList> Steuerelement bereits hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b945d-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="b945d-112">Hinzufügen von Bildern mit einem Schlüsselwert.</span><span class="sxs-lookup"><span data-stu-id="b945d-112">To add images with a key value.</span></span>  
  
-   <span data-ttu-id="b945d-113">Gehen Sie die <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> Methoden der Bildliste <xref:System.Windows.Forms.ImageList.Images%2A> Eigenschaft, die einen Schlüsselwert.</span><span class="sxs-lookup"><span data-stu-id="b945d-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="b945d-114">Im folgenden Codebeispiel legen der Pfad für der Speicherort des Bilds wird die **eigene** Ordner.</span><span class="sxs-lookup"><span data-stu-id="b945d-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="b945d-115">Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass die meisten Computer, auf denen die Windows-Betriebssystem ausgeführt werden dieser Ordner enthält.</span><span class="sxs-lookup"><span data-stu-id="b945d-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="b945d-116">Dieser Speicherort kann auch Benutzer mit minimalen Zugriffsebenen Weitere sicher führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="b945d-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="b945d-117">Das folgende Codebeispiel erfordert, dass ein Formular mit einem <xref:System.Windows.Forms.ImageList> Steuerelement bereits hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b945d-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
1.  
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="b945d-118">So entfernen Sie alle Bilder programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="b945d-118">To remove all images programmatically</span></span>  
  
-   <span data-ttu-id="b945d-119">Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> -Methode zum Entfernen eines einzelnen Images</span><span class="sxs-lookup"><span data-stu-id="b945d-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="b945d-120">, - oder -</span><span class="sxs-lookup"><span data-stu-id="b945d-120">,-or-</span></span>  
  
     <span data-ttu-id="b945d-121">Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> Methode, um alle Bilder in der Bildliste zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b945d-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
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
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="b945d-122">So entfernen Sie die Bilder nach Schlüssel</span><span class="sxs-lookup"><span data-stu-id="b945d-122">To remove images by key</span></span>  
  
-   <span data-ttu-id="b945d-123">Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> Methode, um ein einzelnes Bild anhand ihres Schlüssels zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b945d-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="b945d-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b945d-124">See Also</span></span>  
 [<span data-ttu-id="b945d-125">ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="b945d-125">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)  
 [<span data-ttu-id="b945d-126">Übersicht über die ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="b945d-126">ImageList Component Overview</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-overview-windows-forms.md)  
 [<span data-ttu-id="b945d-127">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="b945d-127">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
