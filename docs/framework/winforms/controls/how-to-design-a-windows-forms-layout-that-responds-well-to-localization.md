---
title: 'Vorgehensweise: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist'
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
ms.openlocfilehash: c1aa62413e1c9cc29507b7b0ed5cbf1c5fcea26a
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928565"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>Vorgehensweise: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist
Mit der Erstellung von Formularen, die bereit für die Lokalisierung sind, lässt sich die Entwicklung für internationale Märkte erheblich beschleunigen. Sie können das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement verwenden, um Layouts zu implementieren, die sich problemlos an die Größenänderung von Steuerelementen aufgrund von Änderungen der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaftswerte anpassen.  
  
## <a name="example"></a>Beispiel  
 Dieses Formular zeigt, wie ein Layout erstellt wird, dass sich proportional anpasst, wenn Sie angezeigte Zeichenfolgenwerte in andere Sprachen übersetzen. Diese Art der Übersetzung wird als *Lokalisierung* bezeichnet. Weitere Informationen finden Sie unter [Lokalisierung](../../../standard/globalization-localization/localization.md).  
  
 Visual Studio bietet umfassende Unterstützung für diese Aufgabe.  Siehe auch [Exemplarische Vorgehensweise: Erstellen eines Layouts, das den Anteil an](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))der Lokalisierung anpasst.  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
## <a name="additional-resources"></a>Zusätzliche Ressourcen

1. [Vorgehensweise: Ausrichten und Strecken eines Steuer Elements in einem TableLayoutPanel-Steuerelement](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  

3. [Vorgehensweise: Spannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4. [Vorgehensweise: Bearbeiten von Spalten und Zeilen in einem TableLayoutPanel-Steuerelement](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5. [Exemplarische Vorgehensweise: Ausführen allgemeiner Aufgaben mit Smarttags auf Windows Forms Steuerelementen](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
  
6. [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  

7. [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mit Auffüll Zeichen, Rändern und der AutoSize-Eigenschaft](windows-forms-controls-padding-autosize.md)  
  
8. [Vorgehensweise: Unterstützung der Lokalisierung auf Windows Forms mithilfe von AutoSize und dem TableLayoutPanel-Steuerelement](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))  
  
9. [Exemplarische Vorgehensweise: Erstellen eines in der Größe geänderten Windows Forms für die Dateneingabe](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [Lokalisierung](../../../standard/globalization-localization/localization.md)
