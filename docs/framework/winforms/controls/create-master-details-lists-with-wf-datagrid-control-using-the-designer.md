---
title: "Gewusst wie: Erstellen von Master-/Detaillisten mit dem DataGrid-Steuerelement in Windows&#160;Forms mithilfe des Designers | Microsoft Docs"
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
  - "DataGrid-Steuerelement [Windows Forms], Master/Detail-Listen"
  - "Master/Detail-Listen"
  - "Verknüpfte Tabellen, Anzeigen in DataGrid-Steuerelementen"
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Erstellen von Master-/Detaillisten mit dem DataGrid-Steuerelement in Windows&#160;Forms mithilfe des Designers
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGrid>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Wenn <xref:System.Data.DataSet> mehrere verwandte Tabellen enthält, können Sie mit zwei <xref:System.Windows.Forms.DataGrid>\-Steuerelementen die Daten im Master\-\/Detailformat anzeigen.  Ein <xref:System.Windows.Forms.DataGrid> wird als Masterraster, das andere als Detailraster festgelegt.  Wenn Sie einen Eintrag in der Masterliste auswählen, werden auch alle zugehörigen Einträge in der Detailliste angezeigt.  Wenn <xref:System.Data.DataSet> beispielsweise die Tabelle Customers enthält, der eine Tabelle Orders zugeordnet ist, können Sie die Tabelle Customers als Masterraster und die Tabelle Orders als Detailraster festlegen.  Wenn ein Kunde aus dem Masterraster ausgewählt wurde, werden alle diesem Kunden zugeordneten Bestellungen in der Tabelle **Bestellungen** im Detailraster angezeigt.  
  
 Im folgenden Verfahren wird ein Projekt vom Typ **Windows\-Anwendung** benötigt.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie eine Master\-\/Detailliste im Designer  
  
1.  Fügen Sie dem Formular zwei <xref:System.Windows.Forms.DataGrid>\-Steuerelemente hinzu.  Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] ist das <xref:System.Windows.Forms.DataGrid>\-Steuerelement in der **Toolbox** standardmäßig nicht enthalten.  Weitere Informationen finden Sie unter [How to: Add Items to the Toolbox](http://msdn.microsoft.com/de-de/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
    > [!NOTE]
    >  Die folgenden Schritte gelten nicht für [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], da in diesem Fall das **Datenquellenfenster** für die Datenbindung zur Entwurfszeit verwendet wird.  Weitere Informationen finden Sie unter [Binden von Steuerelementen an Daten in Visual Studio](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md) und unter [Gewusst wie: Anzeigen von verknüpften Daten in einer Windows Forms\-Anwendung](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md).  
  
2.  Ziehen Sie mindestens zwei Tabellen aus dem **Server\-Explorer** in das Formular.  
  
3.  Wählen Sie im Menü **Daten** die Option **DataSet generieren**.  
  
4.  Legen Sie die Beziehungen zwischen den Tabellen mithilfe des XML\-Designers fest.  Ausführliche Informationen finden Sie auf MSDN unter "Gewusst wie: Erstellen von 1:n\-Beziehungen in XML\-Schemas und Datasets".  
  
5.  Klicken Sie im Menü **Datei** auf **Alle speichern**, um die Beziehungen zu speichern.  
  
6.  Richten Sie das gewünschte <xref:System.Windows.Forms.DataGrid>\-Steuerelement wie folgt für das Masterraster ein:  
  
    1.  Wählen Sie <xref:System.Data.DataSet> aus der Dropdownliste der <xref:System.Windows.Forms.DataGrid.DataSource%2A>\-Eigenschaft aus.  
  
    2.  Wählen Sie die Mastertabelle \(beispielsweise "Customers"\) aus der Dropdownliste der <xref:System.Windows.Forms.DataGrid.DataMember%2A>\-Eigenschaft aus.  
  
7.  Richten Sie das gewünschte <xref:System.Windows.Forms.DataGrid>\-Steuerelement wie folgt für das Detailraster ein:  
  
    1.  Wählen Sie <xref:System.Data.DataSet> aus der Dropdownliste der <xref:System.Windows.Forms.DataGrid.DataSource%2A>\-Eigenschaft aus.  
  
    2.  Wählen Sie die Beziehung zwischen der Master\- und der Detailtabelle \(beispielsweise "Customers.CustOrd"\) aus der Dropdownliste der <xref:System.Windows.Forms.DataGrid.DataMember%2A>\-Eigenschaft aus.  Sie müssen den Knoten erweitern, damit die Beziehung angezeigt wird. Klicken Sie in der Dropdownliste auf das Pluszeichen \(**\+**\) neben der Mastertabelle.  
  
## Siehe auch  
 [DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Übersicht über das DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [Gewusst wie: Binden des DataGrid\-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)   
 [Binden von Steuerelementen an Daten in Visual Studio](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md)