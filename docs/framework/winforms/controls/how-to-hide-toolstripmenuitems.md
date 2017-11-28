---
title: 'Gewusst wie: Ausblenden von ToolStripMenuItems'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cb24fd36bdee76fa80a87d48f41b72f01c8f263
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-toolstripmenuitems"></a>Gewusst wie: Ausblenden von ToolStripMenuItems
Ausblenden von Menüelementen lässt sich die Benutzeroberfläche der Anwendung steuern und Benutzerbefehle einschränken. Häufig, sollten Sie ein ganzes Menü auszublenden, wenn alle Menüelemente im auf ihm nicht verfügbar sind. Dies ist weniger verwirrend für den Benutzer. Darüber hinaus empfiehlt sowohl ausblenden und deaktivieren das Menü oder Menüelement, wie durch das bloße Ausblenden nicht den Benutzer verhindert den Zugriff auf einen Menübefehl über eine Tastenkombination.  
  
### <a name="to-hide-any-menu-item-programmatically"></a>So blenden Sie alle Menüelement programmgesteuert aus  
  
-   Fügen Sie innerhalb der Methode, in dem Sie die Eigenschaften des Menüelements festlegen, Code aus, um die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft `false`.  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 [Übersicht über das MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [Gewusst wie: Deaktivieren von ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)
