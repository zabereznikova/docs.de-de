---
title: 'Gewusst wie: Hinzufügen oder Entfernen von ImageList-Bildern mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: cdc7b563a0ee4f8779b99b4e9a6786e78f8d500f
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628721"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="ee5d2-102">Gewusst wie: Hinzufügen oder Entfernen von ImageList-Bildern mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="ee5d2-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="ee5d2-103">Sie können einem <xref:System.Windows.Forms.ImageList>-Komponente auf verschiedene Weise Bilder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ee5d2-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="ee5d2-104">Sie können Images sehr schnell hinzufügen, indem Sie das Smarttags verwenden, das dem <xref:System.Windows.Forms.ImageList>zugeordnet ist, oder wenn Sie mehrere andere Eigenschaften auf der <xref:System.Windows.Forms.ImageList>festlegen, ist es möglicherweise bequemer, Bilder mit dem Eigenschaftenfenster hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ee5d2-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="ee5d2-105">Mithilfe von Code können Sie auch Bilder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ee5d2-105">You can also add images by using code.</span></span> <span data-ttu-id="ee5d2-106">Weitere Informationen zum Hinzufügen von Bildern mit Code finden Sie unter Gewusst [wie: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="ee5d2-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="ee5d2-107">In der Regel füllen Sie die <xref:System.Windows.Forms.ImageList> Komponente mit Bildern auf, bevor Sie einem-Steuerelement zugeordnet wird, dies ist jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ee5d2-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="ee5d2-108">So können Sie Images mithilfe der Eigenschaftenfenster hinzufügen oder entfernen</span><span class="sxs-lookup"><span data-stu-id="ee5d2-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="ee5d2-109">Wählen Sie die <xref:System.Windows.Forms.ImageList> Komponente aus, oder fügen Sie eine dem Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="ee5d2-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="ee5d2-110">Klicken Sie im Eigenschaftenfenster auf die Schaltfläche mit den Auslassungs Punkten (![der Schaltfläche mit den Auslassungs Punkten (...) im Eigenschaftenfenster von Visual Studio.](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.ImageList.Images%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ee5d2-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="ee5d2-111">Klicken Sie im Bildauflistungs- **Editor**auf **Hinzufügen** oder **Entfernen** , um Bilder in der Liste hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="ee5d2-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="ee5d2-112">So können Sie Images mithilfe des Smarttags hinzufügen oder entfernen</span><span class="sxs-lookup"><span data-stu-id="ee5d2-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="ee5d2-113">Wählen Sie die <xref:System.Windows.Forms.ImageList> Komponente aus, oder fügen Sie eine dem Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="ee5d2-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="ee5d2-114">Klicken Sie auf das Symbol Designer Aktionen (</span><span class="sxs-lookup"><span data-stu-id="ee5d2-114">Click the designer actions glyph (</span></span>![Kleiner schwarzer Pfeil](./media/designer-actions-glyph.gif)<span data-ttu-id="ee5d2-116">)</span><span class="sxs-lookup"><span data-stu-id="ee5d2-116">)</span></span>

3. <span data-ttu-id="ee5d2-117">Wählen Sie im Dialogfeld **ImageList-Aufgaben** die Option **Bilder auswählen**aus.</span><span class="sxs-lookup"><span data-stu-id="ee5d2-117">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="ee5d2-118">Klicken Sie im Bild Auflistungs- **Editor** auf **Hinzufügen** oder **Entfernen** , um Bilder in der Liste hinzuzufügen oder zu entfernen</span><span class="sxs-lookup"><span data-stu-id="ee5d2-118">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee5d2-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee5d2-119">See also</span></span>

- [<span data-ttu-id="ee5d2-120">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="ee5d2-120">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="ee5d2-121">Exemplarische Vorgehensweise: Ausführen allgemeiner Aufgaben mithilfe von Designer Aktionen</span><span class="sxs-lookup"><span data-stu-id="ee5d2-121">Walkthrough: Perform common tasks using designer actions</span></span>](perform-common-tasks-design-actions.md)
- [<span data-ttu-id="ee5d2-122">ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="ee5d2-122">ImageList Component</span></span>](imagelist-component-windows-forms.md)
