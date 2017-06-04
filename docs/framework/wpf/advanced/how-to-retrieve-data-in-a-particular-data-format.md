---
title: "Gewusst wie: Abrufen von Daten in einem bestimmten Datenformat | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DataFormats-Klasse [WPF], Abrufen von Daten"
  - "DataObject-Klasse [WPF], Abrufen von Daten"
  - "Drag & Drop [WPF], Abrufen von Daten"
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Abrufen von Daten in einem bestimmten Datenformat
Die folgenden Beispiele zeigen, wie Sie Daten in einem angegebenen Format aus einem Datenobjekt abrufen.  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispielcode wird die <xref:System.Windows.DataObject.GetDataPresent%28System.String%29>\-Überladung verwendet, um als Erstes zu prüfen, ob ein angegebenes Datenformat verfügbar ist \(im System oder durch automatische Konvertierung\). Wenn das angegebene Format verfügbar ist, ruft der Beispielcode die Daten mithilfe der <xref:System.Windows.DataObject.GetData%28System.String%29>\-Methode ab.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispielcode wird die <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29>\-Überladung verwendet, um als Erstes zu prüfen, ob ein angegebenes Datenformat im System verfügbar ist \(Datenformate, die automatisch konvertiert werden können, werden gefiltert\). Wenn das angegebene Format verfügbar ist, ruft der Beispielcode die Daten mithilfe der <xref:System.Windows.DataObject.GetData%28System.String%29>\-Methode ab.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## Siehe auch  
 <xref:System.Windows.IDataObject>   
 [Übersicht über Drag & Drop](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)