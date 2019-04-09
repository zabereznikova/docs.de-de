---
title: Übersicht über die PageSetupDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: 30ac782cae830ac996132046cbbc57392067c0ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228314"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="dc9d5-102">Übersicht über die PageSetupDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="dc9d5-102">PageSetupDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="dc9d5-103">Die Windows-Formulare <xref:System.Windows.Forms.PageSetupDialog> Komponente ist ein vorkonfiguriertes Dialogfeld zum Festlegen von Seitendetails für das Drucken in Windows-basierten Anwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc9d5-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="dc9d5-104">Verwenden Sie es in Ihrer Windows-basierten Anwendung als einfache Lösung, die für Benutzer zum Festlegen der Einstellungen anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dc9d5-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="dc9d5-105">Sie können die Benutzer zum Festlegen von Rahmen und Rand Anpassungen, Kopfzeilen und Fußzeilen und hoch-oder Querformat aktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc9d5-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="dc9d5-106">Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="dc9d5-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="dc9d5-107">Wichtige Eigenschaften und Methoden</span><span class="sxs-lookup"><span data-stu-id="dc9d5-107">Key Properties and Methods</span></span>  
 <span data-ttu-id="dc9d5-108">Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dc9d5-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="dc9d5-109">Diese Komponente weist Eigenschaften können Sie festlegen, die entweder eine einzelne Seite beziehen (<xref:System.Drawing.Printing.PrintDocument> Klasse) oder eines Dokuments, (<xref:System.Drawing.Printing.PageSettings> Klasse).</span><span class="sxs-lookup"><span data-stu-id="dc9d5-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="dc9d5-110">Darüber hinaus die <xref:System.Windows.Forms.PageSetupDialog> Komponente kann verwendet werden, um bestimmte Druckereinstellungen fest, zu bestimmen, und im rowsetcache der <xref:System.Drawing.Printing.PrinterSettings> Klasse.</span><span class="sxs-lookup"><span data-stu-id="dc9d5-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>  
  
 <span data-ttu-id="dc9d5-111">Wenn es auf ein Formular hinzugefügt wird die <xref:System.Windows.Forms.PageSetupDialog> Komponente, die in der Taskleiste am unteren Rand der Windows Forms-Designer wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc9d5-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc9d5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc9d5-112">See also</span></span>

- <xref:System.Windows.Forms.PageSetupDialog>
- [<span data-ttu-id="dc9d5-113">PageSetupDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="dc9d5-113">PageSetupDialog Component</span></span>](pagesetupdialog-component-windows-forms.md)
