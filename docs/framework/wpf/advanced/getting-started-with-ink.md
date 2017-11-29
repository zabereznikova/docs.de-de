---
title: Erste Schritte mit Freihandeingaben
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- gradient brush [WPF], animating colors of
- XAML [WPF], procedural code in lieu of
- animation [WPF], gradient brush colors
- brushes [WPF], animating colors of
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dc8ffe9ad68060d9dfbcafe99133a736237a2bb3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="getting-started-with-ink"></a><span data-ttu-id="c12f9-102">Erste Schritte mit Freihandeingaben</span><span class="sxs-lookup"><span data-stu-id="c12f9-102">Getting Started with Ink</span></span>
<span data-ttu-id="c12f9-103">Freihandeingaben in Ihre Anwendungen integrieren ist einfacher als je zuvor.</span><span class="sxs-lookup"><span data-stu-id="c12f9-103">Incorporating digital ink into your applications is easier than ever.</span></span> <span data-ttu-id="c12f9-104">Freihandeingaben wurden von wird eine begleitende COM und Windows Forms-Methode der Programmierung zum Erzielen einer vollständige Integration in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c12f9-104">Ink has evolved from being a corollary to the COM and Windows Forms method of programming to achieving full integration into the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="c12f9-105">Sie müssen keine separaten SDKs oder Laufzeitbibliotheken installieren.</span><span class="sxs-lookup"><span data-stu-id="c12f9-105">You do not need to install separate SDKs or runtime libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c12f9-106">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="c12f9-106">Prerequisites</span></span>  
 <span data-ttu-id="c12f9-107">Um die folgenden Beispiele verwenden zu können, müssen Sie zuerst Microsoft Visual Studio 2005 installieren und die [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c12f9-107">To use the following examples, you must first install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="c12f9-108">Sie sollten außerdem mit dem Schreiben von Anwendungen für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="c12f9-108">You should also understand how to write applications for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="c12f9-109">Weitere Informationen zu den ersten Schritten mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="c12f9-109">For more information about getting started with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="quick-start"></a><span data-ttu-id="c12f9-110">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="c12f9-110">Quick Start</span></span>  
 <span data-ttu-id="c12f9-111">Dieser Abschnitt hilft Ihnen das Schreiben einer einfachen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung, die Freihandeingaben erfasst.</span><span class="sxs-lookup"><span data-stu-id="c12f9-111">This section helps you write a simple [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that collects ink.</span></span>  
  
 <span data-ttu-id="c12f9-112">Wenn Sie dies nicht bereits getan haben, installieren Sie Microsoft Visual Studio 2005 und den [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c12f9-112">If you haven't already done so, install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)].</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="c12f9-113">Anwendungen in der Regel müssen kompiliert werden, bevor Sie sie anzeigen können, selbst wenn sie vollständig aus bestehen aus [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c12f9-113"> applications usually must be compiled before you can view them, even if they consist entirely of [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="c12f9-114">Allerdings die [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] enthält Anwendung XamlPad, entwickelt, um den Prozess der Implementierung zu beschleunigen eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-basierte Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="c12f9-114">However, the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] includes an application, XamlPad, designed to speed up the process of implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-based UI.</span></span> <span data-ttu-id="c12f9-115">Sie können diese Anwendung verwenden, anzeigen und Experimentieren mit der ersten einige Beispiele in diesem Dokument.</span><span class="sxs-lookup"><span data-stu-id="c12f9-115">You can use that application to view and tinker with the first few samples in this document.</span></span> <span data-ttu-id="c12f9-116">Der Prozess der Erstellung kompiliert Anwendungen aus [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird weiter unten in diesem Dokument behandelt.</span><span class="sxs-lookup"><span data-stu-id="c12f9-116">The process of creating compiled applications from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is covered later in this document.</span></span>  
  
 <span data-ttu-id="c12f9-117">Um XAMLPad zu starten, klicken Sie auf die **starten** Sie im Menü **Programme**, zeigen Sie auf **Microsoft klicken Sie Winndows SDK**, zeigen Sie auf **Tools**, und klicken Sie auf **XAMLPad**.</span><span class="sxs-lookup"><span data-stu-id="c12f9-117">To launch XAMLPad, click the **Start** menu, point to **All Programs**, point to **Microsoft Winndows SDK**, point to **Tools**, and click **XAMLPad**.</span></span> <span data-ttu-id="c12f9-118">Klicken Sie im Bereich "Wiedergabe" rendert XAMLPad den XAML-Code im Codebereich geschrieben.</span><span class="sxs-lookup"><span data-stu-id="c12f9-118">In the rendering pane, XAMLPad renders the XAML code written in the code pane.</span></span> <span data-ttu-id="c12f9-119">Sie können den XAML-Code bearbeiten und die Änderungen sofort angezeigt werden, klicken Sie im Bereich "Wiedergabe".</span><span class="sxs-lookup"><span data-stu-id="c12f9-119">You can edit the XAML code, and the changes immediately appear in the rendering pane.</span></span>  
  
#### <a name="got-ink"></a><span data-ttu-id="c12f9-120">Erfasst Freihandeingabe?</span><span class="sxs-lookup"><span data-stu-id="c12f9-120">Got Ink?</span></span>  
 <span data-ttu-id="c12f9-121">Starten Sie Ihre erste [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung, die Freihandeingaben unterstützt:</span><span class="sxs-lookup"><span data-stu-id="c12f9-121">To start your first [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that supports ink:</span></span>  
  
1.  <span data-ttu-id="c12f9-122">Öffnen Sie Microsoft Visual Studio 2005</span><span class="sxs-lookup"><span data-stu-id="c12f9-122">Open Microsoft Visual Studio 2005</span></span>  
  
2.  <span data-ttu-id="c12f9-123">Erstellen Sie ein neues **Windows-Anwendung (WPF)**</span><span class="sxs-lookup"><span data-stu-id="c12f9-123">Create a new **Windows Application (WPF)**</span></span>  
  
3.  <span data-ttu-id="c12f9-124">Typ `<InkCanvas/>` zwischen den `<Grid>` Tags</span><span class="sxs-lookup"><span data-stu-id="c12f9-124">Type `<InkCanvas/>` between the `<Grid>` tags</span></span>  
  
4.  <span data-ttu-id="c12f9-125">Drücken Sie **F5** um Ihre Anwendung im Debugger zu starten.</span><span class="sxs-lookup"><span data-stu-id="c12f9-125">Press **F5** to launch your application in the debugger</span></span>  
  
5.  <span data-ttu-id="c12f9-126">Schreiben Sie mit einem Stift oder die Maus **Hello World** im Fenster</span><span class="sxs-lookup"><span data-stu-id="c12f9-126">Using a stylus or mouse, write **hello world** in the window</span></span>  
  
 <span data-ttu-id="c12f9-127">Sie haben die Freihand-Entsprechung einer Anwendung "Hello World" mit nur 12 Tastatureingaben geschrieben.</span><span class="sxs-lookup"><span data-stu-id="c12f9-127">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>  
  
#### <a name="spice-up-your-application"></a><span data-ttu-id="c12f9-128">Interessanter gestalten Sie Ihre Anwendung</span><span class="sxs-lookup"><span data-stu-id="c12f9-128">Spice Up Your Application</span></span>  
 <span data-ttu-id="c12f9-129">Nehmen wir einige Funktionen von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c12f9-129">Let’s take advantage of some features of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  <span data-ttu-id="c12f9-130">Ersetzen Sie alles zwischen das öffnende \<Fenster > und Schließen von \</Window > RFID-Transponder durch Folgendes Markup einen Hintergrund eines Farbverlaufspinsels auf die Oberfläche des Freihand abgerufen.</span><span class="sxs-lookup"><span data-stu-id="c12f9-130">Replace everything between the opening \<Window> and closing \</Window> tags with the following markup to get a gradient brush background on your inking surface.</span></span>  
  
 [!code-xaml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xaml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### <a name="using-animation"></a><span data-ttu-id="c12f9-131">Verwenden von Animationen</span><span class="sxs-lookup"><span data-stu-id="c12f9-131">Using Animation</span></span>  
 <span data-ttu-id="c12f9-132">Animieren Sie für unterhaltsamer wir die Farben des Farbverlaufs.</span><span class="sxs-lookup"><span data-stu-id="c12f9-132">For fun, let's animate the colors of the gradient brush.</span></span> <span data-ttu-id="c12f9-133">Fügen Sie die folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nach dem schließenden `</InkCanvas>` Tag, aber vor der schließenden `</Page>` Tag.</span><span class="sxs-lookup"><span data-stu-id="c12f9-133">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] after the closing `</InkCanvas>` tag but before the closing `</Page>` tag.</span></span>  
  
 [!code-xaml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### <a name="adding-some-code-behind-the-xaml"></a><span data-ttu-id="c12f9-134">Hinzufügen von Code hinter der XAML-Code</span><span class="sxs-lookup"><span data-stu-id="c12f9-134">Adding Some Code Behind the XAML</span></span>  
 <span data-ttu-id="c12f9-135">Während XAML sehr Entwerfen der Benutzeroberfläche erleichtert, muss jede praktische Anwendung Code hinzufügen, um Ereignisse zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="c12f9-135">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="c12f9-136">Hier ist ein einfaches Beispiel, das die Freihandeingabe Reaktion auf einen Rechtsklick aus einer Maus vergrößert ein:</span><span class="sxs-lookup"><span data-stu-id="c12f9-136">Here is a simple example that zooms in on the ink in response to a right-click from a mouse:</span></span>  
  
 <span data-ttu-id="c12f9-137">Legen Sie die `MouseRightButtonUp` Ereignishandler in Ihrem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c12f9-137">Set the `MouseRightButtonUp` handler in your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span></span>  
  
 [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 <span data-ttu-id="c12f9-138">Klicken Sie im Projektmappen-Explorer von Visual Studio erweitern Sie Windows1.XAML im, und öffnen Sie die Code-Behind-Datei Window1.xaml.cs oder Window1.xaml.vb bei Verwendung von Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c12f9-138">In Visual Studio’s Solution Explorer, expand Windows1.xaml and open the code-behind file, Window1.xaml.cs or Window1.xaml.vb if you are using Visual Basic.</span></span> <span data-ttu-id="c12f9-139">Fügen Sie den folgenden Ereignishandlercode hinzu:</span><span class="sxs-lookup"><span data-stu-id="c12f9-139">Add the following event handler code:</span></span>  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 <span data-ttu-id="c12f9-140">Führen Sie nun Ihre Anwendung ein.</span><span class="sxs-lookup"><span data-stu-id="c12f9-140">Now, run your application.</span></span> <span data-ttu-id="c12f9-141">Einige Freihandeingaben und mit der rechten Maustaste, oder eine Entsprechung von drücken und halten Sie mit einen Tablettstift ausführen.</span><span class="sxs-lookup"><span data-stu-id="c12f9-141">Add some ink and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>  
  
#### <a name="using-procedural-code-instead-of-xaml"></a><span data-ttu-id="c12f9-142">Unter Verwendung prozeduralen Codes anstelle von XAML</span><span class="sxs-lookup"><span data-stu-id="c12f9-142">Using Procedural Code Instead of XAML</span></span>  
 <span data-ttu-id="c12f9-143">Sie können Zugriff auf alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Funktionen von prozeduralem Code.</span><span class="sxs-lookup"><span data-stu-id="c12f9-143">You can access all [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] features from procedural code.</span></span> <span data-ttu-id="c12f9-144">Hier ist eine "Hello Freihand-World"-Anwendung für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet, die keine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] überhaupt.</span><span class="sxs-lookup"><span data-stu-id="c12f9-144">Here is a "Hello Ink World" application for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] that doesn’t use any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] at all.</span></span> <span data-ttu-id="c12f9-145">Fügen Sie den folgenden Code in eine leere-Konsolenanwendung in Visual Studio aus.</span><span class="sxs-lookup"><span data-stu-id="c12f9-145">Paste the code below into an empty Console Application in Visual Studio.</span></span> <span data-ttu-id="c12f9-146">Fügen Sie Verweise auf die Assemblys PresentationCore, PresentationFramework und WindowsBase hinzu, und erstellen Sie die Anwendung durch Drücken von **F5**:</span><span class="sxs-lookup"><span data-stu-id="c12f9-146">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies, and build the application by pressing **F5**:</span></span>  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c12f9-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c12f9-147">See Also</span></span>  
 [<span data-ttu-id="c12f9-148">Freihandeingaben</span><span class="sxs-lookup"><span data-stu-id="c12f9-148">Digital Ink</span></span>](../../../../docs/framework/wpf/advanced/digital-ink.md)  
 [<span data-ttu-id="c12f9-149">Erfassen von Freihandeingaben</span><span class="sxs-lookup"><span data-stu-id="c12f9-149">Collecting Ink</span></span>](../../../../docs/framework/wpf/advanced/collecting-ink.md)  
 [<span data-ttu-id="c12f9-150">Schrifterkennung</span><span class="sxs-lookup"><span data-stu-id="c12f9-150">Handwriting Recognition</span></span>](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)  
 [<span data-ttu-id="c12f9-151">Speichern von Eingabehilfen</span><span class="sxs-lookup"><span data-stu-id="c12f9-151">Storing Ink</span></span>](../../../../docs/framework/wpf/advanced/storing-ink.md)
