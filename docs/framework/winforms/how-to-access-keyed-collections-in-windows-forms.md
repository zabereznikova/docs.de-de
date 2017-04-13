---
title: "Gewusst wie: Zugreifen auf verschl&#252;sselte Auflistungen in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Auflistungen, Zugreifen mit Schlüsseln"
  - "Schlüsselgebundene Auflistungen [Windows Forms]"
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Zugreifen auf verschl&#252;sselte Auflistungen in Windows Forms
-   Sie können auf einzelne Auflistungselemente mithilfe von Schlüsseln zugreifen.  Diese Funktionalität wurde vielen Auflistungsklassen hinzugefügt, die üblicherweise von Windows Forms\-Anwendungen verwendet werden.  In der folgende Liste werden einige Auflistungsklassen angezeigt, die über zugreifbare verschlüsselte Auflistungen verfügen:  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 Der einem Element in einer Auflistung zugeordnete Schlüssel ist in der Regel der Name des Elements.  Mithilfe des folgenden Verfahrens wird die Verwendung von Auflistungsklassen zur Durchführung von allgemeinen Aufgaben veranschaulicht.  
  
### So suchen Sie nach einem geschachtelten Steuerelement in einer Steuerelementauflistung und legen den Fokus auf dieses fest.  
  
-   Verwenden Sie die <xref:System.Windows.Forms.Control.ControlCollection.Find%2A>\-Methode und die <xref:System.Windows.Forms.Control.Focus%2A>\-Methode, um den Namen des gesuchten Steuerelements anzugeben und den Fokus darauf festzulegen.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### So greifen Sie in einer Bildauflistung auf ein Bild zu  
  
-   Verwenden Sie die <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A>\-Eigenschaft, um den Namen des Bildes anzugeben, auf das Sie zugreifen möchten.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### So legen Sie eine Registerkarte als ausgewählte Registerkarte fest  
  
-   Verwenden Sie die <xref:System.Windows.Forms.TabControl.SelectedTab%2A>\-Eigenschaft gemeinsam mit der <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A>\-Eigenschaft, um den Namen der Registerkarte anzugeben und diese als ausgewählte Registerkarte festzulegen.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## Siehe auch  
 [Erste Schritte mit Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)   
 [Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList\-Komponente in Windows Forms](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)