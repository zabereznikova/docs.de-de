---
title: 'Vorgehensweise: Erstellen einer Oberfläche im Stil von Windows Explorer in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 34a5cd735c350688d9e83003806668e213932c85
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960626"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="887f6-102">Vorgehensweise: Erstellen einer Oberfläche im Stil von Windows Explorer in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="887f6-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="887f6-103">Windows Explorer ist eine gängige Benutzeroberfläche für Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="887f6-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>

 <span data-ttu-id="887f6-104">Windows-Explorer ist im Grunde genommen <xref:System.Windows.Forms.TreeView> ein Steuerelement <xref:System.Windows.Forms.ListView> und ein Steuerelement in separaten Bereichen.</span><span class="sxs-lookup"><span data-stu-id="887f6-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="887f6-105">Die Größe der Panels wird durch einen Splitter geändert.</span><span class="sxs-lookup"><span data-stu-id="887f6-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="887f6-106">Diese Anordnung von Steuerelementen ist sehr effektiv zum Anzeigen und Durchsuchen von Informationen.</span><span class="sxs-lookup"><span data-stu-id="887f6-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>

 <span data-ttu-id="887f6-107">In den folgenden Schritten wird gezeigt, wie Steuerelemente in einem Windows-Explorer-ähnlichen Formular angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="887f6-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="887f6-108">Sie zeigen nicht, wie Sie die Dateibrowser Funktionalität der Windows Explorer-Anwendung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="887f6-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>

## <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="887f6-109">So erstellen Sie ein Windows-Formular im Windows-Explorer</span><span class="sxs-lookup"><span data-stu-id="887f6-109">To create a Windows Explorer-style Windows Form</span></span>

1. <span data-ttu-id="887f6-110">Erstellen eines neuen Windows-Anwendungs Projekts (**Datei** > "**Neues** > **Projekt** > **C#** " oder **Visual Basic** > **klassischem Desktop**  >  **Windows Forms Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="887f6-110">Create a new Windows Application project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="887f6-111">Aus der **Toolbox**:</span><span class="sxs-lookup"><span data-stu-id="887f6-111">From the **Toolbox**:</span></span>

    1. <span data-ttu-id="887f6-112">Ziehen Sie <xref:System.Windows.Forms.SplitContainer> ein-Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="887f6-112">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>

    2. <span data-ttu-id="887f6-113">Ziehen Sie <xref:System.Windows.Forms.TreeView> ein-Steuerelement in **SplitterPanel1** ( <xref:System.Windows.Forms.SplitContainer> der Bereich des-Steuer Elements, das als **Panel1**gekennzeichnet ist)</span><span class="sxs-lookup"><span data-stu-id="887f6-113">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>

    3. <span data-ttu-id="887f6-114">Ziehen Sie <xref:System.Windows.Forms.ListView> ein-Steuerelement in **SplitterPanel2** ( <xref:System.Windows.Forms.SplitContainer> der Bereich des-Steuer Elements, das als **Panel2**gekennzeichnet ist)</span><span class="sxs-lookup"><span data-stu-id="887f6-114">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>

3. <span data-ttu-id="887f6-115">Wählen Sie alle drei Steuerelemente aus, indem Sie die STRG-Taste gedrückt halten und darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="887f6-115">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="887f6-116">Wenn Sie das <xref:System.Windows.Forms.SplitContainer> Steuerelement auswählen, klicken Sie auf die Splitter Leiste anstelle der Panels.</span><span class="sxs-lookup"><span data-stu-id="887f6-116">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>

    > [!NOTE]
    > <span data-ttu-id="887f6-117">Verwenden Sie nicht den Befehl **Alle auswählen** im Menü **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="887f6-117">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="887f6-118">Wenn Sie dies tun, wird die im nächsten Schritt benötigte Eigenschaft nicht im **Eigenschaften** Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="887f6-118">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>

4. <span data-ttu-id="887f6-119">Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:System.Windows.Forms.SplitContainer.Dock%2A> auf <xref:System.Windows.Forms.DockStyle.Fill>fest.</span><span class="sxs-lookup"><span data-stu-id="887f6-119">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="887f6-120">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="887f6-120">Press F5 to run the application.</span></span>

     <span data-ttu-id="887f6-121">Das Formular zeigt eine zweiteilige Benutzeroberfläche an, ähnlich der von Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="887f6-121">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="887f6-122">Wenn Sie den Splitter ziehen, ändert sich die Größe der Panels.</span><span class="sxs-lookup"><span data-stu-id="887f6-122">When you drag the splitter, the panels resize themselves.</span></span>

## <a name="see-also"></a><span data-ttu-id="887f6-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="887f6-123">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="887f6-124">Vorgehensweise: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="887f6-124">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [<span data-ttu-id="887f6-125">Vorgehensweise: Definieren des Verhaltens der Größenänderung und Positionierung in einem geteilten Fenster</span><span class="sxs-lookup"><span data-stu-id="887f6-125">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [<span data-ttu-id="887f6-126">Vorgehensweise: Fenster horizontal aufteilen</span><span class="sxs-lookup"><span data-stu-id="887f6-126">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)
- [<span data-ttu-id="887f6-127">SplitContainer-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="887f6-127">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
