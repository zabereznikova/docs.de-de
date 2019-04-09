---
title: 'Vorgehensweise: Erstellen einer Oberfläche im Stil von Windows Explorer in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: e559702d5fd7f0f56c7b2b010713e3129504746a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192133"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="2ac92-102">Vorgehensweise: Erstellen einer Oberfläche im Stil von Windows Explorer in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ac92-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="2ac92-103">Windows-Explorer ist eine gemeinsame Benutzeroberfläche Wahl für Anwendungen aufgrund seiner Kenntnisse bereit.</span><span class="sxs-lookup"><span data-stu-id="2ac92-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>  
  
 <span data-ttu-id="2ac92-104">Windows-Explorer ist im Wesentlichen eine <xref:System.Windows.Forms.TreeView> Steuerelement und ein <xref:System.Windows.Forms.ListView> Steuerelement auf separate Bereiche.</span><span class="sxs-lookup"><span data-stu-id="2ac92-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="2ac92-105">Die Bereiche werden durch eine Aufteilung in der Größe veränderbaren vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="2ac92-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="2ac92-106">Diese Anordnung von Steuerelementen ist sehr gut für anzeigen und Durchsuchen von Informationen.</span><span class="sxs-lookup"><span data-stu-id="2ac92-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>  
  
 <span data-ttu-id="2ac92-107">Die folgenden Schritte zeigen, wie Steuerelemente in einem Windows-Explorer-ähnlichen Format angeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="2ac92-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="2ac92-108">Sie sind nicht zum Hinzufügen der Funktion zum Durchsuchen von Datei, der die Windows-Explorer-Anwendung erläutert.</span><span class="sxs-lookup"><span data-stu-id="2ac92-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ac92-109">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="2ac92-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2ac92-110">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2ac92-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2ac92-111">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="2ac92-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="2ac92-112">Um ein Windows-Formular in Windows Explorer-Stil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ac92-112">To create a Windows Explorer-style Windows Form</span></span>  
  
1.  <span data-ttu-id="2ac92-113">Erstellen Sie ein neues Windows-Anwendungsprojekt (**Datei** > **neu** > **Projekt** > **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="2ac92-113">Create a new Windows Application project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="2ac92-114">Von der **Toolbox**:</span><span class="sxs-lookup"><span data-stu-id="2ac92-114">From the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="2ac92-115">Ziehen Sie eine <xref:System.Windows.Forms.SplitContainer> Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="2ac92-115">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>  
  
    2.  <span data-ttu-id="2ac92-116">Ziehen Sie eine <xref:System.Windows.Forms.TreeView> steuern in **SplitterPanel1** (der Bereich von der <xref:System.Windows.Forms.SplitContainer> Steuerelemente **Panel1**).</span><span class="sxs-lookup"><span data-stu-id="2ac92-116">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>  
  
    3.  <span data-ttu-id="2ac92-117">Ziehen Sie eine <xref:System.Windows.Forms.ListView> steuern in **SplitterPanel2** (der Bereich von der <xref:System.Windows.Forms.SplitContainer> Steuerelemente **Panel2**).</span><span class="sxs-lookup"><span data-stu-id="2ac92-117">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>  
  
3.  <span data-ttu-id="2ac92-118">Wählen Sie alle drei Steuerelemente, indem Sie die STRG-Taste drücken, und klicken sie dann auf.</span><span class="sxs-lookup"><span data-stu-id="2ac92-118">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="2ac92-119">Bei der Auswahl der <xref:System.Windows.Forms.SplitContainer> Steuerelement, klicken Sie auf die Teilerleiste, anstatt die Bereiche.</span><span class="sxs-lookup"><span data-stu-id="2ac92-119">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2ac92-120">Verwenden Sie nicht die **Alles markieren** Befehl die **bearbeiten** Menü.</span><span class="sxs-lookup"><span data-stu-id="2ac92-120">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="2ac92-121">Wenn Sie dies tun, die Eigenschaft, die in den nächsten Schritt erforderlich sind, erscheinen nicht im der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="2ac92-121">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>  
  
4.  <span data-ttu-id="2ac92-122">Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:System.Windows.Forms.SplitContainer.Dock%2A> auf <xref:System.Windows.Forms.DockStyle.Fill>fest.</span><span class="sxs-lookup"><span data-stu-id="2ac92-122">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5.  <span data-ttu-id="2ac92-123">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2ac92-123">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="2ac92-124">Das Formular zeigt eine mit dem zweiteiligen Benutzeroberfläche ähnelt der von der Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="2ac92-124">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2ac92-125">Wenn Sie den Splitter ziehen, Größe der Panels selbst.</span><span class="sxs-lookup"><span data-stu-id="2ac92-125">When you drag the splitter, the panels resize themselves.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac92-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ac92-126">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="2ac92-127">Vorgehensweise: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ac92-127">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [<span data-ttu-id="2ac92-128">Vorgehensweise: Definieren des Verhaltens bei Größen- und Positionsänderungen in einem geteilten Fenster</span><span class="sxs-lookup"><span data-stu-id="2ac92-128">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [<span data-ttu-id="2ac92-129">Vorgehensweise: Horizontales Teilen eines Fensters</span><span class="sxs-lookup"><span data-stu-id="2ac92-129">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)
- [<span data-ttu-id="2ac92-130">SplitContainer-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2ac92-130">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
