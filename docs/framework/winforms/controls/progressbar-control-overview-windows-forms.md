---
title: Übersicht über das ProgressBar-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: 7dd434492cd688527ddbce5aaffa442a0b40a9e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968315"
---
# <a name="progressbar-control-overview-windows-forms"></a>Übersicht über das ProgressBar-Steuerelement (Windows Forms)
> [!IMPORTANT]
> Obwohl das <xref:System.Windows.Forms.ToolStripProgressBar>-Steuerelement das <xref:System.Windows.Forms.ProgressBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ProgressBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Das Windows Forms <xref:System.Windows.Forms.ProgressBar> -Steuerelement gibt den Fortschritt eines Prozesses an, indem eine entsprechende Anzahl von Rechtecke in einem horizontalen Balken angezeigt wird. Wenn der Prozess vollständig ist, wird der Balken ausgefüllt. Status anzeigen werden häufig verwendet, um dem Benutzer eine Vorstellung davon zu verschaffen, wie lange auf den Abschluss eines Prozesses gewartet werden soll. zum Beispiel beim Laden einer großen Datei.  
  
> [!NOTE]
> Das <xref:System.Windows.Forms.ProgressBar> Steuerelement kann nur horizontal auf dem Formular ausgerichtet werden.  
  
## <a name="key-properties-and-methods"></a>Schlüsseleigenschaften und-Methoden  
 Die Schlüsseleigenschaften des <xref:System.Windows.Forms.ProgressBar> -Steuer Elements sind <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Value%2A>, und <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. Die-Eigenschaft und die- <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Eigenschaft legen die maximalen und minimalen Werte fest, die die Statusanzeige anzeigen kann. <xref:System.Windows.Forms.ProgressBar.Minimum%2A> Die <xref:System.Windows.Forms.ProgressBar.Value%2A> -Eigenschaft stellt den Fortschritt dar, der zum Abschließen des Vorgangs durchgeführt wurde. Da der im-Steuerelement angezeigte Balken aus-Blöcken besteht, wird der Wert <xref:System.Windows.Forms.ProgressBar> , der vom-Steuer <xref:System.Windows.Forms.ProgressBar.Value%2A> Element angezeigt wird, nur dem aktuellen Wert der Eigenschaft entspricht. Basierend auf der Größe des <xref:System.Windows.Forms.ProgressBar> Steuer Elements bestimmt die <xref:System.Windows.Forms.ProgressBar.Value%2A> -Eigenschaft, wann der nächste Block angezeigt werden soll.  
  
 Die gängigste Methode zum Aktualisieren des aktuellen Fortschritts Werts ist das Schreiben von Code, um <xref:System.Windows.Forms.ProgressBar.Value%2A> die-Eigenschaft festzulegen. Im Beispiel für das Laden einer großen Datei können Sie die maximale Größe der Datei in Kilobyte festlegen. Wenn beispielsweise die <xref:System.Windows.Forms.ProgressBar.Maximum%2A> -Eigenschaft auf 100 festgelegt ist, wird die <xref:System.Windows.Forms.ProgressBar.Minimum%2A> -Eigenschaft auf 10 festgelegt <xref:System.Windows.Forms.ProgressBar.Value%2A> , und die-Eigenschaft wird auf 50 festgelegt, 5 Rechtecke werden angezeigt. Dies ist die Hälfte der Zahl, die angezeigt werden kann.  
  
 Es gibt jedoch weitere Möglichkeiten, den Wert zu ändern, der vom <xref:System.Windows.Forms.ProgressBar> Steuerelement angezeigt wird, abgesehen <xref:System.Windows.Forms.ProgressBar.Value%2A> von der direkten Festlegung der-Eigenschaft. Die <xref:System.Windows.Forms.ProgressBar.Step%2A> -Eigenschaft kann verwendet werden, um einen Wert anzugeben, durch <xref:System.Windows.Forms.ProgressBar.Value%2A> den die-Eigenschaft Inkrement erhöht wird. Beim Aufrufen der <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> -Methode wird der Wert erhöht. Um den Inkrement-Wert zu verändern, können <xref:System.Windows.Forms.ProgressBar.Increment%2A> Sie die-Methode verwenden und einen Wert angeben, mit <xref:System.Windows.Forms.ProgressBar.Value%2A> dem die-Eigenschaft Inkrement erhöht werden soll.  
  
 Ein weiteres Steuerelement, das den Benutzer grafisch über eine aktuelle Aktion <xref:System.Windows.Forms.StatusBar> informiert, ist das Steuerelement.  
  
> [!IMPORTANT]
> Das <xref:System.Windows.Forms.StatusStrip> - <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelement und das-Steuerelement <xref:System.Windows.Forms.StatusBar> ersetzen und fügen Funktionen zu den <xref:System.Windows.Forms.StatusBar> Steuer <xref:System.Windows.Forms.StatusBarPanel> Elementen und <xref:System.Windows.Forms.StatusBarPanel> hinzu. die Steuerelemente und werden jedoch sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, St.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ProgressBar>
- [ProgressBar-Steuerelement](progressbar-control-windows-forms.md)
