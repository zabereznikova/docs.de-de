---
title: 'Gewusst wie: Ausblenden von ToolStripMenuItems'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
ms.openlocfilehash: 73f67bbe6b2d51a59b6f72ab5faf21db9d6db12d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531952"
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="a6835-102">Gewusst wie: Ausblenden von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="a6835-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="a6835-103">Ausblenden von Menüelementen lässt sich die Benutzeroberfläche der Anwendung steuern und Benutzerbefehle einschränken.</span><span class="sxs-lookup"><span data-stu-id="a6835-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="a6835-104">Häufig, sollten Sie ein ganzes Menü auszublenden, wenn alle Menüelemente im auf ihm nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a6835-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="a6835-105">Dies ist weniger verwirrend für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a6835-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="a6835-106">Darüber hinaus empfiehlt sowohl ausblenden und deaktivieren das Menü oder Menüelement, wie durch das bloße Ausblenden nicht den Benutzer verhindert den Zugriff auf einen Menübefehl über eine Tastenkombination.</span><span class="sxs-lookup"><span data-stu-id="a6835-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="a6835-107">So blenden Sie alle Menüelement programmgesteuert aus</span><span class="sxs-lookup"><span data-stu-id="a6835-107">To hide any menu item programmatically</span></span>  
  
-   <span data-ttu-id="a6835-108">Fügen Sie innerhalb der Methode, in dem Sie die Eigenschaften des Menüelements festlegen, Code aus, um die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="a6835-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a6835-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6835-109">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 [<span data-ttu-id="a6835-110">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a6835-110">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="a6835-111">Gewusst wie: Deaktivieren von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="a6835-111">How to: Disable ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)
