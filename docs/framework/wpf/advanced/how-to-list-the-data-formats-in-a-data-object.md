---
title: 'Vorgehensweise: Auflisten der Datenformate in einem Datenobjekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: f8230eac33a18a0d99cc757d54c2b901c1afe977
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077744"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a>Vorgehensweise: Auflisten der Datenformate in einem Datenobjekt
Die folgenden Beispiele zeigen, wie Sie mit der <xref:System.Windows.DataObject.GetFormats%2A> Überladungen der Methode erhalten ein Array von Zeichenfolgen, die jede Datenformat, das in einem Datenobjekt verfügbar ist.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetFormats%2A> -Überladung verwenden, um ein Array von Zeichenfolgen, die alle verfügbaren Datenformate in einem Datenobjekt (systemeigene und automatisch konvertierbare) abrufen.  
  
### <a name="code"></a>Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetFormats%2A> -Überladung verwenden, um ein Array von Zeichenfolgen, die nur verfügbaren Datenformate in einem Datenobjekt (automatisch konvertierbare Daten Formate gefiltert werden) zu erhalten.  
  
### <a name="code"></a>Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.IDataObject>
- [Übersicht über Drag & Drop](drag-and-drop-overview.md)
