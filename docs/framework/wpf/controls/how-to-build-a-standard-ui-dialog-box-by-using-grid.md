---
title: 'Gewusst wie: Erstellen eines Benutzeroberflächen-Standarddialogfelds unter Verwendung des Grid-Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: d0b24e320c2a341b069e1c9c3e8b6d5e93076733
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551881"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="c3dac-102">Gewusst wie: Erstellen eines Benutzeroberflächen-Standarddialogfelds unter Verwendung des Grid-Elements</span><span class="sxs-lookup"><span data-stu-id="c3dac-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="c3dac-103">In diesem Beispiel wird gezeigt, wie eine Standard- [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Dialogfeld mithilfe der <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="c3dac-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3dac-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3dac-104">Example</span></span>  
 <span data-ttu-id="c3dac-105">Das folgende Beispiel erstellt ein Dialogfeld an, wie die **ausführen** im Dialogfeld die [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="c3dac-105">The following example creates a dialog box like the **Run** dialog box in the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="c3dac-106">Das Beispiel erstellt eine <xref:System.Windows.Controls.Grid> und verwendet die <xref:System.Windows.Controls.ColumnDefinition> und <xref:System.Windows.Controls.RowDefinition> Klassen zum Definieren von fünf Spalten und vier Zeilen.</span><span class="sxs-lookup"><span data-stu-id="c3dac-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="c3dac-107">Anschließend fügt hinzu und platziert eine <xref:System.Windows.Controls.Image>, `RunIcon.png`, zum Darstellen des Bilds, das Sie im Dialogfeld gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="c3dac-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="c3dac-108">Das Bild wird in der ersten Spalte und Zeile platziert die <xref:System.Windows.Controls.Grid> (der oberen linken Ecke).</span><span class="sxs-lookup"><span data-stu-id="c3dac-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="c3dac-109">Als Nächstes das Beispiel fügt eine <xref:System.Windows.Controls.TextBlock> Element der ersten Spalte, der die übrigen Spalten der ersten Zeile erstreckt.</span><span class="sxs-lookup"><span data-stu-id="c3dac-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="c3dac-110">Fügt eine andere <xref:System.Windows.Controls.TextBlock> Element der zweiten Zeile in der ersten Spalte zur Darstellung der **öffnen** Textfeld.</span><span class="sxs-lookup"><span data-stu-id="c3dac-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="c3dac-111">Ein <xref:System.Windows.Controls.TextBlock> folgt, das den Dateneingabebereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="c3dac-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="c3dac-112">Schließlich im Beispiel fügt drei <xref:System.Windows.Controls.Button> Elemente, die auf die letzte Zeile darstellen der **OK**, **"Abbrechen"**, und **Durchsuchen** Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="c3dac-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c3dac-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3dac-113">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.GridUnitType>  
 [<span data-ttu-id="c3dac-114">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="c3dac-114">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="c3dac-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="c3dac-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)
