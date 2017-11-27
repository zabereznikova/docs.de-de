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
ms.openlocfilehash: cbcbc786c19ad1af74114915b0fd0689d466fcbe
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="backgroundworker-component"></a><span data-ttu-id="421bf-102">BackgroundWorker-Komponente</span><span class="sxs-lookup"><span data-stu-id="421bf-102">BackgroundWorker Component</span></span>
<span data-ttu-id="421bf-103">Die `BackgroundWorker` ermöglicht es einem Formular oder Steuerelement einen Vorgang asynchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="421bf-103">The `BackgroundWorker` component enables your form or control to run an operation asynchronously.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="421bf-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="421bf-104">In This Section</span></span>  
 [<span data-ttu-id="421bf-105">Übersicht über die BackgroundWorker-Komponente</span><span class="sxs-lookup"><span data-stu-id="421bf-105">BackgroundWorker Component Overview</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <span data-ttu-id="421bf-106">Beschreibt die `BackgroundWorker` Komponente, die die Fähigkeit zur Ausführung von zeitaufwändiger Operations asynchron ("im Hintergrund") in einem Thread, der sich vom primären UI-Thread der Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="421bf-106">Describes the `BackgroundWorker` component, which gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span>  
  
 [<span data-ttu-id="421bf-107">Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="421bf-107">Walkthrough: Running an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 <span data-ttu-id="421bf-108">Veranschaulicht, wie die `BackgroundWorker` Komponente im Designer, um einen zeitaufwändigen Vorgang in einem separaten Thread auszuführen.</span><span class="sxs-lookup"><span data-stu-id="421bf-108">Demonstrates how to use the `BackgroundWorker` component in the designer to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="421bf-109">Gewusst wie: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="421bf-109">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="421bf-110">Veranschaulicht, wie die `BackgroundWorker` Komponente, um einen zeitaufwändigen Vorgang in einem separaten Thread auszuführen.</span><span class="sxs-lookup"><span data-stu-id="421bf-110">Demonstrates how to use the `BackgroundWorker` component to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="421bf-111">Exemplarische Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="421bf-111">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="421bf-112">Erstellt eine Anwendung mithilfe des Designers, die mathematische Berechnungen asynchron ist.</span><span class="sxs-lookup"><span data-stu-id="421bf-112">Creates an application using the designer that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="421bf-113">Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="421bf-113">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="421bf-114">Erstellt eine Anwendung, die mathematische Berechnungen asynchron ist.</span><span class="sxs-lookup"><span data-stu-id="421bf-114">Creates an application that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="421bf-115">Gewusst wie: Downloaden einer Datei im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="421bf-115">How to: Download a File in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 <span data-ttu-id="421bf-116">Veranschaulicht, wie die `BackgroundWorker` Komponente zum Herunterladen einer Datei auf einem separaten Thread.</span><span class="sxs-lookup"><span data-stu-id="421bf-116">Demonstrates how to use the `BackgroundWorker` component to download a file on a separate thread.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="421bf-117">Verweis</span><span class="sxs-lookup"><span data-stu-id="421bf-117">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="421bf-118">Beschreibt diese Klasse und enthält Links zu allen zugehörigen Membern.</span><span class="sxs-lookup"><span data-stu-id="421bf-118">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 <span data-ttu-id="421bf-119">Beschreibt den Typ, der Daten für die <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="421bf-119">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <span data-ttu-id="421bf-120">Beschreibt den Typ, der Daten für die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="421bf-120">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="421bf-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="421bf-121">Related Sections</span></span>  
 [<span data-ttu-id="421bf-122">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="421bf-122">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="421bf-123">Beschreibt, wie das asynchrone Muster die Vorteile von Multithreadanwendungen zur Verfügung und gleichzeitig viele komplexe Aspekte des Multithreaddesigns verbirgt.</span><span class="sxs-lookup"><span data-stu-id="421bf-123">Describes how the asynchronous pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>
