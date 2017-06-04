---
title: "Gewusst wie: &#220;berlagern von Objekten in Windows&#160;Forms | Microsoft Docs"
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
  - "Steuerelemente [Windows Forms], Schichten"
  - "Steuerelemente [Windows Forms], Positionieren"
  - "Windows Forms-Steuerelemente, Schichten"
  - "Z-Reihenfolge"
  - "Z-Reihenfolge"
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: &#220;berlagern von Objekten in Windows&#160;Forms
Wenn Sie eine komplexe Benutzeroberfläche erstellen oder mit einem MDI\-Formular \(Multiple Document Interface \= Mehrfachdokumentschnittstelle\) arbeiten, empfiehlt es sich häufig, Steuerelemente und untergeordnete Formulare zu überlagern, sodass mehrschichtige Benutzeroberflächen \(UI\) entstehen.  Um die Steuerelemente und Fenster innerhalb einer Gruppe zu verschieben und zu kontrollieren, passen Sie deren Z\-Anordnung an.  Bei der *Z\-Anordnung* handelt es sich um die visuelle Überlagerung von Steuerelementen auf einem Formular entlang der Z\-Achse des Formulars \(Tiefenebene\).  Das Fenster, das zuoberst in der Z\-Anordnung angelegt ist, überlappt alle anderen Fenster.  Alle anderen Fenster überlappen wiederum das Fenster, das sich zuunterst in der Z\-Anordnung befindet.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So überlagern Sie Steuerelemente zur Entwurfszeit  
  
1.  Markieren Sie ein zu überlagerndes Steuerelement.  
  
2.  Zeigen Sie im Menü **Format**  auf **Reihenfolge**, und klicken Sie dann auf **In den Vordergrund** oder **In den Hintergrund**.  
  
### So überlagern Sie Steuerelemente programmgesteuert  
  
-   Verwenden Sie die <xref:System.Windows.Forms.Control.BringToFront%2A>\-Methode und die <xref:System.Windows.Forms.Control.SendToBack%2A>\-Methode, um die Z\-Anordnung der Steuerelemente zu ändern.  
  
     Falls sich beispielsweise das <xref:System.Windows.Forms.TextBox>\-Steuerelement `txtFirstName` unter einem anderen Steuerelement befindet, Sie es jedoch in den Vordergrund verlagern möchten, verwenden Sie folgenden Code:  
  
    ```vb  
    txtFirstName.BringToFront()  
  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  Windows Forms unterstützt die *Steuerelementkapselung*.  Bei der Steuerelementkapselung werden mehrere Steuerelemente innerhalb eines Steuerelements platziert, z. B. eine Reihe von <xref:System.Windows.Forms.RadioButton>\-Steuerelementen in einem <xref:System.Windows.Forms.GroupBox>\-Steuerelement.  Sie können die Steuerelemente dann innerhalb des aufnehmenden Steuerelements überlagern.  Beim Verschieben des Gruppenfelds werden automatisch auch die Steuerelemente verschoben, da sie in diesem Feld enthalten sind.  
  
## Siehe auch  
 [Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)   
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Windows Forms\-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)