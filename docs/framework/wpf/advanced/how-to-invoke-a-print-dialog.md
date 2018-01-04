---
title: 'Gewusst wie: Aufrufen eines Druckdialogfelds'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8831566daca6ca36b40fbaaedbec9ff3ca8aaa99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="f3689-102">Gewusst wie: Aufrufen eines Druckdialogfelds</span><span class="sxs-lookup"><span data-stu-id="f3689-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="f3689-103">Um die Möglichkeit zum Drucken aus der Anwendung zu ermöglichen, Sie können einfach erstellen und Öffnen einer <xref:System.Windows.Controls.PrintDialog> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f3689-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3689-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f3689-104">Example</span></span>  
 <span data-ttu-id="f3689-105">Das <xref:System.Windows.Controls.PrintDialog>-Steuerelement stellt einen einheitlichen Einstiegspunkt für [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], Konfiguration und [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]-Auftragsübermittlung bereit.</span><span class="sxs-lookup"><span data-stu-id="f3689-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] job submission.</span></span> <span data-ttu-id="f3689-106">Das Steuerelement ist einfach zu verwenden und instanziiert werden kann, mithilfe von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Markup oder-Code.</span><span class="sxs-lookup"><span data-stu-id="f3689-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="f3689-107">Im folgende Beispiel wird demonstriert, wie zu instanziieren und öffnen das Steuerelement im Code und daraus zu drucken.</span><span class="sxs-lookup"><span data-stu-id="f3689-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="f3689-108">Es wird gezeigt, wie stellen Sie sicher, dass das Dialogfeld "dem Benutzer die Möglichkeit, einen bestimmten Bereich von Seiten bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f3689-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="f3689-109">Im Beispielcode wird davon ausgegangen, dass eine FixedDocumentSequence.xps-Datei im Stammverzeichnis des Laufwerks "c:" vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f3689-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="f3689-110">Sobald das Dialogfeld geöffnet ist, werden Benutzer auf ihrem Computer installierten Drucker auswählen können.</span><span class="sxs-lookup"><span data-stu-id="f3689-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="f3689-111">Sie müssen auch die Möglichkeit auszuwählen der [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319) zum Erstellen einer [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] Datei nicht drucken.</span><span class="sxs-lookup"><span data-stu-id="f3689-111">They will also have the option of selecting the [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319) to create an [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file instead of printing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3689-112">Die <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> Kontrolle über [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], die in diesem Thema erläutert wird dürfen nicht mit verwechselt werden die <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> -Komponente von [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3689-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].</span></span>  
  
 <span data-ttu-id="f3689-113">Streng genommen, können Sie die <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> Methode ohne jemals das Dialogfeld zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f3689-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="f3689-114">In dieser Hinsicht kann das Steuerelement als ein Druckkomponente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f3689-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="f3689-115">Aber aus Gründen der Leistung wäre es besser, verwenden Sie entweder die <xref:System.Printing.PrintQueue.AddJob%2A> Methode oder eine der vielen <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> und <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> Methoden die <xref:System.Windows.Xps.XpsDocumentWriter>.</span><span class="sxs-lookup"><span data-stu-id="f3689-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="f3689-116">Weitere Informationen hierzu finden Sie unter [Programmgesteuertes Drucken XPS-Dateien](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) und.</span><span class="sxs-lookup"><span data-stu-id="f3689-116">For more about this, see [Programmatically Print XPS Files](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) and .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3689-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3689-117">See Also</span></span>  
 <xref:System.Windows.Controls.PrintDialog>  
 [<span data-ttu-id="f3689-118">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="f3689-118">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="f3689-119">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="f3689-119">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="f3689-120">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="f3689-120">Microsoft XPS Document Writer</span></span>](http://go.microsoft.com/fwlink/?LinkId=147319)
