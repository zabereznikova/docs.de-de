---
title: 'Vorgehensweise: Angeben von Standardwerten für neue Zeilen im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
ms.openlocfilehash: cc854f0cdbef8373b74a16c7d5bc044cfee5aa84
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708027"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Angeben von Standardwerten für neue Zeilen im DataGridView-Steuerelement in Windows Forms
Sie können die Dateneingabe praktischer vornehmen, wenn die Anwendung im standardmäßigen Werte für neu hinzugefügte Zeilen füllt. Mit der <xref:System.Windows.Forms.DataGridView> -Klasse, Sie können Standardwerte mit dem <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> Ereignis. Dieses Ereignis wird ausgelöst, wenn der Benutzer die Zeile für neue Datensätze eingibt. Wenn Ihr Code auf dieses Ereignis verarbeitet, können Sie die gewünschte Zellen mit den Werten Ihrer Wahl auffüllen.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Angeben von Standardwerten für neue Zeilen mithilfe der <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> Ereignis.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
-   Ein `NewCustomerId` Funktion zum Generieren von eindeutigen `CustomerID` Werte.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Dateneingabe im DataGridView-Steuerelement in Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Verwenden der Zeile für neue Datensätze im DataGridView-Steuerelement in Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
