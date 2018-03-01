---
title: "Übersicht über das ProgressBar-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c5ca5fd908124b0f38643c7b2833ba591be3b980
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="progressbar-control-overview-windows-forms"></a>Übersicht über das ProgressBar-Steuerelement (Windows Forms)
> [!IMPORTANT]
>  Obwohl das <xref:System.Windows.Forms.ToolStripProgressBar>-Steuerelement das <xref:System.Windows.Forms.ProgressBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ProgressBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Windows Forms <xref:System.Windows.Forms.ProgressBar> Steuerelement gibt den Status eines Prozesses, indem eine entsprechende Anzahl von Rechtecken, die auf einer horizontalen Leiste angezeigt. Wenn der Prozess abgeschlossen ist, wird die Leiste gefüllt. Statusanzeigen werden häufig verwendet, um dem Benutzer einen Überblick darüber, wie lange warten, bis ein Prozess abgeschlossen ist; z. B. bei eine große Datei geladen wird.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.ProgressBar> Steuerelement kann nur horizontal auf dem Formular ausgerichtet werden.  
  
## <a name="key-properties-and-methods"></a>Wichtige Eigenschaften und Methoden  
 Wichtigsten Eigenschaften der <xref:System.Windows.Forms.ProgressBar> Steuerelement sind <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>, und <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. Die <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Eigenschaften festlegen der maximalen und minimalen Werte der Statusanzeige angezeigt werden kann. Die <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft darstellt, den Status, die bis zum Abschließen des Vorgangs vorgenommen wurde. Da die im Steuerelement angezeigte Leiste Blöcke besteht, wird der Wert angezeigt, durch die <xref:System.Windows.Forms.ProgressBar> Steuerelement nur ein Näherungswert der <xref:System.Windows.Forms.ProgressBar.Value%2A> den aktuellen Wert der Eigenschaft. Basierend auf der Größe von der <xref:System.Windows.Forms.ProgressBar> -Steuerelement, das <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft bestimmt, wann der nächste Block angezeigt.  
  
 Die gängigste Methode zum Aktualisieren des aktuellen Status-Werts wird zum Schreiben von Code aus, um die <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft. Im Beispiel für das Laden einer großen Datei können Sie die maximale auf die Größe der Datei in Kilobytes festgelegt. Z. B. wenn die <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Eigenschaftensatz auf 100 erhöht, die <xref:System.Windows.Forms.ProgressBar.Minimum%2A> -Eigenschaft auf 10 festgelegt ist und die <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft festgelegt ist auf 50 5 Rechtecke angezeigt werden. Dies ist die Hälfte der Zahl, die angezeigt werden können.  
  
 Es gibt jedoch auch andere Möglichkeiten zum Ändern des Werts angezeigt, indem die <xref:System.Windows.Forms.ProgressBar> -Steuerelement, abgesehen von der Einstellung der <xref:System.Windows.Forms.ProgressBar.Value%2A> -Eigenschaft direkt. Die <xref:System.Windows.Forms.ProgressBar.Step%2A> Eigenschaft kann verwendet werden, um eine zu inkrementierende Wert geben die <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft durch. Anschließend, durch Aufrufen der <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> Methode den Wert erhöht. Um den Inkrementwert ändern möchten, können Sie die <xref:System.Windows.Forms.ProgressBar.Increment%2A> Methode, und geben Sie einen Wert mit dem Inkrementieren der <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft.  
  
 Ein anderes Steuerelement, mit denen den Benutzer über eine aktuelle Aktion grafisch informiert ist die <xref:System.Windows.Forms.StatusBar> Steuerelement.  
  
> [!IMPORTANT]
>  Die <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelemente ersetzen und Funktionen hinzufügen der <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> steuert; allerdings die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelemente werden für die Abwärtskompatibilität und für zukünftige Verwendung beibehalten, wenn Sie Wählen Sie aus.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ProgressBar>  
 [ProgressBar-Steuerelement](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)
