---
title: "Zusammenf&#252;hren von Men&#252;elementen im MenuStrip-Steuerelement von Windows Forms | Microsoft Docs"
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
  - "MenuStrip, Zusammenführen"
  - "Zusammenführen, Allgemeine Konzepte"
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Zusammenf&#252;hren von Men&#252;elementen im MenuStrip-Steuerelement von Windows Forms
In einer MDI\-\(Multiple Document Interface\-\)Anwendung können Sie Menüelemente oder vollständige Menüs aus dem untergeordneten Formular mit den Menüs aus dem übergeordneten Formular zusammenführen.  
  
 In diesem Thema werden die Grundbegriffe des Zusammenführens von Menüelementen in einer MDI\-Anwendung beschrieben.  
  
## Allgemeine Konzepte  
 Zusammenführungsverfahren schließen sowohl ein Ziel\- als auch eine Quellsteuerelement ein:  
  
-   Das Ziel ist das <xref:System.Windows.Forms.MenuStrip>\-Steuerelement im Hauptformular oder im übergeordneten MDI\-Formular, in dem Menüelemente zusammengeführt werden sollen.  
  
-   Die Quelle ist das <xref:System.Windows.Forms.MenuStrip>\-Steuerelement im untergeordneten MDI\-Formular, in dem die Menüelemente enthalten sind, die Sie in das Zielmenü überführen möchten.  
  
 Die <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>\-Eigenschaft identifiziert das Menüelement im aktuellen übergeordneten MDI\-Formular, in dessen Dropdownliste die Titel der untergeordneten MDI\-Formulare eingefügt werden.  Beispielsweise werden in der Regel die untergeordneten MDI\-Elemente aufgelistet, die derzeit im Menü **Fenster** geöffnet sind.  
  
 Die <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A>\-Eigenschaft identifiziert die Menüelemente, die aus einem <xref:System.Windows.Forms.MenuStrip> eines untergeordneten MDI\-Formulars stammen.  
  
 Menüelemente können manuell oder automatisch zusammengeführt werden.  In beiden Fällen werden die Menüelemente auf die gleiche Weise zusammengeführt, die Zusammenführung wird jedoch unterschiedlich aktiviert. Dies wird in den Abschnitten "Manuelles Zusammenführen" und "Automatisches Zusammenführen" in diesem Thema behandelt.  Sowohl beim manuellen als auch beim automatischen Zusammenführen beeinflusst jeder Zusammenführungsvorgang den nächsten Zusammenführungsvorgang.  
  
 Beim Zusammenführen mit <xref:System.Windows.Forms.MenuStrip> werden Menüelemente aus einem <xref:System.Windows.Forms.ToolStrip> in einen anderen verschoben, während sie mit <xref:System.Windows.Forms.MainMenu> geklont wurden.  
  
## MergeAction\-Werte  
 Der Zusammenführungsvorgang von Menüelementen wird in der <xref:System.Windows.Forms.MenuStrip>\-Quelle mit der <xref:System.Windows.Forms.MergeAction>\-Eigenschaft festgelegt.  
  
 In der folgenden Tabelle werden die Bedeutung und typische Verwendung der verfügbaren Zusammenführungsvorgänge beschrieben.  
  
