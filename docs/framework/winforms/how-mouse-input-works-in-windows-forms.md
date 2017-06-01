---
title: "Funktionsweise von Mauseingaben in Windows Forms | Microsoft Docs"
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
  - "Maus, Eingabe"
  - "Windows Forms, Mauseingabe"
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Funktionsweise von Mauseingaben in Windows Forms
Das Empfangen und Behandeln von Mauseingaben ist ein wichtiger Bestandteil jeder Windows\-Anwendung.  Sie können Mausereignisse behandeln, um eine Aktion in der Anwendung auszuführen, oder mithilfe von Mauspositionsdaten Hit\-Testing oder andere Aktionen ausführen.  Außerdem können Sie die Art und Weise ändern, wie die Steuerelemente in der Anwendung Mauseingaben behandeln.  In diesem Thema werden diese Mausereignisse im Einzelnen beschrieben. Außerdem wird erläutert, wie Systemeinstellungen für die Maus abgerufen und geändert werden.  Weitere Informationen über die mit den Mausereignissen bereitgestellten Daten und die Reihenfolge, in der die Mausklickereignisse ausgelöst werden, finden Sie unter [Mausereignisse in Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).  
  
## Mausposition und Hit\-Testing  
 Wenn der Benutzer die Maus bewegt, bewegt das Betriebssystem den Mauszeiger.  Der Mauszeiger enthält ein einzelnes Pixel, den so genannten Hotspot, den das Betriebssystem verfolgt und als Position des Zeigers erkennt.  Wenn der Benutzer die Maus bewegt oder eine Maustaste drückt, löst das <xref:System.Windows.Forms.Control>, das <xref:System.Windows.Forms.Cursor.HotSpot%2A> enthält, ein entsprechendes Mausereignis aus.  Sie können die aktuelle Mausposition mit der <xref:System.Windows.Forms.MouseEventArgs.Location%2A>\-Eigenschaft des <xref:System.Windows.Forms.MouseEventArgs> abrufen, wenn Sie ein Mausereignis behandeln, oder über die <xref:System.Windows.Forms.Cursor.Position%2A>\-Eigenschaft des <xref:System.Windows.Forms.Cursor>.  Anschließend können Sie mithilfe der Mauspositionsinformationen Hit\-Testing ausführen und dann eine Aktion, die auf der Position der Maus basiert.  Die Hit\-Testing\-Funktion ist in zahlreiche Steuerelemente in Windows Forms integriert, beispielsweise in die Steuerelemente <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> und <xref:System.Windows.Forms.DataGridView>.  In Verbindung mit einem entsprechenden Mausereignis, beispielsweise <xref:System.Windows.Forms.Control.MouseHover>, eignet sich Hit\-Testing, um zu bestimmen, wann die Anwendung eine bestimmte Aktion ausführen soll.  
  
## Mausereignisse  
 Eine Möglichkeit der Reaktion auf Mauseingaben besteht in erster Linie darin, Mausereignisse zu behandeln.  In der folgenden Tabelle werden die Mausereignisse angezeigt, und es wird beschrieben, wann sie ausgelöst werden.  
  
