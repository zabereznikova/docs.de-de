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
ms.openlocfilehash: 64c0f093063357c1e8db5933c035cc8295ad4f1e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623037"
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="77b01-102">Vorgehensweise: Ausblenden von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="77b01-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="77b01-103">Ausblenden von Menüelementen ist eine Möglichkeit zum Steuern der Benutzeroberfläche Ihrer Anwendung und User-Befehle zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="77b01-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="77b01-104">Häufig möchten ein ganzes Menü ausblenden, wenn alle Menüelemente im auf nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="77b01-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="77b01-105">Dies führt zu weniger ablenkungen für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="77b01-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="77b01-106">Darüber hinaus empfiehlt sowohl ausblenden und deaktivieren Sie das Menü oder Menüelement, da allein durch das Ausblenden den Benutzer den Zugriff auf einen Menübefehl mit einer Tastenkombination nicht verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="77b01-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="77b01-107">So blenden Sie eine beliebige Menüoption programmgesteuert aus</span><span class="sxs-lookup"><span data-stu-id="77b01-107">To hide any menu item programmatically</span></span>  
  
- <span data-ttu-id="77b01-108">Fügen Sie innerhalb der Methode, in dem Sie die Eigenschaften des Menüelements festlegen, Code aus, um die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="77b01-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="77b01-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77b01-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [<span data-ttu-id="77b01-110">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="77b01-110">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="77b01-111">Vorgehensweise: Deaktivieren von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="77b01-111">How to: Disable ToolStripMenuItems</span></span>](how-to-disable-toolstripmenuitems.md)
