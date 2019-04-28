---
title: 'Vorgehensweise: Zugreifen auf verschlüsselte Auflistungen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: fdd3a56ab9a267990bb0e832c0d4cc2af9334034
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801828"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a>Vorgehensweise: Zugreifen auf verschlüsselte Auflistungen in Windows Forms
- Sie können auf einzelne Auflistungselemente mit Schlüssel zugreifen. Diese Funktion verfügt über viele Auflistungsklassen hinzugefügt, die in der Regel von Windows Forms-Anwendungen verwendet werden. Die folgende Liste enthält einige der Auflistungsklassen, die zugänglich schlüsselgebundene Auflistungen haben:  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 Ein Element in einer Sammlung zugeordnete Schlüssel wird in der Regel der Name des Elements. Die folgenden Verfahren zeigen, wie Auflistungsklassen zu verwenden, um allgemeine Aufgaben auszuführen.  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a>Suchen, und geben Sie ein geschachteltes Steuerelement in einer steuerelementauflistung den Fokus  
  
- Verwenden der <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> und <xref:System.Windows.Forms.Control.Focus%2A> Methoden geben Sie den Namen des Steuerelements zu finden, und geben Sie den Fokus auf.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a>Auf ein Bild in einer imagesammlung  
  
- Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> -Eigenschaft den Namen des Bilds an die Sie zugreifen möchten.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a>Festlegen eine Registerkarte als ausgewählte Registerkarte  
  
- Verwenden der <xref:System.Windows.Forms.TabControl.SelectedTab%2A> Eigenschaft zusammen mit den <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> Eigenschaft, um den Namen der Registerkarte für die festzulegende als ausgewählte Registerkarte anzugeben.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit Windows Forms](getting-started-with-windows-forms.md)
- [Vorgehensweise: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
