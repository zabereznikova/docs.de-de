---
title: 'Gewusst wie: Speichern von mehreren Datenformaten in einem Datenobjekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], storing multiple formats
- DataFormats class [WPF], storing multiple formats
- drag-and-drop [WPF], storing multiple formats
ms.assetid: 941ace29-29c4-4c26-b75b-ea7d06aa0d69
ms.openlocfilehash: e47d0aa2fe1c573314551ad91a2199ca97fd61a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543467"
---
# <a name="how-to-store-multiple-data-formats-in-a-data-object"></a>Gewusst wie: Speichern von mehreren Datenformaten in einem Datenobjekt
Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> Methode zum Hinzufügen von Daten an ein Datenobjekt in verschiedenen Formaten.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
  
### <a name="code"></a>Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.IDataObject>  
 [Übersicht über Drag & Drop](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
