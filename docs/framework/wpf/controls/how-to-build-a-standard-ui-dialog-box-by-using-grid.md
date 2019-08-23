---
title: 'Vorgehensweise: Erstellen eines Benutzeroberflächen-Standarddialogfelds mithilfe von Grid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 68c9653e616388374aad2ad33ac7dab68446241d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923419"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>Vorgehensweise: Erstellen eines Benutzeroberflächen-Standarddialogfelds mithilfe von Grid
In diesem Beispiel wird gezeigt, wie ein [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Standard Dialogfeld mit <xref:System.Windows.Controls.Grid> dem-Element erstellt wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Dialogfeld wie das Dialogfeld **Ausführen** im Windows-Betriebssystem erstellt.  
  
 Im Beispiel wird ein <xref:System.Windows.Controls.Grid> erstellt und die <xref:System.Windows.Controls.ColumnDefinition> - <xref:System.Windows.Controls.RowDefinition> Klasse und die-Klasse verwendet, um fünf Spalten und vier Zeilen zu definieren.  
  
 Im Beispiel wird dann ein <xref:System.Windows.Controls.Image>, `RunIcon.png`, hinzugefügt und positioniert, um das Bild darzustellen, das im Dialogfeld gefunden wird. Das Bild wird in der ersten Spalte und Zeile der <xref:System.Windows.Controls.Grid> (der oberen linken Ecke) platziert.  
  
 Im folgenden Beispiel wird der ersten <xref:System.Windows.Controls.TextBlock> Spalte, die die restlichen Spalten der ersten Zeile umfasst, ein-Element hinzugefügt. Der zweiten Zeile <xref:System.Windows.Controls.TextBlock> in der ersten Spalte wird ein weiteres Element hinzugefügt, das das **geöffnete** Textfeld darstellt. Ein <xref:System.Windows.Controls.TextBlock> folgt, das den Dateneingabe Bereich darstellt.  
  
 Schließlich werden in diesem Beispiel der <xref:System.Windows.Controls.Button> letzten Zeile drei Elemente hinzugefügt, die die Ereignisse " **OK**", " **Abbrechen**" und " **Durchsuchen** " darstellen.  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [Übersicht über Panel-Elemente](panels-overview.md)
- [Themen zu Vorgehensweisen](grid-how-to-topics.md)
