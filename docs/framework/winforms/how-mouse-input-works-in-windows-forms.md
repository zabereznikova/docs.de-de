---
title: Funktionsweise von Maus Eingaben
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
ms.openlocfilehash: 1164974e65ca1e96c0650569626ad4140baf004e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739633"
---
# <a name="how-mouse-input-works-in-windows-forms"></a>Funktionsweise von Mauseingaben in Windows Forms
Das empfangen und Verarbeiten von Maus Eingaben ist ein wichtiger Bestandteil jeder Windows-Anwendung. Sie können Mausereignisse behandeln, um eine Aktion in Ihrer Anwendung auszuführen, oder Sie können Maus Positionsinformationen verwenden, um Treffer Tests oder andere Aktionen auszuführen. Außerdem können Sie die Art und Weise ändern, in der die Steuerelemente in der Anwendung Maus Eingaben verarbeiten. In diesem Thema werden diese Mausereignisse ausführlich beschrieben, und es wird beschrieben, wie Sie die Systemeinstellungen für die Maus abrufen und ändern. Weitere Informationen zu den mit den Mausereignissen bereitgestellten Daten und der Reihenfolge, in der die Maus Klick Ereignisse ausgelöst werden, finden Sie unter [Mausereignisse in Windows Forms](mouse-events-in-windows-forms.md).  
  
## <a name="mouse-location-and-hit-testing"></a>Mausposition und Treffer Tests  
 Wenn der Benutzer die Maus bewegt, verschiebt das Betriebssystem den Mauszeiger. Der Mauszeiger enthält ein einzelnes Pixel, das als Hot-Spot bezeichnet wird, das vom Betriebssystem nachverfolgt und als Position des Zeigers erkannt wird. Wenn der Benutzer die Maus bewegt oder eine Maustaste drückt, löst die <xref:System.Windows.Forms.Control>, die die <xref:System.Windows.Forms.Cursor.HotSpot%2A> enthält, das entsprechende Maus Ereignis aus. Sie können die aktuelle Mausposition mit der <xref:System.Windows.Forms.MouseEventArgs.Location%2A>-Eigenschaft des <xref:System.Windows.Forms.MouseEventArgs> abrufen, wenn ein Maus Ereignis behandelt wird, oder indem Sie die <xref:System.Windows.Forms.Cursor.Position%2A>-Eigenschaft der <xref:System.Windows.Forms.Cursor>-Klasse verwenden. Anschließend können Sie mithilfe von Maus Positionsinformationen Treffer Tests durchführen und dann eine Aktion basierend auf der Position der Maus ausführen. Die Treffer Testfunktion ist in mehrere Steuerelemente in Windows Forms integriert, z. b. die Steuerelemente <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> und <xref:System.Windows.Forms.DataGridView>. Wird mit dem entsprechenden Maus Ereignis verwendet, <xref:System.Windows.Forms.Control.MouseHover> beispielsweise ist die Treffer Überprüfung sehr nützlich, um zu bestimmen, wann die Anwendung eine bestimmte Aktion ausführen soll.  
  
## <a name="mouse-events"></a>Mausereignisse  
 Die primäre Methode, auf die Maus Eingaben zu reagieren, besteht darin, Mausereignisse zu behandeln. In der folgenden Tabelle werden die Mausereignisse angezeigt, und es wird beschrieben, wann Sie ausgelöst werden.  
  
