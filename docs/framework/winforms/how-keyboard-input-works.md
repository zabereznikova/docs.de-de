---
title: Funktionsweise von Tastatureingaben
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard input [Windows Forms], about keyboard input
- keyboards [Windows Forms], keyboard input
- Windows Forms, keyboard input
ms.assetid: 9a29433c-a180-49bb-b74c-d187786584c8
ms.openlocfilehash: 369c434f5443334ccb8b136ce50ff2d5db8ece01
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963448"
---
# <a name="how-keyboard-input-works"></a>Funktionsweise von Tastatureingaben
Windows Forms verarbeitet Tastatureingaben, indem als Reaktion auf Windows-Meldungen Tastaturereignisse ausgelöst werden. Die meisten Windows Forms-Anwendungen verarbeiten Tastatureingaben ausschließlich durch Bearbeiten der Tastaturereignisse. Sie müssen jedoch die Funktionsweise von Tastaturnachrichten verstehen, damit Sie erweiterte Tastatureingabeszenarios implementieren können, wie z.B. das Abfangen von Schlüssel, bevor diese ein Steuerelement erreichen. Dieses Thema beschreibt die Typen von Schlüsseldaten, die Windows Forms erkennt, und bietet eine Übersicht darüber, wie Tastaturnachrichten weitergeleitet werden. Informationen zu Tastaturereignissen finden Sie unter [Verwenden von Tastaturereignissen](using-keyboard-events.md).  
  
## <a name="types-of-keys"></a>Typen von Tasten  
 Windows Forms identifiziert Tastatureingaben als Codes von virtuellen Schlüsseln, die durch die bitweise <xref:System.Windows.Forms.Keys> -Enumeration dargestellt werden. Mit der <xref:System.Windows.Forms.Keys> -Enumeration können Sie eine Reihe von gedrückten Schlüsseln kombinieren, um einen einzelnen Wert zu erhalten. Diese Werte entsprechen den Werten, die in den Windows-Nachrichten WM_KEYDOWN und WM_SYSKEYDOWN enthalten sind. Sie können die meisten physischen Tastendruck erkennen, indem <xref:System.Windows.Forms.Control.KeyDown> Sie <xref:System.Windows.Forms.Control.KeyUp> die-oder-Ereignisse verarbeiten. Zeichen Schlüssel sind eine Teilmenge der <xref:System.Windows.Forms.Keys> -Enumeration und entsprechen den Werten, die die Windows-Meldungen WM_CHAR und WM_SYSCHAR begleiten. Wenn die Kombination der gedrückten Tasten ein Zeichen ergibt, können Sie das Zeichen erkennen, indem <xref:System.Windows.Forms.Control.KeyPress> Sie das-Ereignis behandeln. Alternativ können Sie verwenden <xref:Microsoft.VisualBasic.Devices.Keyboard>, das von Visual Basic Programmierschnittstelle verfügbar gemacht wird, um zu ermitteln, welche Schlüssel gedrückt und welche Schlüssel gesendet wurden. Weitere Informationen finden Sie unter [Zugreifen auf die Tastatur](../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md).  
  
## <a name="order-of-keyboard-events"></a>Reihenfolge von Tastaturereignissen  
 Wie oben aufgeführt gibt es drei mit der Tastatur verknüpfte Ereignisse, die in einem Steuerelement auftreten können. Die folgende Sequenz zeigt die allgemeine Reihenfolge der Ereignisse:  
  
1. Der Benutzer drückt die Taste "a", der Schlüssel wird vorverarbeitet, verteilt, und ein <xref:System.Windows.Forms.Control.KeyDown> -Ereignis tritt auf.  
  
2. Der Benutzer besitzt den Schlüssel "a", der Schlüssel wird vorverarbeitet, verteilt, und es <xref:System.Windows.Forms.Control.KeyPress> tritt ein-Ereignis auf.  
  
     Dieses Ereignis tritt mehrmals auf, wenn der Benutzer eine Taste gedrückt hält.  
  
3. Der Benutzer gibt den Schlüssel "a" frei, der Schlüssel wird vorverarbeitet, gesendet und <xref:System.Windows.Forms.Control.KeyUp> ein-Ereignis tritt auf.  
  
## <a name="preprocessing-keys"></a>Vorverarbeiten von Tasten  
 Wie bei anderen Meldungen werden Tastatur Meldungen in der <xref:System.Windows.Forms.Control.WndProc%2A> -Methode eines Formulars oder Steuer Elements verarbeitet. Bevor Tastatur Meldungen verarbeitet werden, ruft die <xref:System.Windows.Forms.Control.PreProcessMessage%2A> -Methode jedoch mindestens eine Methode auf, die überschrieben werden kann, um Sonderzeichen Schlüssel und physische Schlüssel zu verarbeiten. Sie können diese Methoden zum Erkennen und Filtern bestimmter Tasten überschreiben, bevor die Nachrichten vom Steuerelement verarbeitet werden. Die folgende Tabelle zeigt die Aktion an, die ausgeführt wird und die zugehörige Methode die auftritt, in der Reihenfolge, in der die Methode auftritt.  
  
