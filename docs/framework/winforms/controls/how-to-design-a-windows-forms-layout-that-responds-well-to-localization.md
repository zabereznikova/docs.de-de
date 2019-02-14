---
title: 'Vorgehensweise: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: a4d0b19698a5f7fd4980fe1e945ee64c7f527ece
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261816"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>Vorgehensweise: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist
Mit der Erstellung von Formularen, die bereit für die Lokalisierung sind, lässt sich die Entwicklung für internationale Märkte erheblich beschleunigen. Sie können das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement verwenden, um Layouts zu implementieren, die sich problemlos an die Größenänderung von Steuerelementen aufgrund von Änderungen der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaftswerte anpassen.  
  
## <a name="example"></a>Beispiel  
 Dieses Formular zeigt, wie ein Layout erstellt wird, dass sich proportional anpasst, wenn Sie angezeigte Zeichenfolgenwerte in andere Sprachen übersetzen. Diese Art der Übersetzung wird als *Lokalisierung* bezeichnet. Weitere Informationen finden Sie unter [Lokalisierung](../../../../docs/standard/globalization-localization/localization.md).  
  
 Visual Studio bietet umfassende Unterstützung für diese Aufgabe.  Siehe auch [Exemplarische Vorgehensweise: Erstellen eines Layouts, das sich proportional für die Lokalisierung anpasst](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
## <a name="additional-resources"></a>Zusätzliche Ressourcen
1.  [Vorgehensweise: Ausrichten und Strecken eines Steuerelements in einem TableLayoutPanel-Steuerelement](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2.  [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  

3.  [Vorgehensweise: Überspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4.  [Vorgehensweise: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5.  [Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags Tags auf Windows Forms-Steuerelemente](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
  
6.  [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  

7.  [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](windows-forms-controls-padding-autosize.md)  
  
8.  [Vorgehensweise: Unterstützen der Lokalisierung in Windows Forms mithilfe von AutoSize und dem TableLayoutPanel-Steuerelement](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))  
  
9. [Exemplarische Vorgehensweise: Erstellen in der Größe veränderbaren Windows Forms für die Dateneingabe](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [Lokalisierung](../../../../docs/standard/globalization-localization/localization.md)
