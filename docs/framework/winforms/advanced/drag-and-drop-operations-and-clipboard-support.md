---
title: Drag &amp; Drop-Operationen und Unterstützung der Zwischenablage
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms]
- drag and drop [Windows Forms], Windows Forms
- Clipboard [Windows Forms], Windows Forms
ms.assetid: 7cce79b6-5835-46fd-b690-73f12ad368b2
ms.openlocfilehash: 5e7bb75b648163dab7e410a159d55ebbb75f1b0a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711745"
---
# <a name="drag-and-drop-operations-and-clipboard-support"></a><span data-ttu-id="ff663-102">Drag &amp; Drop-Operationen und Unterstützung der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="ff663-102">Drag-and-Drop Operations and Clipboard Support</span></span>
<span data-ttu-id="ff663-103">Sie können Drag &amp; Drop-Operationen für Benutzer innerhalb einer Windows-basierten Anwendung aktivieren, indem Sie eine Reihe von Ereignissen, insbesondere die Ereignisse <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> und <xref:System.Windows.Forms.Control.DragDrop>, entsprechend handhaben.</span><span class="sxs-lookup"><span data-stu-id="ff663-103">You can enable user drag-and-drop operations within a Windows-based application by handling a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
 <span data-ttu-id="ff663-104">Mithilfe einfacher Methodenaufrufe können Sie auch die Unterstützung für das Ausschneiden, Kopieren und Einfügen durch die Benutzer sowie die Übertragung von Benutzerdaten in die Zwischenablage in den Windows-basierten Anwendungen implementieren.</span><span class="sxs-lookup"><span data-stu-id="ff663-104">You can also implement user cut/copy/paste support and user data transfer to the Clipboard within your Windows-based applications by using simple method calls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff663-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ff663-105">In This Section</span></span>  
 [<span data-ttu-id="ff663-106">Exemplarische Vorgehensweise: Eine Drag & Drop-Vorgang in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff663-106">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)  
 <span data-ttu-id="ff663-107">Erläutert das Starten einer Drag &amp; Drop-Operation.</span><span class="sxs-lookup"><span data-stu-id="ff663-107">Explains how to start a drag-and-drop operation.</span></span>  
  
 [<span data-ttu-id="ff663-108">Vorgehensweise: Operationen Sie Drag & Drop-zwischen Anwendungen</span><span class="sxs-lookup"><span data-stu-id="ff663-108">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](how-to-perform-drag-and-drop-operations-between-applications.md)  
 <span data-ttu-id="ff663-109">Veranschaulicht die Ausführung von Drag &amp; Drop-Operationen zwischen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ff663-109">Illustrates how to accomplish drag-and-drop operations across applications.</span></span>  
  
 [<span data-ttu-id="ff663-110">Vorgehensweise: Hinzufügen von Daten in die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="ff663-110">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)  
 <span data-ttu-id="ff663-111">Beschreibt ein Verfahren zum programmgesteuerten Einfügen von Daten in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="ff663-111">Describes a way to programmatically insert information on the Clipboard.</span></span>  
  
 [<span data-ttu-id="ff663-112">Vorgehensweise: Abrufen von Daten aus der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="ff663-112">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)  
 <span data-ttu-id="ff663-113">Beschreibt Zugriffsmöglichkeiten auf in der Zwischenablage gespeicherte Daten. </span><span class="sxs-lookup"><span data-stu-id="ff663-113">Describes how to access the data stored on the Clipboard.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ff663-114">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ff663-114">Related Sections</span></span>  
 [<span data-ttu-id="ff663-115">Drag & Drop-Funktionen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff663-115">Drag-and-Drop Functionality in Windows Forms</span></span>](../drag-and-drop-functionality-in-windows-forms.md)  
 <span data-ttu-id="ff663-116">Beschreibt die Methoden, Ereignisse und Klassen, die zur Implementierung des Drag &amp; Drop-Verhaltens verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff663-116">Describes the methods, events, and classes used to implement drag-and-drop behavior.</span></span>  
  
 <xref:System.Windows.Forms.Control.QueryContinueDrag>  
 <span data-ttu-id="ff663-117">Beschreibt die Komplexität des Ereignisses, das die Fortsetzung des Ziehvorgangs beantragt.</span><span class="sxs-lookup"><span data-stu-id="ff663-117">Describes the intricacies of the event that asks permission to continue the drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Control.DoDragDrop%2A>  
 <span data-ttu-id="ff663-118">Beschreibt die Komplexität der Methode, die für das Starten des Ziehvorgangs von zentraler Bedeutung ist. </span><span class="sxs-lookup"><span data-stu-id="ff663-118">Describes the intricacies of the method that is central to beginning a drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Clipboard>  
 <span data-ttu-id="ff663-119">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element](how-to-send-data-to-the-active-mdi-child.md).</span><span class="sxs-lookup"><span data-stu-id="ff663-119">Also see [How to: Send Data to the Active MDI Child](how-to-send-data-to-the-active-mdi-child.md).</span></span>
