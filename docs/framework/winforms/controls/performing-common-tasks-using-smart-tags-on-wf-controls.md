---
title: "Exemplarische Vorgehensweise: Ausf&#252;hren von h&#228;ufigen Aufgaben mit Smarttags auf Windows Forms-Steuerelementen | Microsoft Docs"
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
  - "Designeraktionen"
  - "DesignerAction-Objektmodell"
  - "Smarttags"
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Exemplarische Vorgehensweise: Ausf&#252;hren von h&#228;ufigen Aufgaben mit Smarttags auf Windows Forms-Steuerelementen
Bei der Erstellung von Formularen und Steuerelementen für die Windows Forms\-Anwendung müssen viele Aufgaben wiederholt ausgeführt werden.  Zu diesen häufigen Aufgaben gehören unter anderem folgende:  
  
-   Hinzufügen oder Entfernen einer Registerkarte auf einem <xref:System.Windows.Forms.TabControl>  
  
-   Andocken eines Steuerelements an sein übergeordnetes Element  
  
-   Ändern der Ausrichtung eines <xref:System.Windows.Forms.SplitContainer>\-Steuerelements  
  
 Um die Entwicklung zu beschleunigen, verfügen viele Steuerelemente über Smarttags, d. h. kontextbezogene Menüs, mit denen häufige Aufgaben mit nur einer Aktion zur Entwurfszeit ausgeführt werden können.  Diese Aufgaben werden als *Smarttagverben* bezeichnet.  
  
 Smarttags bleiben während ihrer gesamten Lebensdauer im Designer einem Steuerelement zugeordnet und sind stets sichtbar.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms\-Projekts  
  
-   Verwenden von Smarttags  
  
-   Aktivieren und Deaktivieren von Smarttags  
  
 Anschließend werden Sie verstehen, welche Rolle diese wichtigen Layoutfeatures spielen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Erstellen des Projekts  
 Zunächst wird das Projekt erstellt und das Formular eingerichtet.  
  
#### So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows\-basiertes Anwendungsprojekt mit dem Namen "SmartTagsExample".  Ausführliche Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Wählen Sie im **Windows Forms\-Designer** das Formular aus.  
  
## Verwenden von Smarttags  
 Smarttags sind zur Entwurfszeit auf den zugehörigen Steuerelementen stets verfügbar.  
  
#### So verwenden Sie Smarttags  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TabControl> aus der **Toolbox** auf das Formular.  Beachten Sie das Smarttagsymbol \(![Smarttag&#45;Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\), das an der Seite des <xref:System.Windows.Forms.TabControl> angezeigt wird.  
  
2.  Klicken Sie auf das Smarttagsymbol.  Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **Registerkarte hinzufügen** aus.  Beachten Sie, dass dem <xref:System.Windows.Forms.TabControl> eine neue Registerkartenseite hinzugefügt wird.  
  
3.  Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
4.  Klicken Sie auf das Smarttagsymbol.  Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **Spalte hinzufügen** aus.  Beachten Sie, dass dem <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement eine neue Spalte hinzugefügt wird.  
  
5.  Ziehen Sie ein <xref:System.Windows.Forms.SplitContainer>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
6.  Klicken Sie auf das Smarttagsymbol.  Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **Horizontale Aufteilungsausrichtung** aus.  Beachten Sie, dass die Aufteilungsleiste des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements nun horizontal ausgerichtet ist.  
  
## Siehe auch  
 <xref:System.Windows.Forms.TextBox>   
 <xref:System.Windows.Forms.TabControl>   
 <xref:System.Windows.Forms.SplitContainer>   
 <xref:System.ComponentModel.Design.DesignerActionList>   
 [Walkthrough: Adding Smart Tags to a Windows Forms Component](../Topic/Walkthrough:%20Adding%20Smart%20Tags%20to%20a%20Windows%20Forms%20Component.md)