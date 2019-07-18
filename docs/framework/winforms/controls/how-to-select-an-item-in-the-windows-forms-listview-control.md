---
title: 'Vorgehensweise: Auswählen eines Elements im ListView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
ms.openlocfilehash: 41a30ba6c242d0587e98b458e41ca213e8885bca
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638203"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a>Vorgehensweise: Auswählen eines Elements im ListView-Steuerelement in Windows Forms
In diesem Beispiel wird veranschaulicht, wie ein Element in einem Windows Forms programmgesteuert ausgewählt <xref:System.Windows.Forms.ListView> Steuerelement. Ein Element programmgesteuert ausgewählt automatisch ändert nicht den Fokus an das <xref:System.Windows.Forms.ListView> Steuerelement. Aus diesem Grund werden Sie in der Regel auch das Element festlegen möchten, wie mit Fokus, wenn Sie ein Element auswählen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Ein <xref:System.Windows.Forms.ListView> Steuerelement mit dem Namen `listView1` , die mindestens ein Element enthält.  
  
- Verweise auf die Namespaces <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
