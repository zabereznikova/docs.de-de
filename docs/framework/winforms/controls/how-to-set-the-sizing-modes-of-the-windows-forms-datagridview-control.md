---
title: Festlegen der Größen Anpassungs Modi des DataGridView-Steuer Elements
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], setting sizing modes
- DataGridView control [Windows Forms], sizing modes
ms.assetid: e9ad15e6-b4bb-44aa-a767-3738e9db1651
ms.openlocfilehash: 15b084afa4149ac43d40aeae7f35f0eaff5ac0e1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738391"
---
# <a name="how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control"></a>Gewusst wie: Festlegen der Größenanpassungsmodi des DataGridView-Steuerelements in Windows Forms
Die folgenden Prozeduren veranschaulichen einige allgemeinen Szenarien, die die Größenanpassungsoptionen für das <xref:System.Windows.Forms.DataGridView>-Steuerelement und für bestimmte Spalten in einem Steuerelement anpassen oder kombinieren.  
  
### <a name="to-create-a-fixed-width-column"></a>So erstellen Sie eine Spalte mit fester Breite  
  
- Legen Sie für die <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>Eigenschaft <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>, für die <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A>-Eigenschaft <xref:System.Windows.Forms.DataGridViewTriState.False>, für die <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A>-Eigenschaft `true` und für die <xref:System.Windows.Forms.DataGridViewColumn.Width%2A>-Eigenschaft einen geeigneten Wert fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#10)]  
  
### <a name="to-create-a-column-that-adjusts-its-size-to-fit-its-content"></a>So erstellen Sie eine Spalte, die ihre Größe an ihren Inhalt angepasst  
  
- Legen Sie für die <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>-Eigenschaft einen inhaltsbasierten Größenanpassungsmodus fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#20)]  
  
### <a name="to-create-fill-mode-columns-for-values-of-varying-size-and-importance"></a>So erstellen Sie Füllmodusspalten für Werte unterschiedlicher Größe und Wichtigkeit  
  
- Legen Sie für die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>-Eigenschaft den Wert <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> fest, um den Größenänderungsmodus für alle Spalten festzulegen, die diesen Wert nicht außer Kraft setzen. Legen Sie für die <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>-Eigenschaften der Spalten Werte fest, die proportional zu ihren durchschnittlichen Inhaltsbreiten sind. Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>-Eigenschaften wichtiger Spalten fest, um sicherzustellen, dass Inhalt teilweise angezeigt werden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#30)]  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden vollständigen Codebeispiel steht Ihnen eine Beispielanwendung zur Verfügung, die Ihnen dabei helfen kann, sich mit den in diesem Thema beschriebenen Optionen vertraut zu machen.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#00)]  
  
 So verwenden Sie diese Beispielanwendung  
  
- Ändern Sie die Größe des Formulars. Beachten Sie, wie sich die Breite der Füllmodusspalten ändert, während die Proportionen, die durch die <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>-Eigenschaftenwerte angegeben werden, beibehalten werden. Beachten Sie, wie das <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> einer Spalte verhindert, dass diese sich ändert, wenn das Formular zu klein ist.  
  
- Ändern Sie die Spaltengrößen, indem Sie die Spaltenunterteiler mit der Maus ziehen. Beachten Sie, dass die Größe einiger Spalten nicht geändert werden kann. Beachten Sie außerdem, dass anpassbare Spalten nicht schmaler als ihre Mindestbreite gemacht werden können.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A?displayProperty=nameWithType>
