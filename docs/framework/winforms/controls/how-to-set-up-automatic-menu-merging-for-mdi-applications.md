---
title: 'Vorgehensweise: Richten Sie automatische Zusammenführen von Menüs für MDI-Anwendungen'
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 152db39e7c947d5a49eaed81b00d13c02aa8014c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719728"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a><span data-ttu-id="42126-102">Vorgehensweise: Richten Sie automatische Zusammenführen von Menüs für MDI-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="42126-102">How to: Set Up Automatic Menu Merging for MDI Applications</span></span>
<span data-ttu-id="42126-103">Das folgende Verfahren bietet die grundlegenden Schritte zum Einrichten der automatischen Zusammenführen in einer Anwendung Multiple Document Interface (MDI) mit <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="42126-103">The following procedure gives the basic steps for setting up automatic merging in a multiple-document interface (MDI) application with <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
### <a name="to-set-up-automatic-menu-merging"></a><span data-ttu-id="42126-104">Zum Einrichten des automatischem Zusammenführens von</span><span class="sxs-lookup"><span data-stu-id="42126-104">To set up automatic menu merging</span></span>  
  
1.  <span data-ttu-id="42126-105">Erstellen von übergeordneten MDI-Formulars durch Festlegen seiner <xref:System.Windows.Forms.Form.IsMdiContainer%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="42126-105">Create the MDI parent form by setting its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="42126-106">Hinzufügen einer <xref:System.Windows.Forms.MenuStrip> zum übergeordneten MDI-Fensters, Festlegen der <xref:System.Windows.Forms.Form.MainMenuStrip%2A> Eigenschaft mit dem <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="42126-106">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI parent, setting its <xref:System.Windows.Forms.Form.MainMenuStrip%2A> property to that <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
3.  <span data-ttu-id="42126-107">Erstellen Sie ein untergeordnetes MDI-Formular, und legen dessen <xref:System.Windows.Forms.Form.MdiParent%2A> -Eigenschaft auf den Namen des übergeordneten Formulars.</span><span class="sxs-lookup"><span data-stu-id="42126-107">Create an MDI child form, and set its <xref:System.Windows.Forms.Form.MdiParent%2A> property to the name of the parent form.</span></span>  
  
4.  <span data-ttu-id="42126-108">Hinzufügen einer <xref:System.Windows.Forms.MenuStrip> , untergeordneten MDI-Formulars.</span><span class="sxs-lookup"><span data-stu-id="42126-108">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI child form.</span></span>  
  
5.  <span data-ttu-id="42126-109">Im untergeordneten Formular, legen Sie die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft der <xref:System.Windows.Forms.MenuStrip> zu `false`.</span><span class="sxs-lookup"><span data-stu-id="42126-109">On the child form, set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
6.  <span data-ttu-id="42126-110">Hinzufügen von Menüelementen des untergeordneten Formulars <xref:System.Windows.Forms.MenuStrip> , die Sie mit des übergeordneten Formulars zusammenführen möchten <xref:System.Windows.Forms.MenuStrip> Wenn das untergeordnete Formular aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="42126-110">Add menu items to the child form's <xref:System.Windows.Forms.MenuStrip> that you want to merge into the parent form's <xref:System.Windows.Forms.MenuStrip> when the child form is activated.</span></span>  
  
7.  <span data-ttu-id="42126-111">Verwenden der <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> Eigenschaft, die Sie im Menü des untergeordneten Formulars Elemente <xref:System.Windows.Forms.MenuStrip> steuern, wie sie mit dem übergeordneten Formular zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="42126-111">Use the <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> property on the menu items in the child form's <xref:System.Windows.Forms.MenuStrip> to control how they merge into the parent form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42126-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42126-112">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="42126-113">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="42126-113">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
