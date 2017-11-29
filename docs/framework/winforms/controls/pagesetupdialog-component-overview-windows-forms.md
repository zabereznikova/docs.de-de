---
title: "Übersicht über die PageSetupDialog-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 082dbff66c8a0f06635936011f802c99b88e41df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="63dd8-102">Übersicht über die PageSetupDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="63dd8-102">PageSetupDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="63dd8-103">Windows Forms <xref:System.Windows.Forms.PageSetupDialog> Komponente ist ein vorkonfiguriertes Dialogfeld zum Festlegen der Seite Details für das Drucken in Windows-basierten Anwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="63dd8-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="63dd8-104">Verwenden Sie es in Ihrer Windows basierenden Anwendung als einfache Lösung, die für Benutzer zum Festlegen der Einstellungen für anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="63dd8-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="63dd8-105">Sie können Benutzer zum Festlegen von Rahmen und Rand Korrekturen, Kopf- und Fußzeilen sowie hoch-oder Querformat aktivieren.</span><span class="sxs-lookup"><span data-stu-id="63dd8-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="63dd8-106">Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="63dd8-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="63dd8-107">Wichtige Eigenschaften und Methoden</span><span class="sxs-lookup"><span data-stu-id="63dd8-107">Key Properties and Methods</span></span>  
 <span data-ttu-id="63dd8-108">Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="63dd8-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="63dd8-109">Diese Komponente verfügt über Eigenschaften, die Sie festlegen können, die entweder eine einzelne Seite beziehen (<xref:System.Drawing.Printing.PrintDocument> Klasse) oder einem beliebigen Dokument (<xref:System.Drawing.Printing.PageSettings> Klasse).</span><span class="sxs-lookup"><span data-stu-id="63dd8-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="63dd8-110">Darüber hinaus die <xref:System.Windows.Forms.PageSetupDialog> Komponente kann verwendet werden, um zu bestimmen, und im rowsetcache bestimmte Druckereinstellungen fest, die <xref:System.Drawing.Printing.PrinterSettings> Klasse.</span><span class="sxs-lookup"><span data-stu-id="63dd8-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>  
  
 <span data-ttu-id="63dd8-111">Wenn sie zu einem Formular hinzugefügt wird die <xref:System.Windows.Forms.PageSetupDialog> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63dd8-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63dd8-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63dd8-112">See Also</span></span>  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [<span data-ttu-id="63dd8-113">PageSetupDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="63dd8-113">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
