---
title: Funktionsweise von Mauseingaben in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
ms.openlocfilehash: 7817b6a414f313cd2891fe0e124e230643b06e07
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725324"
---
# <a name="how-mouse-input-works-in-windows-forms"></a>Funktionsweise von Mauseingaben in Windows Forms
Empfang und Verarbeitung von Mauseingaben ist ein wichtiger Bestandteil jeder Windows-Anwendung. Sie können Mausereignisse, die zum Ausführen einer Aktion in Ihrer Anwendung behandeln oder Mauspositionsinformationen Treffertests ausführen oder andere Aktionen. Darüber hinaus können Sie die Art ändern, die Steuerelemente in Ihrer Anwendung Mauseingaben behandeln. Dieses Thema beschreibt diese Mausereignisse im Detail und das Abrufen und Ändern von Systemeinstellungen für die Maus. Weitere Informationen zu den Daten, die mit der Maus bereitgestellten Ereignisse und die Reihenfolge, in dem die Maus, klicken Sie auf Ereignisse, ausgelöst werden, finden Sie unter [Mausereignisse in Windows Forms](mouse-events-in-windows-forms.md).  
  
## <a name="mouse-location-and-hit-testing"></a>Position des Mauszeigers und Treffertests  
 Wenn der Benutzer die Maus bewegt, wird das Betriebssystem der Mauszeiger bewegt. Der Mauszeiger die Form enthält ein einzelnes Pixel bezeichnet den Hotspot, die das Betriebssystem verfolgt und als die Position des Zeigers erkannt. Wenn der Benutzer die Maus bewegt oder eine Maustaste drückt, die <xref:System.Windows.Forms.Control> , enthält die <xref:System.Windows.Forms.Cursor.HotSpot%2A> löst das entsprechende Mausereignis. Erhalten Sie mit die aktuellen Position der <xref:System.Windows.Forms.MouseEventArgs.Location%2A> Eigenschaft der <xref:System.Windows.Forms.MouseEventArgs> beim ein Mausereignis zu behandeln oder mithilfe der <xref:System.Windows.Forms.Cursor.Position%2A> Eigenschaft der <xref:System.Windows.Forms.Cursor> Klasse. Sie können anschließend Mauspositionsinformationen verwenden, zum Ausführen von Treffertests und führen Sie dann eine Aktion basierend auf der Position des Mauszeigers. Hit-testing-Funktion direkt in mehreren Steuerelementen in Windows Forms wie z. B. die <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> und <xref:System.Windows.Forms.DataGridView> Steuerelemente. Das entsprechende Mausereignis, Verwendung <xref:System.Windows.Forms.Control.MouseHover> beispielsweise Treffertests ist sehr nützlich, um zu bestimmen, wenn Ihre Anwendung für eine bestimmte Aktion auszuführen, sollten.  
  
## <a name="mouse-events"></a>Mausereignisse  
 Der einfachste Weg, um die Maus zu reagieren ist, Behandeln von Mausereignissen. In der folgende Tabelle werden die Mausereignisse, und es wird beschrieben, wenn sie ausgelöst werden.  
  
