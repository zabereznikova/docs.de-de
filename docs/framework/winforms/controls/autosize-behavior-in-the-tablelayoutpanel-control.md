---
title: Das AutoSize-Verhalten im TableLayoutPanel-Steuerelement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3d4813b7bd37c0c5bd9b04b37cb825067b35ce3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a><span data-ttu-id="c2f73-102">Das AutoSize-Verhalten im TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c2f73-102">AutoSize Behavior in the TableLayoutPanel Control</span></span>
## <a name="distinct-autosize-behaviors"></a><span data-ttu-id="c2f73-103">Verschiedene AutoSize-Verhalten</span><span class="sxs-lookup"><span data-stu-id="c2f73-103">Distinct AutoSize Behaviors</span></span>  
 <span data-ttu-id="c2f73-104">Die <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement das automatische Größenanpassungsverhalten unterstützt, auf folgende Weise:</span><span class="sxs-lookup"><span data-stu-id="c2f73-104">The <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior in the following ways:</span></span>  
  
-   <span data-ttu-id="c2f73-105">Über die <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="c2f73-105">Through the <xref:System.Windows.Forms.Control.AutoSize%2A> property;</span></span>  
  
-   <span data-ttu-id="c2f73-106">Über die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> Eigenschaft auf die <xref:System.Windows.Forms.TableLayoutPanel> Zeilen- und Spaltenstile des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="c2f73-106">Through the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property on the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a><span data-ttu-id="c2f73-107">Der AutoSize-Eigenschaft mit Zeilen- und Spaltenformate</span><span class="sxs-lookup"><span data-stu-id="c2f73-107">The AutoSize Property with Row and Column Styles</span></span>  
 <span data-ttu-id="c2f73-108">Die folgende Tabelle beschreibt die Interaktion zwischen der <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft und die <xref:System.Windows.Forms.TableLayoutPanel> Zeilen- und Spaltenstile des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="c2f73-108">The following table describes the interaction between the <xref:System.Windows.Forms.Control.AutoSize%2A> property and the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
|<span data-ttu-id="c2f73-109">AutoSize-Einstellung</span><span class="sxs-lookup"><span data-stu-id="c2f73-109">AutoSize setting</span></span>|<span data-ttu-id="c2f73-110">Stil-Aktivität</span><span class="sxs-lookup"><span data-stu-id="c2f73-110">Style interaction</span></span>|  
|----------------------|-----------------------|  
|`false`|<span data-ttu-id="c2f73-111">Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement geht von links nach rechts und weist Speicherplatz für die Spalte oder Zeile oder in der folgenden Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="c2f73-111">The <xref:System.Windows.Forms.TableLayoutPanel> control proceeds from left to right, and allocates space for the column or row or in the following order.</span></span><br /><br /> <span data-ttu-id="c2f73-112">1.  Wenn die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.SizeType.Absolute>, die Anzahl der Pixel, die vom angegebenen <xref:System.Windows.Forms.ColumnStyle.Width%2A> oder <xref:System.Windows.Forms.RowStyle.Height%2A> zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c2f73-112">1.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.Absolute>, the number of pixels specified by <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> is allocated.</span></span><br /><span data-ttu-id="c2f73-113">2.  Wenn die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.SizeType.AutoSize>, die Anzahl der Pixel des untergeordneten Steuerelements zurückgegebene <xref:System.Windows.Forms.Control.GetPreferredSize%2A> Methode zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c2f73-113">2.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.AutoSize>, the number of pixels returned by the child control’s <xref:System.Windows.Forms.Control.GetPreferredSize%2A> method is allocated.</span></span><br /><span data-ttu-id="c2f73-114">3.  Nach der Speicherplatz für alle <xref:System.Windows.Forms.SizeType.Absolute> und <xref:System.Windows.Forms.SizeType.AutoSize> Spalten oder Zeilen belegt, alle Spalten oder Zeilen mit <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> festgelegt <xref:System.Windows.Forms.SizeType.Percent> werden verwendet, um den verbleibenden freien Speicherplatz proportional zu verteilen</span><span class="sxs-lookup"><span data-stu-id="c2f73-114">3.  After space for all <xref:System.Windows.Forms.SizeType.Absolute> and <xref:System.Windows.Forms.SizeType.AutoSize> columns or rows is allocated, any columns or rows with <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> set to <xref:System.Windows.Forms.SizeType.Percent> are used to proportionally allocate the remaining free space</span></span>|  
|`true`|<span data-ttu-id="c2f73-115">Ähnelt der vorherigen Interaktion, mit der Ausnahme, die <xref:System.Windows.Forms.SizeType.Percent> Spalten oder Zeilen erhalten Sie einen automatische größenanpassung Aspekt.</span><span class="sxs-lookup"><span data-stu-id="c2f73-115">Similar to the previous interaction, with the exception that <xref:System.Windows.Forms.SizeType.Percent> columns or rows acquire an automatic sizing aspect.</span></span><br /><br /> <span data-ttu-id="c2f73-116">Die <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement nach unten erweitert die Spalte oder Zeile ausreichend freien Speicherplatz zu erstellen, damit keine Spalte oder Zeile mit <xref:System.Windows.Forms.SizeType.Percent> Styling clips seinen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="c2f73-116">The <xref:System.Windows.Forms.TableLayoutPanel> control expands the column or row to create adequate free space, so that no column or row with <xref:System.Windows.Forms.SizeType.Percent> styling clips its contents.</span></span> <span data-ttu-id="c2f73-117">Die <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement ordnet den neuen Platz proportional anhand der <xref:System.Windows.Forms.ColumnStyle.Width%2A> oder <xref:System.Windows.Forms.RowStyle.Height%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c2f73-117">The <xref:System.Windows.Forms.TableLayoutPanel> control allocates the new space proportionally according to the <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2f73-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2f73-118">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="c2f73-119">Übersicht über das TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c2f73-119">TableLayoutPanel Control Overview</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)
