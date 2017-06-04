---
title: "Gewusst wie: Hinzuf&#252;gen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows&#160;Forms mithilfe des Designers | Microsoft Docs"
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
  - "Spalten [Windows Forms], Hinzufügen zum DataGrid-Steuerelement"
  - "DataGrid-Steuerelement [Windows Forms], Hinzufügen von Tabellen und Spalten"
  - "Tabellen [Windows Forms], Hinzufügen zum DataGrid-Steuerelement"
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Hinzuf&#252;gen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows&#160;Forms mithilfe des Designers
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGrid>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Sie können Daten im <xref:System.Windows.Forms.DataGrid>\-Steuerelement von Windows Forms in Tabellen und Spalten anzeigen, indem Sie <xref:System.Windows.Forms.DataGridTableStyle>\-Objekte erstellen und diese dem <xref:System.Windows.Forms.GridTableStylesCollection>\-Objekt hinzufügen, auf das Sie mithilfe der <xref:System.Windows.Forms.DataGrid.TableStyles%2A>\-Eigenschaft des <xref:System.Windows.Forms.DataGrid>\-Steuerelements zugreifen.  In allen Tabellenformaten wird der Inhalt der Datentabelle angezeigt, die Sie in der <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>\-Eigenschaft von <xref:System.Windows.Forms.DataGridTableStyle> festgelegt haben.  Standardmäßig zeigt ein Tabellenformat, in dem keine Spaltenformate festgelegt sind, alle Spalten der Datentabelle an.  Sie können einschränken, welche Tabellenspalten angezeigt werden, indem Sie <xref:System.Windows.Forms.DataGridColumnStyle>\-Objekte zu <xref:System.Windows.Forms.GridColumnStylesCollection> hinzufügen. Auf diese Auflistung wird jeweils über die <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>\-Eigenschaft von <xref:System.Windows.Forms.DataGridTableStyle> zugegriffen.  
  
 Für die folgenden Verfahren wird ein Projekt vom Typ **Windows\-Anwendung** mit einem Formular benötigt, das ein <xref:System.Windows.Forms.DataGrid>\-Steuerelement enthält.  Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] ist das <xref:System.Windows.Forms.DataGrid>\-Steuerelement in der **Toolbox** standardmäßig nicht enthalten.  Weitere Informationen zum Hinzufügen dieses Steuerelements finden Sie unter [How to: Add Items to the Toolbox](http://msdn.microsoft.com/de-de/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So fügen Sie dem DataGrid\-Steuerelement im Designer eine Tabelle hinzu  
  
1.  Um in der Tabelle Daten anzeigen zu können, müssen Sie das <xref:System.Windows.Forms.DataGrid>\-Steuerelement zunächst an ein DataSet binden.  Weitere Informationen finden Sie unter [Gewusst wie: Binden des DataGrid\-Steuerelements in Windows Forms an eine Datenquelle mithilfe des Designers](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).  
  
2.  Wählen Sie im Eigenschaftenfenster die <xref:System.Windows.Forms.DataGrid.TableStyles%2A>\-Eigenschaft des <xref:System.Windows.Forms.DataGrid>\-Steuerelements aus, und klicken Sie neben der Eigenschaft auf die Schaltfläche mit den Auslassungspunkten \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), um den **DataGridTableStyle\-Auflistungs\-Editor** anzuzeigen.  
  
3.  Klicken Sie zum Einfügen eines Tabellenformats im Auflistungs\-Editor auf **Hinzufügen**.  
  
4.  Klicken Sie zum Schließen des Auflistungs\-Editors auf **OK**, und öffnen Sie ihn erneut, indem Sie neben der <xref:System.Windows.Forms.DataGrid.TableStyles%2A>\-Eigenschaft auf die Schaltfläche mit den Auslassungspunkten klicken.  
  
     Wenn Sie den Auflistungs\-Editor erneut öffnen, werden sämtliche an das Steuerelement gebundenen Datentabellen in der Dropdownliste für die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>\-Eigenschaft des Tabellenformats angezeigt.  
  
5.  Klicken Sie im **Members**\-Feld des Auflistungs\-Editors auf das Tabellenformat.  
  
6.  Wählen Sie im Feld **Eigenschaften** des Auflistungs\-Editors den <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>\-Wert für die anzuzeigende Tabelle.  
  
### So fügen Sie dem DataGrid\-Steuerelement im Designer eine Spalte hinzu  
  
1.  Wählen Sie im **Members**\-Feld des **DataGridTableStyle**\-Auflistungs\-Editors das gewünschte Tabellenformat.  Wählen Sie im Feld **Eigenschaften** des Auflistungs\-Editors die <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>\-Auflistung, und klicken Sie dann neben der Eigenschaft auf die Schaltfläche mit den Auslassungspunkten \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), um den **DataGridColumnStyle\-Auflistungs\-Editor** anzuzeigen.  
  
2.  Um ein Spaltenformat einzufügen, klicken Sie im Auflistungs\-Editor auf **Hinzufügen**, und um einen Spaltentyp anzugeben, klicken Sie neben **Hinzufügen** auf den nach unten weisenden Pfeil.  
  
     Im Dropdownfeld können Sie entweder den <xref:System.Windows.Forms.DataGridTextBoxColumn>\-Typ oder den <xref:System.Windows.Forms.DataGridBoolColumn>\-Typ auswählen.  
  
3.  Klicken Sie zum Schließen des **DataGridColumnStyle\-Auflistungs\-Editors** auf OK, und öffnen Sie ihn erneut, indem Sie neben der <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>\-Eigenschaft auf die Schaltfläche mit den Auslassungspunkten klicken.  
  
     Wenn Sie den Auflistungs\-Editor erneut öffnen, werden sämtliche Datenspalten in der gebundenen Datentabelle in der Dropdownliste für die <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A>\-Eigenschaft des Tabellenformats angezeigt.  
  
4.  Klicken Sie im **Members**\-Feld des Auflistungs\-Editors auf das Spaltenformat.  
  
5.  Wählen Sie im Feld **Eigenschaften** des Auflistungs\-Editors den <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A>\-Wert für die anzuzeigende Spalte.  
  
## Siehe auch  
 [DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)