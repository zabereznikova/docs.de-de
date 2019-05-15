---
title: 'Vorgehensweise: Zuordnen eines ContextMenuStrip zu einem Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: e1b2a49196d6da66d478a3d44eab64298cebe969
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586604"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="d65ab-102">Vorgehensweise: Zuordnen eines ContextMenuStrip zu einem Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d65ab-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="d65ab-103">Nachdem Sie Ihre Steuerelemente und Kontextmenüs erstellt haben, verwenden Sie die folgenden Verfahren, um ein bestimmtes Kontextmenü anzuzeigen, wenn der Benutzer mit der rechten Maustaste auf das Steuerelement klickt.</span><span class="sxs-lookup"><span data-stu-id="d65ab-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="d65ab-104">In diesen Verfahren wird eine <xref:System.Windows.Forms.ContextMenuStrip>-Instanz einem Windows Form-Objekt und einem <xref:System.Windows.Forms.ToolStrip>-Steuerelement zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d65ab-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="d65ab-105">So ordnen Sie eine ContextMenuStrip-Instanz einem Windows Form-Objekt zu</span><span class="sxs-lookup"><span data-stu-id="d65ab-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1. <span data-ttu-id="d65ab-106">Legen Sie die <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>-Eigenschaft auf den Namen der zugeordneten <xref:System.Windows.Forms.ContextMenuStrip>-Instanz fest.</span><span class="sxs-lookup"><span data-stu-id="d65ab-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="d65ab-107">So ordnen Sie eine ContextMenuStrip-Instanz einem ToolStrip-Steuerelement zu</span><span class="sxs-lookup"><span data-stu-id="d65ab-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1. <span data-ttu-id="d65ab-108">Legen Sie die <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>-Eigenschaft des Steuerelements auf den Namen der zugeordneten <xref:System.Windows.Forms.ContextMenuStrip>-Instanz fest.</span><span class="sxs-lookup"><span data-stu-id="d65ab-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d65ab-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d65ab-109">Example</span></span>  
 <span data-ttu-id="d65ab-110">Im folgenden Codebeispiel werden ein Windows Form-Objekt und ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement erstellt, und beiden wird jeweils ein anderes <xref:System.Windows.Forms.ContextMenuStrip>-Steuerelement zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d65ab-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d65ab-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d65ab-111">Compiling the Code</span></span>  
 <span data-ttu-id="d65ab-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d65ab-112">This example requires:</span></span>  
  
- <span data-ttu-id="d65ab-113">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="d65ab-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d65ab-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d65ab-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="d65ab-115">Vorgehensweise: Hinzufügen von Menüelementen zu einem ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="d65ab-115">How to: Add Menu Items to a ContextMenuStrip</span></span>](how-to-add-menu-items-to-a-contextmenustrip.md)
- [<span data-ttu-id="d65ab-116">ContextMenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d65ab-116">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
