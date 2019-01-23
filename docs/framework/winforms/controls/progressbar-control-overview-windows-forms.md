---
title: Übersicht über das ProgressBar-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: 65533bc8f9125666e39c53635f5798573f66ef14
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523180"
---
# <a name="progressbar-control-overview-windows-forms"></a>Übersicht über das ProgressBar-Steuerelement (Windows Forms)
> [!IMPORTANT]
>  Obwohl das <xref:System.Windows.Forms.ToolStripProgressBar>-Steuerelement das <xref:System.Windows.Forms.ProgressBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ProgressBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Die Windows-Formulare <xref:System.Windows.Forms.ProgressBar> -Steuerelement zeigt den Fortschritt eines Prozesses, durch eine geeignete Anzahl von Rechtecken, die in einer horizontalen Leiste anzeigen. Wenn der Prozess abgeschlossen ist, wird die Leiste gefüllt. Statusanzeigen werden häufig verwendet, um dem Benutzer einen Überblick über lange warten, bis ein Prozess abgeschlossen ist; Beispielsweise wird bei eine große Datei geladen wird.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.ProgressBar> Steuerelement kann nur horizontal auf dem Formular ausgerichtet werden.  
  
## <a name="key-properties-and-methods"></a>Wichtige Eigenschaften und Methoden  
 Die Schlüsseleigenschaften von den <xref:System.Windows.Forms.ProgressBar> sind <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>, und <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. Die <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Eigenschaften legen Sie die maximalen und minimalen Werte, die der Statusanzeige angezeigt werden kann. Die <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft darstellt, den Status, die zum Abschließen des Vorgangs vorgenommen wurde. Da die im Steuerelement angezeigten Leiste von Blöcken zusammensetzt, wird der Wert angezeigt, durch die <xref:System.Windows.Forms.ProgressBar> Steuerelement nur ein Näherungswert der <xref:System.Windows.Forms.ProgressBar.Value%2A> aktuellen Wert der Eigenschaft. Basierend auf der Größe des der <xref:System.Windows.Forms.ProgressBar> -Steuerelement, das <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft bestimmt, wann der nächste Block angezeigt.  
  
 Die gängigste Methode zum Aktualisieren des aktuelle Statuswert wird zum Schreiben von Code aus, um die <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft. Im Beispiel für eine große Datei laden können Sie die maximale auf die Größe der Datei in Kilobytes festgelegt. Z. B. wenn die <xref:System.Windows.Forms.ProgressBar.Maximum%2A> -Eigenschaftensatz auf 100 erhöht, die <xref:System.Windows.Forms.ProgressBar.Minimum%2A> Eigenschaft ist auf 10 festgelegt, und die <xref:System.Windows.Forms.ProgressBar.Value%2A> -Eigenschaftensatz bis 50, 5 Rechtecke angezeigt. Dies ist die Hälfte der Zahl, die angezeigt werden können.  
  
 Es gibt jedoch auch andere Möglichkeiten zum Ändern des Werts angezeigt, indem die <xref:System.Windows.Forms.ProgressBar> -Steuerelement, abgesehen von der Einstellung der <xref:System.Windows.Forms.ProgressBar.Value%2A> -Eigenschaft direkt. Die <xref:System.Windows.Forms.ProgressBar.Step%2A> Eigenschaft kann verwendet werden, um eine zu inkrementierende Wert angeben der <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft. Rufen Sie dann, den <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> Methode den Wert erhöht. Um den inkrementellen Wert variieren möchten, können Sie die <xref:System.Windows.Forms.ProgressBar.Increment%2A> Methode, und geben Sie einen Wert mit dem Inkrementieren der <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft.  
  
 Ein anderes Steuerelement grafisch den Benutzer über eine aktuelle Aktion darüber informiert ist die <xref:System.Windows.Forms.StatusBar> Steuerelement.  
  
> [!IMPORTANT]
>  Die <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelemente ersetzen und Hinzufügen von Funktionen, die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> -Steuerelemente jedoch die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelemente werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie Wählen Sie aus.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ProgressBar>
- [ProgressBar-Steuerelement](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)
