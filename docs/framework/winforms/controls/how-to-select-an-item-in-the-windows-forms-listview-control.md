---
title: "Gewusst wie: Auswählen eines Elements im ListView-Steuerelement in Windows Forms"
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
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e7acbda541000655ff96b70a2188169b7e8ccd9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a>Gewusst wie: Auswählen eines Elements im ListView-Steuerelement in Windows Forms
In diesem Beispiel wird veranschaulicht, wie ein Element in einer Windows Forms programmgesteuert ausgewählt <xref:System.Windows.Forms.ListView> Steuerelement. Auswählen eines Elements programmgesteuert automatisch ändert nicht den Fokus an das <xref:System.Windows.Forms.ListView> Steuerelement. Aus diesem Grund werden Sie in der Regel auch das Element festlegen möchten, wie sich der Fokus beim Auswählen eines Elements.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.ListView> Steuerelement namens `listView1` , die mindestens ein Element enthält.  
  
-   Verweise auf die Namespaces <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
