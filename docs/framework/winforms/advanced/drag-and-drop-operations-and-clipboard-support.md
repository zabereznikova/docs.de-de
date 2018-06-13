---
title: Drag & Drop-Operationen und Unterstützung der Zwischenablage
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms]
- drag and drop [Windows Forms], Windows Forms
- Clipboard [Windows Forms], Windows Forms
ms.assetid: 7cce79b6-5835-46fd-b690-73f12ad368b2
ms.openlocfilehash: 05cc79abdeb41cd3bfb7db21ebb206eb309ad5d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522571"
---
# <a name="drag-and-drop-operations-and-clipboard-support"></a><span data-ttu-id="cf215-102">Drag & Drop-Operationen und Unterstützung der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="cf215-102">Drag-and-Drop Operations and Clipboard Support</span></span>
<span data-ttu-id="cf215-103">Sie können Drag & Drop-Operationen für Benutzer innerhalb einer Windows-basierten Anwendung aktivieren, indem Sie eine Reihe von Ereignissen, insbesondere die Ereignisse <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> und <xref:System.Windows.Forms.Control.DragDrop>, entsprechend handhaben.</span><span class="sxs-lookup"><span data-stu-id="cf215-103">You can enable user drag-and-drop operations within a Windows-based application by handling a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
 <span data-ttu-id="cf215-104">Mithilfe einfacher Methodenaufrufe können Sie auch die Unterstützung für das Ausschneiden, Kopieren und Einfügen durch die Benutzer sowie die Übertragung von Benutzerdaten in die Zwischenablage in den Windows-basierten Anwendungen implementieren.</span><span class="sxs-lookup"><span data-stu-id="cf215-104">You can also implement user cut/copy/paste support and user data transfer to the Clipboard within your Windows-based applications by using simple method calls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf215-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cf215-105">In This Section</span></span>  
 [<span data-ttu-id="cf215-106">Exemplarische Vorgehensweise: Ausführen von Drag & Drop-Operationen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf215-106">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)  
 <span data-ttu-id="cf215-107">Erläutert das Starten einer Drag & Drop-Operation.</span><span class="sxs-lookup"><span data-stu-id="cf215-107">Explains how to start a drag-and-drop operation.</span></span>  
  
 [<span data-ttu-id="cf215-108">Gewusst wie: Ausführen von Drag & Drop-Operationen zwischen Anwendungen</span><span class="sxs-lookup"><span data-stu-id="cf215-108">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](../../../../docs/framework/winforms/advanced/how-to-perform-drag-and-drop-operations-between-applications.md)  
 <span data-ttu-id="cf215-109">Veranschaulicht die Ausführung von Drag & Drop-Operationen zwischen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="cf215-109">Illustrates how to accomplish drag-and-drop operations across applications.</span></span>  
  
 [<span data-ttu-id="cf215-110">Gewusst wie: Hinzufügen von Daten zur Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="cf215-110">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 <span data-ttu-id="cf215-111">Beschreibt ein Verfahren zum programmgesteuerten Einfügen von Daten in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="cf215-111">Describes a way to programmatically insert information on the Clipboard.</span></span>  
  
 [<span data-ttu-id="cf215-112">Gewusst wie: Abrufen von Daten aus der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="cf215-112">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 <span data-ttu-id="cf215-113">Beschreibt Zugriffsmöglichkeiten auf in der Zwischenablage gespeicherte Daten. </span><span class="sxs-lookup"><span data-stu-id="cf215-113">Describes how to access the data stored on the Clipboard.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cf215-114">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="cf215-114">Related Sections</span></span>  
 [<span data-ttu-id="cf215-115">Drag & Drop-Funktionen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf215-115">Drag-and-Drop Functionality in Windows Forms</span></span>](../../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)  
 <span data-ttu-id="cf215-116">Beschreibt die Methoden, Ereignisse und Klassen, die zur Implementierung des Drag & Drop-Verhaltens verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf215-116">Describes the methods, events, and classes used to implement drag-and-drop behavior.</span></span>  
  
 <xref:System.Windows.Forms.Control.QueryContinueDrag>  
 <span data-ttu-id="cf215-117">Beschreibt die Komplexität des Ereignisses, das die Fortsetzung des Ziehvorgangs beantragt.</span><span class="sxs-lookup"><span data-stu-id="cf215-117">Describes the intricacies of the event that asks permission to continue the drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Control.DoDragDrop%2A>  
 <span data-ttu-id="cf215-118">Beschreibt die Komplexität der Methode, die für das Starten des Ziehvorgangs von zentraler Bedeutung ist. </span><span class="sxs-lookup"><span data-stu-id="cf215-118">Describes the intricacies of the method that is central to beginning a drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Clipboard>  
 <span data-ttu-id="cf215-119">Siehe auch [wie: Senden von Daten an das aktive untergeordnete MDI-Fenster](http://msdn.microsoft.com/library/y0hkh2c8\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="cf215-119">Also see [How to: Send Data to the Active MDI Child](http://msdn.microsoft.com/library/y0hkh2c8\(v=vs.110\)).</span></span>
