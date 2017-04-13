---
title: "Gewusst wie: Speichern von mehreren Datenformaten in einem Datenobjekt | Microsoft Docs"
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
  - "DataFormats-Klasse [WPF], Speichern von mehreren Formaten"
  - "DataObject-Klasse [WPF], Speichern von mehreren Formaten"
  - "Drag & Drop [WPF], Speichern von mehreren Formaten"
ms.assetid: 941ace29-29c4-4c26-b75b-ea7d06aa0d69
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Speichern von mehreren Datenformaten in einem Datenobjekt
Im folgenden Beispiel wird gezeigt, wie einem Datenobjekt mithilfe der <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29>\-Methode Daten in mehreren Formaten hinzugefügt werden.  
  
## Beispiel  
  
### Beschreibung  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
## Siehe auch  
 <xref:System.Windows.IDataObject>   
 [Übersicht über Drag & Drop](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)