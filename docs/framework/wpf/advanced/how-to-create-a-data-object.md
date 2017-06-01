---
title: "Gewusst wie: Erstellen eines Datenobjekts | Microsoft Docs"
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
  - "Datenobjekte [WPF], Erstellen"
  - "DataObject-Klasse [WPF], Erstellen"
  - "Drag & Drop [WPF], Erstellen von Datenobjekten"
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Erstellen eines Datenobjekts
Im folgenden Beispiel werden verschiedene Möglichkeiten gezeigt, wie Sie Datenobjekte mithilfe der von der <xref:System.Windows.DataObject>\-Klasse bereitgestellten Konstruktoren erstellen.  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispielcode wird ein neues Datenobjekt erstellt. Außerdem wird mithilfe von einem der überladenen Konstruktoren \(<xref:System.Windows.DataObject.%23ctor%28System.Object%29>\) das Datenobjekt mit einer Zeichenfolge initialisiert.  In diesem Fall wird ein geeignetes Datenformat automatisch anhand des Typs der gespeicherten Daten bestimmt, und das automatische Konvertieren der gespeicherten Daten ist in der Standardeinstellung zulässig.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### Beschreibung  
 Der folgende Beispielcode ist eine verkürzte Version des obigen Codes.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispielcode wird ein neues Datenobjekt erstellt. Außerdem wird mithilfe von einem der überladenen Konstruktoren \(<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>\) das Datenobjekt mit einer Zeichenfolge und einem angegebenen Datenformat initialisiert.  In diesem Fall wird das Datenformat durch eine Zeichenfolge angegeben. Die <xref:System.Windows.DataFormats>\-Klasse stellt einen Satz vordefinierter Typzeichenfolgen bereit.  Das automatische Konvertieren der gespeicherten Daten wird standardmäßig zugelassen.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### Beschreibung  
 Der folgende Beispielcode ist eine verkürzte Version des obigen Codes.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispielcode wird ein neues Datenobjekt erstellt. Außerdem wird mithilfe von einem der überladenen Konstruktoren \(<xref:System.Windows.DataObject.%23ctor%2A>\) das Datenobjekt mit einer Zeichenfolge und einem angegebenen Datenformat initialisiert.  In diesem Fall wird das Datenformat von einem <xref:System.Type>\-Parameter angegeben.  Das automatische Konvertieren der gespeicherten Daten wird standardmäßig zugelassen.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### Beschreibung  
 Der folgende Beispielcode ist eine verkürzte Version des obigen Codes.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispielcode wird ein neues Datenobjekt erstellt. Außerdem wird mithilfe von einem der überladenen Konstruktoren \(<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>\) das Datenobjekt mit einer Zeichenfolge und einem angegebenen Datenformat initialisiert.  In diesem Fall wird das Datenformat durch eine Zeichenfolge angegeben. Die <xref:System.Windows.DataFormats>\-Klasse stellt einen Satz vordefinierter Typzeichenfolgen bereit.  Mit dieser spezifischen Konstruktorüberladung kann der Aufrufer angeben, ob eine automatische Konvertierung zulässig ist.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### Beschreibung  
 Der folgende Beispielcode ist eine verkürzte Version des obigen Codes.  
  
### Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## Siehe auch  
 <xref:System.Windows.IDataObject>