|Mausereignis|Beschreibung|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|Dieses Ereignis tritt auf, wenn die Maustaste losgelassen wird, in der Regel vor der <xref:System.Windows.Forms.Control.MouseUp> Ereignis. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>. Behandeln Sie dieses Ereignis, wenn Sie müssen nur bestimmen, wann ein Klick erfolgt.|  
|<xref:System.Windows.Forms.Control.MouseClick>|Dieses Ereignis tritt auf, wenn der Benutzer das Steuerelement mit der Maus klickt. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>. Behandeln Sie dieses Ereignis, wenn müssen Sie Informationen über die Maus abrufen, bei ein Klick.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|Dieses Ereignis tritt auf, wenn das Steuerelement doppelgeklickt wird. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>. Behandeln Sie dieses Ereignis aus, wenn Sie nur benötigen, um zu bestimmen, wenn ein Doppelklick erfolgt.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|Dieses Ereignis tritt auf, wenn der Benutzer das Steuerelement mit der Maus doppelklickt. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>. Behandeln Sie dieses Ereignis, wenn müssen Sie Informationen über die Maus abrufen, wenn ein Doppelklick erfolgt.|  
|<xref:System.Windows.Forms.Control.MouseDown>|Dieses Ereignis tritt auf, wenn der Mauszeiger über das Steuerelement befindet und der Benutzer eine Maustaste drückt. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|Dieses Ereignis tritt auf, wenn der Mauszeiger auf den Rand oder den Bereich des Steuerelements je nach Art des Steuerelements eintritt. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseHover>|Dieses Ereignis tritt auf, wenn der Mauszeiger beendet und über dem Steuerelement befindet. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|Dieses Ereignis tritt auf, wenn der Mauszeiger auf den Rand oder den Bereich des Steuerelements je nach Art des Steuerelements verlässt. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseMove>|Dieses Ereignis tritt auf, wenn der Mauszeiger bewegt wird, während er sich über ein Steuerelement befindet. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseUp>|Dieses Ereignis tritt auf, wenn der Mauszeiger über das Steuerelement befindet und der Benutzer eine Maustaste loslässt. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|Dieses Ereignis tritt auf, wenn der Benutzer das Mausrad dreht, während das Steuerelement den Fokus besitzt. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>. Können Sie die <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> Eigenschaft <xref:System.Windows.Forms.MouseEventArgs> um zu bestimmen, wie weit die Maus ein Bildlauf durchgeführt wurde.|  
  
## <a name="changing-mouse-input-and-detecting-system-settings"></a>Ändern die Mauseingabe und Erkennen von Systemeinstellungen  
 Sie erkennen und ändern Sie die Möglichkeit, ein Steuerelement Mauseingabe, behandelt indem Sie das Steuerelement abgeleitet und, können die <xref:System.Windows.Forms.Control.GetStyle%2A> und <xref:System.Windows.Forms.Control.SetStyle%2A> Methoden. Die <xref:System.Windows.Forms.Control.SetStyle%2A> Methode akzeptiert eine bitweise Kombination von <xref:System.Windows.Forms.ControlStyles> Werte, um zu bestimmen, ob das Steuerelement hat Standard klicken oder doppelklicken Sie auf Verhalten oder das Steuerelement seine eigene mausverarbeitung behandelt. Darüber hinaus die <xref:System.Windows.Forms.SystemInformation> Klasse enthält Eigenschaften, die Beschreibung der Funktionen der Maus und angeben, wie sich die Maus mit dem Betriebssystem interagiert. In der folgende Tabelle werden diese Eigenschaften zusammengefasst.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|Ruft die Abmessungen in Pixel ab, der den Bereich, in dem der Benutzer zweimal für das Betriebssystem zu berücksichtigen die beiden klicken muss, Mausklicks als Doppelklick erkannt.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|Ruft die maximale Anzahl von Millisekunden, die zwischen dem ersten und des Betriebssystems die Mausaktion eines Doppelklick mit einem zweiten Mausklick verstreichen können.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|Ruft die Anzahl der Maustasten ab.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|Ruft einen Wert ab, der angibt, ob die Funktionen der linken und der rechten Maustaste vertauscht wurden.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|Ruft die Abmessungen des Rechtecks in Pixel ab, auf das der Mauszeiger für eine bestimmte Zeit zeigen muss, bevor eine Mausbewegungsmeldung generiert wird.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|Ruft die Zeit in Millisekunden ab, für die sich der Mauszeiger im Bewegungsrechteck befinden muss, bevor eine Mausbewegungsmeldung generiert wird.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|Ruft einen Wert, der angibt, ob eine Maus installiert ist.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|Ruft einen Wert, der angibt, der aktuelle mausgeschwindigkeit von 1 bis 20.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|Ruft einen Wert ab, der angibt, ob eine Maus mit einem Mausrad installiert ist.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|Ruft die Menge des deltawerts Schrittweite für die eine einzelne Drehung des Mausrads ab.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|Ruft die Anzahl der Zeilen ab, die mit einem Bildlauf erfasst werden, wenn das Mausrad gedreht wird.|  
  
## <a name="see-also"></a>Siehe auch
- [Mauseingabe in einer Windows Forms-Anwendung](mouse-input-in-a-windows-forms-application.md)
- [Mauserfassung in Windows Forms](mouse-capture-in-windows-forms.md)
- [Mauszeiger in Windows Forms](mouse-pointers-in-windows-forms.md)
