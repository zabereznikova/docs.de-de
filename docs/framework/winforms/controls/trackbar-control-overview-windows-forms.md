---
title: Übersicht über das TrackBar-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 1606db73485944f3dfa8b9c084bffda817520c7c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009265"
---
# <a name="trackbar-control-overview-windows-forms"></a>Übersicht über das TrackBar-Steuerelement (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.TrackBar> Control (manchmal auch als "ein"Slider"Steuerelement" bezeichnet) Dient zum Navigieren durch eine große Menge an Informationen oder für die visuelle Anpassung einer numerischen Einstellung. Die <xref:System.Windows.Forms.TrackBar> Steuerelement besteht aus zwei Teilen: dem Ziehpunkt, auch bekannt als einen Schieberegler, und die Teilstriche. Der Ziehpunkt ist der Teil, das angepasst werden kann. Entspricht die Position der <xref:System.Windows.Forms.TrackBar.Value%2A> Eigenschaft. Die Teilstriche sind visuelle Indikatoren, die in regelmäßigen Abständen angeordnet sind. Die Positionierungsleiste verschiebt, die Sie angeben und horizontal oder vertikal ausgerichtet werden können. Beispielsweise können Sie die Trackleiste verwenden, können Sie den Cursor Blink Rate oder der Maus Geschwindigkeit für ein System steuern.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Die Schlüsseleigenschaften von den <xref:System.Windows.Forms.TrackBar> sind <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, und <xref:System.Windows.Forms.TrackBar.Maximum%2A>. <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> Gibt den Abstand der Teilstriche. <xref:System.Windows.Forms.TrackBar.Minimum%2A> und <xref:System.Windows.Forms.TrackBar.Maximum%2A> sind die kleinsten und größten Werte, die auf der Trackleiste dargestellt werden können.  
  
 Zwei wichtige Eigenschaften sind <xref:System.Windows.Forms.TrackBar.SmallChange%2A> und <xref:System.Windows.Forms.TrackBar.LargeChange%2A>. Der Wert des der <xref:System.Windows.Forms.TrackBar.SmallChange%2A> -Eigenschaft ist die Anzahl von Positionen, die das Thumb-Steuerelement bewegt wird, nachdem die links oder nach-rechts-Taste gedrückt. Der Wert des der <xref:System.Windows.Forms.TrackBar.LargeChange%2A> -Eigenschaft ist die Anzahl der Positionen, um das Thumb-Steuerelement bewegt wird, nachdem die Bild-auf oder Bild-ab-Taste gedrückt oder als Reaktion auf Maus klickt auf der Trackleiste auf beiden Seiten des Ziehpunkts.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TrackBar>
- [TrackBar-Steuerelement](trackbar-control-windows-forms.md)
