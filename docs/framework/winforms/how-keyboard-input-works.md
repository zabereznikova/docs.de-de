---
title: "Funktionsweise von Tastatureingaben | Microsoft Docs"
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
  - "Tastatureingabe, Informationen über Tastatureingabe"
  - "Tastaturen, Tastatureingabe"
  - "Windows Forms, Tastatureingabe"
ms.assetid: 9a29433c-a180-49bb-b74c-d187786584c8
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Funktionsweise von Tastatureingaben
Windows Forms verarbeitet Tastatureingaben, indem als Reaktion auf Windows\-Meldungen Tastaturereignisse ausgelöst werden.  Die meisten Windows Forms\-Anwendungen verarbeiten Tastatureingaben ausschließlich, indem sie die Tastaturereignisse behandeln.  Sie müssen sich jedoch vergegenwärtigen, wie Tastaturmeldungen funktionieren, um erweiterte Tastatureingabeszenarien, wie das Abfangen von Tastenwerten, bevor sie ein Steuerelement erreichen, implementieren zu können.  In diesem Thema werden die Typen von Tastendaten beschrieben, die von Windows Forms erkannt werden. Außerdem enthält es eine Übersicht darüber, wie Tastaturmeldungen weitergeleitet werden.  Informationen zu Tastaturereignissen finden Sie unter [Verwenden von Tastaturereignissen](../../../docs/framework/winforms/using-keyboard-events.md).  
  
## Arten von Tasten  
 Windows Forms identifiziert Tastatureingaben als virtuelle Tastencodes, die durch die bitweise <xref:System.Windows.Forms.Keys>\-Enumeration dargestellt werden.  Mit der <xref:System.Windows.Forms.Keys>\-Enumeration können Sie eine Folge gedrückter Tasten in einem Wert ausgeben lassen.  Diese Werte entsprechen den Werten, die mit den Windows\-Meldungen WM\_KEYDOWN und WM\_SYSKEYDOWN gesendet werden.  Sie können die meisten Betätigungen physikalischer Tasten erkennen, indem Sie das <xref:System.Windows.Forms.Control.KeyDown>\-Ereignis oder das <xref:System.Windows.Forms.Control.KeyUp>\-Ereignis behandeln.  Zeichentasten bilden eine Untergruppe der <xref:System.Windows.Forms.Keys>\-Enumeration und entsprechen den Werten, die mit den Windows\-Meldungen WM\_CHAR und WM\_SYSCHAR gesendet werden.  Wenn mehrere gedrückte Tasten zu einem Zeichen zusammengefasst sind, können Sie das Zeichen erkennen, indem Sie das <xref:System.Windows.Forms.Control.KeyPress>\-Ereignis behandeln.  Alternativ können Sie das von der Visual Basic\-Programmierschnittstelle verfügbar gemachte Element <xref:Microsoft.VisualBasic.Devices.Keyboard> verwenden. Damit stellen Sie fest, welche Tasten gedrückt wurden, und senden die entsprechenden Tastenwerte.  Weitere Informationen finden Sie unter [Accessing the Keyboard](../Topic/Accessing%20the%20Keyboard%20\(Visual%20Basic\).md).  
  
## Reihenfolge von Tastaturereignissen  
 Wie oben aufgelistet, gibt es drei tastaturbezogene Ereignisse, die in einem Steuerelement auftreten können.  Die folgende Abfolge entspricht der allgemeinen Reihenfolge der Ereignisse:  
  
1.  Der Benutzer drückt die Taste "a", die Taste wird vorverarbeitet und gesendet, und ein <xref:System.Windows.Forms.Control.KeyDown>\-Ereignis tritt ein.  
  
2.  Der Benutzer hält die Taste "a" gedrückt, die Taste wird vorverarbeitet und gesendet, und ein <xref:System.Windows.Forms.Control.KeyPress>\-Ereignis tritt ein.  
  
     Während der Benutzer eine Taste gedrückt hält, wird dieses Ereignis mehrfach wiederholt.  
  
3.  Der Benutzer lässt die Taste "a" los, die Taste wird vorverarbeitet und gesendet, und ein <xref:System.Windows.Forms.Control.KeyUp>\-Ereignis tritt ein.  
  
## Vorverarbeiten von Tasten  
 Wie andere Meldungen werden Tastaturmeldungen in der <xref:System.Windows.Forms.Control.WndProc%2A>\-Methode eines Formulars oder eines Steuerelements verarbeitet.  Bevor Tastaturmeldungen verarbeitet werden, ruft die <xref:System.Windows.Forms.Control.PreProcessMessage%2A>\-Methode jedoch eine oder mehrere Methoden auf, die überschrieben werden können, um bestimmte Zeichentasten und physikalische Tasten zu behandeln.  Sie können diese Methoden überschreiben, um bestimmte Tasten zu erkennen und zu filtern, bevor die Meldungen vom Steuerelement verarbeitet werden.  Der folgenden Tabelle können Sie die ausgeführte Aktion sowie die zugehörige Methode in der Reihenfolge entnehmen, in der die Methode auftritt.  
  
