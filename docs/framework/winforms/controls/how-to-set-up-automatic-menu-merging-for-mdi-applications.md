---
title: "Gewusst wie: Einrichten des automatischem Zusammenführens von Menüs für MDI-Anwendungen (Multiple Document Interface)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e99aed38ed6c3af3424c264631f0eaf27e46af7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a><span data-ttu-id="ca697-102">Gewusst wie: Einrichten des automatischem Zusammenführens von Menüs für MDI-Anwendungen (Multiple Document Interface)</span><span class="sxs-lookup"><span data-stu-id="ca697-102">How to: Set Up Automatic Menu Merging for MDI Applications</span></span>
<span data-ttu-id="ca697-103">Das folgende Verfahren bietet die grundlegenden Schritte zum Einrichten der automatische Zusammenführung wird in einer Anwendung Multiple Document Interface (MDI) mit <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="ca697-103">The following procedure gives the basic steps for setting up automatic merging in a multiple-document interface (MDI) application with <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
### <a name="to-set-up-automatic-menu-merging"></a><span data-ttu-id="ca697-104">Zum Einrichten des automatischem Zusammenführens von Menüs</span><span class="sxs-lookup"><span data-stu-id="ca697-104">To set up automatic menu merging</span></span>  
  
1.  <span data-ttu-id="ca697-105">Erstellen von übergeordneten MDI-Formulars durch Festlegen seiner <xref:System.Windows.Forms.Form.IsMdiContainer%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="ca697-105">Create the MDI parent form by setting its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="ca697-106">Hinzufügen einer <xref:System.Windows.Forms.MenuStrip> an das übergeordnete MDI-Element festlegen seiner <xref:System.Windows.Forms.Form.MainMenuStrip%2A> Eigenschaft mit <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="ca697-106">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI parent, setting its <xref:System.Windows.Forms.Form.MainMenuStrip%2A> property to that <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
3.  <span data-ttu-id="ca697-107">Erstellen Sie ein untergeordnetes MDI-Formular, und legen seine <xref:System.Windows.Forms.Form.MdiParent%2A> -Eigenschaft auf den Namen des übergeordneten Formulars.</span><span class="sxs-lookup"><span data-stu-id="ca697-107">Create an MDI child form, and set its <xref:System.Windows.Forms.Form.MdiParent%2A> property to the name of the parent form.</span></span>  
  
4.  <span data-ttu-id="ca697-108">Hinzufügen einer <xref:System.Windows.Forms.MenuStrip> zu untergeordneten MDI-Formulars.</span><span class="sxs-lookup"><span data-stu-id="ca697-108">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI child form.</span></span>  
  
5.  <span data-ttu-id="ca697-109">Legen Sie auf dem Formular untergeordneten der <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft der <xref:System.Windows.Forms.MenuStrip> auf `false`.</span><span class="sxs-lookup"><span data-stu-id="ca697-109">On the child form, set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
6.  <span data-ttu-id="ca697-110">Hinzufügen von Menüelementen des untergeordneten Formulars <xref:System.Windows.Forms.MenuStrip> , die Sie mit des übergeordneten Formulars zusammenführen möchten <xref:System.Windows.Forms.MenuStrip> Wenn das untergeordnete Formular aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ca697-110">Add menu items to the child form's <xref:System.Windows.Forms.MenuStrip> that you want to merge into the parent form's <xref:System.Windows.Forms.MenuStrip> when the child form is activated.</span></span>  
  
7.  <span data-ttu-id="ca697-111">Verwenden der <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> -Eigenschaft der Elemente in des untergeordneten Formulars <xref:System.Windows.Forms.MenuStrip> steuern, wie sie mit dem übergeordneten Formular zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="ca697-111">Use the <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> property on the menu items in the child form's <xref:System.Windows.Forms.MenuStrip> to control how they merge into the parent form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca697-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca697-112">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="ca697-113">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ca697-113">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
