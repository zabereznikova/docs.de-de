---
title: 'Gewusst wie: Anzeigen von Optionsfeldern in einem MenuStrip (Windows Forms)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0de3b8596bc06c79f391141ef85fec65ac343d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>Gewusst wie: Anzeigen von Optionsfeldern in einem MenuStrip (Windows Forms)
Optionsfelder, auch bekannt als Optionsfelder ähneln Kontrollkästchen, mit dem Unterschied, dass Benutzer nur jeweils einzeln auswählen können. Zwar wird standardmäßig die <xref:System.Windows.Forms.ToolStripMenuItem> Klasse keine Optionsfeld Verhalten bereit, die Klasse bietet ein Kontrollkästchen-Verhalten, das Sie anpassen können, um das Implementieren von Optionsfeld Verhalten für Menüelemente in einer <xref:System.Windows.Forms.MenuStrip> Steuerelement.  
  
 Wenn die <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Eigenschaft eines Menüelements ist `true`, Benutzer können auf das Element, um die ein-und ein Häkchen klicken. Die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Eigenschaft gibt den aktuellen Status des Elements. Um grundlegende Optionsfeld Verhalten zu implementieren, müssen Sie sicherstellen, dass wenn ein Element ausgewählt ist, Sie legen die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> -Eigenschaft für das zuvor ausgewählten Element um `false`.  
  
 Die folgenden Verfahren wird beschrieben, wie zur Implementierung dieser Funktion und weitere Funktionen in einer Klasse, erbt die <xref:System.Windows.Forms.ToolStripMenuItem> Klasse. Die `ToolStripRadioButtonMenuItem` Klasse überschreibt Elemente wie z. B. <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> und <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> , die Verhalten der Funktionsauswahl und Darstellung von Optionsfeldern. Darüber hinaus diese Klasse überschreibt die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft, sodass ein Untermenü Optionen sind deaktiviert, es sei denn, das übergeordnete Element ausgewählt ist.  
  
### <a name="to-implement-option-button-selection-behavior"></a>Zum Implementieren von Optionsfeld Auswahlverhalten  
  
1.  Initialisieren der <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Eigenschaft `true` Elementauswahl zu aktivieren.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> Methode, um die Auswahl der zuvor ausgewählten Element löschen, wenn ein neues Element ausgewählt ist.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> Methode, um sicherzustellen, dass beim Klicken auf ein Element, das bereits ausgewählt wurde, wird nicht die Auswahl gelöscht.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### <a name="to-modify-the-appearance-of-the-option-button-items"></a>So ändern Sie die Darstellung der Optionsfeld Elemente  
  
1.  Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> Methode, um das Standard-Häkchen durch ein Optionsfeld mit ersetzen die <xref:System.Windows.Forms.RadioButtonRenderer> Klasse.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, und <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> Methoden, um den Zustand der Maus nachverfolgen und sicherstellen, dass die <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> zeichnet den Status richtig Optionsfeld-Methode.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>Deaktivieren Sie auf ein Untermenü Optionen aus, wenn das übergeordnete Element nicht ausgewählt ist  
  
1.  Außer Kraft setzen die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft, damit das Element deaktiviert wird, wenn es ein übergeordnetes Element mit sowohl hat eine <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Wert `true` und ein <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Wert `false`.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> Methode zum Abonnieren der <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> -Ereignis des übergeordneten Elements.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  Im Handler für das übergeordnete Element <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> Ereignis, das Element, um die Anzeige zu aktualisieren, mit der neuen Aktivierungszustand für ungültig zu erklären.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel stellt die vollständige `ToolStripRadioButtonMenuItem` -Klasse, und ein <xref:System.Windows.Forms.Form> Klasse und `Program` Klasse das Optionsfeld Verhalten zeigen.  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RadioButtonRenderer>  
 [MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [Gewusst wie: Implementieren eines benutzerdefinierten ToolStripRenderer](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-toolstriprenderer.md)