|MergeAction\-Wert|Beschreibung|Typische Verwendung|  
|-----------------------|------------------|-------------------------|  
|<xref:System.Windows.Forms.MergeAction>|\(Standard\) Das Quellelement wird am Ende der Auflistung des Zielelements hinzugefügt.|Hinzufügen von Menüelementen am Ende des Menüs, wenn ein Bestandteil des Programms aktiviert ist|  
|<xref:System.Windows.Forms.MergeAction>|Das Quellelement wird der Auflistung des Zielelements an der Stelle hinzugefügt, die durch die im Quellelement festgelegte <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>\-Eigenschaft festgelegt wurde.|Hinzufügen von Menüelementen in der Mitte oder am Anfang des Menüs, wenn ein Bestandteil des Programms aktiviert ist<br /><br /> Wenn der <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>\-Wert für beide Menüelemente der gleiche ist, werden sie in umgekehrter Reihenfolge hinzugefügt.  Damit die ursprüngliche Reihenfolge beibehalten wird, muss der richtige <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> festgelegt sein.|  
|<xref:System.Windows.Forms.MergeAction>|Wenn eine Textübereinstimmung festgestellt oder andernfalls der <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>\-Wert verwendet wurde, wird das entsprechende Zielmenüelement durch das Quellmenüelement ersetzt.|Ersetzen eines Zielmenüelements durch ein Quellmenüelement mit dem gleichen Namen und einer anderen Funktion|  
|<xref:System.Windows.Forms.MergeAction>|Wenn eine Textübereinstimmung festgestellt oder andernfalls der <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>\-Wert verwendet wurde, werden dem Ziel alle Dropdownelemente der Quelle hinzugefügt.|Erstellen einer Menüstruktur, mit deren Hilfe Menüelemente in einem Untermenü eingefügt, hinzugefügt oder aus diesem entfernt werden können.  Sie können beispielsweise ein Menüelement eines untergeordneten MDI\-Formulars dem Menü **Speichern unter** im Haupt\-<xref:System.Windows.Forms.MenuStrip> hinzufügen.<br /><br /> Mit <xref:System.Windows.Forms.MergeAction> navigieren Sie durch die Menüstruktur, ohne eine Aktion auszuführen.  Dies bietet eine Möglichkeit zum Auswerten der nachfolgenden Elemente.|  
|<xref:System.Windows.Forms.MergeAction>|Wenn eine Textübereinstimmung festgestellt oder andernfalls der <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>\-Wert verwendet wurde, wird das Element aus dem Ziel entfernt.|Entfernen eines Menüelements aus dem <xref:System.Windows.Forms.MenuStrip>\-Ziel.|  
  
## Manuelles Zusammenführen  
 Lediglich <xref:System.Windows.Forms.MenuStrip>\-Steuerelemente können automatisch zusammengeführt werden.  Wenn Elemente anderer Steuerelemente, beispielsweise <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente oder <xref:System.Windows.Forms.StatusStrip>\-Steuerelemente, miteinander kombiniert werden sollen, müssen diese manuell zusammengeführt werden, indem Sie in Ihrem Code die jeweils erforderliche <xref:System.Windows.Forms.ToolStripManager.Merge%2A>\-Methode und die <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A>\-Methode aufrufen.  
  
## Automatisches Zusammenführen  
 Durch Aktivieren des Quellformulars kann das automatische Zusammenführen für MDI\-Anwendungen verwendet werden.  Um ein <xref:System.Windows.Forms.MenuStrip> in einer MDI\-Anwendung zu verwenden, legen Sie die <xref:System.Windows.Forms.Form.MainMenuStrip%2A>\-Eigenschaft auf das <xref:System.Windows.Forms.MenuStrip> des Ziels fest, sodass Zusammenführungsvorgänge, die im <xref:System.Windows.Forms.MenuStrip> der Quelle durchgeführt werden, Auswirkungen auf das <xref:System.Windows.Forms.MenuStrip> des Ziels haben.  
  
 Das automatische Zusammenführen kann durch Aktivieren des <xref:System.Windows.Forms.MenuStrip> der MDI\-Quelle ausgelöst werden.  Nach der Aktivierung wird das <xref:System.Windows.Forms.MenuStrip> der Quelle mit dem MDI\-Ziel zusammengeführt.  Wird ein neues Formular aktiv, wird die Zusammenführung im letzten Formular zurückgesetzt und im neuen Formular ausgelöst.  Dieses Verhalten kann durch Festlegen der <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A>\-Eigenschaft für jedes <xref:System.Windows.Forms.ToolStripItem> nach Bedarf gesteuert werden, gleichzeitig durch Festlegen der <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>\-Eigenschaft für jedes <xref:System.Windows.Forms.MenuStrip>.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStripManager>   
 <xref:System.Windows.Forms.MenuStrip>   
 [MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)   
 [Gewusst wie: Erstellen einer MDI\-Fensterliste mithilfe von MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)   
 [Gewusst wie: Einrichten des automatischem Zusammenführens von Menüs für MDI\-Anwendungen \(Multiple Document Interface\)](../../../../docs/framework/winforms/controls/how-to-set-up-automatic-menu-merging-for-mdi-applications.md)