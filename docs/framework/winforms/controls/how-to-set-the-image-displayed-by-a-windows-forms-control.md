---
title: 'Vorgehensweise: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Bildes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: 031ddcb3b852e75353fed7420735350e79f23df3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085089"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="aa980-102">Vorgehensweise: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Bildes</span><span class="sxs-lookup"><span data-stu-id="aa980-102">How to: Set the Image Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="aa980-103">Mehrerer Windows Forms-Steuerelemente können Bilder anzeigen.</span><span class="sxs-lookup"><span data-stu-id="aa980-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="aa980-104">Diese Images können Symbole, die Erläuterung des Zwecks des Steuerelements, z. B. ein Diskettensymbol auf eine Schaltfläche, werden die **speichern** Befehl.</span><span class="sxs-lookup"><span data-stu-id="aa980-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="aa980-105">Alternativ können die Symbole Hintergrundbilder, um die Kontrolle zu haben, die Darstellung und das gewünschte Verhalten sein.</span><span class="sxs-lookup"><span data-stu-id="aa980-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="aa980-106">Das von einem Steuerelement angezeigte Bild festlegen</span><span class="sxs-lookup"><span data-stu-id="aa980-106">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="aa980-107">Legen Sie die `Image` oder `BackgroundImage` Eigenschaft, um ein Objekt des Typs <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="aa980-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="aa980-108">In der Regel Laden Sie das Image aus einer Datei mithilfe der <xref:System.Drawing.Image.FromFile%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="aa980-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>  
  
     <span data-ttu-id="aa980-109">Das folgende Codebeispiel zeigt der Pfad festgelegt, für der Speicherort des Images ist der **eigene Bilder** Ordner.</span><span class="sxs-lookup"><span data-stu-id="aa980-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="aa980-110">Die meisten Computer, die das Windows-Betriebssystem ausgeführt wird, werden dieses Verzeichnis enthalten.</span><span class="sxs-lookup"><span data-stu-id="aa980-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="aa980-111">Dies ermöglicht auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="aa980-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="aa980-112">Das folgende Codebeispiel ist erforderlich, dass Sie bereits ein Formular mit einem <xref:System.Windows.Forms.PictureBox> Steuerelement hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="aa980-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>  
  
    ```vb  
    ' Replace the image named below  
    ' with an icon of your own choosing.  
    PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.MyPictures) _  
       & "\Image.gif")  
    ```  
  
    ```csharp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.MyPictures)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    pictureBox1->Image = Image::FromFile(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::MyPictures),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="aa980-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa980-113">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
