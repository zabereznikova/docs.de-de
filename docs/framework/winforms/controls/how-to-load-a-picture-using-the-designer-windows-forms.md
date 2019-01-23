---
title: 'Vorgehensweise: Laden eines Bilds mithilfe des Designers (Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 6142474c2009e0998852dc28d346e73f4abbf1b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539089"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="0ebbd-102">Vorgehensweise: Laden eines Bilds mithilfe des Designers (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="0ebbd-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>
<span data-ttu-id="0ebbd-103">Mit der Windows Forms <xref:System.Windows.Forms.PictureBox> -Steuerelement, können Sie laden und anzeigen ein Bilds auf einem Formular zur Entwurfszeit durch Festlegen der <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft, um ein gültiges Bild.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="0ebbd-104">Die folgende Tabelle zeigt die zulässigen Dateitypen.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-104">The following table shows the acceptable file types.</span></span>  
  
|<span data-ttu-id="0ebbd-105">Typ</span><span class="sxs-lookup"><span data-stu-id="0ebbd-105">Type</span></span>|<span data-ttu-id="0ebbd-106">Dateinamenerweiterung</span><span class="sxs-lookup"><span data-stu-id="0ebbd-106">File name extension</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="0ebbd-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="0ebbd-107">Bitmap</span></span>|<span data-ttu-id="0ebbd-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="0ebbd-108">.bmp</span></span>|  
|<span data-ttu-id="0ebbd-109">Symbol</span><span class="sxs-lookup"><span data-stu-id="0ebbd-109">Icon</span></span>|<span data-ttu-id="0ebbd-110">.ico</span><span class="sxs-lookup"><span data-stu-id="0ebbd-110">.ico</span></span>|  
|<span data-ttu-id="0ebbd-111">GIF</span><span class="sxs-lookup"><span data-stu-id="0ebbd-111">GIF</span></span>|<span data-ttu-id="0ebbd-112">GIF</span><span class="sxs-lookup"><span data-stu-id="0ebbd-112">.gif</span></span>|  
|<span data-ttu-id="0ebbd-113">Metadatei</span><span class="sxs-lookup"><span data-stu-id="0ebbd-113">Metafile</span></span>|<span data-ttu-id="0ebbd-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="0ebbd-114">.wmf</span></span>|  
|<span data-ttu-id="0ebbd-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="0ebbd-115">JPEG</span></span>|<span data-ttu-id="0ebbd-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="0ebbd-116">.jpg</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="0ebbd-117">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0ebbd-118">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0ebbd-119">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="0ebbd-119">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="0ebbd-120">Zur Entwurfszeit ein Bild anzeigen</span><span class="sxs-lookup"><span data-stu-id="0ebbd-120">To display a picture at design time</span></span>  
  
1.  <span data-ttu-id="0ebbd-121">Zeichnen einer <xref:System.Windows.Forms.PictureBox> Steuerelement in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="0ebbd-122">Wählen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.PictureBox.Image%2A> -Eigenschaft, und klicken Sie dann auf klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um anzuzeigen die **öffnen** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>  
  
3.  <span data-ttu-id="0ebbd-123">Wenn Sie für einen bestimmten Dateityp (z. B. GIF-Dateien) suchen, wählen Sie sie in der **Dateityp** Feld.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>  
  
4.  <span data-ttu-id="0ebbd-124">Wählen Sie die Datei, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-124">Select the file you want to display.</span></span>  
  
### <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="0ebbd-125">Um das Bild zur Entwurfszeit zu löschen.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-125">To clear the picture at design time</span></span>  
  
1.  <span data-ttu-id="0ebbd-126">Auf der **Eigenschaften** wählen Sie im Fenster der <xref:System.Windows.Forms.PictureBox.Image%2A> -Eigenschaft und mit der rechten Maustaste die kleine Miniaturansicht, die auf der linken Seite den Namen des Image-Objekt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="0ebbd-127">Wählen Sie **zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-127">Choose **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ebbd-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ebbd-128">See also</span></span>
- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="0ebbd-129">Übersicht über das PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0ebbd-129">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="0ebbd-130">Vorgehensweise: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="0ebbd-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="0ebbd-131">Vorgehensweise: Festlegen von Bildern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="0ebbd-131">How to: Set Pictures at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="0ebbd-132">PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0ebbd-132">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
