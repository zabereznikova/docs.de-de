---
title: "Gewusst wie: Anpassen von Zellen und Spalten im DataGridView-Steuerelement in Windows Forms durch Erweitern des Aussehens und Verhaltens | Microsoft Docs"
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
  - "Zellen, Anpassen im DataGridView-Steuerelement"
  - "Spalten [Windows Forms], Anpassen im DataGridView-Steuerelement"
  - "DataGridView-Steuerelement [Windows Forms], Zellenanpassung"
ms.assetid: 9b7dc7b6-5ce6-4566-9949-902f74f17a81
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Gewusst wie: Anpassen von Zellen und Spalten im DataGridView-Steuerelement in Windows Forms durch Erweitern des Aussehens und Verhaltens
Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement bietet eine Reihe von Möglichkeiten, sein Aussehen und Verhalten mithilfe von Eigenschaften, Ereignissen und Assistentenklassen anzupassen.  Gelegentlich haben Sie möglicherweise Anforderungen an die Zellen, die über die Möglichkeiten hinausgehen, die diese Features bieten können.  Sie können Ihre eigene benutzerdefinierte <xref:System.Windows.Forms.DataGridViewCell>\-Klasse erstellen, um erweiterte Funktionalität bereitzustellen.  
  
 Sie erstellen eine benutzerdefinierte <xref:System.Windows.Forms.DataGridViewCell>\-Klasse, indem Sie von der <xref:System.Windows.Forms.DataGridViewCell>\-Basisklasse oder einer ihrer abgeleiteten Klassen ableiten.  Auch wenn Sie in jedem Spaltentyp jeden Zellentyp anzeigen können, erstellen Sie in der Regel außerdem eine benutzerdefinierte <xref:System.Windows.Forms.DataGridViewColumn>\-Klasse speziell zum Anzeigen des Zellentyps.  Spaltenklassen werden von <xref:System.Windows.Forms.DataGridViewColumn> oder einem davon abgeleiteten Typ abgeleitet.  
  
 Im folgenden Codebeispiel erstellen Sie eine benutzerdefinierte Zellenklasse namens `DataGridViewRolloverCell`, die erkennt, wann sich der Mauszeiger innerhalb bzw. außerhalb der Zellenumgrenzung befindet.  Wenn sich der Mauszeiger innerhalb der Zellenumgrenzungen befindet, wird ein abgesenktes Rechteck gezeichnet.  Dieser neue Typ leitet sich von <xref:System.Windows.Forms.DataGridViewTextBoxCell> ab und verhält sich in jeder anderen Hinsicht wie seine Basisklasse.  Die Assistentenspaltenklasse heißt `DataGridViewRolloverColumn`.  
  
 Erstellen Sie zum Verwenden dieser Klassen ein Formular mit einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement, fügen Sie der <xref:System.Windows.Forms.DataGridView.Columns%2A>\-Auflistung ein oder mehrere `DataGridViewRolloverColumn`\-Objekte hinzu, und füllen Sie das Steuerelement mit Zeilen, die Werte enthalten.  
  
> [!NOTE]
>  Dieses Beispiel funktioniert nicht ordnungsgemäß, wenn Sie leere Zeilen hinzufügen.  Leere Zeilen werden beispielsweise erstellt, wenn Sie dem Steuerelement Zeilen hinzufügen, indem Sie die <xref:System.Windows.Forms.DataGridView.RowCount%2A>\-Eigenschaft festlegen.  Der Grund dafür ist, dass die in diesem Fall hinzugefügten Zeilen automatisch freigegeben werden. Das heißt, dass `DataGridViewRolloverCell`\-Objekte erst instanziiert werden, wenn Sie auf einzelne Zellen klicken und somit die Freigabe der zugeordneten Zeilen aufheben.  
  
 Da bei dieser Art der Zellenanpassung nicht freigegebene Zeilen benötigt werden, eignet sie sich nicht für große DataSets.  Weitere Informationen zum Freigeben von Zeilen finden Sie unter [Empfohlene Vorgehensweisen für das Skalieren des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
> [!NOTE]
>  Wenn Sie von <xref:System.Windows.Forms.DataGridViewCell> oder <xref:System.Windows.Forms.DataGridViewColumn> ableiten und der abgeleiteten Klasse neue Eigenschaften hinzufügen, müssen Sie die `Clone`\-Methode überschreiben, damit die neuen Eigenschaften bei Klonvorgängen kopiert werden.  Außerdem sollten Sie die `Clone`\-Methode der Basisklasse aufrufen, damit die Eigenschaften der Basisklasse in die neue Zelle oder Spalte kopiert werden.  
  
### So passen Sie Zellen und Spalten im DataGridView\-Steuerelement an  
  
1.  Leiten Sie eine neue Zellenklasse namens `DataGridViewRolloverCell` vom <xref:System.Windows.Forms.DataGridViewTextBoxCell>\-Typ ab.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#201)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#201)]  
    [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#202](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#202)]
    [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#202](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#202)]  
  
2.  Überschreiben Sie die <xref:System.Windows.Forms.DataGridViewTextBoxCell.Paint%2A>\-Methode in der `DataGridViewRolloverCell`\-Klasse.  Rufen Sie in der Überschreibung zuerst die Basisklassenimplementierung auf, die die gehosteten Textfeldfunktionen behandelt.  Verwenden Sie dann die <xref:System.Windows.Forms.Control.PointToClient%2A>\-Methode des Steuerelements, um die Cursorposition \(in Bildschirmkoordinaten\) in die Koordinaten des <xref:System.Windows.Forms.DataGridView>\-Clientbereichs umzuwandeln.  Wenn die Mauskoordinaten innerhalb der Zellenumgrenzung liegen, zeichnen Sie das abgesenkte Rechteck.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#210](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#210)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#210](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#210)]  
  
3.  Überschreiben Sie die <xref:System.Windows.Forms.DataGridViewCell.OnMouseEnter%2A>\-Methode und die <xref:System.Windows.Forms.DataGridViewCell.OnMouseLeave%2A>\-Methode in der `DataGridViewRolloverCell`\-Klasse, um Zellen dazu zu zwingen, sich selbst neu zu zeichnen, wenn der Mauszeiger darüber bewegt wird.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#220)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#220)]  
  
4.  Leiten Sie eine neue Klasse namens `DataGridViewRolloverCellColumn` vom <xref:System.Windows.Forms.DataGridViewColumn>\-Typ ab.  Weisen Sie im Konstruktor ein neues `DataGridViewRolloverCell`\-Objekt seiner <xref:System.Windows.Forms.DataGridViewColumn.CellTemplate%2A>\-Eigenschaft zu.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#300)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#300)]  
  
## Beispiel  
 Das vollständige Codebeispiel umfasst ein kleines Testformular, das das Verhalten des benutzerdefinierten Zellentyps veranschaulicht.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#000)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Windows.Forms" und "System.Drawing".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCell>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 [Anpassen des DataGridView\-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)   
 [Architektur des DataGridView\-Steuerelements](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)   
 [Spaltentypen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)   
 [Empfohlene Vorgehensweisen für das Skalieren des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)