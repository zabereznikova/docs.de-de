---
title: 'Vorgehensweise: Hinzufügen oder Entfernen von ImageList-Bildern mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: be17d5e6a12824c1c9edc867c99e77a6a1437a36
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658584"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="4500d-102">Vorgehensweise: Hinzufügen oder Entfernen von ImageList-Bildern mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="4500d-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="4500d-103">Sie können einer <xref:System.Windows.Forms.ImageList> -Komponente auf verschiedene Weise Bilder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4500d-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="4500d-104">Sie können Bilder sehr schnell mithilfe des Smarttags hinzufügen <xref:System.Windows.Forms.ImageList>, das zugeordnet ist, oder wenn Sie mehrere andere Eigenschaften <xref:System.Windows.Forms.ImageList>im festlegen, ist es möglicherweise bequemer, Bilder mit dem Eigenschaftenfenster hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4500d-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="4500d-105">Mithilfe von Code können Sie auch Bilder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4500d-105">You can also add images by using code.</span></span> <span data-ttu-id="4500d-106">Weitere Informationen zum Hinzufügen von Bildern mit Code finden [Sie unter Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="4500d-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="4500d-107">In der Regel füllen Sie <xref:System.Windows.Forms.ImageList> die Komponente mit Bildern auf, bevor Sie einem-Steuerelement zugeordnet wird, dies ist jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4500d-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="4500d-108">So können Sie Images mithilfe der Eigenschaftenfenster hinzufügen oder entfernen</span><span class="sxs-lookup"><span data-stu-id="4500d-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="4500d-109">Wählen Sie <xref:System.Windows.Forms.ImageList> die Komponente aus, oder fügen Sie eine dem Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="4500d-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="4500d-110">Klicken Sie im Eigenschaftenfenster auf die Schaltfläche mit den![Auslassungs Punkten (die Schaltfläche mit den Auslassungs Punkten (...](./media/visual-studio-ellipsis-button.png)) in der Eigenschaftenfenster <xref:System.Windows.Forms.ImageList.Images%2A> von Visual Studio.) neben der-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4500d-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="4500d-111">Klicken Sie im Bildauflistungs- **Editor**auf **Hinzufügen** oder **Entfernen** , um Bilder in der Liste hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="4500d-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="4500d-112">So können Sie Images mithilfe des Smarttags hinzufügen oder entfernen</span><span class="sxs-lookup"><span data-stu-id="4500d-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="4500d-113">Wählen Sie <xref:System.Windows.Forms.ImageList> die Komponente aus, oder fügen Sie eine dem Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="4500d-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="4500d-114">Klicken Sie auf das Smarttagsymbol (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")).</span><span class="sxs-lookup"><span data-stu-id="4500d-114">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>

3. <span data-ttu-id="4500d-115">Wählen Sie im Dialogfeld **ImageList-Aufgaben** die Option **Bilder auswählen**aus.</span><span class="sxs-lookup"><span data-stu-id="4500d-115">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="4500d-116">Klicken Sie im Bild Auflistungs- **Editor** auf **Hinzufügen** oder **Entfernen** , um Bilder in der Liste hinzuzufügen oder zu entfernen</span><span class="sxs-lookup"><span data-stu-id="4500d-116">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="4500d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4500d-117">See also</span></span>

- [<span data-ttu-id="4500d-118">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="4500d-118">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="4500d-119">Exemplarische Vorgehensweise: Ausführen allgemeiner Aufgaben mit Smarttags auf Windows Forms Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="4500d-119">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="4500d-120">ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="4500d-120">ImageList Component</span></span>](imagelist-component-windows-forms.md)
