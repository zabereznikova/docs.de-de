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
# <a name="how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="86ac2-102">Gewusst wie: Festlegen der Größenanpassungsmodi des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86ac2-102">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="86ac2-103">Die folgenden Prozeduren veranschaulichen einige allgemeinen Szenarien, die die Größenanpassungsoptionen für das <xref:System.Windows.Forms.DataGridView>-Steuerelement und für bestimmte Spalten in einem Steuerelement anpassen oder kombinieren.</span><span class="sxs-lookup"><span data-stu-id="86ac2-103">The following procedures demonstrate some common scenarios that customize or combine the sizing options available for the <xref:System.Windows.Forms.DataGridView> control and for specific columns in a control.</span></span>  
  
### <a name="to-create-a-fixed-width-column"></a><span data-ttu-id="86ac2-104">So erstellen Sie eine Spalte mit fester Breite</span><span class="sxs-lookup"><span data-stu-id="86ac2-104">To create a fixed-width column</span></span>  
  
- <span data-ttu-id="86ac2-105">Legen Sie für die <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>Eigenschaft <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>, für die <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A>-Eigenschaft <xref:System.Windows.Forms.DataGridViewTriState.False>, für die <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A>-Eigenschaft `true` und für die <xref:System.Windows.Forms.DataGridViewColumn.Width%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="86ac2-105">Set the <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> property to <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>, the <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> property to <xref:System.Windows.Forms.DataGridViewTriState.False>, the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`, and the <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> property to an appropriate value.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#10)]  
  
### <a name="to-create-a-column-that-adjusts-its-size-to-fit-its-content"></a><span data-ttu-id="86ac2-106">So erstellen Sie eine Spalte, die ihre Größe an ihren Inhalt angepasst</span><span class="sxs-lookup"><span data-stu-id="86ac2-106">To create a column that adjusts its size to fit its content</span></span>  
  
- <span data-ttu-id="86ac2-107">Legen Sie für die <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>-Eigenschaft einen inhaltsbasierten Größenanpassungsmodus fest.</span><span class="sxs-lookup"><span data-stu-id="86ac2-107">Set the <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> property to a content-based sizing mode.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#20)]  
  
### <a name="to-create-fill-mode-columns-for-values-of-varying-size-and-importance"></a><span data-ttu-id="86ac2-108">So erstellen Sie Füllmodusspalten für Werte unterschiedlicher Größe und Wichtigkeit</span><span class="sxs-lookup"><span data-stu-id="86ac2-108">To create fill-mode columns for values of varying size and importance</span></span>  
  
- <span data-ttu-id="86ac2-109">Legen Sie für die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>-Eigenschaft den Wert <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> fest, um den Größenänderungsmodus für alle Spalten festzulegen, die diesen Wert nicht außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="86ac2-109">Set the <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> to set the sizing mode for all columns that do not override this value.</span></span> <span data-ttu-id="86ac2-110">Legen Sie für die <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>-Eigenschaften der Spalten Werte fest, die proportional zu ihren durchschnittlichen Inhaltsbreiten sind.</span><span class="sxs-lookup"><span data-stu-id="86ac2-110">Set the <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> properties of the columns to values that are proportional to their average content widths.</span></span> <span data-ttu-id="86ac2-111">Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>-Eigenschaften wichtiger Spalten fest, um sicherzustellen, dass Inhalt teilweise angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="86ac2-111">Set the <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> properties of important columns to ensure partial content display.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="86ac2-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86ac2-112">Example</span></span>  
 <span data-ttu-id="86ac2-113">Mit dem folgenden vollständigen Codebeispiel steht Ihnen eine Beispielanwendung zur Verfügung, die Ihnen dabei helfen kann, sich mit den in diesem Thema beschriebenen Optionen vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="86ac2-113">The following complete code example provides a demonstration application that can help you understand the sizing options described in this topic.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#00)]  
  
 <span data-ttu-id="86ac2-114">So verwenden Sie diese Beispielanwendung:</span><span class="sxs-lookup"><span data-stu-id="86ac2-114">To use this demonstration application:</span></span>  
  
- <span data-ttu-id="86ac2-115">Ändern Sie die Größe des Formulars.</span><span class="sxs-lookup"><span data-stu-id="86ac2-115">Change the size of the form.</span></span> <span data-ttu-id="86ac2-116">Beachten Sie, wie sich die Breite der Füllmodusspalten ändert, während die Proportionen, die durch die <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>-Eigenschaftenwerte angegeben werden, beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="86ac2-116">Observe how the fill-mode columns change their widths while retaining the proportions indicated by the <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> property values.</span></span> <span data-ttu-id="86ac2-117">Beachten Sie, wie das <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> einer Spalte verhindert, dass diese sich ändert, wenn das Formular zu klein ist.</span><span class="sxs-lookup"><span data-stu-id="86ac2-117">Observe how a column's <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> prevents it from changing when the form is too small.</span></span>  
  
- <span data-ttu-id="86ac2-118">Ändern Sie die Spaltengrößen, indem Sie die Spaltenunterteiler mit der Maus ziehen.</span><span class="sxs-lookup"><span data-stu-id="86ac2-118">Change the column sizes by dragging the column dividers with the mouse.</span></span> <span data-ttu-id="86ac2-119">Beachten Sie, dass die Größe einiger Spalten nicht geändert werden kann. Beachten Sie außerdem, dass anpassbare Spalten nicht schmaler als ihre Mindestbreite gemacht werden können.</span><span class="sxs-lookup"><span data-stu-id="86ac2-119">Observe how some columns cannot be resized, and how resizable columns cannot be made narrower than their minimum widths.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="86ac2-120">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="86ac2-120">Compiling the Code</span></span>  
 <span data-ttu-id="86ac2-121">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="86ac2-121">This example requires:</span></span>  
  
- <span data-ttu-id="86ac2-122">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="86ac2-122">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ac2-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86ac2-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A?displayProperty=nameWithType>
