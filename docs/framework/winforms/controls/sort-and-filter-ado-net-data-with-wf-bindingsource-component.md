---
title: "Gewusst wie: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ADO.NET [Windows Forms]"
  - "BindingSource-Komponente [Windows Forms], Sortieren und Filtern von Daten"
  - "Daten [Windows Forms], Filtern"
  - "Daten [Windows Forms], Sortieren"
  - "Datensortierung, ADO.NET"
  - "Filtern [Windows Forms], ADO.NET"
  - "Sortieren von Daten"
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms
Sie können die Sortier\- und Filterfunktion des <xref:System.Windows.Forms.BindingSource>\-Steuerelements über die <xref:System.Windows.Forms.BindingSource.Sort%2A>\-Eigenschaft und die <xref:System.Windows.Forms.BindingSource.Filter%2A>\-Eigenschaft verfügbar machen.  Einfaches Sortieren kann angewendet werden, wenn die zugrunde liegende Datenquelle eine <xref:System.ComponentModel.IBindingList> ist. Filtern und erweitertes Sortieren kann angewendet werden, wenn die Datenquelle eine <xref:System.ComponentModel.IBindingListView> ist.  Für die <xref:System.Windows.Forms.BindingSource.Sort%2A>\-Eigenschaft ist eine [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]\-Standardsyntax erforderlich: eine Zeichenfolge, die den Namen einer Datenspalte in der Datenquelle darstellt und auf die `ASC` oder `DESC` folgt, um festzulegen, ob die Liste in aufsteigender oder absteigender Reihenfolge sortiert wird.  Sie können das erweiterte Sortieren oder das mehrspaltige Sortieren festlegen, indem Sie jede Spalte mit einem Kommatrennzeichen trennen.  Die <xref:System.Windows.Forms.BindingSource.Filter%2A>\-Eigenschaft verwendet einen Zeichenfolgenausdruck.  
  
> [!NOTE]
>  Das Speichern vertraulicher Informationen, beispielsweise Kennwörter, innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.  Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows\-Authentifizierung \(wird auch als integrierte Sicherheit bezeichnet\) sicherer steuern.  Weitere Informationen finden Sie unter [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
### So filtern Sie Daten mit der BindingSource\-Komponente  
  
-   Legen Sie die <xref:System.Windows.Forms.BindingSource.Filter%2A>\-Eigenschaft auf den gewünschten Ausdruck fest.  
  
     Im folgenden Codebeispiel handelt es sich bei diesem Ausdruck um einen Spaltennamen, gefolgt von dem für diese Spalte gewünschten Wert.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### So sortieren Sie Daten mit der BindingSource\-Komponente  
  
1.  Legen Sie die <xref:System.Windows.Forms.BindingSource.Sort%2A>\-Eigenschaft auf den gewünschten Spaltennamen fest, gefolgt von `ASC` oder `DESC`, um anzugeben, ob absteigend oder aufsteigend sortiert werden soll.  
  
2.  Trennen Sie mehrere Spalten jeweils durch ein Komma.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## Beispiel  
 Im folgenden Codebeispiel werden Daten aus der Tabelle Customers der Beispieldatenbank Northwind in ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement geladen, und die angezeigten Daten werden gefiltert und sortiert.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## Kompilieren des Codes  
 Um dieses Beispiel auszuführen, fügen Sie den Code in ein Formular ein, das eine <xref:System.Windows.Forms.BindingSource> mit dem Namen `BindingSource1` und eine <xref:System.Windows.Forms.DataGridView> mit dem Namen `dataGridView1` enthält.  Behandeln Sie das <xref:System.Windows.Forms.Form.Load>\-Ereignis für das Formular, und rufen Sie in der Load\-Ereignishandlermethode `InitializeSortedFilteredBindingSource` auf.  
  
## Siehe auch  
 <xref:System.Windows.Forms.BindingSource.Sort%2A>   
 <xref:System.Windows.Forms.BindingSource.Filter%2A>   
 [Gewusst wie: Installieren von Beispieldatenbanken](../Topic/How%20to:%20Install%20Sample%20Databases.md)   
 [BindingSource\-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md)