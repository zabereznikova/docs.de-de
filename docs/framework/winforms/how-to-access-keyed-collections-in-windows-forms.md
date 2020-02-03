---
title: 'Gewusst wie: Zugreifen auf verschlüsselte Auflistungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: 717ba9cc8605da08701de1bd13d6bc6da1c9b758
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739617"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a>Gewusst wie: Zugreifen auf verschlüsselte Auflistungen in Windows Forms

- Sie können auf einzelne Sammel Elemente nach Schlüssel zugreifen. Diese Funktionalität wurde vielen Sammlungs Klassen hinzugefügt, die in der Regel von Windows Forms Anwendungen verwendet werden. In der folgenden Liste sind einige der Auflistungs Klassen aufgeführt, für die barrierefreie Sammlungen zugänglich sind:  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 Der Schlüssel, der einem Element in einer Auflistung zugeordnet ist, ist in der Regel der Name des Elements. In den folgenden Verfahren wird gezeigt, wie Sie mithilfe von Auflistungs Klassen häufige Aufgaben ausführen.  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a>So suchen und setzen Sie den Fokus auf ein in einer Steuerelement Sammlung eingefügter Steuerelement  
  
- Verwenden Sie die Methoden <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> und <xref:System.Windows.Forms.Control.Focus%2A>, um den Namen des Steuer Elements anzugeben, das gesucht und dem Fokus zugewiesen werden soll.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a>So greifen Sie auf ein Bild in einer Bild Auflistung zu  
  
- Verwenden Sie die <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A>-Eigenschaft, um den Namen des Abbilds anzugeben, auf das Sie zugreifen möchten.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a>So legen Sie eine Registerkarte als ausgewählte Registerkarte fest  
  
- Verwenden Sie die <xref:System.Windows.Forms.TabControl.SelectedTab%2A>-Eigenschaft in Verbindung mit der <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A>-Eigenschaft, um den Namen der Registerkarte anzugeben, die als ausgewählte Registerkarte festgelegt werden soll.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Erste Schritte mit Windows Forms](getting-started-with-windows-forms.md)
- [Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
