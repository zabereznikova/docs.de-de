---
title: MDI-Anwendungen (Multiple Document Interface)
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 23e0275d5e6b081ec02d669a78e8695453360637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956560"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="447fc-102">MDI-Anwendungen (Multiple Document Interface)</span><span class="sxs-lookup"><span data-stu-id="447fc-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="447fc-103">MDI-Anwendungen (Multiple Document Interface) ermöglichen es Ihnen, mehrere Dokumente gleichzeitig anzuzeigen, wobei jedes Dokument in einem eigenen Fenster angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="447fc-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="447fc-104">MDI-Anwendungen haben häufig ein Fenstermenü Element mit Untermenüs zum Wechseln zwischen Fenstern oder Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="447fc-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="447fc-105">Es gibt einige Verhaltensunterschiede zwischen MDI-Formularen und SDI-Fenstern (Single-Document Interface) in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="447fc-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="447fc-106">Die `Opacity` -Eigenschaft hat keine Auswirkung auf die Darstellung von untergeordneten MDI-Formularen.</span><span class="sxs-lookup"><span data-stu-id="447fc-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="447fc-107">Außerdem hat die <xref:System.Windows.Forms.Form.CenterToParent%2A> -Methode keine Auswirkung auf das Verhalten von untergeordneten MDI-Formularen.</span><span class="sxs-lookup"><span data-stu-id="447fc-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="447fc-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="447fc-108">In This Section</span></span>  
 [<span data-ttu-id="447fc-109">Vorgehensweise: Übergeordnete MDI-Formulare erstellen</span><span class="sxs-lookup"><span data-stu-id="447fc-109">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="447fc-110">Gibt Anweisungen zum Erstellen des Containers für mehrere Dokumente in einer MDI-Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="447fc-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="447fc-111">Vorgehensweise: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="447fc-111">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="447fc-112">Hier finden Sie Anleitungen zum Erstellen eines oder mehrerer Fenster, die in einem übergeordneten MDI-Formular betrieben werden.</span><span class="sxs-lookup"><span data-stu-id="447fc-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="447fc-113">Vorgehensweise: Festlegen des aktiven untergeordneten MDI-Elements</span><span class="sxs-lookup"><span data-stu-id="447fc-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="447fc-114">Gibt Anweisungen zum Überprüfen des untergeordneten Fensters an, das den Fokus besitzt (und seinen Inhalt in die Zwischenablage sendet).</span><span class="sxs-lookup"><span data-stu-id="447fc-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="447fc-115">Vorgehensweise: Senden von Daten an das aktive untergeordnete MDI-Element</span><span class="sxs-lookup"><span data-stu-id="447fc-115">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="447fc-116">Gibt Anleitungen zum Transportieren von Informationen in das aktive untergeordnete Fenster an.</span><span class="sxs-lookup"><span data-stu-id="447fc-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="447fc-117">Vorgehensweise: Untergeordnete MDI-Formulare anordnen</span><span class="sxs-lookup"><span data-stu-id="447fc-117">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="447fc-118">Hier finden Sie Anleitungen zum Ticken, kaskadieren oder Anordnen der untergeordneten Fenster einer MDI-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="447fc-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
