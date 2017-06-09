---
title: "Gewusst wie: Auflisten der Datenformate in einem Datenobjekt | Microsoft Docs"
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
  - "Datenformate [WPF], Auflisten"
  - "DataFormats-Klasse [WPF]"
  - "Drag & Drop [WPF], Auflisten von Datenformaten"
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Auflisten der Datenformate in einem Datenobjekt
In den folgenden Beispielen wird gezeigt, wie mit <xref:System.Windows.DataObject.GetFormats%2A>\-Methodenüberladungen ein Zeichenfolgenarray abgerufen wird, das alle in einem Datenobjekt verfügbaren Datenformate angibt.  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispielcode wird mit der <xref:System.Windows.DataObject.GetFormats%2A>\-Überladung ein Zeichenfolgenarray abgerufen, das alle in einem Datenobjekt verfügbaren Datenformate \(systemeigene und automatisch konvertierbare\) angibt.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispielcode wird mit der <xref:System.Windows.DataObject.GetFormats%2A>\-Überladung ein Zeichenfolgenarray abgerufen, das nur die in einem Datenobjekt verfügbaren Datenformate angibt \(automatisch konvertierbare Datenformate werden gefiltert\).  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## Siehe auch  
 <xref:System.Windows.IDataObject>   
 [Übersicht über Drag & Drop](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)