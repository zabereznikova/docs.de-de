---
title: "Gewusst wie: Erstellen von Zugriffstasten f&#252;r Windows&#160;Forms-Steuerelemente mithilfe des Designers | Microsoft Docs"
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
  - "Zugriffstasten, Erstellen für Steuerelemente"
  - "Zugriffstasten, Windows Forms"
  - "ALT-TASTE"
  - "Kaufmännisches Und-Zeichen in Tastenkombination"
  - "Button-Steuerelement [Windows Forms], Zugriffstasten"
  - "Steuerelemente [Windows Forms], Zugriffstasten"
  - "Dialogfeldsteuerelemente, Zugriffstasten"
  - "Beispiele [Windows Forms], Steuerelemente"
  - "Tastenkombinationen, Erstellen für Steuerelemente"
  - "Zugriffstasten, Hinzufügen zu Dialogfeld-Steuerelementen"
  - "Text-Eigenschaft, Angeben von Zugriffstasten für Steuerelemente"
  - "Windows Forms-Steuerelemente, Zugriffstasten"
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Erstellen von Zugriffstasten f&#252;r Windows&#160;Forms-Steuerelemente mithilfe des Designers
Eine *Zugriffstaste* ist ein unterstrichenes Zeichen im Text eines Menüs oder Menüelements oder in der Beschriftung eines Steuerelements, z. B. einer Schaltfläche.  Durch gleichzeitiges Drücken der ALT\-TASTE und der vordefinierten Tastenkombination können Benutzer auf eine Schaltfläche "klicken".  Ein Beispiel: Wenn eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausführt und ihre `Text`\-Eigenschaft daher auf "Drucken" festgelegt ist, wird der Buchstabe "D" durch Hinzufügen eines kaufmännischen Und\-Zeichens vor diesem Buchstaben zur Laufzeit im Schaltflächentext unterstrichen angezeigt.  Der Benutzer kann den der Schaltfläche zugeordneten Befehl durch Drücken von ALT\+P ausführen.  Tastenkombinationen für Steuerelemente, die den Fokus nicht erhalten können, sind nicht zulässig.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie eine Tastenkombination für ein Steuerelement  
  
1.  Legen Sie für die `Text`\-Eigenschaft im **Eigenschaftenfenster** eine Zeichenfolge fest, die ein kaufmännisches Und\-Zeichen vor dem Buchstaben der Tastenkombination enthält.  Wenn Sie beispielsweise den Buchstaben "D" als Tastenkombination festlegen möchten, geben Sie &Drucken in das Raster ein.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Button>   
 [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Gewusst wie: Festlegen des durch ein Windows Forms\-Steuerelement angezeigten Textes](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)