---
title: 'Vorgehensweise: Laden eines Bilds mithilfe des Designers'
description: Erfahren Sie, wie Sie das Windows Forms PictureBox-Steuerelement verwenden, um ein Bild zur Entwurfszeit auf einem Formular zu laden und anzuzeigen.
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: a05ffe19412fc7a4e3e02f01336d89cce39fac8a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325600"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="10c69-103">Gewusst wie: Laden eines Bilds mithilfe des Designers (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="10c69-103">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="10c69-104">Mit dem Windows Forms <xref:System.Windows.Forms.PictureBox> -Steuerelement können Sie ein Bild auf einem Formular zur Entwurfszeit laden und anzeigen, indem Sie die- <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft auf ein gültiges Bild festlegen.</span><span class="sxs-lookup"><span data-stu-id="10c69-104">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="10c69-105">In der folgenden Tabelle sind die zulässigen Dateitypen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="10c69-105">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="10c69-106">Type</span><span class="sxs-lookup"><span data-stu-id="10c69-106">Type</span></span>|<span data-ttu-id="10c69-107">Dateinamenerweiterung</span><span class="sxs-lookup"><span data-stu-id="10c69-107">File name extension</span></span>|
|---|---|
|<span data-ttu-id="10c69-108">Bitmap</span><span class="sxs-lookup"><span data-stu-id="10c69-108">Bitmap</span></span>|<span data-ttu-id="10c69-109">BMP</span><span class="sxs-lookup"><span data-stu-id="10c69-109">.bmp</span></span>|
|<span data-ttu-id="10c69-110">Symbol</span><span class="sxs-lookup"><span data-stu-id="10c69-110">Icon</span></span>|<span data-ttu-id="10c69-111">.ico</span><span class="sxs-lookup"><span data-stu-id="10c69-111">.ico</span></span>|
|<span data-ttu-id="10c69-112">GIF</span><span class="sxs-lookup"><span data-stu-id="10c69-112">GIF</span></span>|<span data-ttu-id="10c69-113">.gif</span><span class="sxs-lookup"><span data-stu-id="10c69-113">.gif</span></span>|
|<span data-ttu-id="10c69-114">Metadatei</span><span class="sxs-lookup"><span data-stu-id="10c69-114">Metafile</span></span>|<span data-ttu-id="10c69-115">. WMF</span><span class="sxs-lookup"><span data-stu-id="10c69-115">.wmf</span></span>|
|<span data-ttu-id="10c69-116">JPEG</span><span class="sxs-lookup"><span data-stu-id="10c69-116">JPEG</span></span>|<span data-ttu-id="10c69-117">.jpg</span><span class="sxs-lookup"><span data-stu-id="10c69-117">.jpg</span></span>|

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="10c69-118">So zeigen Sie ein Bild zur Entwurfszeit an</span><span class="sxs-lookup"><span data-stu-id="10c69-118">To display a picture at design time</span></span>

1. <span data-ttu-id="10c69-119">Zeichnen Sie ein- <xref:System.Windows.Forms.PictureBox> Steuerelement in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="10c69-119">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="10c69-120">Wählen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft aus, und klicken Sie dann auf die Schaltfläche mit den Auslassungs Punkten, um das Dialogfeld **Öffnen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="10c69-120">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then select the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="10c69-121">Wenn Sie nach einem bestimmten Dateityp suchen (z. b. GIF-Dateien), wählen Sie ihn im Feld **Dateityp aus** .</span><span class="sxs-lookup"><span data-stu-id="10c69-121">If you're looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="10c69-122">Wählen Sie die Datei aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="10c69-122">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="10c69-123">So löschen Sie das Bild zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="10c69-123">To clear the picture at design time</span></span>

1. <span data-ttu-id="10c69-124">Wählen Sie im Fenster **Eigenschaften** die- <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="10c69-124">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property.</span></span> <span data-ttu-id="10c69-125">Klicken Sie mit der rechten Maustaste auf das kleine Miniaturbild, das links neben dem Namen des Bildobjekts angezeigt wird, und wählen Sie dann **Zurücksetzen**aus.</span><span class="sxs-lookup"><span data-stu-id="10c69-125">Right-click the small thumbnail image that appears to the left of the name of the image object, and then choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="10c69-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10c69-126">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="10c69-127">Übersicht über das PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="10c69-127">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="10c69-128">Vorgehensweise: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="10c69-128">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="10c69-129">Vorgehensweise: Festlegen von Bildern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="10c69-129">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="10c69-130">PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="10c69-130">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