### <a name="preprocessing-for-a-keydown-event"></a>Vorverarbeiten eines KeyDown-Ereignisses  
  
|Aktion|Verknüpfte Methode|Hinweise|  
|------------|--------------------|-----------|  
|Überprüfen Sie, ob eine Befehlstaste vorhanden ist, z.B. eine Zugriffstaste oder eine Menü-Tastenkombination.|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|Diese Methode verarbeitet eine Befehlstaste, die Vorrang gegenüber regulären Tasten hat. Wenn diese Methode `true` zurückgibt, wird die Schlüsselmeldung nicht weitergeleitet, und es tritt kein Schlüsselereignis auf. Wenn zurück `false`gegeben wird <xref:System.Windows.Forms.Control.IsInputKey%2A> , wird aufgerufen.`.`|  
|Suchen Sie nach einem speziellen Schlüssel, der eine Vorverarbeitung erfordert, oder einen normalen Zeichen Schlüssel <xref:System.Windows.Forms.Control.KeyDown> , der ein-Ereignis hervorrufen und an ein Steuerelement weitergeleitet werden soll.|<xref:System.Windows.Forms.Control.IsInputKey%2A>|Wenn die Methode zurück `true`gibt, bedeutet dies, dass das Steuerelement ein reguläres Zeichen ist und ein <xref:System.Windows.Forms.Control.KeyDown> -Ereignis ausgelöst wird. Wenn `false` ,<xref:System.Windows.Forms.Control.ProcessDialogKey%2A> wird aufgerufen. **Hinweis**:  Um sicherzustellen, dass ein Steuerelement einen Schlüssel oder eine Kombination von Schlüsseln <xref:System.Windows.Forms.Control.PreviewKeyDown> abruft, <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> können Sie <xref:System.Windows.Forms.PreviewKeyDownEventArgs> das `true` -Ereignis und das-Element für den gewünschten Schlüssel oder die gewünschten Schlüssel verarbeiten.|  
|Führen Sie eine Überprüfung auf eine Navigationstaste aus (ESC-, TAB-, Return oder Pfeiltaste).|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|Diese Methode verarbeitet eine physische Taste, die eine besondere Funktionalität innerhalb des Steuerelements nutzt und z.B. den Fokus zwischen dem Steuerelement und seinem übergeordneten Element umschaltet. Wenn das unmittelbare Steuerelement den Schlüssel nicht behandelt, <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> wird für das übergeordnete Steuerelement aufgerufen usw. für das oberste Steuerelement in der Hierarchie. Wenn diese Methode `true` zurückgibt, ist die Vorverarbeitung abgeschlossen, und es wird kein Tastenereignis generiert. Wenn Sie zurück `false`gibt, <xref:System.Windows.Forms.Control.KeyDown> tritt ein-Ereignis auf.|  
  
### <a name="preprocessing-for-a-keypress-event"></a>Vorverarbeiten eines KeyPress-Ereignisses  
  
|Aktion|Verknüpfte Methode|Hinweise|  
|------------|--------------------|-----------|  
|Überprüfen Sie, ob die Taste ein normales Zeichen darstellt, das vom Steuerelement verarbeitet werden sollte|<xref:System.Windows.Forms.Control.IsInputChar%2A>|Wenn das Zeichen ein normales Zeichen ist, gibt diese Methode `true`zurück, <xref:System.Windows.Forms.Control.KeyPress> das-Ereignis wird ausgelöst, und es erfolgt keine weitere Vorverarbeitung. Andernfalls <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> wird aufgerufen.|  
|Überprüfen Sie, ob es sich bei dem Zeichen um ein mnemonisches Zeichen handelt (z.B. &OK auf einer Schaltfläche)|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|Diese Methode, ähnlich wie <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>, wird in der Steuerelement Hierarchie aufgerufen. Handelt es sich bei dem Steuerelement um ein Container Steuerelement, wird durch Aufrufen <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> von für sich selbst und dessen untergeordneter Steuerelemente nach mnetmonics gesucht. Wenn <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> zurück `true`gibt ,<xref:System.Windows.Forms.Control.KeyPress> tritt kein-Ereignis auf.|  
  
