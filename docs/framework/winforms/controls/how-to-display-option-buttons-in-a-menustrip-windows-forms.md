---
title: 'Vorgehensweise: Anzeigen von Optionsfeldern in einem MenuStrip (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: 07dd6a93e88119fa8a729747e0cb716170072cd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643714"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>Vorgehensweise: Anzeigen von Optionsfeldern in einem MenuStrip (Windows Forms)
Optionsfelder, auch bekannt als die Optionsfelder, ähneln der Kontrollkästchen, mit dem Unterschied, dass Benutzer nur jeweils eine auswählen können. Zwar wird standardmäßig die <xref:System.Windows.Forms.ToolStripMenuItem> -Klasse keinen Optionsfeld-aus-Verhalten, das die Klasse bietet ein Kontrollkästchen-Verhalten, das Sie anpassen können, um das Implementieren des Verhaltens von Optionsfeldern für Menüelemente in einem <xref:System.Windows.Forms.MenuStrip> Steuerelement.  
  
 Wenn die <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> -Eigenschaft eines Menüelements ist `true`, Benutzer können auf das Element, um die ein-und ein Häkchen klicken. Die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Eigenschaft gibt den aktuellen Zustand des Elements an. Um grundlegende Optionsfeld-Verhalten zu implementieren, müssen Sie sicherstellen, dass wenn ein Element ausgewählt ist, Sie legen die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> -Eigenschaft für das zuvor ausgewählte Element `false`.  
  
 Die folgenden Verfahren wird beschrieben, wie dies implementiert und weitere Funktionen in einer Klasse, erbt die <xref:System.Windows.Forms.ToolStripMenuItem> Klasse. Die `ToolStripRadioButtonMenuItem` Klasse überschreibt z. B. <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> und <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> das Verhalten der Funktionsauswahl und Darstellung von Optionsfeldern angeben. Darüber hinaus diese Klasse überschreibt die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft, sodass Sie in einem Untermenü Optionen sind deaktiviert, es sei denn, das übergeordnete Element ausgewählt ist.  
  
### <a name="to-implement-option-button-selection-behavior"></a>Zum Implementieren des Verhaltens von Optionsfeld-Auswahl  
  
1.  Initialisieren der <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Eigenschaft `true` Elementauswahl zu aktivieren.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  Überschreiben der <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> Methode, um die Auswahl der zuvor ausgewählten Elements zu löschen, wenn ein neues Element ausgewählt ist.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  Überschreiben der <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> Methode, um sicherzustellen, dass beim Klicken auf ein Element, das bereits ausgewählt wurde, wird nicht die Auswahl gelöscht.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### <a name="to-modify-the-appearance-of-the-option-button-items"></a>Zum Ändern der Darstellung der Optionsfeld-Elemente  
  
1.  Überschreiben der <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> Methode, um das Standard-Häkchen ein Optionsfeld mit mit Ersetzen der <xref:System.Windows.Forms.RadioButtonRenderer> Klasse.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  Überschreiben der <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, und <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> Methoden zum Nachverfolgen des Status der Maus, und stellen sicher, dass die <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> zeichnet den Status richtig Optionsfeld-Methode.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>So deaktivieren Sie Optionen in einem Untermenü, wenn das übergeordnete Element nicht ausgewählt ist  
  
1.  Außer Kraft setzen der <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft so, dass das Element deaktiviert wird, wenn es sich um ein übergeordnetes Element mit sowohl hat eine <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Wert `true` und ein <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Wert `false`.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  Überschreiben der <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> Methode zum Abonnieren der <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> Ereignis des übergeordneten Elements.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  Im Handler für den übergeordneten Elements <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> -Ereignis, das Element, um die Anzeige zu aktualisieren, mit dem neuen aktivierten Zustand ungültig.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel stellt die vollständige `ToolStripRadioButtonMenuItem` -Klasse, und ein <xref:System.Windows.Forms.Form> Klasse und `Program` Klasse zur Veranschaulichung des Verhaltens von Optionsfeldern.  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
- [Vorgehensweise: Implementieren eines benutzerdefinierten ToolStripRenderer](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-toolstriprenderer.md)
