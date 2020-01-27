---
title: Übersicht über das HScrollBar-Steuerelement und das VScrollBar-Steuerelement
ms.date: 03/30/2017
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
ms.openlocfilehash: abe0c8da9723f17cb80715454f6ab7297724a21f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728163"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>Übersicht über das HScrollBar-Steuerelement und das VScrollBar-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.ScrollBar>-Steuerelemente werden verwendet, um eine einfache Navigation durch eine lange Liste von Elementen oder eine große Menge an Informationen zu ermöglichen, indem Sie in einer Anwendung oder einem Steuerelement entweder horizontal oder vertikal scrollen. Scrollleisten sind ein gängiges Element der Windows-Benutzeroberfläche, sodass das <xref:System.Windows.Forms.ScrollBar> Steuerelement häufig mit Steuerelementen verwendet wird, die nicht von der <xref:System.Windows.Forms.ScrollableControl> Klasse abgeleitet werden. Ebenso haben viele Entwickler beim Erstellen Ihrer eigenen Benutzer Steuerelemente die Möglichkeit, das <xref:System.Windows.Forms.ScrollBar>-Steuerelement zu integrieren.  
  
 Die <xref:System.Windows.Forms.HScrollBar> (horizontal) und <xref:System.Windows.Forms.VScrollBar> (vertikalen) Steuerelemente agieren unabhängig von anderen Steuerelementen und verfügen über einen eigenen Satz von Ereignissen, Eigenschaften und Methoden. <xref:System.Windows.Forms.ScrollBar> Steuerelemente stimmen nicht mit den integrierten Schiebe leisten überein, die an Textfelder, Listenfelder, Kombinations Felder oder MDI-Formulare angefügt sind (das <xref:System.Windows.Forms.TextBox> Steuerelement verfügt über eine <xref:System.Windows.Forms.TextBox.ScrollBars%2A>-Eigenschaft, um Scrollleisten anzuzeigen oder auszublenden, die an das Steuerelement angefügt sind).  
  
 Die <xref:System.Windows.Forms.ScrollBar>-Steuerelemente verwenden das <xref:System.Windows.Forms.ScrollBar.Scroll>-Ereignis, um die Bewegung des Bild Lauf Felds (manchmal auch als Ziehpunkt bezeichnet) entlang der Bild Lauf Leiste zu überwachen. Die Verwendung des <xref:System.Windows.Forms.ScrollBar.Scroll> Ereignisses ermöglicht den Zugriff auf den Scrollleisten-Wert, während er gezogen wird.  
  
## <a name="value-property"></a>Value-Eigenschaft  
 Die <xref:System.Windows.Forms.ScrollBar.Value%2A>-Eigenschaft (standardmäßig 0) ist ein `integer` Wert, der der Position des Bild Lauf Felds auf der Bild Lauf Leiste entspricht. Wenn die Position des Bild Lauf Felds den Minimalwert hat, wechselt es zur äußersten linken Position (bei horizontalen Schiebe leisten) oder zur obersten Position (bei vertikalen Schiebe leisten). Wenn das Bild Lauf Feld den maximalen Wert hat, wechselt das Bild Lauf Feld nach rechts oder unten. Entsprechend wird ein Wert, der sich in der Mitte zwischen dem unteren und oberen Bereich des Bereichs befand, in der Mitte der Bild Lauf Leiste den führenden Rand des Bild Lauf Felds platziert.  
  
 Zusätzlich zur Verwendung von Mausklicks zum Ändern des Bild Lauf leisten Werts kann ein Benutzer auch das Bild Lauf Feld an einen beliebigen Punkt entlang der Leiste ziehen. Der resultierende Wert hängt von der Position des Bild Lauf Felds ab, liegt jedoch immer innerhalb des Bereichs der <xref:System.Windows.Forms.ScrollBar.Minimum%2A>, um die Eigenschaften zu <xref:System.Windows.Forms.ScrollBar.Maximum%2A>, die vom Benutzer festgelegt werden.  
  
## <a name="largechange-and-smallchange-properties"></a>LargeChange-und SmallChange-Eigenschaften  
 Wenn der Benutzer die Bild-auf-oder Bild-ab-Taste drückt oder in der Scrollleiste auf beiden Seiten des Bild Lauf Felds klickt, ändert sich die <xref:System.Windows.Forms.ScrollBar.Value%2A>-Eigenschaft entsprechend dem Wert, der in der <xref:System.Windows.Forms.ScrollBar.LargeChange%2A>-Eigenschaft festgelegt ist.  
  
 Wenn der Benutzer eine der Pfeiltasten drückt oder auf eine der Schiebe leisten Schaltflächen klickt, ändert sich die <xref:System.Windows.Forms.ScrollBar.Value%2A>-Eigenschaft entsprechend dem Wert, der in der <xref:System.Windows.Forms.ScrollBar.SmallChange%2A>-Eigenschaft festgelegt ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