### Vorverarbeitung für ein KeyDown\-Ereignis.  
  
|Aktion|Verwandte Methode|Hinweise|  
|------------|-----------------------|--------------|  
|Suchen nach einer Befehlstaste, z. B. einer Zugriffstaste oder einer Menüverknüpfung.|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|Diese Methode verarbeitet eine Befehlstaste, die Vorrang gegenüber regulären Tasten hat.  Wenn diese Methode `true` zurückgibt, wird die Tastenmeldung nicht weitergeleitet, und es tritt kein Tastenereignis ein.  Wenn sie `false` zurückgibt, wird <xref:System.Windows.Forms.Control.IsInputKey%2A> aufgerufen.|  
|Suchen Sie eine bestimmte Taste, die eine Vorverarbeitung erfordert, oder eine normale Zeichentaste, die ein <xref:System.Windows.Forms.Control.KeyDown>\-Ereignis auslöst und an ein Steuerelement weitergeleitet werden soll.|<xref:System.Windows.Forms.Control.IsInputKey%2A>|Wenn die Methode `true` zurückgibt, bedeutet dies, dass das Steuerelement ein normales Zeichen ist und ein <xref:System.Windows.Forms.Control.KeyDown>\-Ereignis ausgelöst wird.  Bei `false` wird <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> aufgerufen. **Note:**  Um sicherzustellen, dass ein Steuerelement eine Taste oder eine Tastenkombination abruft, können Sie das <xref:System.Windows.Forms.Control.PreviewKeyDown>\-Ereignis behandeln und <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> von <xref:System.Windows.Forms.PreviewKeyDownEventArgs> für die gewünschte Taste bzw. die gewünschten Tasten auf `true` festlegen.|  
|Suchen Sie eine Navigationstaste \(ESC, TAB, EINGABE oder Pfeiltasten\).|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|Durch diese Methode wird eine physikalische Taste verarbeitet, die bestimmte Funktionalität innerhalb des Steuerelements implementiert, beispielsweise das Verschieben des Fokus von einem Steuerelement zu seinem übergeordneten Element.  Falls die Taste vom unmittelbaren Steuerelement nicht behandelt wird, wird <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> für das übergeordnete Steuerelement und danach für alle weiteren Steuerelemente bis zum Anfang der Hierarchie aufgerufen.  Wenn diese Methode `true` zurückgibt, ist die Vorverarbeitung abgeschlossen, und es wird kein Tastenereignis generiert.  Wenn sie `false` zurückgibt, tritt ein <xref:System.Windows.Forms.Control.KeyDown>\-Ereignis ein.|  
  
### Vorverarbeitung für ein KeyPress\-Ereignis  
  
|Aktion|Verwandte Methode|Hinweise|  
|------------|-----------------------|--------------|  
|Überprüfen, ob die Taste ein normales Zeichen ist, das vom Steuerelement verarbeitet werden soll.|<xref:System.Windows.Forms.Control.IsInputChar%2A>|Wenn die Taste ein normales Zeichen ist, gibt diese Methode `true` zurück, das <xref:System.Windows.Forms.Control.KeyPress>\-Ereignis wird ausgelöst, und es findet keine weitere Vorverarbeitung statt.  Andernfalls wird <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> aufgerufen.|  
|Überprüfen, ob das Zeichen ein mnemonisches Zeichen ist \(beispielsweise &OK für eine Schaltfläche\).|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|Diese Methode wird ähnlich wie <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> für jedes Steuerelement bis zum obersten Element in der Hierarchie aufgerufen.  Wenn es sich bei dem Steuerelement um ein Containersteuerelement handelt, sucht es nach mnemonischen Zeichen, indem es <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> für sich selbst und alle untergeordneten Steuerelemente aufruft.  Wenn <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> den Wert `true` zurückgibt, tritt kein <xref:System.Windows.Forms.Control.KeyPress>\-Ereignis ein.|  
  
