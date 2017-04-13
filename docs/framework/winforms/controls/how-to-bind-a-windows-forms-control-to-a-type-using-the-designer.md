---
title: "Gewusst wie: Binden eines Windows Forms-Steuerelements an einen Typ mithilfe des Designers | Microsoft Docs"
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
  - "BindingSource-Komponente [Windows Forms], Binden an einen Typ"
  - "Steuerelemente [Windows Forms], Binden an einen Typ"
  - "Typen [Windows Forms], Binden von Steuerelementen an"
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Binden eines Windows Forms-Steuerelements an einen Typ mithilfe des Designers
Wenn Sie Steuerelemente erstellen, die mit Daten interagieren, ist es zeitweise erforderlich, ein Steuerelement an einen Typ anstatt an ein Objekt zu binden.  Steuerelemente müssen normalerweise zur Entwurfszeit an einen Typ gebunden werden, wenn vielleicht keine Daten verfügbar sind, Sie aber trotzdem Daten aus der öffentlichen Schnittstelle eines Typs in datengebundenen Steuerelementen anzeigen möchten.  In den folgenden Verfahren wird veranschaulicht, wie Sie eine neue an einen Typ gebundene <xref:System.Windows.Forms.BindingSource> erstellen und dann eine der Eigenschaften des Typs an die <xref:System.Windows.Forms.TextBox.Text%2A>\-Eigenschaft von <xref:System.Windows.Forms.TextBox> binden.  
  
### So binden Sie BindingSource an einen Typ  
  
1.  Erstellen Sie ein Windows Forms\-Projekt.  
  
     Weitere Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Ziehen Sie in der **Entwurfsansicht** eine <xref:System.Windows.Forms.BindingSource>\-Komponente auf das Formular.  
  
3.  Klicken Sie im **Eigenschaftenfenster** auf den Pfeil neben der <xref:System.Windows.Forms.BindingSource.DataSource%2A>\-Eigenschaft.  
  
4.  Klicken Sie im **DataSource\-Benutzeroberflächentyp\-Editor** auf **Projektdatenquelle hinzufügen**.  
  
5.  Wählen Sie auf der Seite **Datenquellentyp auswählen** die Option **Objekt** aus, und klicken Sie dann auf **Weiter**.  
  
6.  Wählen Sie den Typ aus, an den die Bindung erfolgen soll:  
  
    -   Wenn sich der Typ, an den Sie die Bindung vornehmen möchten, im aktuellen Projekt befindet oder die Assembly, in der der Typ enthalten ist, bereit als Verweis hinzugefügt wurde, erweitern Sie die Knoten, um den gewünschten Typ zu suchen, und wählen ihn aus.  
  
         \- oder \-  
  
    -   Wenn sich der Typ, an den Sie die Bindung vornehmen möchten, in einer anderen Assembly enthalten ist, die derzeit nicht in der Verweisliste enthalten ist, klicken Sie auf **Verweis hinzufügen** und dann auf die Registerkarte **Projekte**.  Wählen Sie das Projekt aus, das das gewünschte Geschäftsobjekt enthält, und klicken Sie auf **OK**.  Dieses Projekt wird in der Assemblyliste angezeigt. Sie können die Knoten erweitern, um den gewünschten Typ zu suchen und auszuwählen.  
  
        > [!NOTE]
        >  Wenn Sie eine Bindung an einen Typ in einem Framework oder einer Microsoft\-Assembly vornehmen möchten, deaktivieren Sie das Kontrollkästchen **Assemblys ausblenden, die mit "Microsoft" oder "System" beginnen**.  
  
7.  Klicken Sie auf **Weiter** und anschließend auf **Fertig stellen**.  
  
### So binden Sie das Steuerelement an BindingSource  
  
1.  Fügen Sie dem Formular <xref:System.Windows.Forms.TextBox> hinzu.  
  
2.  Erweitern Sie im **Eigenschaftenfenster** den Knoten **\(DataBindings\)**.  
  
3.  Klicken Sie auf den Pfeil neben der <xref:System.Windows.Forms.TextBox.Text%2A>\-Eigenschaft.  
  
4.  Erweitern Sie im **DataSource\-Benutzeroberflächentyp\-Editor** den Knoten für die zuvor hinzugefügte <xref:System.Windows.Forms.BindingSource>, und wählen Sie die Eigenschaft des gebundenen Typs aus, den Sie an die <xref:System.Windows.Forms.TextBox.Text%2A>\-Eigenschaft von <xref:System.Windows.Forms.TextBox> binden möchten.  
  
## Siehe auch  
 [BindingSource\-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Gewusst wie: Binden eines Windows Forms\-Steuerelements an einen Typ](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)   
 [Binden von Steuerelementen an Daten in Visual Studio](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md)