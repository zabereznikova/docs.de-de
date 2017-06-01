---
title: "Gewusst wie: Binden des DataGrid-Steuerelements in Windows&#160;Forms an eine Datenquelle mithilfe des Designers | Microsoft Docs"
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
  - "Gebundene Steuerelemente"
  - "Gebundene Steuerelemente, DataGrid-Steuerelement"
  - "Datenbindung, DataGrid-Steuerelement"
  - "Datengebundene Steuerelemente, DataGrid"
  - "DataGrid-Steuerelement [Windows Forms], Datenbindung"
  - "Datasets [Windows Forms], Binden an DataGrid-Steuerelement"
  - "Windows Forms-Steuerelemente, Datenbindung"
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Binden des DataGrid-Steuerelements in Windows&#160;Forms an eine Datenquelle mithilfe des Designers
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGrid>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Das <xref:System.Windows.Forms.DataGrid>\-Steuerelement in Windows Forms wurde speziell für die Anzeige von Informationen aus einer Datenquelle entwickelt.  Sie binden das Steuerelement zur Entwurfszeit, indem Sie die <xref:System.Windows.Forms.DataGrid.DataSource%2A>\-Eigenschaft und die <xref:System.Windows.Forms.DataGrid.DataMember%2A>\-Eigenschaft festlegen oder zur Laufzeit die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\-Methode aufrufen.  Daten können aus einer Vielzahl von Datenquellen angezeigt werden. Die gebräuchlichsten sind jedoch DataSets und Datenansichten.  
  
 Wenn die Datenquelle zur Entwurfszeit verfügbar ist – wenn das Formular z. B. eine Instanz eines DataSets oder einer Datenansicht enthält – kann das Datenblatt zur Entwurfszeit an die Datenquelle gebunden werden.  Sie können dann eine Vorschau der Daten im Raster anzeigen lassen.  
  
 Das Datenblatt kann auch programmgesteuert zur Laufzeit gebunden werden.  Dies ist dann sinnvoll, wenn die Datenquelle anhand von Informationen festgelegt wird, die sich zur Laufzeit ergeben,  beispielsweise, wenn der Benutzer in der Anwendung den Namen der Tabelle angeben kann, die angezeigt werden soll.  Außerdem ist es in solchen Fällen notwendig, in denen die Datenquelle zur Entwurfszeit nicht vorhanden ist.  Dazu gehören Datenquellen wie Arrays, Auflistungen, nicht typisierte DataSets und Datenreader.  
  
 Für das folgende Verfahren wird ein Projekt vom Typ **Windows\-Anwendung** mit einem Formular benötigt, das ein <xref:System.Windows.Forms.DataGrid>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] ist das <xref:System.Windows.Forms.DataGrid>\-Steuerelement in der **Toolbox** standardmäßig nicht enthalten.  Weitere Informationen zum Hinzufügen dieses Steuerelements finden Sie unter [How to: Add Items to the Toolbox](http://msdn.microsoft.com/de-de/458e119e-17fe-450b-b889-e31c128bd7e0).  Zusätzlich können Sie in [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] das **Datenquellenfenster** verwenden, um Daten zur Entwurfszeit zu binden.  Weitere Informationen finden Sie unter [Binden von Steuerelementen an Daten in Visual Studio](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So binden Sie das DataGrid\-Steuerelement im Designer an eine einzelne Tabelle  
  
1.  Legen Sie für die <xref:System.Windows.Forms.DataGrid.DataSource%2A>\-Eigenschaft des Steuerelements das Objekt fest, das die Datenelemente enthält, an die die Bindung erfolgen soll.  
  
2.  Wenn es sich bei der Datenquelle um ein DataSet handelt, legen Sie für die <xref:System.Windows.Forms.DataGrid.DataMember%2A>\-Eigenschaft den Namen der Tabelle fest, an die die Bindung erfolgen soll.  
  
3.  Wenn es sich bei der Datenquelle um ein DataSet oder eine auf einer DataSet\-Tabelle beruhende Datenansicht handelt, fügen Sie dem Formular Code zum Füllen des DataSets hinzu.  
  
     Der genaue Code richtet sich dabei danach, woher das DataSet die Daten bezieht.  Wenn ein DataSet direkt aus einer Datenbank gefüllt wird, wird üblicherweise die `Fill`\-Methode eines Datenadapters aufgerufen, wie in folgendem Codebeispiel, in dem das DataSet `DsCategories1` gefüllt wird:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  \(Optional\) Weisen Sie dem Raster die gewünschten Tabellen\- und Spaltenformate zu.  
  
     Die Tabelle wird zwar auch ohne Tabellenformate angezeigt, jedoch mit einer minimalen Formatierung und allen vorhandenen Spalten.  
  
### So binden Sie das DataGrid\-Steuerelement im Designer an mehrere Tabellen in einem DataSet  
  
1.  Legen Sie für die <xref:System.Windows.Forms.DataGrid.DataSource%2A>\-Eigenschaft des Steuerelements das Objekt fest, das die Datenelemente enthält, an die die Bindung erfolgen soll.  
  
2.  Wenn das DataSet verknüpfte Tabellen enthält, d. h. ein Beziehungsobjekt, legen Sie für die <xref:System.Windows.Forms.DataGrid.DataMember%2A>\-Eigenschaft den Namen der übergeordneten Tabelle fest.  
  
3.  Schreiben Sie Code, um das DataSet aufzufüllen.  
  
## Siehe auch  
 [Übersicht über das DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Datenbindung in Web Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Zugreifen auf Daten in Visual Studio](../Topic/Accessing%20data%20in%20Visual%20Studio.md)