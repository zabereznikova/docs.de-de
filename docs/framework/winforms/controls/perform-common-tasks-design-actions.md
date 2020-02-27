---
title: Ausführen allgemeiner Aufgaben mithilfe von Designer Aktionen für Steuerelemente
ms.date: 02/13/2019
helpviewer_keywords:
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 342741b9ce032b1b8ec50a6c689d9109d12f5b3b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77634894"
---
# <a name="walkthrough-perform-common-tasks-using-designer-actions"></a><span data-ttu-id="6a8b8-102">Exemplarische Vorgehensweise: Ausführen allgemeiner Aufgaben mithilfe von Designer Aktionen</span><span class="sxs-lookup"><span data-stu-id="6a8b8-102">Walkthrough: Perform common tasks using designer actions</span></span>

<span data-ttu-id="6a8b8-103">Wenn Sie Formulare und Steuerelemente für Ihre Windows Forms-Anwendung erstellen, gibt es viele Aufgaben, die Sie wiederholt ausführen.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-103">As you construct forms and controls for your Windows Forms application, there are many tasks you'll perform repeatedly.</span></span> <span data-ttu-id="6a8b8-104">In der folgenden Liste sind einige der häufig ausgeführten Aufgaben aufgeführt, die Sie durchführen werden:</span><span class="sxs-lookup"><span data-stu-id="6a8b8-104">The following list shows some of the commonly performed tasks you'll come across:</span></span>

- <span data-ttu-id="6a8b8-105">Hinzufügen oder Entfernen einer Registerkarte auf einem <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>
- <span data-ttu-id="6a8b8-106">Andocken eines Steuer Elements an das übergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-106">Docking a control to its parent.</span></span>
- <span data-ttu-id="6a8b8-107">Ändern der Ausrichtung eines <xref:System.Windows.Forms.SplitContainer> Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="6a8b8-108">Um die Entwicklung zu beschleunigen, bieten viele Steuerelemente Designer Aktionen, bei denen es sich um Kontextbezogene Menüs handelt, mit denen Sie häufige Aufgaben wie diese in einer einzigen Geste zur Entwurfszeit ausführen können.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-108">To speed development, many controls offer designer actions, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="6a8b8-109">Diese Aufgaben werden als *Designer-Aktions Verben*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-109">These tasks are called *designer actions verbs*.</span></span>

<span data-ttu-id="6a8b8-110">Designer Aktionen bleiben während ihrer Lebensdauer im Designer an eine Steuerelement Instanz angefügt und sind immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-110">Designer actions remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="6a8b8-111">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="6a8b8-111">Create the project</span></span>

<span data-ttu-id="6a8b8-112">Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="6a8b8-113">Erstellen Sie in Visual Studio ein Windows-basiertes Anwendungsprojekt mit dem Namen **DesignerAction sexample**.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-113">In Visual Studio, create a Windows-based application project called **DesignerActionsExample**.</span></span>

2. <span data-ttu-id="6a8b8-114">Wählen Sie in der **Windows Forms-Designer**das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-designer-actions"></a><span data-ttu-id="6a8b8-115">Designer Aktionen verwenden</span><span class="sxs-lookup"><span data-stu-id="6a8b8-115">Use designer actions</span></span>

<span data-ttu-id="6a8b8-116">Designer Aktionen sind immer zur Entwurfszeit für Steuerelemente verfügbar, die Sie bieten.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-116">Designer actions are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="6a8b8-117">Ziehen Sie eine <xref:System.Windows.Forms.TabControl> aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="6a8b8-118">Beachten Sie das Symbol "Designer Aktionen" (![kleinen schwarzen Pfeil](./media/designer-actions-glyph.gif)), der auf der Seite des <xref:System.Windows.Forms.TabControl>angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-118">Note the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="6a8b8-119">Klicken Sie auf das Symbol Designer Aktionen.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-119">Click the designer actions glyph.</span></span> <span data-ttu-id="6a8b8-120">Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **Registerkarte hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="6a8b8-121">Beachten Sie, dass dem <xref:System.Windows.Forms.TabControl>eine neue Registerkarte hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="6a8b8-122">Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="6a8b8-123">Klicken Sie auf das Symbol Designer Aktionen.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-123">Click the designer actions glyph.</span></span> <span data-ttu-id="6a8b8-124">Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **Spalten hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="6a8b8-125">Beachten Sie, dass dem <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement eine neue Spalte hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="6a8b8-126">Ziehen Sie ein <xref:System.Windows.Forms.SplitContainer> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="6a8b8-127">Klicken Sie auf das Symbol Designer Aktionen.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-127">Click the designer actions glyph.</span></span> <span data-ttu-id="6a8b8-128">Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **horizontale Splitter Ausrichtung** aus.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-128">In the shortcut menu that appears next to the glyph, select the **Horizontal Splitter Orientation** item.</span></span> <span data-ttu-id="6a8b8-129">Beachten Sie, dass die Splitter Leiste des <xref:System.Windows.Forms.SplitContainer> Steuer Elements nun horizontal ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a8b8-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a8b8-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
