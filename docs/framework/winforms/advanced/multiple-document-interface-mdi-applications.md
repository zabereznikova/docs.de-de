---
title: MDI-Anwendungen (Multiple Document Interface)
description: Erfahren Sie, wie Sie mit Windows Forms Multiple Document Interface (MDI)-Anwendungen mehrere Dokumente gleichzeitig anzeigen können, wobei jedes Dokument in einem eigenen Fenster angezeigt wird.
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0912a989ac1710d72c9db1cceb0e695f0ca85dee
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174652"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="929c5-103">MDI-Anwendungen (Multiple Document Interface)</span><span class="sxs-lookup"><span data-stu-id="929c5-103">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="929c5-104">MDI-Anwendungen (Multiple Document Interface) ermöglichen es Ihnen, mehrere Dokumente gleichzeitig anzuzeigen, wobei jedes Dokument in einem eigenen Fenster angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="929c5-104">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="929c5-105">MDI-Anwendungen haben häufig ein Fenstermenü Element mit Untermenüs zum Wechseln zwischen Fenstern oder Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="929c5-105">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="929c5-106">Es gibt einige Verhaltensunterschiede zwischen MDI-Formularen und SDI-Fenstern (Single-Document Interface) in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="929c5-106">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="929c5-107">Die- `Opacity` Eigenschaft hat keine Auswirkung auf die Darstellung von untergeordneten MDI-Formularen.</span><span class="sxs-lookup"><span data-stu-id="929c5-107">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="929c5-108">Außerdem hat die- <xref:System.Windows.Forms.Form.CenterToParent%2A> Methode keine Auswirkung auf das Verhalten von untergeordneten MDI-Formularen.</span><span class="sxs-lookup"><span data-stu-id="929c5-108">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="929c5-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="929c5-109">In This Section</span></span>  
 [<span data-ttu-id="929c5-110">Vorgehensweise: Erstellen von übergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="929c5-110">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="929c5-111">Gibt Anweisungen zum Erstellen des Containers für mehrere Dokumente in einer MDI-Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="929c5-111">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="929c5-112">Vorgehensweise: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="929c5-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="929c5-113">Hier finden Sie Anleitungen zum Erstellen eines oder mehrerer Fenster, die in einem übergeordneten MDI-Formular betrieben werden.</span><span class="sxs-lookup"><span data-stu-id="929c5-113">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="929c5-114">Vorgehensweise: Bestimmen des aktiven untergeordneten MDI-Elements</span><span class="sxs-lookup"><span data-stu-id="929c5-114">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="929c5-115">Gibt Anweisungen zum Überprüfen des untergeordneten Fensters an, das den Fokus besitzt (und seinen Inhalt in die Zwischenablage sendet).</span><span class="sxs-lookup"><span data-stu-id="929c5-115">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="929c5-116">Vorgehensweise: Senden von Daten an das aktive untergeordnete MDI-Element</span><span class="sxs-lookup"><span data-stu-id="929c5-116">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="929c5-117">Gibt Anleitungen zum Transportieren von Informationen in das aktive untergeordnete Fenster an.</span><span class="sxs-lookup"><span data-stu-id="929c5-117">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="929c5-118">Vorgehensweise: Anordnen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="929c5-118">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="929c5-119">Hier finden Sie Anleitungen zum Ticken, kaskadieren oder Anordnen der untergeordneten Fenster einer MDI-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="929c5-119">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
