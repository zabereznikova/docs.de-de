---
title: "Gewusst wie: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b314fe58413c0a284f5ebb41642e8c8dd1fb02b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="4ed01-102">Gewusst wie: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="4ed01-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="4ed01-103">Windows Forms <xref:System.Windows.Forms.DataGridView> Steuerelement muss Spalten enthalten, um Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4ed01-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="4ed01-104">Wenn das Steuerelement manuell gefüllt werden sollen, müssen Sie die Spalten selbst hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4ed01-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="4ed01-105">Klicken Sie Alternativ können Sie das Steuerelement an eine Datenquelle binden, die generiert und füllt die Spalten automatisch.</span><span class="sxs-lookup"><span data-stu-id="4ed01-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="4ed01-106">Wenn die Datenquelle mehr Spalten enthält als angezeigt werden soll, können Sie die benötigte Spalten entfernen.</span><span class="sxs-lookup"><span data-stu-id="4ed01-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>  
  
 <span data-ttu-id="4ed01-107">Erfordern die folgenden Verfahren eine **Windows-Anwendung** Projekt ein Formular mit einem <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4ed01-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4ed01-108">Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4ed01-108">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ed01-109">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="4ed01-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4ed01-110">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4ed01-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4ed01-111">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="4ed01-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="4ed01-112">Zum Hinzufügen einer Spalte mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="4ed01-112">To add a column using the designer</span></span>  
  
1.  <span data-ttu-id="4ed01-113">Klicken Sie auf das Smarttag-Symbol (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) in der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> steuern, und wählen Sie dann **Add Column**.</span><span class="sxs-lookup"><span data-stu-id="4ed01-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>  
  
2.  <span data-ttu-id="4ed01-114">In der **Add Column** Dialogfeld Wählen Sie die **datengebundene Spalte** aus, und wählen Sie eine Spalte aus der Datenquelle, oder wählen Sie die **ungebundenen Spalte** aus, und definieren Sie die Spalte verwenden die angezeigten Felder ein.</span><span class="sxs-lookup"><span data-stu-id="4ed01-114">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>  
  
3.  <span data-ttu-id="4ed01-115">Klicken Sie auf die **hinzufügen** Schaltfläche zum Hinzufügen der Spalte, die wegen der er im Designer angezeigt wird, wenn die vorhandenen Spalten den Anzeigebereich des Steuerelements nicht bereits aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="4ed01-115">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4ed01-116">Sie können Spalteneigenschaften im Ändern der **Spalten bearbeiten** (Dialogfeld), die Sie aus dem Smarttag des Steuerelements zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="4ed01-116">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>  
  
### <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="4ed01-117">So entfernen Sie eine Spalte mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="4ed01-117">To remove a column using the designer</span></span>  
  
1.  <span data-ttu-id="4ed01-118">Wählen Sie **Spalten bearbeiten** aus dem Smarttag des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="4ed01-118">Choose **Edit Columns** from the control's smart tag.</span></span>  
  
2.  <span data-ttu-id="4ed01-119">Wählen Sie eine Spalte aus der **ausgewählte Spalten** Liste.</span><span class="sxs-lookup"><span data-stu-id="4ed01-119">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="4ed01-120">Klicken Sie auf die **entfernen** Schaltfläche beim Löschen der Spalte, die wegen der er vom Designer nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ed01-120">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ed01-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ed01-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="4ed01-122">Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts</span><span class="sxs-lookup"><span data-stu-id="4ed01-122">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="4ed01-123">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ed01-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
