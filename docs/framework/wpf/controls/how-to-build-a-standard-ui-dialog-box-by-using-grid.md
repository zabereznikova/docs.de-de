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
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="c7ce1-102">Vorgehensweise: Erstellen eines Benutzeroberflächen-Standarddialogfelds mithilfe von Grid</span><span class="sxs-lookup"><span data-stu-id="c7ce1-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="c7ce1-103">In diesem Beispiel wird gezeigt, wie ein [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Standard Dialogfeld mit <xref:System.Windows.Controls.Grid> dem-Element erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c7ce1-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7ce1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7ce1-104">Example</span></span>  
 <span data-ttu-id="c7ce1-105">Im folgenden Beispiel wird ein Dialogfeld wie das Dialogfeld **Ausführen** im Windows-Betriebssystem erstellt.</span><span class="sxs-lookup"><span data-stu-id="c7ce1-105">The following example creates a dialog box like the **Run** dialog box in the Windows operating system.</span></span>  
  
 <span data-ttu-id="c7ce1-106">Im Beispiel wird ein <xref:System.Windows.Controls.Grid> erstellt und die <xref:System.Windows.Controls.ColumnDefinition> - <xref:System.Windows.Controls.RowDefinition> Klasse und die-Klasse verwendet, um fünf Spalten und vier Zeilen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="c7ce1-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="c7ce1-107">Im Beispiel wird dann ein <xref:System.Windows.Controls.Image>, `RunIcon.png`, hinzugefügt und positioniert, um das Bild darzustellen, das im Dialogfeld gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="c7ce1-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="c7ce1-108">Das Bild wird in der ersten Spalte und Zeile der <xref:System.Windows.Controls.Grid> (der oberen linken Ecke) platziert.</span><span class="sxs-lookup"><span data-stu-id="c7ce1-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="c7ce1-109">Im folgenden Beispiel wird der ersten <xref:System.Windows.Controls.TextBlock> Spalte, die die restlichen Spalten der ersten Zeile umfasst, ein-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c7ce1-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="c7ce1-110">Der zweiten Zeile <xref:System.Windows.Controls.TextBlock> in der ersten Spalte wird ein weiteres Element hinzugefügt, das das **geöffnete** Textfeld darstellt.</span><span class="sxs-lookup"><span data-stu-id="c7ce1-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="c7ce1-111">Ein <xref:System.Windows.Controls.TextBlock> folgt, das den Dateneingabe Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="c7ce1-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="c7ce1-112">Schließlich werden in diesem Beispiel der <xref:System.Windows.Controls.Button> letzten Zeile drei Elemente hinzugefügt, die die Ereignisse " **OK**", " **Abbrechen**" und " **Durchsuchen** " darstellen.</span><span class="sxs-lookup"><span data-stu-id="c7ce1-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c7ce1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7ce1-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="c7ce1-114">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="c7ce1-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="c7ce1-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="c7ce1-115">How-to Topics</span></span>](grid-how-to-topics.md)
