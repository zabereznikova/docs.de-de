---
title: "Übersicht über das HScrollBar-Steuerelement und das VScrollBar-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7a6f1d569234f7cee4b5eedc81fcc68a41fcf0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>Übersicht über das HScrollBar-Steuerelement und das VScrollBar-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.ScrollBar> Steuerelemente werden verwendet, um die einfache Navigation in einer langen Liste von Elementen oder eine große Menge an Informationen entweder horizontal oder vertikal innerhalb einer Anwendung bzw. eines Steuerelements bereitzustellen. Bildlaufleisten sind ein häufiges Element der Windows-Schnittstelle, damit die <xref:System.Windows.Forms.ScrollBar> Steuerelement wird häufig mit Steuerelementen, die nicht von abgeleitet sind, verwendet der <xref:System.Windows.Forms.ScrollableControl> Klasse. Ebenso viele Entwickler wählen, integriert der <xref:System.Windows.Forms.ScrollBar> gesteuert werden, wenn ihre eigenen Benutzersteuerelemente zu erstellen.  
  
 Die <xref:System.Windows.Forms.HScrollBar> (horizontal) und <xref:System.Windows.Forms.VScrollBar> (vertikal) funktionieren unabhängig von anderen Steuerelementen und verfügen über ihre eigenen Satz von Ereignissen, Eigenschaften und Methoden. <xref:System.Windows.Forms.ScrollBar>Steuerelemente sind nicht identisch mit den integrierten Bildlaufleisten, die Textfelder, Kombinationsfelder oder MDI-Formulare zugeordnet sind (die <xref:System.Windows.Forms.TextBox> Steuerelement verfügt über eine <xref:System.Windows.Forms.TextBox.ScrollBars%2A> Eigenschaft anzeigen oder Ausblenden von Bildlaufleisten, die dem Steuerelement zugeordnet sind).  
  
 Die <xref:System.Windows.Forms.ScrollBar> steuert die Verwendung der <xref:System.Windows.Forms.ScrollBar.Scroll> Ereignis zum Überwachen von der Verschiebung des Bildlauffelds (auch als Ziehpunkt bezeichnet) entlang der Bildlaufleiste angezeigt. Mithilfe der <xref:System.Windows.Forms.ScrollBar.Scroll> Ereignis ermöglicht den Zugriff auf den Wert der Scroll Bar gezogen wird.  
  
## <a name="value-property"></a>Value-Eigenschaft  
 Die <xref:System.Windows.Forms.ScrollBar.Value%2A> -Eigenschaft (d. h. in der Standardeinstellung 0) ist ein `integer` Wert, der die Position des Bildlauffelds auf der Bildlaufleiste. Die Position des Bildlauffelds auf den Mindestwert ist, verschoben in die linke Position (für horizontale Bildlaufleisten) oder die obere Position (für die vertikalen Schiebeleisten). Wenn das Bildlauffeld auf der maximale Wert, der verschoben, die sich ganz rechts oder untere Position ist. Auf ähnliche Weise fügt ein Wert in der Mitte zwischen dem unteren und oberen Ende des Bereichs führenden Rand des Bildlauffelds in der Mitte der Bildlaufleiste angezeigt.  
  
 Benutzer kann mit Mausklicks so ändern Sie den Wert der Bildlaufleiste an, das Bildlauffeld auch auf einen beliebigen Punkt auf der Leiste ziehen. Der resultierende Wert hängt von der Position des Bildlauffelds allerdings handelt es sich immer innerhalb des Bereichs von der <xref:System.Windows.Forms.ScrollBar.Minimum%2A> auf <xref:System.Windows.Forms.ScrollBar.Maximum%2A> Eigenschaften, die vom Benutzer festgelegt.  
  
## <a name="largechange-and-smallchange-properties"></a>LargeChange und SmallChange-Eigenschaften  
 Wenn der Benutzer die Bild-auf oder Bild-ab-Taste drückt oder in der Schiebeleiste auf beiden Seiten des Bildlauffelds, klickt auf die <xref:System.Windows.Forms.ScrollBar.Value%2A> Eigenschaft ändert sich entsprechend der im festgelegte Wert die <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> Eigenschaft.  
  
 Tasten oder auf eine der Schaltflächen der Bildlaufleiste, wenn der Benutzer eine der Pfeiltasten drückt die <xref:System.Windows.Forms.ScrollBar.Value%2A> Eigenschaft ändert sich entsprechend der im festgelegte Wert die <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.HScrollBar>  
 <xref:System.Windows.Forms.VScrollBar>  
 [Ergänzungen für Windows Forms für .NET Framework 2.0](http://msdn.microsoft.com/en-us/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