|Mausereignis|Beschreibung|  
|------------------|------------------|  
|<xref:System.Windows.Forms.Control.Click>|Dieses Ereignis tritt auf, wenn die Maustaste losgelassen wird, normalerweise vor dem <xref:System.Windows.Forms.Control.MouseUp>\-Ereignis.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>.  Behandeln Sie dieses Ereignis, wenn Sie nur feststellen müssen, wann ein Klick erfolgt.|  
|<xref:System.Windows.Forms.Control.MouseClick>|Dieses Ereignis tritt auf, wenn der Benutzer mit der Maus auf das Steuerelement klickt.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>.  Behandeln Sie dieses Ereignis, wenn Sie Informationen über die Maus abrufen müssen, wenn ein Klick erfolgt.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|Dieses Ereignis tritt auf, wenn auf das Steuerelement doppelt geklickt wird.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>.  Behandeln Sie dieses Ereignis, wenn Sie nur feststellen müssen, wann ein Doppelklick erfolgt.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|Dieses Ereignis tritt auf, wenn der Benutzer mit der Maus auf das Steuerelement doppelklickt.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>.  Behandeln Sie dieses Ereignis, wenn Sie Informationen über die Maus abrufen müssen, wenn ein Doppelklick erfolgt.|  
|<xref:System.Windows.Forms.Control.MouseDown>|Dieses Ereignis tritt auf, wenn sich der Mauszeiger über dem Steuerelement befindet und der Benutzer eine Maustaste drückt.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|Dieses Ereignis tritt auf, wenn der Mauszeiger den Rand oder den Innenbereich des Steuerelements berührt, je nach Art des Steuerelements.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseHover>|Dieses Ereignis tritt auf, wenn der Mauszeiger über dem Steuerelement ruht.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|Dieses Ereignis tritt auf, wenn der Mauszeiger den Rand oder den Innenbereich des Steuerelements verlässt, je nach Art des Steuerelements.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseMove>|Dieses Ereignis tritt auf, wenn der Mauszeiger bewegt wird, während er sich über einem Steuerelement befindet.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseUp>|Dieses Ereignis tritt auf, wenn sich der Mauszeiger über dem Steuerelement befindet und der Benutzer eine Maustaste loslässt.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|Dieses Ereignis tritt auf, wenn der Benutzer das Mausrad dreht, während das Steuerelement im Fokus ist.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.MouseEventArgs>.  Sie können mithilfe der <xref:System.Windows.Forms.MouseEventArgs.Delta%2A>\-Eigenschaft von <xref:System.Windows.Forms.MouseEventArgs> bestimmen, wie weit die Maus einen Bildlauf durchgeführt hat.|  
  
## Ändern von Mauseingabe und Erkennen von Systemeinstellungen  
 Sie können die Art, wie ein Steuerelement die Mauseingabe behandelt, erkennen und ändern, indem Sie von dem Steuerelement ableiten sowie die <xref:System.Windows.Forms.Control.GetStyle%2A>\-Methode und die <xref:System.Windows.Forms.Control.SetStyle%2A>\-Methode verwenden.  Die <xref:System.Windows.Forms.Control.SetStyle%2A>\-Methode bestimmt anhand einer bitweisen Kombination von <xref:System.Windows.Forms.ControlStyles>\-Werten, ob das Steuerelement Standard\- oder Doppelklickverhalten aufweist oder ob es seine eigene Mausverarbeitung behandelt.  Darüber hinaus umfasst die <xref:System.Windows.Forms.SystemInformation>\-Klasse Eigenschaften, die die Funktionen der Maus beschreiben und die festlegen, wie die Maus mit dem Betriebssystem interagiert.  In der folgenden Tabelle werden diese Eigenschaften zusammengefasst.  
  
|Property|Beschreibung|  
|--------------|------------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|Ruft die Abmessungen des Bereichs in Pixel ab, in den der Benutzer zweimal klicken muss, damit das Betriebssystem die beiden Klicks als einen Doppelklick interpretiert.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|Ruft die maximale Anzahl an Millisekunden ab, die zwischen einem ersten und einem zweiten Klick verstreichen können, damit das Betriebssystem die Mausaktion als Doppelklick interpretiert.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|Ruft die Anzahl der Maustasten ab.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|Ruft einen Wert ab, der angibt, ob die Funktionen der linken und der rechten Maustaste vertauscht wurden.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|Ruft die Abmessungen des Rechtecks in Pixel ab, auf das der Mauszeiger für eine bestimmte Zeit zeigen muss, bevor eine Mausbewegungsmeldung generiert wird.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|Ruft die Zeit in Millisekunden ab, für die sich der Mauszeiger im Bewegungsrechteck befinden muss, bevor eine Mausbewegungsmeldung generiert wird.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|Ruft einen Wert ab, der angibt, ob eine Maus installiert ist.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|Ruft einen Wert ab, der die aktuelle Mausgeschwindigkeit angibt \(zwischen 1 und 20\).|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|Ruft einen Wert ab, der angibt, ob eine Maus mit einem Mausrad installiert ist.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|Ruft die Höhe des Deltawerts der Erhöhung einer einzelnen Mausraddrehung ab.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|Ruft die Anzahl der Zeilen ab, die mit einem Bildlauf erfasst werden, wenn das Mausrad gedreht wird.|  
  
## Siehe auch  
 [Mauseingabe in einer Windows Forms\-Anwendung](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)   
 [Mauserfassung in Windows Forms](../../../docs/framework/winforms/mouse-capture-in-windows-forms.md)   
 [Mauszeiger in Windows Forms](../../../docs/framework/winforms/mouse-pointers-in-windows-forms.md)