---
title: "&#220;bersicht &#252;ber das ProgressBar-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ProgressBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Statussteuerelemente, Informationen über Statussteuerelemente"
  - "ProgressBar-Steuerelement [Windows Forms], Informationen über das ProgressBar-Steuerelement"
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# &#220;bersicht &#252;ber das ProgressBar-Steuerelement (Windows&#160;Forms)
> [!IMPORTANT]
>  Obwohl das <xref:System.Windows.Forms.ToolStripProgressBar>\-Steuerelement das <xref:System.Windows.Forms.ProgressBar>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ProgressBar>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Das <xref:System.Windows.Forms.ProgressBar>\-Steuerelement in Windows Forms gibt den Fortschritt eines Prozesses an, wobei eine entsprechende Anzahl von Rechtecken auf einer horizontalen Leiste angezeigt wird.  Wenn der Prozess beendet ist, ist die Leiste vollständig mit Rechtecken gefüllt.  Statusanzeigen werden im Allgemeinen dazu verwendet, Benutzern eine Übersicht über die Dauer eines Prozesses zu verschaffen, z. B. beim Laden einer großen Datei.  
  
> [!NOTE]
>  Das <xref:System.Windows.Forms.ProgressBar>\-Steuerelement kann im Formular nur horizontal ausgerichtet werden.  
  
## Wichtige Eigenschaften und Methoden  
 Die wichtigsten Eigenschaften des <xref:System.Windows.Forms.ProgressBar>\-Steuerelements sind <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A>.  Die Eigenschaften <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> legen die Maximal\- und Minimalwerte fest, die in der Statusanzeige angezeigt werden können.  Die <xref:System.Windows.Forms.ProgressBar.Value%2A>\-Eigenschaft stellt den Fortschritt dar bei der Ausführung bis zum Abschluss der Operation.  Da die im Steuerelement angezeigte Leiste aus Blöcken zusammengesetzt ist, entspricht der vom <xref:System.Windows.Forms.ProgressBar>\-Steuerelement angezeigte Wert nur ungefähr dem Wert der <xref:System.Windows.Forms.ProgressBar.Value%2A>\-Eigenschaft.  Die <xref:System.Windows.Forms.ProgressBar.Value%2A>\-Eigenschaft bestimmt entsprechend der Größe des <xref:System.Windows.Forms.ProgressBar>\-Steuerelements, wann der nächste Block anzuzeigen ist.  
  
 Meistens wird zum Aktualisieren des aktuellen Fortschrittswerts Code geschrieben, um die <xref:System.Windows.Forms.ProgressBar.Value%2A>\-Eigenschaft festzulegen.  Im genannten Beispiel, dem Laden einer großen Datei, könnten Sie als Maximalwert die Dateigröße in KB festlegen.  Wird beispielsweise die <xref:System.Windows.Forms.ProgressBar.Maximum%2A>\-Eigenschaft auf 100, die <xref:System.Windows.Forms.ProgressBar.Minimum%2A>\-Eigenschaft auf 10 und die <xref:System.Windows.Forms.ProgressBar.Value%2A>\-Eigenschaft auf 50 festgelegt, so werden 5 Rechtecke angezeigt.  Das ist die Hälfte der Anzahl, die insgesamt angezeigt werden kann.  
  
 Neben dem direkten Festlegen der <xref:System.Windows.Forms.ProgressBar.Value%2A>\-Eigenschaft gibt es auch andere Möglichkeiten zur Änderung des vom <xref:System.Windows.Forms.ProgressBar>\-Steuerelement angezeigten Werts.  Mit der <xref:System.Windows.Forms.ProgressBar.Step%2A>\-Eigenschaft kann ein Wert zur Erhöhung der <xref:System.Windows.Forms.ProgressBar.Value%2A>\-Eigenschaft festgelegt werden.  Anschließend wird durch das Aufrufen der <xref:System.Windows.Forms.ProgressBar.PerformStep%2A>\-Methode der Wert erhöht.  Um den Wert für die Erhöhung zu variieren, können Sie die <xref:System.Windows.Forms.ProgressBar.Increment%2A>\-Methode verwenden und einen Wert angeben, mit dem die <xref:System.Windows.Forms.ProgressBar.Value%2A>\-Eigenschaft erhöht wird.  
  
 Ein weiteres Steuerelement, mit dem der Benutzer anhand einer grafischen Anzeige über eine aktuelle Aktion informiert wird, ist das <xref:System.Windows.Forms.StatusBar>\-Steuerelement.  
  
> [!IMPORTANT]
>  Obwohl die Steuerelemente <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> durch die Steuerelemente <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> ersetzt und funktionell erweitert werden, werden die Steuerelemente <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ProgressBar>   
 [ProgressBar\-Steuerelement](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)