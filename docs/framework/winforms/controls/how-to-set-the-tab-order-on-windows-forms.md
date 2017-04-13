---
title: "Gewusst wie: Festlegen der Aktivierreihenfolge in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TabStop"
  - "TabIndex"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Steuerelemente [Windows Forms], Festlegen der Aktivierreihenfolge"
  - "Aktivierreihenfolge, Steuerelemente in Windows Forms"
  - "Windows Forms-Steuerelemente, Festlegen der Aktivierreihenfolge"
  - "Windows Forms, Festlegen der Aktivierreihenfolge"
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Festlegen der Aktivierreihenfolge in Windows&#160;Forms
Die Aktivierreihenfolge ist die Reihenfolge, in der ein Benutzer den Fokus durch Drücken der TAB\-TASTE von einem Steuerelement zum nächsten bewegt.  Jedes Formular verfügt über eine eigene Aktivierreihenfolge.  Normalerweise entspricht die Aktivierreihenfolge der Reihenfolge, in der die Steuerelemente erstellt wurden.  Die Nummerierung der Aktivierreihenfolge beginnt mit Null.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So legen Sie die Aktivierreihenfolge eines Steuerelements fest  
  
1.  Klicken Sie im Menü **Ansicht** auf **Aktivierreihenfolge**.  
  
     Auf diese Weise wird der Modus zur Auswahl der Aktivierreihenfolge im Formular aktiviert.  In der oberen linken Ecke der einzelnen Kontrollkästchen wird eine Ziffer \(für die <xref:System.Windows.Forms.Control.TabIndex%2A>\-Eigenschaft\) angezeigt.  
  
2.  Klicken Sie nacheinander auf die Steuerelemente, um die gewünschte Aktivierreihenfolge festzulegen.  
  
    > [!NOTE]
    >  Die Position eines Steuerelements innerhalb der Aktivierreihenfolge kann auf einen beliebigen Wert größer oder gleich 0 festgelegt werden.  Beim Auftreten von Duplikaten wird die Z\-Anordnung der beiden Steuerelemente ausgewertet, und das obere Steuerelement wird als erstes angesteuert.  \(Bei der Z\-Anordnung handelt es sich um die visuelle Überlagerung von Steuerelementen auf einem Formular entlang der Z\-Achse des Formulars \[Tiefenebene\].  Die Z\-Anordnung bestimmt, welche Steuerelemente vor anderen angezeigt werden.\) Weitere Informationen zur Z\-Anordnung finden Sie unter [Überlagern von Objekten in Windows Forms](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md).  
  
3.  Nachdem der Vorgang abgeschlossen ist, klicken Sie im Menü **Ansicht** erneut auf **Aktivierreihenfolge**, um den Modus zur Auswahl der Aktivierreihenfolge zu beenden.  
  
    > [!NOTE]
    >  Steuerelemente, die den Fokus nicht erhalten können, sowie deaktivierte und nicht sichtbare Steuerelemente haben keine <xref:System.Windows.Forms.Control.TabIndex%2A>\-Eigenschaft und sind nicht in der Aktivierreihenfolge enthalten.  Diese Steuerelemente werden übersprungen, wenn der Benutzer die TAB\-TASTE drückt.  
  
 Alternativ kann die Aktivierreihenfolge im Eigenschaftenfenster über die <xref:System.Windows.Forms.Control.TabIndex%2A>\-Eigenschaft festgelegt werden.  Durch die <xref:System.Windows.Forms.Control.TabIndex%2A>\-Eigenschaft eines Steuerelements wird bestimmt, an welcher Stelle in der Aktivierreihenfolge sich das Element befindet.  Das zuerst gezeichnete Steuerelement verfügt standardmäßig über den <xref:System.Windows.Forms.Control.TabIndex%2A>\-Wert 0, das zweite über den <xref:System.Windows.Forms.Control.TabIndex%2A>\-Wert 1 usw.  
  
 Ein <xref:System.Windows.Forms.GroupBox>\-Steuerelement verfügt standardmäßig über einen eigenen <xref:System.Windows.Forms.Control.TabIndex%2A>\-Wert, der einer ganzen Zahl entspricht.  Ein <xref:System.Windows.Forms.GroupBox>\-Steuerelement selbst kann zur Laufzeit nicht den Fokus erhalten.  Daher verfügt jedes Steuerelement innerhalb eines <xref:System.Windows.Forms.GroupBox>s über einen eigenen <xref:System.Windows.Forms.Control.TabIndex%2A>\-Dezimalwert, der mit 0,0 beginnt.  Wenn der <xref:System.Windows.Forms.Control.TabIndex%2A>\-Wert eines <xref:System.Windows.Forms.GroupBox>\-Steuerelements erhöht wird, erhöhen sich die Werte der darin enthaltenen Steuerelemente natürlich entsprechend.  Wenn Sie einen <xref:System.Windows.Forms.Control.TabIndex%2A>\-Wert von 5 in 6 ändern, ändert sich der <xref:System.Windows.Forms.Control.TabIndex%2A>\-Wert des ersten Steuerelements innerhalb der Gruppe automatisch in 6.0 usw.  
  
 Schließlich sollte beachtet werden, dass jedes der zahlreichen, im Formular enthaltenen Steuerelemente in der Aktivierreihenfolge übersprungen werden kann.  Normalerweise werden die Steuerelemente nacheinander in der Aktivierreihenfolge ausgewählt, wenn Sie die TAB\-TASTE zur Laufzeit wiederholt drücken.  Sie können vermeiden, dass ein Steuerelement in der formularspezifischen Aktivierreihenfolge den Fokus erhält, indem Sie seine <xref:System.Windows.Forms.Control.TabStop%2A>\-Eigenschaft deaktivieren.  
  
#### So entfernen Sie ein Steuerelement aus der Aktivierreihenfolge  
  
1.  Legen Sie für die <xref:System.Windows.Forms.Control.TabStop%2A>\-Eigenschaft des Steuerelements im Eigenschaftenfenster `false` fest.  
  
     Ein Steuerelement, dessen <xref:System.Windows.Forms.Control.TabStop%2A>\-Eigenschaft auf `false` festgelegt wurde, behält weiterhin seine Position in der Aktivierreihenfolge bei, wird jedoch übersprungen, wenn der Benutzer die Steuerelemente durch Drücken der TAB\-TASTE durchläuft.  
  
    > [!NOTE]
    >  Eine Optionsfeldgruppe entspricht zur Laufzeit genau einer Position in der Aktivierreihenfolge.  Die <xref:System.Windows.Forms.Control.TabStop%2A>\-Eigenschaft der ausgewählten Schaltfläche \(d. h. der Schaltfläche, deren <xref:System.Windows.Forms.RadioButton.Checked%2A>\-Eigenschaft auf `true` festgelegt ist\) wird automatisch auf `true` festgelegt, während die <xref:System.Windows.Forms.Control.TabStop%2A>\-Eigenschaft der anderen Schaltflächen auf `false` festgelegt wird.  Weitere Informationen zum Gruppieren von <xref:System.Windows.Forms.RadioButton>\-Steuerelementen finden Sie unter [Gruppieren von RadioButton\-Steuerelementen in Windows Forms für die Verwendung als Set](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).  
  
## Siehe auch  
 [Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)   
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Windows Forms\-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)