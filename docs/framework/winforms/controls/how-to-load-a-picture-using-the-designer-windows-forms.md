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
ms.openlocfilehash: 818bc63b5b3bea6c73804f716a72ba3cd1a62b4c
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039680"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="17c56-102">Vorgehensweise: Laden eines Bilds mithilfe des Designers (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="17c56-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="17c56-103">Mit dem Windows Forms <xref:System.Windows.Forms.PictureBox> -Steuerelement können Sie ein Bild auf einem Formular zur Entwurfszeit laden und anzeigen, indem <xref:System.Windows.Forms.PictureBox.Image%2A> Sie die-Eigenschaft auf ein gültiges Bild festlegen.</span><span class="sxs-lookup"><span data-stu-id="17c56-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="17c56-104">In der folgenden Tabelle sind die zulässigen Dateitypen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="17c56-104">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="17c56-105">Typ</span><span class="sxs-lookup"><span data-stu-id="17c56-105">Type</span></span>|<span data-ttu-id="17c56-106">Dateinamenerweiterung</span><span class="sxs-lookup"><span data-stu-id="17c56-106">File name extension</span></span>|
|---|---|
|<span data-ttu-id="17c56-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="17c56-107">Bitmap</span></span>|<span data-ttu-id="17c56-108">. bmp</span><span class="sxs-lookup"><span data-stu-id="17c56-108">.bmp</span></span>|
|<span data-ttu-id="17c56-109">Symbol</span><span class="sxs-lookup"><span data-stu-id="17c56-109">Icon</span></span>|<span data-ttu-id="17c56-110">.ico</span><span class="sxs-lookup"><span data-stu-id="17c56-110">.ico</span></span>|
|<span data-ttu-id="17c56-111">GIF</span><span class="sxs-lookup"><span data-stu-id="17c56-111">GIF</span></span>|<span data-ttu-id="17c56-112">GIF</span><span class="sxs-lookup"><span data-stu-id="17c56-112">.gif</span></span>|
|<span data-ttu-id="17c56-113">Metadatei</span><span class="sxs-lookup"><span data-stu-id="17c56-113">Metafile</span></span>|<span data-ttu-id="17c56-114">. WMF</span><span class="sxs-lookup"><span data-stu-id="17c56-114">.wmf</span></span>|
|<span data-ttu-id="17c56-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="17c56-115">JPEG</span></span>|<span data-ttu-id="17c56-116">JPG</span><span class="sxs-lookup"><span data-stu-id="17c56-116">.jpg</span></span>|

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="17c56-117">So zeigen Sie ein Bild zur Entwurfszeit an</span><span class="sxs-lookup"><span data-stu-id="17c56-117">To display a picture at design time</span></span>

1. <span data-ttu-id="17c56-118">Zeichnen Sie <xref:System.Windows.Forms.PictureBox> ein-Steuerelement in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="17c56-118">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="17c56-119">Wählen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft aus, und klicken Sie dann auf die Schaltfläche mit den Auslassungs Punkten, um das Dialogfeld **Öffnen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="17c56-119">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then select the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="17c56-120">Wenn Sie nach einem bestimmten Dateityp suchen (z. b. GIF-Dateien), wählen Sie ihn im Feld **Dateityp aus** .</span><span class="sxs-lookup"><span data-stu-id="17c56-120">If you're looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="17c56-121">Wählen Sie die Datei aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="17c56-121">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="17c56-122">So löschen Sie das Bild zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="17c56-122">To clear the picture at design time</span></span>

1. <span data-ttu-id="17c56-123">Wählen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.PictureBox.Image%2A> -Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="17c56-123">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property.</span></span> <span data-ttu-id="17c56-124">Klicken Sie mit der rechten Maustaste auf das kleine Miniaturbild, das links neben dem Namen des Bildobjekts angezeigt wird, und wählen Sie dann **Zurücksetzen**aus.</span><span class="sxs-lookup"><span data-stu-id="17c56-124">Right-click the small thumbnail image that appears to the left of the name of the image object, and then choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="17c56-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17c56-125">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="17c56-126">Übersicht über das PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="17c56-126">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="17c56-127">Vorgehensweise: Ändern der Größe oder Platzierung eines Bilds zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="17c56-127">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="17c56-128">Vorgehensweise: Festlegen von Bildern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="17c56-128">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="17c56-129">PictureBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="17c56-129">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
