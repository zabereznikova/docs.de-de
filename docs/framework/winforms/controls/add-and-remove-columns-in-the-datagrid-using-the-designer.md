---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 80ede9b7bc5bf667e03dc0a745fbc0b5f6c2663a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343284"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="f4efe-102">Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="f4efe-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="f4efe-103">Die Windows-Formulare <xref:System.Windows.Forms.DataGridView> Steuerelement muss Spalten enthalten, um Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f4efe-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="f4efe-104">Wenn Sie das Steuerelement manuell auffüllen möchten, müssen Sie die Spalten selbst hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f4efe-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="f4efe-105">Alternativ können Sie das Steuerelement an eine Datenquelle binden generiert und füllt die Spalten automatisch.</span><span class="sxs-lookup"><span data-stu-id="f4efe-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="f4efe-106">Wenn die Datenquelle mehr Spalten enthält als angezeigt werden soll, können Sie die gewünschten Spalten entfernen.</span><span class="sxs-lookup"><span data-stu-id="f4efe-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>  
  
 <span data-ttu-id="f4efe-107">Benötigen Sie die folgenden Verfahren eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f4efe-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f4efe-108">Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f4efe-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4efe-109">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="f4efe-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f4efe-110">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f4efe-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f4efe-111">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f4efe-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="f4efe-112">Hinzufügen eine Spalte mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="f4efe-112">To add a column using the designer</span></span>  
  
1. <span data-ttu-id="f4efe-113">Klicken Sie auf die Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) auf der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> steuern, und wählen Sie dann **Add Column**.</span><span class="sxs-lookup"><span data-stu-id="f4efe-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>  
  
2. <span data-ttu-id="f4efe-114">In der **Spalte hinzufügen** Dialogfeld auf die **datengebundene Spalte** option aus, und wählen Sie eine Spalte aus der Datenquelle, oder wählen die **ungebundenen Spalte** aus, und definieren Sie die Spalte verwenden die angezeigten Felder ein.</span><span class="sxs-lookup"><span data-stu-id="f4efe-114">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>  
  
3. <span data-ttu-id="f4efe-115">Klicken Sie auf die **hinzufügen** , um die Spalte im Designer angezeigt werden, wenn die vorhandenen Spalten den Anzeigebereich des Steuerelements nicht bereits ausfüllen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f4efe-115">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f4efe-116">Sie können Spalteneigenschaften im Ändern der **Spalten bearbeiten** Dialogfeld, das Sie von smart Tag des Steuerelements zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="f4efe-116">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>  
  
### <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="f4efe-117">So entfernen Sie eine Spalte, die mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="f4efe-117">To remove a column using the designer</span></span>  
  
1. <span data-ttu-id="f4efe-118">Wählen Sie **Spalten bearbeiten** von smart Tag des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="f4efe-118">Choose **Edit Columns** from the control's smart tag.</span></span>  
  
2. <span data-ttu-id="f4efe-119">Wählen Sie eine Spalte aus der **Selected Columns** Liste.</span><span class="sxs-lookup"><span data-stu-id="f4efe-119">Select a column from the **Selected Columns** list.</span></span>  
  
3. <span data-ttu-id="f4efe-120">Klicken Sie auf die **entfernen** Schaltfläche, um die Spalte, und vom Designer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f4efe-120">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4efe-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4efe-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="f4efe-122">Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts</span><span class="sxs-lookup"><span data-stu-id="f4efe-122">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="f4efe-123">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4efe-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
