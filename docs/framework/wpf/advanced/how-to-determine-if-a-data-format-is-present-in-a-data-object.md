---
title: "Gewusst wie: Feststellen, ob ein Datenformat in einem Datenobjekt vorhanden ist | Microsoft Docs"
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
  - "Datenformate [WPF], Feststellen des Vorhandenseins"
  - "DataFormats-Klasse [WPF]"
  - "Drag & Drop [WPF], Vorhandene Datenformate"
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Feststellen, ob ein Datenformat in einem Datenobjekt vorhanden ist
Im folgenden Beispiel wird veranschaulicht, wie mit den verschiedenen <xref:System.Windows.DataObject.GetDataPresent%2A>\-Methodenüberladungen abgefragt wird, ob ein bestimmtes Datenformat in einem Datenobjekt vorhanden ist.  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispielcode wird mit der <xref:System.Windows.DataObject.GetDataPresent%28System.String%29>\-Überladung das Vorhandensein eines bestimmten Datenformats mithilfe einer Deskriptorzeichenfolge abgefragt.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispielcode wird mit der <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29>\-Überladung das Vorhandensein eines bestimmten Datenformats mithilfe eines Typs abgefragt.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispielcode wird mit der <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29>\-Überladung eine Abfrage auf Daten mit einer Deskriptorzeichenfolge ausgeführt, und es wird angegeben, wie Datenformate behandelt werden sollen, die automatisch konvertiert werden können.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## Siehe auch  
 <xref:System.Windows.IDataObject>