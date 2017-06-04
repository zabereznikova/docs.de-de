---
title: "Gewusst wie: Erstellen eines Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "02/15/2017"
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
  - "DataGridView-Steuerelement [Windows Forms], Master/Detail-Formular"
  - "Master/Detail-Listen, Erstellen"
  - "Übergeordnete/untergeordnete Tabellen, Anzeigen in Windows Forms"
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Gewusst wie: Erstellen eines Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms
Im folgenden Codebeispiel wird ein Master\-\/Detailformular mit zwei <xref:System.Windows.Forms.DataGridView>\-Steuerelementen erstellt, die an zwei <xref:System.Windows.Forms.BindingSource>\-Komponenten gebunden sind.  Die Datenquelle ist ein <xref:System.Data.DataSet>, das die Tabellen `Customers` und `Orders` aus der SQL Server\-Beispieldatenbank "Northwind" sowie eine <xref:System.Data.DataRelation> enthält, mit der die beiden Tabellen über die Spalte `CustomerID` in Beziehung gesetzt werden.  
  
 Eine <xref:System.Windows.Forms.BindingSource> ist an die übergeordnete `Customers`\-Tabelle im DataSet gebunden.  Diese Daten werden im <xref:System.Windows.Forms.DataGridView>\-Mastersteuerelement angezeigt.  Die andere <xref:System.Windows.Forms.BindingSource> ist an die erste Datenverbindung gebunden.  Die <xref:System.Windows.Forms.BindingSource.DataMember%2A>\-Eigenschaft der zweiten <xref:System.Windows.Forms.BindingSource> ist auf den Namen der <xref:System.Data.DataRelation> festgelegt.  Dadurch zeigt das zugeordnete <xref:System.Windows.Forms.DataGridView>\-Detailsteuerelement die Zeilen der untergeordneten `Orders`\-Tabelle an, die der aktuellen Zeile im <xref:System.Windows.Forms.DataGridView>\-Mastersteuerelement entsprechen.  
  
 Eine vollständige Erläuterung dieses Codebeispiels finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines Master\-\/Detailformulars mit zwei DataGridView\-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagrids.md).  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Windows.Forms" und "System.XML".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## .NET Framework-Sicherheit  
 Das Speichern vertraulicher Informationen \(z. B. eines Kennworts\) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.  Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows\-Authentifizierung \(wird auch als integrierte Sicherheit bezeichnet\) sicherer steuern.  Weitere Informationen finden Sie unter [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Exemplarische Vorgehensweise: Erstellen eines Master\-\/Detailformulars mit zwei DataGridView\-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagrids.md)   
 [Anzeigen von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md)