## <a name="processing-keyboard-messages"></a>Verarbeiten von Tastaturmeldungen  
 Nachdem Tastatur Meldungen die <xref:System.Windows.Forms.Control.WndProc%2A> Methode eines Formulars oder Steuer Elements erreicht haben, werden Sie von einer Reihe von Methoden verarbeitet, die überschrieben werden können. Jede dieser Methoden gibt einen <xref:System.Boolean> Wert zurück, der angibt, ob die Tastatur Meldung vom Steuerelement verarbeitet und verwendet wurde. Wenn eine der Methoden `true` zurückgibt, dann gilt die Nachricht als bearbeitet. Sie wird nicht zur weiteren Verarbeitung an das Basiselement oder das übergeordnete Element des Steuerelements übergeben. Andernfalls bleibt die Nachricht in der Nachrichtenwarteschlange und kann in einer anderen Methode im Basiselement oder übergeordneten Element des Steuerelements verarbeitet werden. Die folgende Tabelle enthält die Methoden, die Tastaturmeldungen verarbeiten.  
  
|Methode|Hinweise|  
|------------|-----------|  
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|Diese Methode verarbeitet alle Tastatur Meldungen, die von der <xref:System.Windows.Forms.Control.WndProc%2A> -Methode des-Steuer Elements empfangen werden.|  
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|Diese Methode sendet die Tastaturmeldung an das übergeordnete Element des Steuerelements. Wenn <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A> zurück `true`gibt, wird kein Schlüsselereignis generiert; <xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A> andernfalls wird aufgerufen.|  
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|Diese Methode löst die <xref:System.Windows.Forms.Control.KeyDown>Ereignisse <xref:System.Windows.Forms.Control.KeyPress>, und <xref:System.Windows.Forms.Control.KeyUp> entsprechend aus.|  
  
## <a name="overriding-keyboard-methods"></a>Überschreiben von Tastaturmethoden  
 Es sind viele Methoden zum Überschreiben verfügbar, wenn eine Tastaturmeldung vorverarbeitet und verarbeitet wird. Einige Methoden sind jedoch besser geeignet als andere. Die folgende Tabelle enthält Aufgaben, die Sie möglicherweise ausführen möchten, sowie die beste Methode für das Überschreiben der Tastaturmethoden. Weitere Informationen zum Überschreiben von Methoden finden Sie unter Überschreiben von [Eigenschaften und Methoden in abgeleiteten Klassen](../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md#overriding-properties-and-methods-in-derived-classes).  
  
|Aufgabe|Methode|  
|----------|------------|  
|Fangen Sie eine Navigations Taste ab und <xref:System.Windows.Forms.Control.KeyDown> rufen Sie ein-Ereignis auf. Beispiel: Sie möchten, dass die TAB- und die Return-Taste in einem Textfeld bearbeitet werden.|Überschreiben Sie <xref:System.Windows.Forms.Control.IsInputKey%2A>. **Hinweis**:  <xref:System.Windows.Forms.Control.PreviewKeyDown> Alternativ können Sie das-Ereignis und den-Satz <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> von <xref:System.Windows.Forms.PreviewKeyDownEventArgs> `true` für den gewünschten Schlüssel oder Schlüssel verarbeiten.|  
|Nehmen Sie bei einem Steuerelement eine besondere Eingabe oder Navigationsbehandlung vor. Beispiel: Sie möchten bei dem ausgewählten Element die Verwendung der Pfeiltasten in Ihrem Listensteuerelement ändern.|Überschreiben Sie <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>.|  
|Fangen Sie eine Navigations Taste ab und <xref:System.Windows.Forms.Control.KeyPress> rufen Sie ein-Ereignis auf. Beispiel: Sie möchten, dass durch mehrfaches Drücken der Pfeiltaste in einem Drehfeld-Steuerelement der Fortschritt durch die Elemente beschleunigt wird.|Überschreiben Sie <xref:System.Windows.Forms.Control.IsInputChar%2A>.|  
|Führen Sie während eines-Ereignisses eine <xref:System.Windows.Forms.Control.KeyPress> spezielle Eingabe-oder Navigations Behandlung aus. Beispiel: Wenn in einem Listensteuerelement die Taste „r“ gedrückt gehalten wird, werden Elemente übersprungen, die mit diesem Buchstaben beginnen.|Überschreiben Sie <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>.|  
|Führen Sie eine benutzerdefinierte Bearbeitung mnemonischer Zeichen durch. Beispiel: Sie möchten mnemonische Zeichen in von Benutzern gezeichneten Schaltflächen bearbeiten, die in einer Symbolleiste enthalten sind.|Überschreiben Sie <xref:System.Windows.Forms.Control.ProcessMnemonic%2A>.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.WndProc%2A>
- <xref:System.Windows.Forms.Control.PreProcessMessage%2A>
- [My.Computer.Keyboard-Objekt](../../visual-basic/language-reference/objects/my-computer-keyboard-object.md)
- [Zugreifen auf die Tastatur](../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md)
- [Verwenden von Tastaturereignissen](using-keyboard-events.md)
