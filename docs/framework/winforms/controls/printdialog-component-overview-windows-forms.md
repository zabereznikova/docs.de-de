---
title: Übersicht über die PrintDialog-Komponente
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728666"
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="6625e-102">Übersicht über die PrintDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6625e-102">PrintDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="6625e-103">Bei der Windows Forms [PrintDialog](printdialog-component-windows-forms.md) -Komponente handelt es sich um ein vorkonfiguriertes Dialogfeld, das zum Auswählen eines Druckers, zum Auswählen der zu Druck Ende Seiten und zum bestimmen anderer Druck bezogener Einstellungen in Windows-basierten Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6625e-103">The Windows Forms [PrintDialog](printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="6625e-104">Verwenden Sie sie als einfache Lösung für die Auswahl von Druckern und druckbezogenen Einstellungen, anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6625e-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="6625e-105">Sie können es Benutzern ermöglichen, viele Teile Ihrer Dokumente zu drucken: alle drucken, den ausgewählten Seitenbereich drucken oder eine Auswahl drucken.</span><span class="sxs-lookup"><span data-stu-id="6625e-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="6625e-106">Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="6625e-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="6625e-107">Die <xref:System.Windows.Forms.PrintDialog> Komponente erbt von der <xref:System.Windows.Forms.CommonDialog>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6625e-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-component"></a><span data-ttu-id="6625e-108">Arbeiten mit der Komponente</span><span class="sxs-lookup"><span data-stu-id="6625e-108">Working with the Component</span></span>

<span data-ttu-id="6625e-109">Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>-Methode, um das Dialogfeld zur Laufzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6625e-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="6625e-110">Diese Komponente verfügt über Eigenschaften, die entweder mit einem einzelnen Druckauftrag (<xref:System.Drawing.Printing.PrintDocument>-Klasse) oder den Einstellungen eines einzelnen Druckers (<xref:System.Drawing.Printing.PrinterSettings>-Klasse) in Beziehung stehen.</span><span class="sxs-lookup"><span data-stu-id="6625e-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="6625e-111">Beide können wiederum von mehreren Druckern gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="6625e-111">Either of these, in turn, may be shared by multiple printers.</span></span>

<span data-ttu-id="6625e-112">Wenn Sie einem Formular hinzugefügt wird, wird die <xref:System.Windows.Forms.PrintDialog> Komponente in der Leiste am unteren Rand des Windows Forms-Designer in Visual Studio angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6625e-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="6625e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6625e-113">See also</span></span>

- <xref:System.Windows.Forms.PrintDialog>
- [<span data-ttu-id="6625e-114">PrintDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="6625e-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
