---
title: "Übersicht über das PrintPreviewControl-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47bef441b01d8bdcf9a365c341005cff28c64f27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a><span data-ttu-id="fbb04-102">Übersicht über das PrintPreviewControl-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="fbb04-102">PrintPreviewControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="fbb04-103">Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> dient zum Anzeigen einer [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) wie es gedruckt wird.</span><span class="sxs-lookup"><span data-stu-id="fbb04-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> is used to display a [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) as it will appear when printed.</span></span> <span data-ttu-id="fbb04-104">Da dieses Steuerelement weder Schaltflächen noch andere Elemente einer Benutzeroberfläche besitzt, verwenden Sie <xref:System.Windows.Forms.PrintPreviewControl> in der Regel nur, wenn Sie eine eigene Benutzeroberfläche für die Seitenansicht programmieren möchten.</span><span class="sxs-lookup"><span data-stu-id="fbb04-104">This control has no buttons or other user interface elements, so typically you use the <xref:System.Windows.Forms.PrintPreviewControl> only if you wish to write your own print-preview user interface.</span></span> <span data-ttu-id="fbb04-105">Wenn Sie die Standardbenutzeroberfläche möchten, verwenden eine <xref:System.Windows.Forms.PrintPreviewDialog> steuern, finden Sie unter [Übersicht über das PrintPreviewDialog-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) eine Übersicht über.</span><span class="sxs-lookup"><span data-stu-id="fbb04-105">If you want the standard user interface, use a <xref:System.Windows.Forms.PrintPreviewDialog> control; see [PrintPreviewDialog Control Overview](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) for an overview.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="fbb04-106">Wichtige Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fbb04-106">Key Properties</span></span>  
 <span data-ttu-id="fbb04-107">Das Steuerelement Schlüsseleigenschaft ist <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, wodurch das Dokument in der Vorschau angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fbb04-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="fbb04-108">Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument> Objekt.</span><span class="sxs-lookup"><span data-stu-id="fbb04-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="fbb04-109">Einen Überblick über das Erstellen von Dokumenten für das Drucken finden Sie unter [Übersicht über die PrintDocument-Komponente](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) und [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).</span><span class="sxs-lookup"><span data-stu-id="fbb04-109">For an overview of creating documents for printing, see [PrintDocument Component Overview](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) and [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).</span></span> <span data-ttu-id="fbb04-110">Die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> und <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> Eigenschaften bestimmen die Anzahl der Seiten, die horizontal und vertikal auf dem Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fbb04-110">The <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="fbb04-111">Antialiasing kann den Text glattere angezeigt, aber es kann auch die Anzeige langsamer, Legen Sie zur Verwendung der <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="fbb04-111">Antialiasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbb04-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbb04-112">See Also</span></span>  
 <xref:System.Windows.Forms.PrintPreviewControl>  
 [<span data-ttu-id="fbb04-113">Übersicht über das PrintPreviewDialog-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fbb04-113">PrintPreviewDialog Control Overview</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)  
 [<span data-ttu-id="fbb04-114">PrintPreviewControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fbb04-114">PrintPreviewControl Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)  
 [<span data-ttu-id="fbb04-115">Dialogfeld-Steuerelemente und -Komponenten</span><span class="sxs-lookup"><span data-stu-id="fbb04-115">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