|Mausereignis|Beschreibung|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|Dieses Ereignis tritt auf, wenn die Maustaste losgelassen wird, in der Regel vor dem <xref:System.Windows.Forms.Control.MouseUp>-Ereignis. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>. Behandeln Sie dieses Ereignis, wenn Sie nur bestimmen müssen, wann ein Klick auftritt.|  
|<xref:System.Windows.Forms.Control.MouseClick>|Dieses Ereignis tritt auf, wenn der Benutzer mit der Maus auf das-Steuerelement klickt. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>. Behandeln Sie dieses Ereignis, wenn Sie Informationen über die Maus erhalten müssen, wenn ein Klick auftritt.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|Dieses Ereignis tritt auf, wenn auf das Steuerelement Doppel geklickt wird. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>. Behandeln Sie dieses Ereignis, wenn Sie nur bestimmen müssen, wann ein Doppelklick auftritt.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|Dieses Ereignis tritt auf, wenn der Benutzer mit der Maus auf das-Steuerelement doppelklickt. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>. Behandeln Sie dieses Ereignis, wenn Sie Informationen über die Maus erhalten müssen, wenn ein Doppelklick auftritt.|  
|<xref:System.Windows.Forms.Control.MouseDown>|Dieses Ereignis tritt auf, wenn sich der Mauszeiger über dem Steuerelement befindet und der Benutzer eine Maustaste drückt. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|Dieses Ereignis tritt auf, wenn der Mauszeiger in den Rahmen oder den Client Bereich des Steuer Elements wechselt, abhängig vom Typ des Steuer Elements. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseHover>|Dieses Ereignis tritt auf, wenn der Mauszeiger angehalten wird und sich über dem Steuerelement befindet. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|Dieses Ereignis tritt auf, wenn der Mauszeiger den Rahmen oder den Client Bereich des Steuer Elements verlässt, abhängig vom Typ des Steuer Elements. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseMove>|Dieses Ereignis tritt auf, wenn der Mauszeiger bewegt wird, während er sich über einem-Steuerelement befindet. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseUp>|Dieses Ereignis tritt auf, wenn sich der Mauszeiger über dem Steuerelement befindet und der Benutzer eine Maustaste loslässt. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|Dieses Ereignis tritt auf, wenn der Benutzer das Mausrad dreht, während das Steuerelement den Fokus besitzt. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>. Sie können die <xref:System.Windows.Forms.MouseEventArgs.Delta%2A>-Eigenschaft von <xref:System.Windows.Forms.MouseEventArgs> verwenden, um zu bestimmen, wie weit der Mauszeiger gescrollt wurde.|  
  
## <a name="changing-mouse-input-and-detecting-system-settings"></a>Ändern der Maus Eingaben und erkennen von System Einstellungen  
 Sie können die Methode, mit der ein Steuerelement Maus Eingaben behandelt, erkennen und ändern, indem Sie vom-Steuerelement ableiten und die Methoden <xref:System.Windows.Forms.Control.GetStyle%2A> und <xref:System.Windows.Forms.Control.SetStyle%2A> verwenden. Die <xref:System.Windows.Forms.Control.SetStyle%2A>-Methode verwendet eine bitweise Kombination von <xref:System.Windows.Forms.ControlStyles> Werten, um zu bestimmen, ob das Steuerelement ein Standardmäßiges Click-oder Doppelklick Verhalten aufweist oder ob das Steuerelement seine eigene Maus Verarbeitung behandelt. Außerdem enthält die <xref:System.Windows.Forms.SystemInformation>-Klasse Eigenschaften, die die Funktionen der Maus beschreiben und angeben, wie die Maus mit dem Betriebssystem interagiert. In der folgenden Tabelle werden diese Eigenschaften zusammengefasst.  
  
|Die Eigenschaften-|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|Ruft die Abmessungen des Bereichs in Pixel ab, in dem der Benutzer zweimal auf die beiden Klicks klicken muss, damit das Betriebssystem auf einen Doppelklick klickt.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|Ruft die maximale Anzahl von Millisekunden ab, die zwischen dem ersten und einem zweiten Mausklick vergehen können, damit das Betriebssystem die Maus Aktion als Doppelklick berücksichtigt.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|Ruft die Anzahl der Maustasten ab.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|Ruft einen Wert ab, der angibt, ob die Funktionen der linken und der rechten Maustaste vertauscht wurden.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|Ruft die Abmessungen des Rechtecks in Pixel ab, auf das der Mauszeiger für eine bestimmte Zeit zeigen muss, bevor eine Mausbewegungsmeldung generiert wird.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|Ruft die Zeit in Millisekunden ab, für die sich der Mauszeiger im Bewegungsrechteck befinden muss, bevor eine Mausbewegungsmeldung generiert wird.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|Ruft einen Wert ab, der angibt, ob eine Maus installiert ist.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|Ruft einen Wert ab, der die aktuelle Maus Geschwindigkeit zwischen 1 und 20 angibt.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|Ruft einen Wert ab, der angibt, ob eine Maus mit einem Mausrad installiert ist.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|Ruft die Menge des Delta Werts für das Inkrement einer einzelnen Mausrad Drehung ab.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|Ruft die Anzahl der Zeilen ab, die mit einem Bildlauf erfasst werden, wenn das Mausrad gedreht wird.|  
  
## <a name="see-also"></a>Siehe auch

- [Mauseingabe in einer Windows Forms-Anwendung](mouse-input-in-a-windows-forms-application.md)
- [Mauserfassung in Windows Forms](mouse-capture-in-windows-forms.md)
- [Mauszeiger in Windows Forms](mouse-pointers-in-windows-forms.md)
