---
title: MDI-Anwendungen (Multiple Document Interface)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 74735afcb1d6be319ad5d497615a3b725a4d5574
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="de778-102">MDI-Anwendungen (Multiple Document Interface)</span><span class="sxs-lookup"><span data-stu-id="de778-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="de778-103">Multiple Document Interface (MDI)-Anwendungen ermöglichen es Ihnen, mehrere Dokumente zur gleichen Zeit angezeigt, mit jedes Dokument in einem eigenen Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de778-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="de778-104">MDI-Anwendungen haben häufig ein Fenster Menüelement mit Untermenüs zum Wechseln zwischen Fenstern oder Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="de778-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de778-105">Es gibt einige Unterschiede im Verhalten zwischen MDI-Formulare und Single Document Interface (SDI) Windows in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="de778-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="de778-106">Die `Opacity` Eigenschaft wirkt sich nicht auf die Darstellung des untergeordneten MDI-Formulare.</span><span class="sxs-lookup"><span data-stu-id="de778-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="de778-107">Darüber hinaus die <xref:System.Windows.Forms.Form.CenterToParent%2A> Methode wirkt sich nicht auf das Verhalten des untergeordneten MDI-Formulare.</span><span class="sxs-lookup"><span data-stu-id="de778-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="de778-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="de778-108">In This Section</span></span>  
 [<span data-ttu-id="de778-109">Gewusst wie: Erstellen von übergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="de778-109">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="de778-110">Gibt richtungshinweise für den Container für mehrere Dokumente in einer MDI-Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="de778-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="de778-111">Gewusst wie: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="de778-111">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="de778-112">Enthält Anweisungen zum Erstellen von einem oder mehreren Fenstern, die innerhalb eines übergeordneten MDI-Formulars ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="de778-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="de778-113">Gewusst wie: Bestimmen des aktiven untergeordneten MDI-Elements</span><span class="sxs-lookup"><span data-stu-id="de778-113">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="de778-114">Enthält Anweisungen für das untergeordnete Fenster, das Fokus hat (und dessen Inhalt in die Zwischenablage senden).</span><span class="sxs-lookup"><span data-stu-id="de778-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="de778-115">Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element</span><span class="sxs-lookup"><span data-stu-id="de778-115">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="de778-116">Enthält Anweisungen für die Übermittlung von Informationen auf dem aktiven untergeordneten Fenster.</span><span class="sxs-lookup"><span data-stu-id="de778-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="de778-117">Gewusst wie: Anordnen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="de778-117">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="de778-118">Gibt richtungshinweise für Kacheln, cascading oder Anordnen von der untergeordneten Fenster einer MDI-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="de778-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
