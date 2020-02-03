---
title: Übersicht über das TrackBar-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 6901405100df4633c84850757f55b756bc9a0199
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741465"
---
# <a name="trackbar-control-overview-windows-forms"></a>Übersicht über das TrackBar-Steuerelement (Windows Forms)
Das Windows Forms <xref:System.Windows.Forms.TrackBar>-Steuerelement (auch als "Schieberegler" bezeichnet) wird zum Navigieren durch eine große Menge an Informationen oder zum visuellen Anpassen einer numerischen Einstellung verwendet. Das <xref:System.Windows.Forms.TrackBar> Steuerelement besteht aus zwei Teilen: dem Thumb-Steuerelement, auch als Schieberegler bezeichnet, und den Teil Strichen. Der Ziehpunkt ist der Teil, der angepasst werden kann. Seine Position entspricht der <xref:System.Windows.Forms.TrackBar.Value%2A>-Eigenschaft. Bei den Teil Strichen handelt es sich um visuelle Indikatoren, deren Abstand in regelmäßigen Abständen liegt. Die TrackBar wird in von Ihnen angegebenen Inkrementen verschoben und kann horizontal oder vertikal ausgerichtet werden. Beispielsweise können Sie die Trackleiste verwenden, um die Cursor blinderate oder die Maus Geschwindigkeit für ein System zu steuern.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Die Schlüsseleigenschaften des <xref:System.Windows.Forms.TrackBar>-Steuer Elements sind <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>und <xref:System.Windows.Forms.TrackBar.Maximum%2A>. <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> ist der Abstand der Ticks. <xref:System.Windows.Forms.TrackBar.Minimum%2A> und <xref:System.Windows.Forms.TrackBar.Maximum%2A> sind die kleinsten und größten Werte, die auf der Trackleiste dargestellt werden können.  
  
 Zwei weitere wichtige Eigenschaften sind <xref:System.Windows.Forms.TrackBar.SmallChange%2A> und <xref:System.Windows.Forms.TrackBar.LargeChange%2A>. Der Wert der <xref:System.Windows.Forms.TrackBar.SmallChange%2A>-Eigenschaft ist die Anzahl der Positionen, um die der Ziehpunkt bewegt wird, wenn die nach-links-oder nach-rechts-Taste gedrückt wird. Der Wert der <xref:System.Windows.Forms.TrackBar.LargeChange%2A>-Eigenschaft ist die Anzahl der Positionen, um die der Ziehpunkt bewegt wird, wenn die Bild-auf-oder Bild-ab-Taste gedrückt wird, oder als Reaktion auf Mausklicks auf der Trackleiste auf beiden Seiten des Zieh Punkts.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.TrackBar>
- [TrackBar-Steuerelement](trackbar-control-windows-forms.md)
