---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: d88d658b31c87e7ae89bfb4a11fe794bfbb0e848
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040098"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="5dd1b-102">Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="5dd1b-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="5dd1b-103">Das Windows Forms <xref:System.Windows.Forms.DataGridView> Steuerelement muss Spalten enthalten, um Daten anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="5dd1b-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="5dd1b-104">Wenn Sie das Steuerelement manuell auffüllen möchten, müssen Sie die Spalten selbst hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5dd1b-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="5dd1b-105">Alternativ können Sie das Steuerelement an eine Datenquelle binden, die die Spalten automatisch generiert und auffüllt.</span><span class="sxs-lookup"><span data-stu-id="5dd1b-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="5dd1b-106">Wenn die Datenquelle mehr Spalten enthält, als Sie anzeigen möchten, können Sie die unerwünschten Spalten entfernen.</span><span class="sxs-lookup"><span data-stu-id="5dd1b-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>

 <span data-ttu-id="5dd1b-107">Die folgenden Prozeduren erfordern ein **Windows-Anwendungs** Projekt mit einem <xref:System.Windows.Forms.DataGridView> Formular, das ein-Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="5dd1b-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="5dd1b-108">Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="5dd1b-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="5dd1b-109">So fügen Sie eine Spalte mithilfe des Designers hinzu</span><span class="sxs-lookup"><span data-stu-id="5dd1b-109">To add a column using the designer</span></span>

1. <span data-ttu-id="5dd1b-110">Klicken Sie <xref:System.Windows.Forms.DataGridView> in der oberen rechten Ecke des Steuer Elements auf das Smarttagsymbol (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie dann **Spalte hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="5dd1b-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>

2. <span data-ttu-id="5dd1b-111">Wählen Sie im Dialogfeld **Spalte hinzufügen** die Option **Daten gebundene Spalte** aus, und wählen Sie eine Spalte aus der Datenquelle aus, oder wählen Sie die Option **ungebundene Spalte** aus, und definieren Sie die Spalte mithilfe der angegebenen Felder.</span><span class="sxs-lookup"><span data-stu-id="5dd1b-111">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>

3. <span data-ttu-id="5dd1b-112">Klicken Sie auf die Schaltfläche **Hinzufügen** , um die Spalte hinzuzufügen. Dies bewirkt, dass Sie im Designer angezeigt wird, wenn die vorhandenen Spalten den Anzeigebereich des Steuer Elements nicht bereits ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="5dd1b-112">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="5dd1b-113">Sie können Spalten Eigenschaften im Dialogfeld **Spalten bearbeiten** ändern, auf das Sie über das Smarttag des Steuer Elements zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="5dd1b-113">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>

## <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="5dd1b-114">So entfernen Sie eine Spalte mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="5dd1b-114">To remove a column using the designer</span></span>

1. <span data-ttu-id="5dd1b-115">Wählen Sie Spalten aus dem Smarttag des-Steuer Elements **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd1b-115">Choose **Edit Columns** from the control's smart tag.</span></span>

2. <span data-ttu-id="5dd1b-116">Wählen Sie in der Liste **Ausgewählte Spalten** eine Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="5dd1b-116">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="5dd1b-117">Klicken Sie auf die Schaltfläche **Entfernen** , um die Spalte zu löschen, sodass Sie nicht mehr im Designer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5dd1b-117">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="5dd1b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dd1b-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="5dd1b-119">Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts</span><span class="sxs-lookup"><span data-stu-id="5dd1b-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="5dd1b-120">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5dd1b-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
