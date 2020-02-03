---
title: Übersicht über das ProgressBar-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: a0c4a0401d06614ab3ad148b932ebc64080c592c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741283"
---
# <a name="progressbar-control-overview-windows-forms"></a>Übersicht über das ProgressBar-Steuerelement (Windows Forms)
> [!IMPORTANT]
> Obwohl das <xref:System.Windows.Forms.ToolStripProgressBar>-Steuerelement das <xref:System.Windows.Forms.ProgressBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ProgressBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Das Windows Forms <xref:System.Windows.Forms.ProgressBar>-Steuerelement gibt den Fortschritt eines Prozesses an, indem eine entsprechende Anzahl von Rechtecke in einem horizontalen Balken angezeigt wird. Wenn der Prozess vollständig ist, wird der Balken ausgefüllt. Status anzeigen werden häufig verwendet, um dem Benutzer eine Vorstellung davon zu verschaffen, wie lange auf den Abschluss eines Prozesses gewartet werden soll. zum Beispiel beim Laden einer großen Datei.  
  
> [!NOTE]
> Das <xref:System.Windows.Forms.ProgressBar> Steuerelement kann nur horizontal auf dem Formular ausgerichtet werden.  
  
## <a name="key-properties-and-methods"></a>Schlüsseleigenschaften und-Methoden  
 Die Schlüsseleigenschaften des <xref:System.Windows.Forms.ProgressBar>-Steuer Elements sind <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>und <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. Die Eigenschaften "<xref:System.Windows.Forms.ProgressBar.Minimum%2A>" und "<xref:System.Windows.Forms.ProgressBar.Maximum%2A>" legen die maximalen und minimalen Werte fest, die die Statusanzeige anzeigen kann. Die <xref:System.Windows.Forms.ProgressBar.Value%2A>-Eigenschaft stellt den Fortschritt für den Abschluss des Vorgangs dar. Da der im-Steuerelement angezeigte Balken aus-Blöcken besteht, wird der Wert, der vom <xref:System.Windows.Forms.ProgressBar>-Steuerelement angezeigt wird, nur dem aktuellen Wert der <xref:System.Windows.Forms.ProgressBar.Value%2A>-Eigenschaft entspricht. Basierend auf der Größe des <xref:System.Windows.Forms.ProgressBar> Steuer Elements bestimmt die <xref:System.Windows.Forms.ProgressBar.Value%2A>-Eigenschaft, wann der nächste Block angezeigt werden soll.  
  
 Die gängigste Methode zum Aktualisieren des aktuellen Fortschritts Werts ist das Schreiben von Code, um die <xref:System.Windows.Forms.ProgressBar.Value%2A>-Eigenschaft festzulegen. Im Beispiel für das Laden einer großen Datei können Sie die maximale Größe der Datei in Kilobyte festlegen. Wenn die <xref:System.Windows.Forms.ProgressBar.Maximum%2A>-Eigenschaft z. b. auf 100 festgelegt ist, wird die <xref:System.Windows.Forms.ProgressBar.Minimum%2A>-Eigenschaft auf 10 festgelegt, und die <xref:System.Windows.Forms.ProgressBar.Value%2A>-Eigenschaft ist auf 50 festgelegt, 5 Rechtecke werden angezeigt. Dies ist die Hälfte der Zahl, die angezeigt werden kann.  
  
 Es gibt jedoch andere Möglichkeiten, den Wert zu ändern, der vom <xref:System.Windows.Forms.ProgressBar>-Steuerelement angezeigt wird, abgesehen von der direkten Festlegung der <xref:System.Windows.Forms.ProgressBar.Value%2A>-Eigenschaft. Die <xref:System.Windows.Forms.ProgressBar.Step%2A>-Eigenschaft kann verwendet werden, um einen Wert anzugeben, um die Eigenschaft <xref:System.Windows.Forms.ProgressBar.Value%2A> um zu erhöhen. Wenn Sie die <xref:System.Windows.Forms.ProgressBar.PerformStep%2A>-Methode aufrufen, wird der Wert erhöht. Um den Inkrement-Wert zu verändern, können Sie die <xref:System.Windows.Forms.ProgressBar.Increment%2A>-Methode verwenden und einen Wert angeben, mit dem die <xref:System.Windows.Forms.ProgressBar.Value%2A>-Eigenschaft erhöht werden soll.  
  
 Ein weiteres Steuerelement, das den Benutzer grafisch über eine aktuelle Aktion informiert, ist das <xref:System.Windows.Forms.StatusBar>-Steuerelement.  
  
> [!IMPORTANT]
> Die Steuerelemente <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> ersetzen und fügen Funktionen zum <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelementen hinzu. die <xref:System.Windows.Forms.StatusBar>-und <xref:System.Windows.Forms.StatusBarPanel>-Steuerelemente werden jedoch sowohl für Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie sich entscheiden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ProgressBar>
- [ProgressBar-Steuerelement](progressbar-control-windows-forms.md)
