---
title: "Gewusst wie: Festlegen, dass mehrere Zellen aus dem DataGridView-Steuerelement in Windows Forms in die Zwischenablage kopiert werden k&#246;nnen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Zellen, Kopieren in die Zwischenablage"
  - "Zwischenablage, Kopieren von mehreren Zellen"
  - "Datenblätter, Kopieren von mehreren Zellen"
  - "DataGridView-Steuerelement [Windows Forms], Kopieren von mehreren Zellen"
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Festlegen, dass mehrere Zellen aus dem DataGridView-Steuerelement in Windows Forms in die Zwischenablage kopiert werden k&#246;nnen
Wenn Sie das Kopieren von Zellen aktivieren, stellen Sie die Daten in Ihrem <xref:System.Windows.Forms.DataGridView>\-Steuerelement problemlos für andere Anwendungen über <xref:System.Windows.Forms.Clipboard> zur Verfügung.  Die Werte der ausgewählten Zellen werden in Zeichenfolgen konvertiert und als durch Tabstopp getrennte Textwerte zur Zwischenablage hinzugefügt, damit sie in Anwendungen wie Notepad und Excel eingefügt sowie als HTML\-formatierte Tabelle zum Einfügen in Anwendungen wie Word verwendet werden können.  
  
 Sie können das Kopieren von Zellen konfigurieren, sodass nur Zellwerte kopiert werden, damit der Text von Zeilen\- und Spaltenüberschriften in die Zwischenablagedaten einbezogen wird. Sie können den Headertext auch nur für den Fall einbeziehen, dass Benutzer ganze Zeilen oder Spalten auswählen.  
  
 Je nach Auswahlmodus können Benutzer mehrere getrennte Gruppen von Zellen auswählen.  Wenn ein Benutzer Zellen in die Zwischenablage kopiert, werden Zeilen und Spalten ohne ausgewählte Zellen nicht kopiert.  Alle anderen Zeilen oder Spalten werden zu Zeilen und Spalten in der Tabelle der Daten, die in die Zwischenablage kopiert wurden.  Nicht ausgewählte Zellen in diesen Zeilen oder Spalten werden als leere Platzhalter in die Zwischenablage kopiert.  
  
### So aktivieren Sie das Kopieren von Zellen  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=fullName>\-Eigenschaft fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## Beispiel  
 Im folgenden vollständigen Codebeispiel wird veranschaulicht, wie die Zellen in die Zwischenablage kopiert werden.  Dieses Beispiel enthält eine Schaltfläche, die ausgewählte Zellen mithilfe der <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=fullName>\-Methode in die Zwischenablage kopiert und den Inhalt der Zwischenablage in einem Textfeld anzeigt.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## Kompilieren des Codes  
 Dieser Code erfordert:  
  
-   Verweise auf die Assemblys "N:System" und "N:System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>   
 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>   
 [Verwendung von Auswahl und Zwischenablage mit dem DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)