---
title: 'Vorgehensweise: Ausblenden von ToolStripMenuItems'
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
ms.openlocfilehash: 73e49c96c20f145490a2d494177e21bc957605b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727624"
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="8087d-102">Vorgehensweise: Ausblenden von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="8087d-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="8087d-103">Ausblenden von Menüelementen ist eine Möglichkeit zum Steuern der Benutzeroberfläche Ihrer Anwendung und User-Befehle zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="8087d-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="8087d-104">Häufig möchten ein ganzes Menü ausblenden, wenn alle Menüelemente im auf nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8087d-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="8087d-105">Dies führt zu weniger ablenkungen für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8087d-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="8087d-106">Darüber hinaus empfiehlt sowohl ausblenden und deaktivieren Sie das Menü oder Menüelement, da allein durch das Ausblenden den Benutzer den Zugriff auf einen Menübefehl mit einer Tastenkombination nicht verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="8087d-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="8087d-107">So blenden Sie eine beliebige Menüoption programmgesteuert aus</span><span class="sxs-lookup"><span data-stu-id="8087d-107">To hide any menu item programmatically</span></span>  
  
-   <span data-ttu-id="8087d-108">Fügen Sie innerhalb der Methode, in dem Sie die Eigenschaften des Menüelements festlegen, Code aus, um die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="8087d-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8087d-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8087d-109">See also</span></span>
- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [<span data-ttu-id="8087d-110">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8087d-110">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="8087d-111">Vorgehensweise: Deaktivieren von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="8087d-111">How to: Disable ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)
