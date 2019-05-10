---
title: 'Vorgehensweise: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms'
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
ms.openlocfilehash: 31ae91958dbc02a2f64945af896b4a2408224d05
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624037"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="07658-102">Vorgehensweise: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07658-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="07658-103">Die Windows-Formulare <xref:System.Windows.Forms.ImageList> Komponente wird mit Bildern in der Regel aufgefüllt, bevor sie mit einem Steuerelement verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="07658-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="07658-104">Sie können jedoch hinzufügen und entfernen Bilder, nachdem die Bildliste mit einem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="07658-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07658-105">Entfernen von Bildern sicher, dass die <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> Eigenschaft aller verknüpften Steuerelemente ist weiterhin gültig.</span><span class="sxs-lookup"><span data-stu-id="07658-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="07658-106">Programmgesteuertes Hinzufügen von Bildern</span><span class="sxs-lookup"><span data-stu-id="07658-106">To add images programmatically</span></span>  
  
- <span data-ttu-id="07658-107">Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> -Methode der Liste der Bilder <xref:System.Windows.Forms.ImageList.Images%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="07658-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="07658-108">Das folgende Codebeispiel zeigt der Pfad festgelegt, für der Speicherort des Images ist der **eigene** Ordner.</span><span class="sxs-lookup"><span data-stu-id="07658-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="07658-109">Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass dieser Ordner enthält die meisten Computer, auf denen die Windows-Betriebssystem ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="07658-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="07658-110">Dieser Speicherort können auch Benutzer mit minimalen Systemzugriffsebenen Weitere problemlos die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="07658-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="07658-111">Das folgende Codebeispiel ist erforderlich, dass ein Formular mit einem <xref:System.Windows.Forms.ImageList> Steuerelement bereits hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="07658-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="07658-112">Hinzufügen von Bildern mit einem Schlüsselwert.</span><span class="sxs-lookup"><span data-stu-id="07658-112">To add images with a key value.</span></span>  
  
- <span data-ttu-id="07658-113">Gehen Sie die <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> Methoden der Liste der Bilder <xref:System.Windows.Forms.ImageList.Images%2A> -Eigenschaft, die einen Schlüsselwert verwendet.</span><span class="sxs-lookup"><span data-stu-id="07658-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="07658-114">Das folgende Codebeispiel zeigt der Pfad festgelegt, für der Speicherort des Images ist der **eigene** Ordner.</span><span class="sxs-lookup"><span data-stu-id="07658-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="07658-115">Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass dieser Ordner enthält die meisten Computer, auf denen die Windows-Betriebssystem ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="07658-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="07658-116">Dieser Speicherort können auch Benutzer mit minimalen Systemzugriffsebenen Weitere problemlos die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="07658-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="07658-117">Das folgende Codebeispiel ist erforderlich, dass ein Formular mit einem <xref:System.Windows.Forms.ImageList> Steuerelement bereits hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="07658-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="07658-118">So entfernen Sie alle Bilder programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="07658-118">To remove all images programmatically</span></span>  
  
- <span data-ttu-id="07658-119">Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> Methode, um ein einzelnes Bild entfernen</span><span class="sxs-lookup"><span data-stu-id="07658-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="07658-120">, – oder –</span><span class="sxs-lookup"><span data-stu-id="07658-120">,-or-</span></span>  
  
     <span data-ttu-id="07658-121">Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> Methode, um alle Bilder in der Bildliste zu löschen.</span><span class="sxs-lookup"><span data-stu-id="07658-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
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
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="07658-122">So entfernen Sie die Bilder nach Schlüssel</span><span class="sxs-lookup"><span data-stu-id="07658-122">To remove images by key</span></span>  
  
- <span data-ttu-id="07658-123">Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> Methode, um ein einzelnes Abbild über seinen Schlüssel zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="07658-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="07658-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07658-124">See also</span></span>

- [<span data-ttu-id="07658-125">ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="07658-125">ImageList Component</span></span>](imagelist-component-windows-forms.md)
- [<span data-ttu-id="07658-126">Übersicht über die ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="07658-126">ImageList Component Overview</span></span>](imagelist-component-overview-windows-forms.md)
- [<span data-ttu-id="07658-127">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="07658-127">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
