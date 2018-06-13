---
title: Funktionsweise von Tastatureingaben
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard input [Windows Forms], about keyboard input
- keyboards [Windows Forms], keyboard input
- Windows Forms, keyboard input
ms.assetid: 9a29433c-a180-49bb-b74c-d187786584c8
ms.openlocfilehash: a0b814a18f4a8b25fba9fa0b36da44954590f056
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541345"
---
# <a name="how-keyboard-input-works"></a>Funktionsweise von Tastatureingaben
Windows Forms verarbeitet Tastatureingaben, indem als Reaktion auf Windows-Meldungen Tastaturereignisse ausgelöst werden. Die meisten Windows Forms-Anwendungen verarbeiten Tastatureingaben ausschließlich durch Bearbeiten der Tastaturereignisse. Sie müssen jedoch die Funktionsweise von Tastaturnachrichten verstehen, damit Sie erweiterte Tastatureingabeszenarios implementieren können, wie z.B. das Abfangen von Schlüssel, bevor diese ein Steuerelement erreichen. Dieses Thema beschreibt die Typen von Schlüsseldaten, die Windows Forms erkennt, und bietet eine Übersicht darüber, wie Tastaturnachrichten weitergeleitet werden. Informationen zu Tastaturereignissen finden Sie unter [Verwenden von Tastaturereignissen](../../../docs/framework/winforms/using-keyboard-events.md).  
  
## <a name="types-of-keys"></a>Typen von Tasten  
 Windows Forms identifiziert Tastatureingaben als virtuelle Tastencodes, die durch die bitweisen dargestellt sind <xref:System.Windows.Forms.Keys> Enumeration. Mit der <xref:System.Windows.Forms.Keys> -Enumeration, Sie können eine Reihe von gedrückten Taste, um einen einzelnen Wert ergeben kombinieren. Diese Werte entsprechen den Werten, die in den Windows-Nachrichten WM_KEYDOWN und WM_SYSKEYDOWN enthalten sind. Sie können die meisten physische Tastatureingaben erkennen, durch Behandeln der <xref:System.Windows.Forms.Control.KeyDown> oder <xref:System.Windows.Forms.Control.KeyUp> Ereignisse. Zeichentasten bilden einen Teil der <xref:System.Windows.Forms.Keys> Enumeration und entsprechen den Werten, die die Nachrichten WM_CHAR und WM_SYSCHAR Windows offen. Wenn die gedrückte Tastenkombination in einem Zeichen ergibt, können Sie das Zeichen erkennen, durch Behandeln der <xref:System.Windows.Forms.Control.KeyPress> Ereignis. Alternativ können Sie <xref:Microsoft.VisualBasic.Devices.Keyboard>, vom Visual Basic-Programmierschnittstelle ermitteln, welche-Taste gedrückt wurden und senden Schlüssel verfügbar gemacht. Weitere Informationen finden Sie unter [Zugreifen auf die Tastatur](~/docs/visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md).  
  
## <a name="order-of-keyboard-events"></a>Reihenfolge von Tastaturereignissen  
 Wie oben aufgeführt gibt es drei mit der Tastatur verknüpfte Ereignisse, die in einem Steuerelement auftreten können. Die folgende Sequenz zeigt die allgemeine Reihenfolge der Ereignisse:  
  
1.  Der Benutzer drückt die Taste "a", der Schlüssel vorverarbeitet und gesendet, und ein <xref:System.Windows.Forms.Control.KeyDown> Ereignis auftritt.  
  
2.  Der Benutzer die Taste "a" hält, der Schlüssel vorverarbeitet und gesendet, und ein <xref:System.Windows.Forms.Control.KeyPress> Ereignis auftritt.  
  
     Dieses Ereignis tritt mehrmals auf, wenn der Benutzer eine Taste gedrückt hält.  
  
3.  Der Benutzer lässt die Taste "a, der Schlüssel" wird vorverarbeitet, verteilt und ein <xref:System.Windows.Forms.Control.KeyUp> Ereignis auftritt.  
  
## <a name="preprocessing-keys"></a>Vorverarbeiten von Tasten  
 Wie andere Meldungen, Tastatur Nachrichten verarbeitet werden, der <xref:System.Windows.Forms.Control.WndProc%2A> Methode von einem Formular oder Steuerelement. Allerdings vor Tastatur Nachrichten verarbeitet werden, die <xref:System.Windows.Forms.Control.PreProcessMessage%2A> Methode ruft eine oder mehrere Methoden, die überschrieben werden können, um spezielle Zeichentasten und Steuer-bzw. Funktionstasten zu behandeln. Sie können diese Methoden zum Erkennen und Filtern bestimmter Tasten überschreiben, bevor die Nachrichten vom Steuerelement verarbeitet werden. Die folgende Tabelle zeigt die Aktion an, die ausgeführt wird und die zugehörige Methode die auftritt, in der Reihenfolge, in der die Methode auftritt.  
  
