---
title: 'Gewusst wie: Deaktivieren von Schaltflächen in einer Schaltflächenspalte im DataGridView-Steuerelement von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
ms.openlocfilehash: 0687b4e4c3896e7663c5c093a43a2db72e0053f8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44138851"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Deaktivieren von Schaltflächen in einer Schaltflächenspalte im DataGridView-Steuerelement von Windows Forms
Das <xref:System.Windows.Forms.DataGridView>-Steuerelement enthält die <xref:System.Windows.Forms.DataGridViewButtonCell>-Klasse, über die Zellen mit einer schaltflächenähnlichen Benutzeroberfläche angezeigt werden können. <xref:System.Windows.Forms.DataGridViewButtonCell> bietet jedoch keine Möglichkeit, die Darstellung der in der Zelle angezeigten Schaltfläche zu deaktivieren.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie die <xref:System.Windows.Forms.DataGridViewButtonCell>-Klasse angepasst wird, um Schaltflächen anzuzeigen, die deaktiviert angezeigt werden können. Im Beispiel wird der neue Zellentyp `DataGridViewDisableButtonCell` definiert, der aus <xref:System.Windows.Forms.DataGridViewButtonCell> abgeleitet wird. Dieser Zellentyp stellt eine neue `Enabled`-Eigenschaft bereit, die auf `false` festgelegt werden kann, um eine deaktivierte Schaltfläche in der Zelle zu zeichnen. Im Beispiel wird auch der neue Spaltentyp `DataGridViewDisableButtonColumn` definiert, der `DataGridViewDisableButtonCell`-Objekte anzeigt. Zur Veranschaulichung dieses neuen Zellen- und Spaltentyps wird durch den aktuellen Wert jeder <xref:System.Windows.Forms.DataGridViewCheckBoxCell> im übergeordneten <xref:System.Windows.Forms.DataGridView> bestimmt, ob die `Enabled`-Eigenschaft der `DataGridViewDisableButtonCell` in derselben Zeile gleich `true` oder gleich `false` ist.  
  
> [!NOTE]
>  Wenn Sie aus <xref:System.Windows.Forms.DataGridViewCell> oder <xref:System.Windows.Forms.DataGridViewColumn> ableiten und der abgeleiteten Klasse neue Eigenschaften hinzufügen, müssen Sie die `Clone`-Methode überschreiben, damit die neuen Eigenschaften bei Klonvorgängen kopiert werden. Außerdem sollten Sie die `Clone`-Methode der Basisklasse aufrufen, damit die Eigenschaften der Basisklasse in die neue Zelle oder Spalte kopiert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing", "System.Windows.Forms" und "System.Windows.Forms.VisualStyles".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch: [Vorgehensweise Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch  
 [Anpassen des DataGridView-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [Architektur des DataGridView-Steuerelements](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [Spaltentypen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
