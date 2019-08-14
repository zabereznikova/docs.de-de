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
ms.openlocfilehash: 1d95d5baafa42c7dea40933ba837b684d90b7b2b
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972373"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="ddb05-102">Vorgehensweise: Laden eines Bilds mithilfe des Designers (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ddb05-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="ddb05-103">Mit dem Windows Forms <xref:System.Windows.Forms.PictureBox> -Steuerelement können Sie ein Bild auf einem Formular zur Entwurfszeit laden und anzeigen, indem <xref:System.Windows.Forms.PictureBox.Image%2A> Sie die-Eigenschaft auf ein gültiges Bild festlegen.</span><span class="sxs-lookup"><span data-stu-id="ddb05-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="ddb05-104">In der folgenden Tabelle sind die zulässigen Dateitypen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ddb05-104">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="ddb05-105">Typ</span><span class="sxs-lookup"><span data-stu-id="ddb05-105">Type</span></span>|<span data-ttu-id="ddb05-106">Dateinamenerweiterung</span><span class="sxs-lookup"><span data-stu-id="ddb05-106">File name extension</span></span>|
|----------|-------------------------|
|<span data-ttu-id="ddb05-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="ddb05-107">Bitmap</span></span>|<span data-ttu-id="ddb05-108">. bmp</span><span class="sxs-lookup"><span data-stu-id="ddb05-108">.bmp</span></span>|
|<span data-ttu-id="ddb05-109">Symbol</span><span class="sxs-lookup"><span data-stu-id="ddb05-109">Icon</span></span>|<span data-ttu-id="ddb05-110">.ico</span><span class="sxs-lookup"><span data-stu-id="ddb05-110">.ico</span></span>|
|<span data-ttu-id="ddb05-111">GIF</span><span class="sxs-lookup"><span data-stu-id="ddb05-111">GIF</span></span>|<span data-ttu-id="ddb05-112">GIF</span><span class="sxs-lookup"><span data-stu-id="ddb05-112">.gif</span></span>|
|<span data-ttu-id="ddb05-113">Metadatei</span><span class="sxs-lookup"><span data-stu-id="ddb05-113">Metafile</span></span>|<span data-ttu-id="ddb05-114">. WMF</span><span class="sxs-lookup"><span data-stu-id="ddb05-114">.wmf</span></span>|
|<span data-ttu-id="ddb05-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="ddb05-115">JPEG</span></span>|<span data-ttu-id="ddb05-116">JPG</span><span class="sxs-lookup"><span data-stu-id="ddb05-116">.jpg</span></span>|

> [!NOTE]
>  <span data-ttu-id="ddb05-117">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="ddb05-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ddb05-118">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ddb05-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ddb05-119">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="ddb05-119">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="ddb05-120">So zeigen Sie ein Bild zur Entwurfszeit an</span><span class="sxs-lookup"><span data-stu-id="ddb05-120">To display a picture at design time</span></span>

1. <span data-ttu-id="ddb05-121">Zeichnen Sie <xref:System.Windows.Forms.PictureBox> ein-Steuerelement in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="ddb05-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="ddb05-122">Wählen Sie auf der Eigenschaftenfenster die <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft aus, und klicken Sie auf die Schaltfläche mit den Auslassungs Punkten, um das Dialogfeld **Öffnen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ddb05-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="ddb05-123">Wenn Sie nach einem bestimmten Dateityp suchen (z. b. GIF-Dateien), wählen Sie ihn im Feld **Dateityp aus** .</span><span class="sxs-lookup"><span data-stu-id="ddb05-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="ddb05-124">Wählen Sie die Datei aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="ddb05-124">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="ddb05-125">So löschen Sie das Bild zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="ddb05-125">To clear the picture at design time</span></span>

1. <span data-ttu-id="ddb05-126">Wählen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft aus, und klicken Sie mit der rechten Maustaste auf das kleine Miniaturbild, das links neben dem Namen des Bildobjekts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ddb05-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="ddb05-127">Wählen Sie **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="ddb05-127">Choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddb05-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddb05-128">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="ddb05-129">Übersicht über das PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ddb05-129">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="ddb05-130">Vorgehensweise: Ändern der Größe oder Platzierung eines Bilds zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ddb05-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="ddb05-131">Vorgehensweise: Festlegen von Bildern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ddb05-131">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="ddb05-132">PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ddb05-132">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