### <a name="preprocessing-for-a-keydown-event"></a>Vorverarbeiten eines KeyDown-Ereignisses  
  
|Aktion|Verknüpfte Methode|Hinweise|  
|------------|--------------------|-----------|  
|Überprüfen Sie, ob eine Befehlstaste vorhanden ist, z.B. eine Zugriffstaste oder eine Menü-Tastenkombination.|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|Diese Methode verarbeitet eine Befehlstaste, die Vorrang gegenüber regulären Tasten hat. Wenn diese Methode `true` zurückgibt, wird die Schlüsselmeldung nicht weitergeleitet, und es tritt kein Schlüsselereignis auf. Wenn zurückgegeben `false`, <xref:System.Windows.Forms.Control.IsInputKey%2A> wird aufgerufen`.`|  
|Überprüfen Sie für eine spezielle Taste, die vorverarbeitung erforderlich ist oder ein normales Zeichen-Schlüssel, der auslösen soll eine <xref:System.Windows.Forms.Control.KeyDown> Ereignis und an ein Steuerelement verteilt werden.|<xref:System.Windows.Forms.Control.IsInputKey%2A>|Wenn die-Methode zurückgibt `true`, es bedeutet, dass das Steuerelement ist ein reguläres Zeichen und ein <xref:System.Windows.Forms.Control.KeyDown> Ereignis wird ausgelöst. Wenn `false`, <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> aufgerufen wird. **Hinweis:** um sicherzustellen, dass ein Steuerelement ruft einen Schlüssel oder eine Tastenkombination, behandeln Sie die <xref:System.Windows.Forms.Control.PreviewKeyDown> Ereignis, und legen <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> von der <xref:System.Windows.Forms.PreviewKeyDownEventArgs> zu `true` für die Tasten werden sollen.|  
|Führen Sie eine Überprüfung auf eine Navigationstaste aus (ESC-, TAB-, Return oder Pfeiltaste).|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|Diese Methode verarbeitet eine physische Taste, die eine besondere Funktionalität innerhalb des Steuerelements nutzt und z.B. den Fokus zwischen dem Steuerelement und seinem übergeordneten Element umschaltet. Wenn die direkte Kontrolle den Schlüssel nicht verarbeiten kann die <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> für das übergeordnete Steuerelement und so weiter auf das oberste Steuerelement in der Hierarchie aufgerufen wird. Wenn diese Methode `true` zurückgibt, ist die Vorverarbeitung abgeschlossen, und es wird kein Tastenereignis generiert. Wenn zurückgegeben `false`ein <xref:System.Windows.Forms.Control.KeyDown> Ereignis auftritt.|  
  
### <a name="preprocessing-for-a-keypress-event"></a>Vorverarbeiten eines KeyPress-Ereignisses  
  
|Aktion|Verknüpfte Methode|Hinweise|  
|------------|--------------------|-----------|  
|Überprüfen Sie, ob die Taste ein normales Zeichen darstellt, das vom Steuerelement verarbeitet werden sollte|<xref:System.Windows.Forms.Control.IsInputChar%2A>|Wenn das Zeichen ein normales Zeichen ist, gibt diese Methode `true`die <xref:System.Windows.Forms.Control.KeyPress> Ereignis wird ausgelöst, und keine weiteren vorverarbeitung auftritt. Andernfalls <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> aufgerufen wird.|  
|Überprüfen Sie, ob es sich bei dem Zeichen um ein mnemonisches Zeichen handelt (z.B. &OK auf einer Schaltfläche)|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|Diese Methode ähnelt <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>, wird der Steuerelementhierarchie nach oben aufgerufen werden. Wenn das Steuerelement ein Container-Steuerelement ist, er überprüft Mnemonik durch Aufrufen von <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> auf sich selbst und seine untergeordneten Steuerelemente. Wenn <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> gibt `true`ein <xref:System.Windows.Forms.Control.KeyPress> Ereignis tritt nicht auf.|  
  
