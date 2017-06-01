---
title: "Gewusst wie: Binden von Daten an das DataGridView-Steuerelement in Windows Forms mithilfe des Designers | Microsoft Docs"
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
  - "Datenquellen, Bindung an Windows Forms-Steuerelemente"
  - "DataGridView-Steuerelement [Windows Forms], Datenbindung"
  - "Windows Forms-Steuerelemente, Binden an eine Datenquelle"
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Gewusst wie: Binden von Daten an das DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Mit dem Designer können Sie ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement an verschiedene Datenquellen binden, z. B. an Datenbanken, Geschäftsobjekte oder Webdienste.  Wenn Sie das Steuerelement mit dem Designer an eine Datenquelle binden, wird es automatisch an eine <xref:System.Windows.Forms.BindingSource>\-Komponente gebunden, die der Datenquelle entspricht.  Des Weiteren werden gemäß den von der Datenquelle bereitgestellten Schemainformationen automatisch Spalten im Steuerelement generiert.  
  
 Nachdem Spalten generiert wurden, können Sie sie an Ihre Anforderungen anpassen.  Beispielsweise können Sie Spalten, die Sie nicht interessieren, entfernen oder ausblenden, die Spalten neu anordnen oder die Spaltentypen ändern.  Weitere Informationen über das Ändern von Spalten finden Sie im Abschnitt mit den weiterführenden Themen.  
  
 Sie können auch mehrere <xref:System.Windows.Forms.DataGridView>\-Steuerelemente an verknüpfte Tabellen binden, um Master\/Detail\-Beziehungen herzustellen.  Bei dieser Konfiguration zeigt ein Steuerelement eine übergeordnete Tabelle an, und ein anderes Steuerelement zeigt nur die Zeilen in einer untergeordneten Tabelle an, die in Beziehung zu der aktuellen Zeile in der übergeordneten Tabelle stehen.  Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen von verknüpften Daten in einer Windows Forms\-Anwendung](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md).  
  
 Für das folgende Verfahren wird ein Projekt vom Typ **Windows\-Anwendung** mit einem Formular benötigt, das ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement bzw. zwei Steuerelemente für eine Master\/Detail\-Beziehung enthält.  Informationen zum Starten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So binden Sie das Steuerelement an eine Datenquelle  
  
1.  Klicken Sie auf das Smarttagsymbol \(![Smarttag&#45;Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) in der rechten oberen Ecke des <xref:System.Windows.Forms.DataGridView>\-Steuerelements.  
  
2.  Klicken Sie auf den Dropdownpfeil für die Option **Datenquelle auswählen**.  
  
3.  Wenn Ihr Projekt noch nicht über eine Datenquelle verfügt, klicken Sie auf **Projektdatenquelle hinzufügen**, und führen Sie die im Assistenten angezeigten Schritte aus.  
  
     Weitere Informationen finden Sie unter [Assistent zum Konfigurieren von Datenquellen](../Topic/Data%20Source%20Configuration%20Wizard.md).  Die neue Datenquelle wird im Dropdownfenster **Datenquelle auswählen** angezeigt.  Wenn die neue Datenquelle nur einen Member enthält \(z. B. eine einzelne Datenbanktabelle\), wird das Steuerelement automatisch an diesen Member gebunden.  Fahren Sie andernfalls mit dem nächsten Schritt fort.  
  
4.  Erweitern Sie die Knoten **Weitere Datenquellen** und **Projektdatenquellen**, sofern diese noch nicht erweitert sind, und wählen Sie anschließend die Datenquelle aus, an die das Steuerelement gebunden werden soll.  
  
5.  Wenn die Datenquelle mehrere Member enthält \(wenn Sie beispielsweise einen <xref:System.Data.DataSet?displayProperty=fullName> mit mehreren Tabellen erstellt haben\), erweitern Sie die Datenquelle und wählen den Member aus, an den gebunden werden soll.  
  
6.  Um eine Master\/Detail\-Beziehung zu erstellen, erweitern Sie im Dropdownfenster **Datenquelle auswählen** eines zweiten <xref:System.Windows.Forms.DataGridView>\-Steuerelements die für die übergeordnete Tabelle erstellte <xref:System.Windows.Forms.BindingSource>, und wählen Sie dann in der angezeigten Liste die gewünschte untergeordnete Tabelle aus.  
  
    > [!NOTE]
    >  Wenn das Projekt bereits über eine Datenquelle verfügt, haben Sie zusätzlich die Möglichkeit, über das **Datenquellenfenster** ein Datenformular zu erstellen.  Weitere Informationen finden Sie unter [Datenquellenfenster](../Topic/Data%20Sources%20Window.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName>   
 [Gewusst wie: Herstellen einer Verbindung zu Daten in einer Datenbank](../Topic/How%20to:%20Connect%20to%20Data%20in%20a%20Database.md)   
 [Gewusst wie: Hinzufügen und Entfernen von Spalten im DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [Gewusst wie: Ändern der Reihenfolge von Spalten des DataGridView\-Steuerelements in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)   
 [Gewusst wie: Ändern des Typs einer DataGridView\-Spalte in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)   
 [Gewusst wie: Fixieren von Spalten im DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)   
 [Gewusst wie: Ausblenden von Spalten im DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)   
 [Gewusst wie: Festlegen von schreibgeschützten Spalten im DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)   
 [Datenquellenfenster](../Topic/Data%20Sources%20Window.md)   
 [Gewusst wie: Anzeigen von verknüpften Daten in einer Windows Forms\-Anwendung](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md)