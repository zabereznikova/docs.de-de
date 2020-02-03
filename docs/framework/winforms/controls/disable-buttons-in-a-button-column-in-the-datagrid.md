---
title: Deaktivieren von Schaltflächen in einer Schaltflächen Spalte im DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
ms.openlocfilehash: 691781a43005d66e13029ab8110eb7f9daacc35f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745952"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Deaktivieren von Schaltflächen in einer Schaltflächenspalte im DataGridView-Steuerelement von Windows Forms
Das <xref:System.Windows.Forms.DataGridView>-Steuerelement enthält die <xref:System.Windows.Forms.DataGridViewButtonCell>-Klasse, über die Zellen mit einer schaltflächenähnlichen Benutzeroberfläche angezeigt werden können. <xref:System.Windows.Forms.DataGridViewButtonCell> bietet jedoch keine Möglichkeit, die Darstellung der in der Zelle angezeigten Schaltfläche zu deaktivieren.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie die <xref:System.Windows.Forms.DataGridViewButtonCell>-Klasse angepasst wird, um Schaltflächen anzuzeigen, die deaktiviert angezeigt werden können. Im Beispiel wird der neue Zellentyp `DataGridViewDisableButtonCell` definiert, der aus <xref:System.Windows.Forms.DataGridViewButtonCell> abgeleitet wird. Dieser Zellentyp stellt eine neue `Enabled`-Eigenschaft bereit, die auf `false` festgelegt werden kann, um eine deaktivierte Schaltfläche in der Zelle zu zeichnen. Im Beispiel wird auch der neue Spaltentyp `DataGridViewDisableButtonColumn` definiert, der `DataGridViewDisableButtonCell`-Objekte anzeigt. Zur Veranschaulichung dieses neuen Zellen- und Spaltentyps wird durch den aktuellen Wert jeder <xref:System.Windows.Forms.DataGridViewCheckBoxCell> im übergeordneten <xref:System.Windows.Forms.DataGridView> bestimmt, ob die `Enabled`-Eigenschaft der `DataGridViewDisableButtonCell` in derselben Zeile gleich `true` oder gleich `false` ist.  
  
> [!NOTE]
> Wenn Sie aus <xref:System.Windows.Forms.DataGridViewCell> oder <xref:System.Windows.Forms.DataGridViewColumn> ableiten und der abgeleiteten Klasse neue Eigenschaften hinzufügen, müssen Sie die `Clone`-Methode überschreiben, damit die neuen Eigenschaften bei Klonvorgängen kopiert werden. Außerdem sollten Sie die `Clone`-Methode der Basisklasse aufrufen, damit die Eigenschaften der Basisklasse in die neue Zelle oder Spalte kopiert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Drawing", "System.Windows.Forms" und "System.Windows.Forms.VisualStyles".  
  
## <a name="see-also"></a>Weitere Informationen

- [Anpassen des DataGridView-Steuerelements von Windows Forms](customizing-the-windows-forms-datagridview-control.md)
- [Architektur des DataGridView-Steuerelements](datagridview-control-architecture-windows-forms.md)
- [Spaltentypen im DataGridView-Steuerelement in Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
