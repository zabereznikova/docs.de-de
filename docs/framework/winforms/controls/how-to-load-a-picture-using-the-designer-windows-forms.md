---
title: 'Gewusst wie: Laden eines Bilds mithilfe des Designers (Windows Forms)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1dec3c71c0c93ce580925744fe55f05cd2e5f383
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="08b2f-102">Gewusst wie: Laden eines Bilds mithilfe des Designers (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="08b2f-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>
<span data-ttu-id="08b2f-103">Mit dem Windows Forms <xref:System.Windows.Forms.PictureBox> -Steuerelement, laden und anzeigen ein Bilds auf einem Formular zur Entwurfszeit durch Festlegen der <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft, um ein gültiges Bild.</span><span class="sxs-lookup"><span data-stu-id="08b2f-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="08b2f-104">Die folgende Tabelle zeigt die zulässige Dateitypen.</span><span class="sxs-lookup"><span data-stu-id="08b2f-104">The following table shows the acceptable file types.</span></span>  
  
|<span data-ttu-id="08b2f-105">Typ</span><span class="sxs-lookup"><span data-stu-id="08b2f-105">Type</span></span>|<span data-ttu-id="08b2f-106">Dateinamenerweiterung</span><span class="sxs-lookup"><span data-stu-id="08b2f-106">File name extension</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="08b2f-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="08b2f-107">Bitmap</span></span>|<span data-ttu-id="08b2f-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="08b2f-108">.bmp</span></span>|  
|<span data-ttu-id="08b2f-109">Symbol</span><span class="sxs-lookup"><span data-stu-id="08b2f-109">Icon</span></span>|<span data-ttu-id="08b2f-110">.ico</span><span class="sxs-lookup"><span data-stu-id="08b2f-110">.ico</span></span>|  
|<span data-ttu-id="08b2f-111">GIF</span><span class="sxs-lookup"><span data-stu-id="08b2f-111">GIF</span></span>|<span data-ttu-id="08b2f-112">GIF</span><span class="sxs-lookup"><span data-stu-id="08b2f-112">.gif</span></span>|  
|<span data-ttu-id="08b2f-113">Metadatei</span><span class="sxs-lookup"><span data-stu-id="08b2f-113">Metafile</span></span>|<span data-ttu-id="08b2f-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="08b2f-114">.wmf</span></span>|  
|<span data-ttu-id="08b2f-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="08b2f-115">JPEG</span></span>|<span data-ttu-id="08b2f-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="08b2f-116">.jpg</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="08b2f-117">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="08b2f-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="08b2f-118">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="08b2f-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="08b2f-119">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="08b2f-119">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="08b2f-120">Zum Anzeigen eines Bilds zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="08b2f-120">To display a picture at design time</span></span>  
  
1.  <span data-ttu-id="08b2f-121">Zeichnen einer <xref:System.Windows.Forms.PictureBox> Steuerelement eines Formulars.</span><span class="sxs-lookup"><span data-stu-id="08b2f-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="08b2f-122">Wählen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.PictureBox.Image%2A> -Eigenschaft, und klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um anzuzeigen die **öffnen** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="08b2f-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>  
  
3.  <span data-ttu-id="08b2f-123">Wenn Sie für einen bestimmten Dateityp (z. B. GIF-Dateien) suchen, wählen Sie diese in die **Dateityp** Feld.</span><span class="sxs-lookup"><span data-stu-id="08b2f-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>  
  
4.  <span data-ttu-id="08b2f-124">Wählen Sie die Datei, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="08b2f-124">Select the file you want to display.</span></span>  
  
### <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="08b2f-125">So löschen Sie das Bild zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="08b2f-125">To clear the picture at design time</span></span>  
  
1.  <span data-ttu-id="08b2f-126">Auf der **Eigenschaften** wählen die <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft und mit der rechten Maustaste die kleine Miniaturansicht, die auf der linken Seite des Namens des Image-Objekt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="08b2f-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="08b2f-127">Wählen Sie **zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="08b2f-127">Choose **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b2f-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08b2f-128">See Also</span></span>  
 <xref:System.Windows.Forms.PictureBox>  
 [<span data-ttu-id="08b2f-129">Übersicht über das PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="08b2f-129">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [<span data-ttu-id="08b2f-130">Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="08b2f-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [<span data-ttu-id="08b2f-131">Gewusst wie: Festlegen von Bildern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="08b2f-131">How to: Set Pictures at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [<span data-ttu-id="08b2f-132">PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="08b2f-132">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
