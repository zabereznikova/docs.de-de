---
title: 'Gewusst wie: Zugreifen auf verschlüsselte Auflistungen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: 59e5cea29ee520b1f13f8fae98ae4042cc86fef7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a>Gewusst wie: Zugreifen auf verschlüsselte Auflistungen in Windows Forms
-   Sie können einzelne Auflistungselemente durch Schlüssel zugreifen. Diese Funktionalität wurde um viele Auflistungsklassen hinzugefügt, die in der Regel von Windows Forms-Anwendungen verwendet werden. Die folgende Liste enthält einige der Auflistungsklassen, die zugänglich schlüsselgebundene Auflistungen haben:  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 Der zugeordneten Schlüssel für ein Element in einer Auflistung ist in der Regel der Name des Elements. Nachfolgend wird erläutert, wie Auflistungsklassen zu verwenden, um allgemeine Aufgaben auszuführen.  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a>Zum Suchen, und geben Sie ein geschachteltes Steuerelement in einer steuerelementauflistung den Fokus  
  
-   Verwenden der <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> und <xref:System.Windows.Forms.Control.Focus%2A> Methoden, um den Namen des Steuerelements zu suchen, und setzen Sie den Fokus zu geben.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a>Auf ein Bild in einer Auflistung zuzugreifen.  
  
-   Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> -Eigenschaft den Namen des Bilds an die Sie zugreifen möchten.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a>Festlegen eine Registerkarte als ausgewählte Registerkarte  
  
-   Verwenden der <xref:System.Windows.Forms.TabControl.SelectedTab%2A> Eigenschaft zusammen mit der <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> Eigenschaft, um den Namen der Registerkartenseite festzulegende als der ausgewählten Registerkarte anzugeben.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte mit Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
