---
title: 'Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock
helpviewer_keywords:
- layout [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
- TableLayoutPanel control [Windows Forms], child controls
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
ms.openlocfilehash: eee67d739de13b125aa1eb8ee86de19ba645a2f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a>Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement
Das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement unterstützt die <xref:System.Windows.Forms.Control.Anchor%2A>- und die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft in seinen untergeordneten Steuerelementen.  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a>So richten Sie ein untergeordnetes Steuerelement in einer TableLayoutPanel-Zelle aus  
  
1.  Erstellen Sie ein <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement auf dem Formular.  
  
2.  Legen Sie den Wert, der die <xref:System.Windows.Forms.TableLayoutPanel> des Steuerelements <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> und <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> Eigenschaften **1**.  
  
3.  Erstellen Sie ein <xref:System.Windows.Forms.Button>-Steuerelement im <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement. Das <xref:System.Windows.Forms.Button> nimmt die obere linke Ecke der Zelle ein.  
  
4.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `Left`. Das <xref:System.Windows.Forms.Button>-Steuerelement wird so verschoben, dass es sich am linken Rand der Zelle ausrichtet.  
  
    > [!NOTE]
    >  Dieses Verhalten weicht vom Verhalten anderer Containersteuerelemente ab. Bei anderen Containersteuerelementen wird das untergeordnete Steuerelement nicht verschoben, wenn die <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft festgelegt wird, und der Abstand zwischen dem verankerten Steuerelement und der Grenze des übergeordneten Containers ist zum Zeitpunkt der Festlegung der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft fixiert.  
  
5.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `Top, Left`. Das <xref:System.Windows.Forms.Button>-Steuerelement wird so verschoben, dass es die ober linke Ecke der Zelle einnimmt.  
  
6.  Wiederholen Sie Schritt 5 mit einem Wert von `Top, Right` zum Verschieben der <xref:System.Windows.Forms.Button> Steuerelement in der oberen rechten Ecke der Zelle. Wiederholen Sie diesen Schritt mit den Werten `Bottom, Left` und `Bottom, Right`.  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a>So strecken Sie ein untergeordnetes Steuerelement in einer TableLayoutPanel-Zelle  
  
1.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `Left, Right`. Die Größe des <xref:System.Windows.Forms.Button>-Steuerelements wird so angepasst, dass es die gesamte Breite der Zelle einnimmt.  
  
    > [!NOTE]
    >  Dieses Verhalten weicht vom Verhalten anderer Containersteuerelemente ab. In anderen Containersteuerelementen wird das untergeordnete Steuerelement nicht angepasst, wenn die <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaftensatz auf `Left, Right` oder `Top, Bottom`.  
  
2.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `Top, Bottom`. Die Größe des <xref:System.Windows.Forms.Button>-Steuerelements wird so angepasst, dass es die gesamte Höhe der Zelle einnimmt.  
  
3.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `Top, Bottom, Left, Right`. Die Größe des <xref:System.Windows.Forms.Button>-Steuerelements wird so geändert, dass es die gesamte Zelle ausfüllt.  
  
4.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `None`. Die Größe des <xref:System.Windows.Forms.Button>-Steuerelements wird geändert, und es wird mittig in der Zelle positioniert.  
  
5.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in <xref:System.Windows.Forms.DockStyle.Left>. Das <xref:System.Windows.Forms.Button>-Steuerelement wird so verschoben, dass es sich am linken Rand der Zelle ausrichtet. Das <xref:System.Windows.Forms.Button>-Steuerelement behält seine Breite, aber seine Höhe wird so angepasst, dass es die gesamte Zellenhöhe einnimmt.  
  
    > [!NOTE]
    >  Dies ist dasselbe Verhalten, das in anderen Containersteuerelementen auftritt.  
  
6.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in <xref:System.Windows.Forms.DockStyle.Fill>. Die Größe des <xref:System.Windows.Forms.Button>-Steuerelements wird so geändert, dass es die gesamte Zelle ausfüllt.  
  
## <a name="example"></a>Beispiel  
 Die folgende Abbildung zeigt fünf Schaltflächen, die in fünf separaten <xref:System.Windows.Forms.TableLayoutPanel>-Zellen verankert sind.  
  
 ![TableLayoutPanel-Verankerung](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.gif "VS_TLPanchor")  
  
 Die folgende Abbildung zeigt vier Schaltflächen, die in den Ecken von vier separaten <xref:System.Windows.Forms.TableLayoutPanel>-Zellen verankert sind.  
  
 ![TableLayoutPanel-Verankerung](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.gif "VS_TLPanchor2")  
  
 Die folgende Abbildung zeigt drei Schaltflächen, die durch die Verankerung in drei separaten <xref:System.Windows.Forms.TableLayoutPanel>-Zellen gestreckt wurden.  
  
 ![TableLayoutPanel-Verankerung](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.gif "VS_TLPAnchor3")  
  
 Das folgende Codebeispiel veranschaulicht alle Kombinationen aus <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaftswerte für ein <xref:System.Windows.Forms.Button>-Steuerelement in einem <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [TableLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
