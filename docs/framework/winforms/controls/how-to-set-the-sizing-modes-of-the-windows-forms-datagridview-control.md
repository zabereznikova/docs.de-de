---
title: 'Vorgehensweise: Festlegen der Größenanpassungsmodi des DataGridView-Steuerelements in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], setting sizing modes
- DataGridView control [Windows Forms], sizing modes
ms.assetid: e9ad15e6-b4bb-44aa-a767-3738e9db1651
ms.openlocfilehash: d92322da6644c110f5e3177acebea62799a0ed89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977872"
---
# <a name="how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control"></a>Vorgehensweise: Festlegen der Größenanpassungsmodi des DataGridView-Steuerelements in Windows Forms
Die folgenden Prozeduren veranschaulichen einige allgemeinen Szenarien, die die Größenanpassungsoptionen für das <xref:System.Windows.Forms.DataGridView>-Steuerelement und für bestimmte Spalten in einem Steuerelement anpassen oder kombinieren.  
  
### <a name="to-create-a-fixed-width-column"></a>So erstellen Sie eine Spalte mit fester Breite  
  
-   Legen Sie für die <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>Eigenschaft <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>, für die <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A>-Eigenschaft <xref:System.Windows.Forms.DataGridViewTriState.False>, für die <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A>-Eigenschaft `true` und für die <xref:System.Windows.Forms.DataGridViewColumn.Width%2A>-Eigenschaft einen geeigneten Wert fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#10)]  
  
### <a name="to-create-a-column-that-adjusts-its-size-to-fit-its-content"></a>So erstellen Sie eine Spalte, die ihre Größe an ihren Inhalt angepasst  
  
-   Legen Sie für die <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>-Eigenschaft einen inhaltsbasierten Größenanpassungsmodus fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#20)]  
  
### <a name="to-create-fill-mode-columns-for-values-of-varying-size-and-importance"></a>So erstellen Sie Füllmodusspalten für Werte unterschiedlicher Größe und Wichtigkeit  
  
-   Legen Sie für die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>-Eigenschaft den Wert <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> fest, um den Größenänderungsmodus für alle Spalten festzulegen, die diesen Wert nicht außer Kraft setzen. Legen Sie für die <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>-Eigenschaften der Spalten Werte fest, die proportional zu ihren durchschnittlichen Inhaltsbreiten sind. Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>-Eigenschaften wichtiger Spalten fest, um sicherzustellen, dass Inhalt teilweise angezeigt werden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#30)]  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden vollständigen Codebeispiel steht Ihnen eine Beispielanwendung zur Verfügung, die Ihnen dabei helfen kann, sich mit den in diesem Thema beschriebenen Optionen vertraut zu machen.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#00)]  
  
 So verwenden Sie diese Beispielanwendung  
  
-   Ändern Sie die Größe des Formulars. Beachten Sie, wie sich die Breite der Füllmodusspalten ändert, während die Proportionen, die durch die <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>-Eigenschaftenwerte angegeben werden, beibehalten werden. Beachten Sie, wie das <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> einer Spalte verhindert, dass diese sich ändert, wenn das Formular zu klein ist.  
  
-   Ändern Sie die Spaltengrößen, indem Sie die Spaltenunterteiler mit der Maus ziehen. Beachten Sie, dass die Größe einiger Spalten nicht geändert werden kann. Beachten Sie außerdem, dass anpassbare Spalten nicht schmaler als ihre Mindestbreite gemacht werden können.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A?displayProperty=nameWithType>
