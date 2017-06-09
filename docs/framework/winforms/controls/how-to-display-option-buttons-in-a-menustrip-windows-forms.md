---
title: "Gewusst wie: Anzeigen von Optionsfeldern in einem MenuStrip (Windows Forms) | Microsoft Docs"
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
  - "Anzeigen von Optionsfeldern, MenuStrip [Windows Forms]"
  - "MenuStrip [Windows Forms], Anzeigen von Optionsfeldern"
  - "Optionsfelder [Windows Forms], Anzeigen in MenuStrip"
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Anzeigen von Optionsfeldern in einem MenuStrip (Windows Forms)
Optionsfelder, auch Optionsschaltflächen genannt, ähneln Kontrollkästchen. Benutzer können jedoch nur ein Optionsfeld gleichzeitig auswählen.  In der Standardeinstellung stellt die <xref:System.Windows.Forms.ToolStripMenuItem>\-Klasse kein Optionsfeldverhalten bereit. Das von der Klasse bereitgestellte Kontrollkästchenverhalten kann jedoch so angepasst werden, dass ein Optionsfeldverhalten für Menüelemente in einem <xref:System.Windows.Forms.MenuStrip>\-Steuerelement implementiert wird.  
  
 Wenn die <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>\-Eigenschaft eines Menüelements auf `true` festgelegt wird, können Benutzer durch Klicken auf das Element die Anzeige eines Häkchens ein\- und ausblenden.  Die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>\-Eigenschaft gibt den aktuellen Zustand des Menüelements an.  Zum Implementieren von einfachem Optionsfeldverhalten müssen Sie sicherstellen, dass beim Auswählen eines Elements die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>\-Eigenschaft für das zuvor ausgewählte Element auf `false` festgelegt wird.  
  
 In den folgenden Schritten wird erläutert, wie Sie dieses Verhalten und weitere Funktionen in einer Klasse implementieren, die die <xref:System.Windows.Forms.ToolStripMenuItem>\-Klasse erbt.  Die `ToolStripRadioButtonMenuItem`\-Klasse überschreibt Member wie <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> und <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>, um das Auswahlverhalten und die Darstellung von Optionsfeldern bereitzustellen.  Außerdem überschreibt diese Klasse die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>\-Eigenschaft, sodass Optionen in einem Untermenü so lange deaktiviert sind, bis das übergeordnete Element ausgewählt wird.  
  
### So implementieren Sie das Auswahlverhalten für Optionsfelder  
  
1.  Initialisieren Sie die <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>\-Eigenschaft mit dem Wert`true`, um die Auswahl von Elementen zu aktivieren.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A>\-Methode, um bei Auswahl eines neuen Elements die des zuvor ausgewählten Elements aufzuheben.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A>\-Methode, um sicherzustellen, dass beim Klicken auf ein bereits ausgewähltes Element die Auswahl dieses Elements nicht aufgehoben wird.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### So ändern Sie die Darstellung von Optionsfeldelementen  
  
1.  Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>\-Methode, um die Standardmarkierung mithilfe der <xref:System.Windows.Forms.RadioButtonRenderer>\-Klasse durch eine Optionsschaltfläche zu ersetzen.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  Überschreiben Sie die Methoden <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A> und <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A>, um den Mauszustand zu überwachen und sicherzustellen, dass die <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>\-Methode den richtigen Zustand des Optionsfelds darstellt.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### So deaktivieren Sie Optionen in einem Untermenü, wenn das übergeordnete Element nicht ausgewählt ist  
  
1.  Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>\-Eigenschaft, damit das Element deaktiviert wird, wenn es ein übergeordnetes Element mit einen <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>\-Wert von `true` und einen <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>\-Wert von `false` aufweist.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A>\-Methode, um das <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged>\-Ereignis des übergeordneten Elements zu abonnieren.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  Erklären Sie das Element im Handler für das <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged>\-Ereignis des übergeordneten Elements für ungültig, um die Anzeige mit dem neuen, aktivierten Zustand zu aktualisieren.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## Beispiel  
 Im folgenden Codebeispiel werden die gesamte `ToolStripRadioButtonMenuItem`\-Klasse sowie eine <xref:System.Windows.Forms.Form>\-Klasse und eine `Program`\-Klasse bereitgestellt, um das Optionsfeldverhalten zu veranschaulichen.  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Verweise auf die Assemblys System, System.Drawing und System.Windows.Forms.  
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.RadioButtonRenderer>   
 [MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)   
 [Gewusst wie: Implementieren eines benutzerdefinierten ToolStripRenderer](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-toolstriprenderer.md)