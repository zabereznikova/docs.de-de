---
title: "Gewusst wie: Hinzufügen oder Entfernen von ImageList-Bildern mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71fa29fc36292bb6620ab458785abaabc749c38d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="d0ec0-102">Gewusst wie: Hinzufügen oder Entfernen von ImageList-Bildern mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="d0ec0-102">How to: Add or Remove ImageList Images with the Designer</span></span>
<span data-ttu-id="d0ec0-103">Sie können Bilder, Hinzufügen einer <xref:System.Windows.Forms.ImageList> Komponente auf verschiedene Weise.</span><span class="sxs-lookup"><span data-stu-id="d0ec0-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="d0ec0-104">Sie können Bilder sehr schnell hinzufügen, indem mithilfe des Smarttags zugeordnet der <xref:System.Windows.Forms.ImageList>, oder wenn Sie mehrere andere Eigenschaften festlegen der <xref:System.Windows.Forms.ImageList>, Sie könnten praktischerweise mehr Hinzufügen von Bildern mit dem Eigenschaftenfenster.</span><span class="sxs-lookup"><span data-stu-id="d0ec0-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="d0ec0-105">Sie können auch Bilder hinzufügen, mithilfe von Code.</span><span class="sxs-lookup"><span data-stu-id="d0ec0-105">You can also add images by using code.</span></span> <span data-ttu-id="d0ec0-106">Weitere Informationen zum Hinzufügen von Bildern mit Code finden Sie unter [wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="d0ec0-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="d0ec0-107">Füllen Sie in der Regel die <xref:System.Windows.Forms.ImageList> -Komponente mit Bildern, bevor Sie mit einem Steuerelement verknüpft ist, aber dies ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d0ec0-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0ec0-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="d0ec0-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d0ec0-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d0ec0-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d0ec0-110">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="d0ec0-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="d0ec0-111">Zum Hinzufügen oder Entfernen von Bildern über das Fenster "Eigenschaften"</span><span class="sxs-lookup"><span data-stu-id="d0ec0-111">To add or remove images by using the Properties window</span></span>  
  
1.  <span data-ttu-id="d0ec0-112">Wählen Sie die <xref:System.Windows.Forms.ImageList> -Komponente, oder fügen Sie dem Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="d0ec0-112">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="d0ec0-113">Klicken Sie im Fenster Eigenschaften auf die Schaltfläche mit den Auslassungspunkten (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.ImageList.Images%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d0ec0-113">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
3.  <span data-ttu-id="d0ec0-114">In der **Auflistung Bildbearbeitung**, klicken Sie auf **hinzufügen** oder **entfernen** zum Hinzufügen oder Entfernen von Bildern aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="d0ec0-114">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="d0ec0-115">Hinzufügen oder Entfernen von Bildern mithilfe des Smarttags</span><span class="sxs-lookup"><span data-stu-id="d0ec0-115">To add or remove images using the smart tag</span></span>  
  
1.  <span data-ttu-id="d0ec0-116">Wählen Sie die <xref:System.Windows.Forms.ImageList> -Komponente, oder fügen Sie dem Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="d0ec0-116">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="d0ec0-117">Klicken Sie auf das Smarttag-Symbol (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="d0ec0-117">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>  
  
3.  <span data-ttu-id="d0ec0-118">In der **ImageList Aufgaben** wählen Sie im Dialogfeld **Bilder auswählen**.</span><span class="sxs-lookup"><span data-stu-id="d0ec0-118">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>  
  
4.  <span data-ttu-id="d0ec0-119">In der **Auflistungs-Editor für Bilder** klicken Sie auf **hinzufügen** oder **entfernen** zum Hinzufügen oder Entfernen von Bildern aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="d0ec0-119">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ec0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0ec0-120">See Also</span></span>  
 [<span data-ttu-id="d0ec0-121">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="d0ec0-121">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="d0ec0-122">Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags auf Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="d0ec0-122">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 [<span data-ttu-id="d0ec0-123">ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="d0ec0-123">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
