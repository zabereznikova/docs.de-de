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
ms.openlocfilehash: 0ade908e92e552017acb9ba242ccba2c28c3c995
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149525"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="928e8-102">Vorgehensweise: Erstellen eines Benutzeroberflächen-Standarddialogfelds mithilfe von Grid</span><span class="sxs-lookup"><span data-stu-id="928e8-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="928e8-103">In diesem Beispiel wird gezeigt, wie eine Standard- [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Dialogfeld mithilfe der <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="928e8-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="928e8-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="928e8-104">Example</span></span>  
 <span data-ttu-id="928e8-105">Das folgende Beispiel erstellt ein Dialogfeld wie das **ausführen** im Dialogfeld die [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="928e8-105">The following example creates a dialog box like the **Run** dialog box in the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="928e8-106">Das Beispiel erstellt eine <xref:System.Windows.Controls.Grid> und verwendet die <xref:System.Windows.Controls.ColumnDefinition> und <xref:System.Windows.Controls.RowDefinition> Klassen zum Definieren von fünf Spalten und vier Zeilen.</span><span class="sxs-lookup"><span data-stu-id="928e8-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="928e8-107">Anschließend fügt hinzu und platziert eine <xref:System.Windows.Controls.Image>, `RunIcon.png`, zum Darstellen des Bilds, die Sie im Dialogfeld befindet.</span><span class="sxs-lookup"><span data-stu-id="928e8-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="928e8-108">Das Bild wird in der ersten Spalte und Zeile platziert die <xref:System.Windows.Controls.Grid> (linke obere Ecke).</span><span class="sxs-lookup"><span data-stu-id="928e8-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="928e8-109">Als Nächstes das Beispiel fügt eine <xref:System.Windows.Controls.TextBlock> Element der ersten Spalte, die die verbleibenden Spalten der ersten Zeile erstreckt.</span><span class="sxs-lookup"><span data-stu-id="928e8-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="928e8-110">Fügt einen anderen <xref:System.Windows.Controls.TextBlock> Element der zweiten Zeile in der ersten Spalte zur Darstellung der **öffnen** Textfeld.</span><span class="sxs-lookup"><span data-stu-id="928e8-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="928e8-111">Ein <xref:System.Windows.Controls.TextBlock> folgt, das den Dateneingabebereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="928e8-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="928e8-112">Zum Schluss das Beispiel fügt drei <xref:System.Windows.Controls.Button> Elemente der letzten Zeile, die darstellen der **OK**, **Abbrechen**, und **Durchsuchen** Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="928e8-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="928e8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="928e8-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="928e8-114">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="928e8-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="928e8-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="928e8-115">How-to Topics</span></span>](grid-how-to-topics.md)
