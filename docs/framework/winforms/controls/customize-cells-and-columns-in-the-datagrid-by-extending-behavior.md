---
title: Anpassen von Zellen und Spalten in DataGridView Control durch Erweiterung ihres Verhaltens und Aussehens
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell customization
- columns [Windows Forms], customizing in DataGridView control
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 9b7dc7b6-5ce6-4566-9949-902f74f17a81
ms.openlocfilehash: e111f0bce812fc0851fabd1fde0fc2a6d44dd25f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182393"
---
# <a name="how-to-customize-cells-and-columns-in-the-windows-forms-datagridview-control-by-extending-their-behavior-and-appearance"></a>Gewusst wie: Anpassen von Zellen und Spalten im DataGridView-Steuerelement in Windows Forms durch Erweitern des Aussehens und Verhaltens
Das <xref:System.Windows.Forms.DataGridView>-Steuerelement bietet eine Reihe von Möglichkeiten, sein Aussehen und Verhalten mithilfe von Eigenschaften, Ereignissen und Assistentenklassen anzupassen. Gelegentlich haben Sie möglicherweise Anforderungen an die Zellen, die über die Möglichkeiten hinausgehen, die diese Funktionen bieten können. Sie können Ihre eigene benutzerdefinierte <xref:System.Windows.Forms.DataGridViewCell>-Klasse erstellen, um erweiterte Funktionalität bereitzustellen.  
  
 Sie erstellen eine benutzerdefinierte <xref:System.Windows.Forms.DataGridViewCell>-Klasse, indem Sie von der <xref:System.Windows.Forms.DataGridViewCell>-Basisklasse oder einer ihrer abgeleiteten Klassen ableiten. Auch wenn Sie in jedem Spaltentyp jeden Zellentyp anzeigen können, erstellen Sie in der Regel außerdem eine benutzerdefinierte <xref:System.Windows.Forms.DataGridViewColumn>-Klasse speziell zum Anzeigen des Zellentyps. Spaltenklassen werden von <xref:System.Windows.Forms.DataGridViewColumn> oder einem davon abgeleiteten Typ abgeleitet.  
  
 Im folgenden Codebeispiel erstellen Sie eine benutzerdefinierte Zellenklasse namens `DataGridViewRolloverCell`, die erkennt, wann sich der Mauszeiger innerhalb bzw. außerhalb der Zellenumgrenzung befindet. Wenn sich der Mauszeiger innerhalb der Zellenumgrenzungen befindet, wird ein abgesenktes Rechteck gezeichnet. Dieser neue Typ leitet sich von <xref:System.Windows.Forms.DataGridViewTextBoxCell> ab und verhält sich in jeder anderen Hinsicht wie seine Basisklasse. Die Assistentenspaltenklasse heißt `DataGridViewRolloverColumn`.  
  
 Erstellen Sie zum Verwenden dieser Klassen ein Formular mit einem <xref:System.Windows.Forms.DataGridView>-Steuerelement, fügen Sie der <xref:System.Windows.Forms.DataGridView.Columns%2A>-Auflistung ein oder mehrere `DataGridViewRolloverColumn`-Objekte hinzu, und füllen Sie das Steuerelement mit Zeilen, die Werte enthalten.  
  
> [!NOTE]
> Dieses Beispiel funktioniert nicht ordnungsgemäß, wenn Sie leere Zeilen hinzufügen. Leere Zeilen werden beispielsweise erstellt, wenn Sie dem Steuerelement Zeilen hinzufügen, indem Sie die <xref:System.Windows.Forms.DataGridView.RowCount%2A>-Eigenschaft festlegen. Der Grund dafür ist, dass die in diesem Fall hinzugefügten Zeilen automatisch freigegeben werden. Das heißt, dass `DataGridViewRolloverCell`-Objekte erst instanziiert werden, wenn Sie auf einzelne Zellen klicken und somit die Freigabe der zugeordneten Zeilen aufheben.  
  
 Da bei dieser Art der Zellenanpassung nicht freigegebene Zeilen benötigt werden, eignet sie sich nicht für große DataSets. Weitere Informationen zur Zeilenfreigabe finden Sie unter [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
> [!NOTE]
> Wenn Sie aus <xref:System.Windows.Forms.DataGridViewCell> oder <xref:System.Windows.Forms.DataGridViewColumn> ableiten und der abgeleiteten Klasse neue Eigenschaften hinzufügen, müssen Sie die `Clone`-Methode überschreiben, damit die neuen Eigenschaften bei Klonvorgängen kopiert werden. Außerdem sollten Sie die `Clone`-Methode der Basisklasse aufrufen, damit die Eigenschaften der Basisklasse in die neue Zelle oder Spalte kopiert werden.  
  
### <a name="to-customize-cells-and-columns-in-the-datagridview-control"></a>So passen Sie Zellen und Spalten im DataGridView-Steuerelement an  
  
1. Leiten Sie eine neue Zellenklasse namens `DataGridViewRolloverCell` vom <xref:System.Windows.Forms.DataGridViewTextBoxCell>-Typ ab.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#201)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#201)]  
    [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#202](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#202)]
    [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#202](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#202)]  
  
2. Überschreiben Sie die <xref:System.Windows.Forms.DataGridViewTextBoxCell.Paint%2A> -Methode in der `DataGridViewRolloverCell` -Klasse. Rufen Sie in der Überschreibung zuerst die Basisklassenimplementierung auf, die die gehosteten Textfeldfunktionen behandelt. Verwenden Sie dann die <xref:System.Windows.Forms.Control.PointToClient%2A>-Methode des Steuerelements, um die Cursorposition (in Bildschirmkoordinaten) in die Koordinaten des <xref:System.Windows.Forms.DataGridView>-Clientbereichs umzuwandeln. Wenn die Mauskoordinaten innerhalb der Zellenumgrenzung liegen, zeichnen Sie das abgesenkte Rechteck.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#210](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#210)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#210](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#210)]  
  
3. Überschreiben Sie die <xref:System.Windows.Forms.DataGridViewCell.OnMouseEnter%2A>-Methode und die <xref:System.Windows.Forms.DataGridViewCell.OnMouseLeave%2A>-Methode in der `DataGridViewRolloverCell`-Klasse, um Zellen dazu zu zwingen, sich selbst neu zu zeichnen, wenn der Mauszeiger darüber bewegt wird.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#220)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#220)]  
  
4. Leiten Sie eine neue Klasse namens `DataGridViewRolloverCellColumn` vom <xref:System.Windows.Forms.DataGridViewColumn>-Typ ab. Weisen Sie im Konstruktor ein neues `DataGridViewRolloverCell`-Objekt seiner <xref:System.Windows.Forms.DataGridViewColumn.CellTemplate%2A>-Eigenschaft zu.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#300)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#300)]  
  
## <a name="example"></a>Beispiel  
 Das vollständige Codebeispiel umfasst ein kleines Testformular, das das Verhalten des benutzerdefinierten Zellentyps veranschaulicht.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#000)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Windows.Forms" und "System.Drawing".  

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Anpassen des DataGridView-Steuerelements von Windows Forms](customizing-the-windows-forms-datagridview-control.md)
- [Architektur des DataGridView-Steuerelements](datagridview-control-architecture-windows-forms.md)
- [Spaltentypen im DataGridView-Steuerelement in Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
- [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
