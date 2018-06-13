---
title: 'Gewusst wie: Abrufen von Daten in einem bestimmten Datenformat'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
ms.openlocfilehash: 405fff1b586207249fbabafb28791ffa2901cf49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545106"
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a>Gewusst wie: Abrufen von Daten in einem bestimmten Datenformat
Die folgenden Beispiele zeigen, wie zum Abrufen von Daten aus einem Datenobjekt in einem angegebenen Format.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> methodenüberladung, um zuerst überprüfen Sie, ob eine angegebene Datenformat ist verfügbar, (systemeigen oder durch automatische Konvertierung), wenn das angegebene Format verfügbar ist, ruft das Beispiel die Daten mithilfe der <xref:System.Windows.DataObject.GetData%28System.String%29> Methode.  
  
### <a name="code"></a>Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> methodenüberladung, um zuerst überprüfen Sie, ob ein angegebenes Datenformat systemintern verfügbar ist (Auto-Datenformate werden gefiltert); Wenn das angegebene Format verfügbar ist, ruft das Beispiel die Daten mithilfe der <xref:System.Windows.DataObject.GetData%28System.String%29>Methode.  
  
### <a name="code"></a>Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.IDataObject>  
 [Übersicht über Drag & Drop](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
