---
title: "Mausereignisse in Windows Forms | Microsoft Docs"
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
  - "Click-Ereignis, Auslösungsreihenfolge"
  - "Ereignisse [Windows Forms], Maus"
  - "Maus, Ereignisse"
  - "MouseClick-Ereignis"
  - "MouseDoubleClick-Ereignis"
  - "MouseDown-Ereignis"
  - "MouseEnter-Ereignis"
  - "MouseHover-Ereignis"
  - "MouseLeave-Ereignis"
  - "MouseMove-Ereignis"
  - "MouseUp-Ereignis"
  - "Windows Forms-Steuerelemente, Click-Ereignisse"
ms.assetid: 8cf0070d-793b-4876-b09e-d20d28280fab
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Mausereignisse in Windows Forms
Wenn Sie Mauseingaben behandeln, möchten Sie in der Regel die Position des Mauszeigers und den Zustand der Maustasten kennen.  Dieses Thema enthält Details zum Abrufen dieser Informationen von Mausereignissen und erörtert die Reihenfolge, in der Mausklickereignisse in Windows Forms\-Steuerelementen ausgelöst werden.  Eine Liste und Beschreibungen aller Mausereignisse finden Sie unter [Funktionsweise von Mauseingaben in Windows Forms](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).  Siehe auch [Übersicht über Ereignishandler \(Windows Forms\)](http://msdn.microsoft.com/library/be6fx1bb\(v=vs.110\)), [Übersicht über Ereignisse \(Windows Forms\)](http://msdn.microsoft.com/library/1h12f09z\(v=vs.110\))  
  
## Mausinformationen  
 Ein <xref:System.Windows.Forms.MouseEventArgs> wird an Handler von Mausereignissen gesendet, die beim Drücken einer Maustaste und Verfolgen von Mausbewegungen ausgelöst werden.  <xref:System.Windows.Forms.MouseEventArgs> enthält Informationen zum aktuellen Zustand der Maus, z. B. die Position des Mauszeigers in Clientkoordinaten, welche Maustasten gedrückt werden und ob das Mausrad bewegt wurde.  Zahlreiche Mausereignisse, beispielsweise Ereignisse, die lediglich darüber informieren, dass der Mauszeiger die Grenzen eines Steuerelements überschritten hat, senden ein <xref:System.EventArgs> ohne weitere Informationen an den Ereignishandler.  
  
 Wenn Sie den aktuellen Zustand der Maustasten oder die Position des Mauszeigers erfahren möchten, ohne ein Mausereignis zu behandeln, können Sie auch die <xref:System.Windows.Forms.Control.MouseButtons%2A>\-Eigenschaft und die <xref:System.Windows.Forms.Control.MousePosition%2A>\-Eigenschaft der <xref:System.Windows.Forms.Control>\-Klasse verwenden.  <xref:System.Windows.Forms.Control.MouseButtons%2A> gibt Informationen darüber zurück, welche Maustasten aktuell gedrückt werden.  <xref:System.Windows.Forms.Control.MousePosition%2A> gibt die Bildschirmkoordinaten des Mauszeigers zurück, was dem von <xref:System.Windows.Forms.Cursor.Position%2A> zurückgegebenen Wert entspricht.  
  
## Konvertieren zwischen Bildschirm\- und Clientkoordinaten  
 Da einige Mauspositionsinformationen in Clientkoordinaten und einige in Bildschirmkoordinaten vorhanden sind, müssen Sie möglicherweise einen Punkt aus einem Koordinatensystem in das andere Koordinatensystem konvertieren.  Eine einfache Möglichkeit hierzu bieten die <xref:System.Windows.Forms.Control.PointToClient%2A>\-Methode und die <xref:System.Windows.Forms.Control.PointToScreen%2A>\-Methode der <xref:System.Windows.Forms.Control>\-Klasse.  
  
## Standardverhalten bei Mausklickereignissen  
 Wenn Sie Mausklickereignisse in der richtigen Reihenfolge behandeln möchten, müssen Sie die Reihenfolge kennen, in der Mausklickereignisse in Windows Forms\-Steuerelementen ausgelöst werden.  Wenn eine Maustaste gedrückt und wieder losgelassen wird \(unabhängig davon, um welche Maustaste es sich handelt\), lösen alle Windows Forms\-Steuerelemente Mausklickereignisse in derselben Reihenfolge aus.  In der folgenden Liste ist die Reihenfolge der Ereignisse aufgeführt, die bei einem einzelnen Mausklick ausgelöst werden:  
  
1.  <xref:System.Windows.Forms.Control.MouseDown>\-Ereignis.  
  
2.  <xref:System.Windows.Forms.Control.Click>\-Ereignis.  
  
3.  <xref:System.Windows.Forms.Control.MouseClick>\-Ereignis.  
  
4.  <xref:System.Windows.Forms.Control.MouseUp>\-Ereignis.  
  
 In der folgenden Liste ist die Reihenfolge der Ereignisse aufgeführt, die bei einem Doppelklick mit der Maus ausgelöst werden:  
  
1.  <xref:System.Windows.Forms.Control.MouseDown>\-Ereignis.  
  
2.  <xref:System.Windows.Forms.Control.Click>\-Ereignis.  
  
3.  <xref:System.Windows.Forms.Control.MouseClick>\-Ereignis.  
  
4.  <xref:System.Windows.Forms.Control.MouseUp>\-Ereignis.  
  
5.  <xref:System.Windows.Forms.Control.MouseDown>\-Ereignis.  
  
6.  <xref:System.Windows.Forms.Control.DoubleClick>\-Ereignis.  \(Dies kann abhängig davon variieren, ob für das betreffende Steuerelement das <xref:System.Windows.Forms.ControlStyles>\-Stilbit auf `true` festgelegt ist.  Weitere Informationen zum Festlegen eines <xref:System.Windows.Forms.ControlStyles>\-Bits finden Sie unter der <xref:System.Windows.Forms.Control.SetStyle%2A>\-Methode.\)  
  
7.  <xref:System.Windows.Forms.Control.MouseDoubleClick>\-Ereignis.  
  
8.  <xref:System.Windows.Forms.Control.MouseUp>\-Ereignis.  
  
 Ein Codebeispiel zur Veranschaulichung der Reihenfolge der Mausklickereignisse finden Sie unter [Gewusst wie: Behandeln von Benutzereingabeereignissen in Windows Forms\-Steuerelementen](../../../docs/framework/winforms/how-to-handle-user-input-events-in-windows-forms-controls.md).  
  
### Einzelne Steuerelemente  
 Die folgenden Steuerelemente weisen nicht das Standardverhalten bei Mausklickereignissen auf:  
  
-   <xref:System.Windows.Forms.Button>\-Steuerelement, <xref:System.Windows.Forms.CheckBox>\-Steuerelement, <xref:System.Windows.Forms.ComboBox>\-Steuerelement und <xref:System.Windows.Forms.RadioButton>\-Steuerelement  
  
    > [!NOTE]
    >  Für das <xref:System.Windows.Forms.ComboBox>\-Steuerelement tritt das im Folgenden beschriebene Verhalten auf, wenn der Benutzer auf das Bearbeitungsfeld, die Schaltfläche oder ein Element in der Liste klickt.  
  
    -   Klick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Klick mit der rechten Maustaste: Es werden keine Click\-Ereignisse ausgelöst.  
  
    -   Doppelklick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Doppelklick mit der rechten Maustaste: Es werden keine Click\-Ereignisse ausgelöst.  
  
-   <xref:System.Windows.Forms.TextBox>\-Steuerelement, <xref:System.Windows.Forms.RichTextBox>\-Steuerelement, <xref:System.Windows.Forms.ListBox>\-Steuerelement, <xref:System.Windows.Forms.MaskedTextBox>\-Steuerelement und <xref:System.Windows.Forms.CheckedListBox>\-Steuerelement  
  
    > [!NOTE]
    >  Das im Folgenden beschriebene Verhalten tritt auf, wenn der Benutzer innerhalb dieser Steuerelemente auf eine beliebige Stelle klickt.  
  
    -   Klick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Klick mit der rechten Maustaste: Es werden keine Click\-Ereignisse ausgelöst.  
  
    -   Doppelklick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
    -   Doppelklick mit der rechten Maustaste: Es werden keine Click\-Ereignisse ausgelöst.  
  
-   <xref:System.Windows.Forms.ListView>\-Steuerelement  
  
    > [!NOTE]
    >  Das im Folgenden beschriebene Verhalten tritt nur auf, wenn der Benutzer auf die Elemente im <xref:System.Windows.Forms.ListView>\-Steuerelement klickt.  Wenn der Benutzer im Steuerelement auf eine andere Stelle klickt, werden keine Ereignisse ausgelöst.  Neben den weiter unten beschriebenen Ereignissen könnten auch das <xref:System.Windows.Forms.ListView.BeforeLabelEdit>\-Ereignis und das <xref:System.Windows.Forms.ListView.AfterLabelEdit>\-Ereignis für Sie von Interesse sein, wenn Sie eine Validierung mit dem <xref:System.Windows.Forms.ListView>\-Steuerelement durchführen möchten.  
  
    -   Klick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Klick mit der rechten Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Doppelklick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
    -   Doppelklick mit der rechten Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
-   <xref:System.Windows.Forms.TreeView>\-Steuerelement  
  
    > [!NOTE]
    >  Das im Folgenden beschriebene Verhalten tritt nur auf, wenn der Benutzer im <xref:System.Windows.Forms.TreeView>\-Steuerelement auf die Elemente selbst oder rechts neben sie klickt.  Wenn der Benutzer im Steuerelement auf eine andere Stelle klickt, werden keine Ereignisse ausgelöst.  Neben den weiter unten beschriebenen Ereignissen könnten auch die Ereignisse <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck> und <xref:System.Windows.Forms.TreeView.AfterLabelEdit> für Sie von Interesse sein, wenn Sie eine Validierung mit dem <xref:System.Windows.Forms.TreeView>\-Steuerelement durchführen möchten.  
  
    -   Klick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Klick mit der rechten Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Doppelklick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
    -   Doppelklick mit der rechten Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
### Zeichnungsverhalten umschaltbarer Steuerelemente  
 Umschaltbare Steuerelemente, wie die Steuerelemente, die von der <xref:System.Windows.Forms.ButtonBase>\-Klasse abgeleitet werden, weisen bei Mausklickereignissen das folgende Zeichnungsverhalten auf:  
  
1.  Der Benutzer drückt die Maustaste.  
  
2.  Das Steuerelement zeichnet im gedrückten Zustand.  
  
3.  Das <xref:System.Windows.Forms.Control.MouseDown>\-Ereignis wird ausgelöst.  
  
4.  Der Benutzer lässt die Maustaste los.  
  
5.  Das Steuerelement zeichnet im erhöhten Zustand.  
  
6.  Das <xref:System.Windows.Forms.Control.Click>\-Ereignis wird ausgelöst.  
  
7.  Das <xref:System.Windows.Forms.Control.MouseClick>\-Ereignis wird ausgelöst.  
  
8.  Das <xref:System.Windows.Forms.Control.MouseUp>\-Ereignis wird ausgelöst.  
  
    > [!NOTE]
    >  Wenn der Benutzer den Mauszeiger bei gedrückter Maustaste aus dem umschaltbaren Steuerelement bewegt \(z. B. wenn er die Maus bei gedrückter Maustaste vom <xref:System.Windows.Forms.Button>\-Steuerelement weg bewegt\), zeichnet das umschaltbare Steuerelement im erhöhten Zustand, und es tritt nur das <xref:System.Windows.Forms.Control.MouseUp>\-Ereignis auf.  Das <xref:System.Windows.Forms.Control.Click>\-Ereignis oder das <xref:System.Windows.Forms.Control.MouseClick>\-Ereignis tritt in dieser Situation nicht auf.  
  
## Siehe auch  
 [Mauseingabe in einer Windows Forms\-Anwendung](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)