---
title: "Gewusst wie: Erstellen von zusammengesetzten Steuerelementen | Microsoft Docs"
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
  - "Zusammengesetzte Steuerelemente, Erstellen"
  - "Benutzersteuerelemente [Windows Forms], Erstellen"
  - "Benutzersteuerelemente [Windows Forms], Erben von"
  - "UserControl-Klasse, Erstellen von zusammengesetzten Steuerelementen"
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Erstellen von zusammengesetzten Steuerelementen
Zusammengesetzte Steuerelemente können auf vielfältige Weise eingesetzt werden.  Einerseits können sie als Teil eines Projekts für Windows\-Desktopanwendungen erstellt und lediglich in Formularen des Projekts verwendet werden.  Andererseits können sie in einem Windows\-Steuerelementbibliothek\-Projekt erstellt werden. Daraufhin wird das Projekt in eine Assembly kompiliert und die Steuerelemente in anderen Projekten verwendet.  Es kann sogar von ihnen geerbt werden. Durch visuelle Vererbung können sie schnell für besondere Aufgaben angepasst werden.  
  
> [!NOTE]
>  Informationen über das Erstellen eines zusammengesetzten Steuerelements zur Verwendung in Web Forms finden Sie unter [Developing Custom ASP.NET Server Controls](../Topic/Developing%20Custom%20ASP.NET%20Server%20Controls.md).  
>   
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie ein zusammengesetztes Steuerelement  
  
1.  Erstellen Sie ein neues **Windows\-Anwendung**\-Projekt mit dem Namen `DemoControlHost`.  
  
2.  Klicken Sie im Menü **Projekt** auf **Benutzersteuerelement hinzufügen**.  
  
3.  Geben Sie im Dialogfeld **Neues Element hinzufügen** der Klassendatei \(VB\- oder CS\-Datei\) den Namen, den das zusammengesetzte Steuerelement haben soll.  
  
4.  Klicken Sie auf die Schaltfläche **Hinzufügen**, um die Klassendatei für das zusammengesetzte Steuerelement zu erstellen.  
  
5.  Fügen Sie Steuerelemente aus der **Toolbox** zur Oberfläche des zusammengesetzten Steuerelements hinzu.  
  
6.  Platzieren Sie Code in Ereignisprozeduren, um Ereignisse zu behandeln, die durch das zusammengesetzte Steuerelement oder eines seiner Steuerelemente ausgelöst werden.  
  
7.  Schließen Sie den Designer für das zusammengesetzte Steuerelement, und speichern Sie die Datei, wenn Sie dazu aufgefordert werden.  
  
8.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Das Projekt muss erstellt werden, damit benutzerdefinierte Steuerelemente in der **Toolbox** angezeigt werden.  
  
9. Fügen Sie `Form1` mithilfe der Registerkarte **DemoControlHost** der **Toolbox** Instanzen des Steuerelements hinzu.  
  
### So erstellen Sie eine Klassenbibliothek für Steuerelemente  
  
1.  Öffnen Sie ein neues **Windows\-Steuerelementbibliothek**\-Projekt.  
  
     Standardmäßig ist ein zusammengesetztes Steuerelement im Projekt enthalten.  
  
2.  Fügen Sie Steuerelemente und Code hinzu, wie in der obenstehenden Prozedur beschrieben ist.  
  
3.  Wählen Sie ein Steuerelement, dessen geerbte Klassen nicht geändert werden sollen, und legen Sie die **Modifiers**\-Eigenschaft des Steuerelements auf **Private** fest.  
  
4.  Erstellen Sie die DLL.  
  
### So erben Sie von einem zusammengesetzten Steuerelement in einer Klassenbibliothek für Steuerelemente  
  
1.  Zeigen Sie im Menü **Datei** auf **Hinzufügen**, und wählen Sie **Neues Projekt**, um der Projektmappe ein neues **Windows\-Anwendung**\-Projekt hinzuzufügen.  
  
2.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Ordner **Verweise** für das neue Projekt, und wählen Sie **Verweis hinzufügen**, um das Dialogfeld **Verweis hinzufügen** zu öffnen.  
  
3.  Wählen Sie die Registerkarte **Projekte** aus, und doppelklicken Sie auf das Steuerelementbibliothek\-Projekt.  
  
4.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
5.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Steuerelementbibliothek\-Projekt, und klicken Sie im Kontextmenü auf **Neues Element hinzufügen**.  
  
6.  Wählen Sie die Vorlage **Geerbtes Benutzersteuerelement** im Dialogfeld **Neues Element hinzufügen** aus.  
  
7.  Doppelklicken Sie im Dialogfeld **Vererbungsauswahl** auf das Steuerelement, von dem geerbt werden soll.  
  
     Ein neues Steuerelement wird dem Projekt hinzugefügt.  
  
8.  Öffnen Sie den visuellen Designer für das neue Steuerelement, und fügen Sie anschließend zusätzliche konstituierende Steuerelemente hinzu.  
  
     Die konstituierenden Steuerelemente, die vom zusammengesetzten Steuerelement geerbt wurden, sind in der DLL sichtbar. Die Eigenschaften der Steuerelemente, deren **Modifiers**\-Eigenschaft auf **Public** festgelegt wurde, können geändert werden.  Die Eigenschaften eines Steuerelements, dessen **Modifiers**\-Eigenschaft auf **Private** festgelegt wurde, können nicht geändert werden.  
  
## Siehe auch  
 [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)   
 [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual C\#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)   
 [Exemplarische Vorgehensweise: Vererben eines Windows Forms\-Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)   
 [Exemplarische Vorgehensweise: Vererben von einem Windows Forms\-Steuerelement mit Visual C\#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)   
 [Empfehlungen zum Typ von Steuerelementen](../../../../docs/framework/winforms/controls/control-type-recommendations.md)   
 [Gewusst wie: Erstellen von Steuerelementen für Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)   
 [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)