---
title: "Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms mithilfe des Designers | Microsoft Docs"
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
  - "Gruppieren"
  - "Gruppen, In Windows Forms-Steuerelementen"
  - "ListView-Steuerelement [Windows Forms], Gruppieren von Elementen"
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms mithilfe des Designers
Das Gruppierungsfeature des <xref:System.Windows.Forms.ListView>\-Steuerelements ermöglicht es Ihnen, verwandte Elemente in Gruppen anzuzeigen.  Diese Gruppen werden auf dem Bildschirm durch horizontale Gruppenheader getrennt, die die Gruppentitel enthalten.  Sie können <xref:System.Windows.Forms.ListView>\-Gruppen verwenden, um das Navigieren in umfangreichen Listen zu vereinfachen, indem Sie Elemente alphabetisch, nach Datum oder nach einem anderen logischen Gruppierungsmerkmal gruppieren.  In der folgenden Abbildung werden einige gruppierte Elemente angezeigt.  
  
 ![ListView&#45;Gruppen](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
  
 Für das folgende Verfahren wird ein Projekt vom Typ **Windows\-Anwendung** mit einem Formular benötigt, das ein <xref:System.Windows.Forms.ListView>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
 Zur Aktivierung der Gruppierung müssen Sie zunächst im Designer oder programmgesteuert mindestens ein <xref:System.Windows.Forms.ListViewGroup>\-Objekt erstellen.  Nachdem eine Gruppe definiert wurde, können Sie ihr Elemente zuweisen.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView>\-Gruppen sind in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] nur verfügbar, wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>\-Methode aufruft.  Auf älteren Betriebssystemen ist Code in Zusammenhang mit Gruppen unwirksam; folglich werden keine Gruppen angezeigt.  Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=fullName>.  
>   
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So fügen Sie im Designer Gruppen hinzu oder entfernen sie  
  
1.  Klicken Sie im **Eigenschaftenfenster** auf die Schaltfläche mit dem **Auslassungszeichen** \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), die sich neben der <xref:System.Windows.Forms.ListView.Groups%2A>\-Eigenschaft befindet.  
  
     Der **ListViewItem\-Auflistungs\-Editor** wird angezeigt.  
  
2.  Klicken Sie auf die Schaltfläche **Hinzufügen**, um eine Gruppe hinzuzufügen.  Im Anschluss können Sie die Eigenschaften der neuen Gruppe festlegen, z. B. <xref:System.Windows.Forms.ListViewGroup.Header%2A> und <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>.  Um eine Gruppe zu entfernen, wählen Sie sie aus und klicken auf die Schaltfläche **Entfernen**.  
  
### So weisen Sie Gruppen im Designer Elemente zu  
  
1.  Klicken Sie im **Eigenschaftenfenster** auf die Schaltfläche mit dem **Auslassungszeichen** \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), die sich neben der <xref:System.Windows.Forms.ListView.Items%2A>\-Eigenschaft befindet.  
  
     Der **ListViewItem**\-Auflistungs\-Editor wird angezeigt.  
  
2.  Klicken Sie auf die Schaltfläche **Hinzufügen**, um ein neues Element hinzuzufügen.  Im Anschluss können Sie die Eigenschaften des neuen Elements festlegen, z. B. <xref:System.Windows.Forms.ListViewItem.Text%2A> und <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.  
  
3.  Wählen Sie die <xref:System.Windows.Forms.ListViewItem.Group%2A>\-Eigenschaft und aus der dazugehörigen Dropdownliste eine Gruppe aus.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.Groups%2A>   
 <xref:System.Windows.Forms.ListViewGroup>   
 [ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Übersicht über das ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/de-de/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)   
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)