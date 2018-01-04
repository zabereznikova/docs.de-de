---
title: BackgroundWorker-Komponente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6d83ff69053a71626d0bf9a844d9e94235080d78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="backgroundworker-component"></a><span data-ttu-id="f57a7-102">BackgroundWorker-Komponente</span><span class="sxs-lookup"><span data-stu-id="f57a7-102">BackgroundWorker Component</span></span>
<span data-ttu-id="f57a7-103">Die `BackgroundWorker` ermöglicht es einem Formular oder Steuerelement einen Vorgang asynchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f57a7-103">The `BackgroundWorker` component enables your form or control to run an operation asynchronously.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f57a7-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f57a7-104">In This Section</span></span>  
 [<span data-ttu-id="f57a7-105">Übersicht über die BackgroundWorker-Komponente</span><span class="sxs-lookup"><span data-stu-id="f57a7-105">BackgroundWorker Component Overview</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <span data-ttu-id="f57a7-106">Beschreibt die `BackgroundWorker` Komponente, die die Fähigkeit zur Ausführung von zeitaufwändiger Operations asynchron ("im Hintergrund") in einem Thread, der sich vom primären UI-Thread der Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="f57a7-106">Describes the `BackgroundWorker` component, which gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span>  
  
 [<span data-ttu-id="f57a7-107">Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="f57a7-107">Walkthrough: Running an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 <span data-ttu-id="f57a7-108">Veranschaulicht, wie die `BackgroundWorker` Komponente im Designer, um einen zeitaufwändigen Vorgang in einem separaten Thread auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f57a7-108">Demonstrates how to use the `BackgroundWorker` component in the designer to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="f57a7-109">Gewusst wie: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="f57a7-109">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="f57a7-110">Veranschaulicht, wie die `BackgroundWorker` Komponente, um einen zeitaufwändigen Vorgang in einem separaten Thread auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f57a7-110">Demonstrates how to use the `BackgroundWorker` component to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="f57a7-111">Exemplarische Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="f57a7-111">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="f57a7-112">Erstellt eine Anwendung mithilfe des Designers, die mathematische Berechnungen asynchron ist.</span><span class="sxs-lookup"><span data-stu-id="f57a7-112">Creates an application using the designer that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="f57a7-113">Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="f57a7-113">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="f57a7-114">Erstellt eine Anwendung, die mathematische Berechnungen asynchron ist.</span><span class="sxs-lookup"><span data-stu-id="f57a7-114">Creates an application that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="f57a7-115">Gewusst wie: Downloaden einer Datei im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="f57a7-115">How to: Download a File in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 <span data-ttu-id="f57a7-116">Veranschaulicht, wie die `BackgroundWorker` Komponente zum Herunterladen einer Datei auf einem separaten Thread.</span><span class="sxs-lookup"><span data-stu-id="f57a7-116">Demonstrates how to use the `BackgroundWorker` component to download a file on a separate thread.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f57a7-117">Verweis</span><span class="sxs-lookup"><span data-stu-id="f57a7-117">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="f57a7-118">Beschreibt diese Klasse und enthält Links zu allen zugehörigen Membern.</span><span class="sxs-lookup"><span data-stu-id="f57a7-118">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 <span data-ttu-id="f57a7-119">Beschreibt den Typ, der Daten für die <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="f57a7-119">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <span data-ttu-id="f57a7-120">Beschreibt den Typ, der Daten für die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="f57a7-120">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f57a7-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="f57a7-121">Related Sections</span></span>  
 [<span data-ttu-id="f57a7-122">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="f57a7-122">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="f57a7-123">Beschreibt, wie das asynchrone Muster die Vorteile von Multithreadanwendungen zur Verfügung und gleichzeitig viele komplexe Aspekte des Multithreaddesigns verbirgt.</span><span class="sxs-lookup"><span data-stu-id="f57a7-123">Describes how the asynchronous pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>
