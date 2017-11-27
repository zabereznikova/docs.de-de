---
title: TableLayoutPanel-Steuerelement (Windows Forms)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms]
- controls [Windows Forms], sizing
- sizing [Windows Forms], automatic
- layout [Windows Forms], TableLayoutPanel control
- automatic sizing
ms.assetid: f55175c6-424e-4782-a86e-3f79c1550235
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6f8f949edcf637f4b56ab0bcfdd121c5cb29e543
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="tablelayoutpanel-control-windows-forms"></a><span data-ttu-id="8cc52-102">TableLayoutPanel-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="8cc52-102">TableLayoutPanel Control (Windows Forms)</span></span>
<span data-ttu-id="8cc52-103">Das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement ordnet seinen Inhalt in einem Raster an.</span><span class="sxs-lookup"><span data-stu-id="8cc52-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="8cc52-104">Da das Layout sowohl zur Entwurfszeit als auch zur Laufzeit ausgeführt wird, kann es sich dynamisch ändern, wenn sich die Anwendungsumgebung ändert.</span><span class="sxs-lookup"><span data-stu-id="8cc52-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="8cc52-105">Dadurch können sich die Steuerelemente im Bereich proportional in der Größe anpassen, sodass sie auf Änderungen wie die Größenanpassung des übergeordneten Steuerelements oder eine durch Lokalisierung veränderte Textlänge reagieren.</span><span class="sxs-lookup"><span data-stu-id="8cc52-105">This gives the controls in the panel the ability to proportionally resize, so it can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8cc52-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8cc52-106">In This Section</span></span>  
 [<span data-ttu-id="8cc52-107">Übersicht über das TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8cc52-107">TableLayoutPanel Control Overview</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)  
 <span data-ttu-id="8cc52-108">Stellt die allgemeinen Konzepte des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements vor, mit dem Sie ein Layout mit Zeilen und Spalten erstellen können.</span><span class="sxs-lookup"><span data-stu-id="8cc52-108">Introduces the general concepts of the <xref:System.Windows.Forms.TableLayoutPanel> control, which allows you to create a layout with rows and columns.</span></span>  
  
 [<span data-ttu-id="8cc52-109">Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8cc52-109">Best Practices for the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="8cc52-110">Enthält Empfehlungen zur optimalen Nutzung der Layoutfunktionen des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="8cc52-110">Outlines recommendations to help you get the most out of the layout features of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="8cc52-111">Das AutoSize-Verhalten im TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8cc52-111">AutoSize Behavior in the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/autosize-behavior-in-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="8cc52-112">Erläutert die Möglichkeiten, in denen das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement das automatische Größenanpassungsverhalten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8cc52-112">Explains the ways in which the <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior.</span></span>  
  
 [<span data-ttu-id="8cc52-113">Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8cc52-113">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 <span data-ttu-id="8cc52-114">Veranschaulicht das Verankern und Andocken von untergeordneten Steuerelementen in einem <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8cc52-114">Shows how to anchor and dock child controls in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="8cc52-115">Gewusst wie: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist</span><span class="sxs-lookup"><span data-stu-id="8cc52-115">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 <span data-ttu-id="8cc52-116">Veranschaulicht die Verwendung eines <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements zum Erstellen eines Formulars, das zur Lokalisierung gut geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="8cc52-116">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to localization.</span></span>  
  
 [<span data-ttu-id="8cc52-117">Gewusst wie: Erstellen von in der Größe veränderbaren Windows Forms für die Dateneingabe</span><span class="sxs-lookup"><span data-stu-id="8cc52-117">How to: Create a Resizable Windows Form for Data Entry</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)  
 <span data-ttu-id="8cc52-118">Veranschaulicht die Verwendung eines <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements zum Erstellen eines Formulars, das ordnungsgemäß auf die Größenänderung reagiert.</span><span class="sxs-lookup"><span data-stu-id="8cc52-118">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to resizing.</span></span>  
  
1.  <span data-ttu-id="8cc52-119">[Vorgehensweise: Ausrichten und Strecken eines Steuerelements in einem TableLayoutPanel-Steuerelement](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="8cc52-119">[How to: Align and Stretch a Control in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span></span>  
  
2.  <span data-ttu-id="8cc52-120">[Vorgehensweise: Überspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="8cc52-120">[How to: Span Rows and Columns in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span></span>  
  
3.  <span data-ttu-id="8cc52-121">[Vorgehensweise: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="8cc52-121">[How to: Edit Columns and Rows in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span></span>  
  
4.  <span data-ttu-id="8cc52-122">[Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="8cc52-122">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8cc52-123">Verweis</span><span class="sxs-lookup"><span data-stu-id="8cc52-123">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="8cc52-124">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8cc52-124">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 <span data-ttu-id="8cc52-125">Enthält die Referenzdokumentation für den <xref:System.Windows.Forms.TableLayoutSettings>-Typ.</span><span class="sxs-lookup"><span data-stu-id="8cc52-125">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutSettings> type.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="8cc52-126">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8cc52-126">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8cc52-127">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="8cc52-127">Related Sections</span></span>  
 [<span data-ttu-id="8cc52-128">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="8cc52-128">Localization</span></span>](../../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="8cc52-129">Bietet eine Übersicht über Themen zur Lokalisierung.</span><span class="sxs-lookup"><span data-stu-id="8cc52-129">Provides an overview of topics relating to localization.</span></span>  
  
 <span data-ttu-id="8cc52-130">Siehe auch [Lokalisieren von Anwendungen](http://msdn.microsoft.com/library/z68135h5\(v=vs.110\)) oder [Lokalisieren von Anwendungen](http://msdn.microsoft.com/library/z68135h5\(v=vs.120\))</span><span class="sxs-lookup"><span data-stu-id="8cc52-130">Also see [Localizing Applications](http://msdn.microsoft.com/library/z68135h5\(v=vs.110\)) or [Localizing Applications](http://msdn.microsoft.com/library/z68135h5\(v=vs.120\))</span></span>
