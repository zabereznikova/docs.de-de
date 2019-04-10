---
title: Übersicht über das TableLayoutPanel-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- TableLayoutPanel
helpviewer_keywords:
- controls [Windows Forms], resizing
- resizable controls [Windows Forms]
- Windows Forms controls, proportional resizing
- Windows Forms, proportional resizing of controls
- layout [Windows Forms], TableLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
ms.openlocfilehash: 57a57b9f888f2fc46eddba5b97b9e833a7e9f028
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134016"
---
# <a name="tablelayoutpanel-control-overview"></a><span data-ttu-id="d2a39-102">Übersicht über das TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d2a39-102">TableLayoutPanel Control Overview</span></span>
<span data-ttu-id="d2a39-103">Das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement ordnet seinen Inhalt in einem Raster an.</span><span class="sxs-lookup"><span data-stu-id="d2a39-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="d2a39-104">Da das Layout sowohl zur Entwurfszeit als auch zur Laufzeit ausgeführt wird, kann es sich dynamisch ändern, wenn sich die Anwendungsumgebung ändert.</span><span class="sxs-lookup"><span data-stu-id="d2a39-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="d2a39-105">Dadurch können sich die Steuerelemente im Bereich proportional in der Größe anpassen, sodass sie auf Änderungen wie die Größenanpassung des übergeordneten Steuerelements oder eine durch Lokalisierung veränderte Textlänge reagieren.</span><span class="sxs-lookup"><span data-stu-id="d2a39-105">This gives the controls in the panel the ability to proportionally resize, so they can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
 <span data-ttu-id="d2a39-106">Jedes Windows Forms-Steuerelement kann ein untergeordnetes Element des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements sein, einschließlich anderer Instanzen von <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d2a39-106">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.TableLayoutPanel> control, including other instances of <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="d2a39-107">Dadurch können Sie anspruchsvolle Layouts erstellen, die sich zur Laufzeit an Änderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="d2a39-107">This allows you to construct sophisticated layouts that adapt to changes at run time.</span></span>  
  
 <span data-ttu-id="d2a39-108">Das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement kann je nach Wert der Eigenschaften <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> und <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> erweitert werden, sodass neue Steuerelemente hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="d2a39-108">The <xref:System.Windows.Forms.TableLayoutPanel> control can expand to accommodate new controls when they are added, depending on the value of the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>, and <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> properties.</span></span> <span data-ttu-id="d2a39-109">Indem Sie die <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>-Eigenschaft oder die <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>-Eigenschaft auf den Wert 0 festlegen, geben Sie an, dass der <xref:System.Windows.Forms.TableLayoutPanel> in der entsprechenden Richtung ungebunden ist.</span><span class="sxs-lookup"><span data-stu-id="d2a39-109">Setting either the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> or <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> property to a value of 0 specifies that the <xref:System.Windows.Forms.TableLayoutPanel> will be unbound in the corresponding direction.</span></span>  
  
 <span data-ttu-id="d2a39-110">Außerdem können Sie festlegen, in welche Richtung (horizontal oder vertikal) das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement erweitert wird, wenn es bereits mit untergeordneten Steuerelementen gefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="d2a39-110">You can also control the direction of expansion (horizontal or vertical) after the <xref:System.Windows.Forms.TableLayoutPanel> control is full of child controls.</span></span> <span data-ttu-id="d2a39-111">Standardmäßig wird das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement nach unten erweitert, indem Zeilen hinzufügt werden.</span><span class="sxs-lookup"><span data-stu-id="d2a39-111">By default, the <xref:System.Windows.Forms.TableLayoutPanel> control expands downward by adding rows.</span></span>  
  
 <span data-ttu-id="d2a39-112">Wenn Sie Zeilen und Spalten ein anderes Verhalten als das Standardverhalten zuweisen möchten, können Sie deren Eigenschaften mithilfe der <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A>-Eigenschaft und <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>-Eigenschaft steuern.</span><span class="sxs-lookup"><span data-stu-id="d2a39-112">If you want rows and columns that behave differently from the default behavior, you can control the properties of rows and columns by using the <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> and <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> properties.</span></span> <span data-ttu-id="d2a39-113">Sie können die Eigenschaften von Zeilen oder Spalten individuell festlegen.</span><span class="sxs-lookup"><span data-stu-id="d2a39-113">You can set the properties of rows or columns individually.</span></span>  
  
 <span data-ttu-id="d2a39-114">Das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement fügt seinen untergeordneten Steuerelementen folgende Eigenschaften hinzu: `Cell`, `Column`, `Row`, `ColumnSpan` und `RowSpan`.</span><span class="sxs-lookup"><span data-stu-id="d2a39-114">The <xref:System.Windows.Forms.TableLayoutPanel> control adds the following properties to its child controls: `Cell`, `Column`, `Row`, `ColumnSpan`, and `RowSpan`.</span></span>  
  
 <span data-ttu-id="d2a39-115">Sie können Zellen im <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement zusammenführen, indem Sie die `ColumnSpan`-Eigenschaft oder `RowSpan`-Eigenschaft für ein untergeordnetes Steuerelement festlegen.</span><span class="sxs-lookup"><span data-stu-id="d2a39-115">You can merge cells in the <xref:System.Windows.Forms.TableLayoutPanel> control by setting the `ColumnSpan` or `RowSpan` properties on a child control.</span></span>  
  
1.  [<span data-ttu-id="d2a39-116">Vorgehensweise: Ausrichten und Strecken eines Steuerelements in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d2a39-116">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2.  [<span data-ttu-id="d2a39-117">Vorgehensweise: Überspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d2a39-117">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3.  [<span data-ttu-id="d2a39-118">Vorgehensweise: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d2a39-118">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4.  [<span data-ttu-id="d2a39-119">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d2a39-119">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
  
## <a name="see-also"></a><span data-ttu-id="d2a39-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2a39-120">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutSettings>
- [<span data-ttu-id="d2a39-121">Vorgehensweise: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist</span><span class="sxs-lookup"><span data-stu-id="d2a39-121">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="d2a39-122">Vorgehensweise: Erstellen von in der Größe veränderbaren Windows Forms für die Dateneingabe</span><span class="sxs-lookup"><span data-stu-id="d2a39-122">How to: Create a Resizable Windows Form for Data Entry</span></span>](how-to-create-a-resizable-windows-form-for-data-entry.md)
- [<span data-ttu-id="d2a39-123">Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d2a39-123">Best Practices for the TableLayoutPanel Control</span></span>](best-practices-for-the-tablelayoutpanel-control.md)
