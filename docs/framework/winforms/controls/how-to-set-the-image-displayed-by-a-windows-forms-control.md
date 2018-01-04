---
title: "Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Bildes"
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
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4bf42fc90e19cbac0f165b59c0c6d3dfb7456b5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="d58c6-102">Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Bildes</span><span class="sxs-lookup"><span data-stu-id="d58c6-102">How to: Set the Image Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="d58c6-103">Einige Windows Forms-Steuerelemente können Bilder anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d58c6-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="d58c6-104">Diese Bilder können Symbole, die Erläuterung des Zwecks des Steuerelements, wie z. B. ein Diskettensymbol auf eine Schaltfläche, werden die **speichern** Befehl.</span><span class="sxs-lookup"><span data-stu-id="d58c6-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="d58c6-105">Alternativ kann die Symbole Hintergrundbilder zum Steuern der Darstellung und das gewünschte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="d58c6-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="d58c6-106">Das von einem Steuerelement angezeigte Bild festlegen</span><span class="sxs-lookup"><span data-stu-id="d58c6-106">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="d58c6-107">Legen Sie das Steuerelement `Image` oder `BackgroundImage` Eigenschaft, um ein Objekt vom Typ <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="d58c6-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="d58c6-108">Im Allgemeinen, laden Sie das Bild aus einer Datei mithilfe der <xref:System.Drawing.Image.FromFile%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="d58c6-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>  
  
     <span data-ttu-id="d58c6-109">Im folgenden Codebeispiel legen der Pfad für der Speicherort des Bilds wird die **eigene Bilder** Ordner.</span><span class="sxs-lookup"><span data-stu-id="d58c6-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="d58c6-110">Die meisten Computer das Windows-Betriebssystem ausgeführt wird, werden dieses Verzeichnis enthalten.</span><span class="sxs-lookup"><span data-stu-id="d58c6-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="d58c6-111">Außerdem können Benutzer mit minimalen problemlos die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d58c6-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="d58c6-112">Das folgende Codebeispiel erfordert, dass Sie bereits ein Formular mit einem <xref:System.Windows.Forms.PictureBox> ein Steuerelement hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="d58c6-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d58c6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d58c6-113">See Also</span></span>  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>
