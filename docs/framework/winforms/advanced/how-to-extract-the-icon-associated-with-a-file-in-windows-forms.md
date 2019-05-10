---
title: 'Vorgehensweise: Extrahieren eines mit einer Datei verknüpften Symbols in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: c3173a3fa756a3294154217f5cf0a13dbc8721f3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645402"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="22731-102">Vorgehensweise: Extrahieren eines mit einer Datei verknüpften Symbols in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22731-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="22731-103">Viele Dateien verfügen über eingebettete Symbole, die eine visuelle Darstellung des zugeordneten Dateityps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="22731-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="22731-104">Microsoft Word-Dokumente enthalten z. B. ein Symbol, das sie als Word-Dokumenten identifiziert.</span><span class="sxs-lookup"><span data-stu-id="22731-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="22731-105">Zum Anzeigen von Dateien in einem Listensteuerelement oder Datentabellen-Steuerelement können Sie das Symbol für den Dateityp neben jedem Dateinamen anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="22731-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="22731-106">Sie können dazu einfach die <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="22731-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22731-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22731-107">Example</span></span>  
 <span data-ttu-id="22731-108">Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit einer Datei verknüpften Symbols zu extrahieren und Anzeigen der Dateiname und das zugehörige Symbol im eine <xref:System.Windows.Forms.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="22731-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="22731-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="22731-109">Compiling the Code</span></span>  
 <span data-ttu-id="22731-110">Um das Beispiel zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="22731-110">To compile the example:</span></span>  
  
- <span data-ttu-id="22731-111">Fügen Sie den vorherigen Code in einem Windows Form, und rufen die `ExtractAssociatedIconExample` Methode aus dem Konstruktor des Formulars oder <xref:System.Windows.Forms.Form.Load> Ereignisbehandlungsmethode.</span><span class="sxs-lookup"><span data-stu-id="22731-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="22731-112">Sie müssen sicherstellen, dass das Formular importiert die <xref:System.IO> Namespace.</span><span class="sxs-lookup"><span data-stu-id="22731-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22731-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22731-113">See also</span></span>

- [<span data-ttu-id="22731-114">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="22731-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="22731-115">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="22731-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
