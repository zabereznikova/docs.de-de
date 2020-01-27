---
title: Übersicht über die OpenFileDialog-Komponente
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: c519b373150a49ee41dbb0c503f7d5a4862477d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728439"
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="74bc7-102">Übersicht über die OpenFileDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="74bc7-102">OpenFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="74bc7-103">Bei der Windows Forms-Komponente <xref:System.Windows.Forms.OpenFileDialog> handelt es sich um ein vorkonfiguriertes Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="74bc7-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="74bc7-104">Es ist das gleiche Dialogfeld **Öffnen** , das vom Windows-Betriebssystem verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="74bc7-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="74bc7-105">Sie erbt von der <xref:System.Windows.Forms.CommonDialog>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="74bc7-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="use-this-component"></a><span data-ttu-id="74bc7-106">Diese Komponente verwenden</span><span class="sxs-lookup"><span data-stu-id="74bc7-106">Use this component</span></span>

<span data-ttu-id="74bc7-107">Verwenden Sie diese Komponente in der Windows-basierten Anwendung als einfache Lösung für die Dateiauswahl, anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="74bc7-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="74bc7-108">Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="74bc7-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="74bc7-109">Beachten Sie jedoch, dass Sie bei Verwendung der <xref:System.Windows.Forms.OpenFileDialog> Komponente eine eigene Datei öffnende Logik schreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="74bc7-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>

<span data-ttu-id="74bc7-110">Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>-Methode, um das Dialogfeld zur Laufzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="74bc7-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="74bc7-111">Sie können es Benutzern ermöglichen, Dateien mit mehreren SELECT-Dateien zu öffnen, die mit der <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A>-Eigenschaft geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="74bc7-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="74bc7-112">Darüber hinaus können Sie mit der <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A>-Eigenschaft bestimmen, ob im Dialogfeld ein Schreib geschütztes Kontrollkästchen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="74bc7-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="74bc7-113">Die <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A>-Eigenschaft gibt an, ob das Kontrollkästchen Schreibgeschützt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="74bc7-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="74bc7-114">Zum Schluss legt die <xref:System.Windows.Forms.FileDialog.Filter%2A>-Eigenschaft die aktuelle Datei namens Filter Zeichenfolge fest, die die im Dialogfeld im Feld "Dateityp" angezeigten Optionen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="74bc7-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>

<span data-ttu-id="74bc7-115">Wenn Sie einem Formular hinzugefügt wird, wird die <xref:System.Windows.Forms.OpenFileDialog> Komponente in der Leiste am unteren Rand des Windows Forms-Designer in Visual Studio angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74bc7-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="74bc7-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74bc7-116">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="74bc7-117">OpenFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="74bc7-117">OpenFileDialog Component</span></span>](openfiledialog-component-windows-forms.md)