## <a name="processing-keyboard-messages"></a>Verarbeiten von Tastaturmeldungen  
 Nach der Tastatur Reach Nachrichten die <xref:System.Windows.Forms.Control.WndProc%2A> Methode von einem Formular oder Steuerelement, verarbeitet werden durch eine Reihe von Methoden, die überschrieben werden kann. Jede dieser Methoden gibt eine <xref:System.Boolean> Wert, der angibt, ob die Tastatureingabe verarbeitet und vom Steuerelement verarbeitet wurde. Wenn eine der Methoden `true` zurückgibt, dann gilt die Nachricht als bearbeitet. Sie wird nicht zur weiteren Verarbeitung an das Basiselement oder das übergeordnete Element des Steuerelements übergeben. Andernfalls bleibt die Nachricht in der Nachrichtenwarteschlange und kann in einer anderen Methode im Basiselement oder übergeordneten Element des Steuerelements verarbeitet werden. Die folgende Tabelle enthält die Methoden, die Tastaturmeldungen verarbeiten.  
  
|Methode|Hinweise|  
|------------|-----------|  
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|Diese Methode verarbeitet alle Tastatur-Nachrichten, die von empfangen werden die <xref:System.Windows.Forms.Control.WndProc%2A> Methode des Steuerelements.|  
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|Diese Methode sendet die Tastaturmeldung an das übergeordnete Element des Steuerelements. Wenn <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A> gibt `true`, ohne ein Ereignis generiert wird, andernfalls <xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A> aufgerufen wird.|  
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|Diese Methode löst die <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, und <xref:System.Windows.Forms.Control.KeyUp> Ereignisse nach Bedarf.|  
  
## <a name="overriding-keyboard-methods"></a>Überschreiben von Tastaturmethoden  
 Es sind viele Methoden zum Überschreiben verfügbar, wenn eine Tastaturmeldung vorverarbeitet und verarbeitet wird. Einige Methoden sind jedoch besser geeignet als andere. Die folgende Tabelle enthält Aufgaben, die Sie möglicherweise ausführen möchten, sowie die beste Methode für das Überschreiben der Tastaturmethoden. Weitere Informationen zum Überschreiben von Methoden finden Sie unter [Überschreiben von Eigenschaften und Methoden in abgeleiteten Klassen](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md#overriding-properties-and-methods-in-derived-classes).  
  
|Aufgabe|Methode|  
|----------|------------|  
|Abfangen eine Navigationstaste und Auslösen einer <xref:System.Windows.Forms.Control.KeyDown> Ereignis. Beispiel: Sie möchten, dass die TAB- und die Return-Taste in einem Textfeld bearbeitet werden.|Überschreiben Sie <xref:System.Windows.Forms.Control.IsInputKey%2A>. **Hinweis:** Alternativ können Sie behandeln die <xref:System.Windows.Forms.Control.PreviewKeyDown> Ereignis, und legen <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> von der <xref:System.Windows.Forms.PreviewKeyDownEventArgs> zu `true` für die Tasten werden sollen.|  
|Nehmen Sie bei einem Steuerelement eine besondere Eingabe oder Navigationsbehandlung vor. Beispiel: Sie möchten bei dem ausgewählten Element die Verwendung der Pfeiltasten in Ihrem Listensteuerelement ändern.|Überschreiben Sie <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>.|  
|Abfangen eine Navigationstaste und Auslösen einer <xref:System.Windows.Forms.Control.KeyPress> Ereignis. Beispiel: Sie möchten, dass durch mehrfaches Drücken der Pfeiltaste in einem Drehfeld-Steuerelement der Fortschritt durch die Elemente beschleunigt wird.|Überschreiben Sie <xref:System.Windows.Forms.Control.IsInputChar%2A>.|  
|Behandlung spezielle Eingabe oder Navigationstasten während einer <xref:System.Windows.Forms.Control.KeyPress> Ereignis. Beispiel: Wenn in einem Listensteuerelement die Taste „r“ gedrückt gehalten wird, werden Elemente übersprungen, die mit diesem Buchstaben beginnen.|Überschreiben Sie <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>.|  
|Führen Sie eine benutzerdefinierte Bearbeitung mnemonischer Zeichen durch. Beispiel: Sie möchten mnemonische Zeichen in von Benutzern gezeichneten Schaltflächen bearbeiten, die in einer Symbolleiste enthalten sind.|Überschreiben Sie <xref:System.Windows.Forms.Control.ProcessMnemonic%2A>.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Keys>  
 <xref:System.Windows.Forms.Control.WndProc%2A>  
 <xref:System.Windows.Forms.Control.PreProcessMessage%2A>  
 [My.Computer.Keyboard-Objekt](~/docs/visual-basic/language-reference/objects/my-computer-keyboard-object.md)  
 [Zugreifen auf die Tastatur](~/docs/visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md)  
 [Verwenden von Tastaturereignissen](../../../docs/framework/winforms/using-keyboard-events.md)