## Verarbeiten von Tastaturmeldungen  
 Nachdem die Tastaturmeldungen die <xref:System.Windows.Forms.Control.WndProc%2A>\-Methode eines Formulars oder Steuerelements erreicht haben, werden sie von einer Gruppen von Methoden verarbeitet, die überschrieben werden können.  Jede dieser Methoden gibt einen <xref:System.Boolean>\-Wert zurück, der angibt, ob die Tastaturmeldung verarbeitet und vom Steuerelement konsumiert wurde.  Wenn eine der Methoden `true` zurückgibt, wird die Meldung als behandelt betrachtet und nicht zur weiteren Verarbeitung an das Basiselement oder übergeordnete Element des Steuerelements übergeben.  Andernfalls verbleibt die Meldung in der Meldungswarteschlange und wird möglicherweise in einer anderen Methode im Basiselement oder übergeordneten Element des Steuerelements verarbeitet.  In der folgenden Tabelle werden die Methoden dargestellt, die Tastaturmeldungen verarbeiten.  
  
|Methode|Hinweise|  
|-------------|--------------|  
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|Diese Methode verarbeitet alle Tastaturmeldungen, die von der <xref:System.Windows.Forms.Control.WndProc%2A>\-Methode des Steuerelements empfangen werden.|  
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|Diese Methode sendet die Tastaturmeldung an das übergeordnete Element des Steuerelements.  Wenn <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A> den Wert `true` zurückgibt, wird kein Tastenereignis generiert, andernfalls wird <xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A> aufgerufen.|  
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|Diese Methode löst die Ereignisse <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress> bzw. <xref:System.Windows.Forms.Control.KeyUp> aus.|  
  
## Überschreiben von Tastaturmethoden  
 Wenn eine Tastaturmeldung vorverarbeitet und verarbeitet wird, sind viele Methoden zum Überschreiben verfügbar. Einige Methoden sind jedoch besser geeignet als andere.  In der folgenden Tabelle sind mögliche Aufgaben und der optimale Weg zum Überschreiben der Tastaturmethoden aufgeführt.  Weitere Informationen zum Überschreiben von Methoden finden Sie unter [NOT IN BUILD: Overriding Properties and Methods](http://msdn.microsoft.com/de-de/2167e8f5-1225-4b13-9ebd-02591ba90213).  
  
|Aufgabe|Methode|  
|-------------|-------------|  
|Abfangen einer Navigationstaste und Auslösen eines <xref:System.Windows.Forms.Control.KeyDown>\-Ereignisses.  Beispielsweise sollen TAB\- und EINGABETASTE in einem Textfeld behandelt werden.|Überschreiben Sie <xref:System.Windows.Forms.Control.IsInputKey%2A>. **Note:**  Alternativ können Sie das <xref:System.Windows.Forms.Control.PreviewKeyDown>\-Ereignis behandeln und <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> von <xref:System.Windows.Forms.PreviewKeyDownEventArgs> für die gewünschte Taste bzw. die gewünschten Tasten auf `true` festlegen.|  
|Behandlung bestimmter Eingaben oder Navigationstasten für ein Steuerelement.  Möglicherweise möchten Sie die Pfeiltasten im Listensteuerelement verwenden, um das ausgewählte Element zu ändern.|Überschreiben Sie <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>.|  
|Abfangen einer Navigationstaste und Auslösen eines <xref:System.Windows.Forms.Control.KeyPress>\-Ereignisses.  Möglicherweise möchten Sie mehrere gedrückte Pfeiltasten in ein Drehfeldsteuerelement aufnehmen, um das Durchlaufen der Elemente zu beschleunigen.|Überschreiben Sie <xref:System.Windows.Forms.Control.IsInputChar%2A>.|  
|Behandlung spezieller Eingaben oder Navigationstasten während eines <xref:System.Windows.Forms.Control.KeyPress>\-Ereignisses.  Beispiel: Wenn in einem Listensteuerelement die Taste "r" anhaltend gedrückt wird, springt der Benutzer zwischen Elementen, die mit dem Buchstaben "r" beginnen.|Überschreiben Sie <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>.|  
|Behandlung benutzerdefinierter mnemonischer Zeichen, beispielsweise wenn Sie mnemonische Zeichen auf Ownerdrawn\-Schaltflächen in einer Symbolleiste behandeln möchten.|Überschreiben Sie <xref:System.Windows.Forms.Control.ProcessMnemonic%2A>.|  
  
## Siehe auch  
 <xref:System.Windows.Forms.Keys>   
 <xref:System.Windows.Forms.Control.WndProc%2A>   
 <xref:System.Windows.Forms.Control.PreProcessMessage%2A>   
 [My.Computer.Keyboard Object](../../../ocs/visual-basic/language-reference/objects/my-computer-keyboard-object.md)   
 [Accessing the Keyboard](../Topic/Accessing%20the%20Keyboard%20\(Visual%20Basic\).md)   
 [Verwenden von Tastaturereignissen](../../../docs/framework/winforms/using-keyboard-events.md)