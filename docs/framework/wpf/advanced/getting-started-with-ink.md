---
title: Erstellen Sie ein InkCanvas-Steuerelement in einer WPF-app in Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: 600d8528125606c6e1af5b031e2fc31aabb79206
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925043"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="6111c-102">Erste Schritte mit Freihandeingaben in WPF</span><span class="sxs-lookup"><span data-stu-id="6111c-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="6111c-103">Windows Presentation Foundation (WPF) ist ein Freihand-Feature, das es einfach macht, Freihandeingaben in Ihre app zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="6111c-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6111c-104">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="6111c-104">Prerequisites</span></span>

<span data-ttu-id="6111c-105">Verwenden Sie die folgenden Beispielen wird zuerst [installieren Sie Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="6111c-105">To use the following examples, first [install Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span></span> <span data-ttu-id="6111c-106">Außerdem können wissen, wie Sie einfache WPF-apps zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="6111c-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="6111c-107">Erste Schritte mit WPF Hilfe finden Sie [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="6111c-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="6111c-108">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="6111c-108">Quick Start</span></span>

<span data-ttu-id="6111c-109">In diesem Abschnitt können Sie eine einfache WPF-Anwendung zu schreiben, die Freihandeingaben erfasst.</span><span class="sxs-lookup"><span data-stu-id="6111c-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="6111c-110">Erfasst Freihandeingabe?</span><span class="sxs-lookup"><span data-stu-id="6111c-110">Got Ink?</span></span>

<span data-ttu-id="6111c-111">Zum Erstellen einer WPF-app, die Freihandeingaben unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6111c-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="6111c-112">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6111c-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="6111c-113">Erstellen Sie ein neues **WPF-App**.</span><span class="sxs-lookup"><span data-stu-id="6111c-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="6111c-114">In der **neues Projekt** Dialogfeld erweitern Sie die **installiert** > **Visual C#-** oder **Visual Basic**  >   **Windows-Desktop** Kategorie.</span><span class="sxs-lookup"><span data-stu-id="6111c-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="6111c-115">Wählen Sie dann die **WPF-App ((.NET Framework)** -app-Vorlage.</span><span class="sxs-lookup"><span data-stu-id="6111c-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="6111c-116">Geben Sie einen Namen ein, und wählen Sie dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="6111c-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="6111c-117">Visual Studio erstellt das Projekt, und *"MainWindow.xaml"* im Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6111c-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="6111c-118">Typ `<InkCanvas/>` zwischen der `<Grid>` Tags.</span><span class="sxs-lookup"><span data-stu-id="6111c-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![XAML-Designer mit InkCanvas-Steuerelement-tag](media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="6111c-120">Drücken Sie **F5** auf die Anwendung im Debugger zu starten.</span><span class="sxs-lookup"><span data-stu-id="6111c-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="6111c-121">Schreiben Sie mit einem Stift oder der Maus **Hallo Welt** im Fenster.</span><span class="sxs-lookup"><span data-stu-id="6111c-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="6111c-122">Sie haben die Freihand-Entsprechung einer "Hello World"-Anwendung mit nur 12 Tastatureingaben geschrieben.</span><span class="sxs-lookup"><span data-stu-id="6111c-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="6111c-123">Darstellungsschichten interessanter zu gestalten Sie Ihre App</span><span class="sxs-lookup"><span data-stu-id="6111c-123">Spice Up Your App</span></span>

<span data-ttu-id="6111c-124">Lassen Sie uns einige Funktionen von WPF nutzen.</span><span class="sxs-lookup"><span data-stu-id="6111c-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="6111c-125">Ersetzen Sie alles zwischen den öffnenden und schließenden \<Fenster >-Tags mit folgendem Markup:</span><span class="sxs-lookup"><span data-stu-id="6111c-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

<span data-ttu-id="6111c-126">Dieses XAML erstellt einen Farbverlaufspinsel-Hintergrund für die Freihandoberfläche.</span><span class="sxs-lookup"><span data-stu-id="6111c-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![Verlaufsfarben auf Freihand-Oberfläche in WPF-app](media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="6111c-128">Hinzufügen von Code hinter der XAML</span><span class="sxs-lookup"><span data-stu-id="6111c-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="6111c-129">Während der XAML sehr Entwerfen der Benutzeroberfläche erleichtert, muss jeder reale Anwendung Code hinzufügen, um Ereignisse zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="6111c-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="6111c-130">Hier ist ein einfaches Beispiel, das auf die Freihandeingabe in Reaktion auf eine mit der rechten Maustaste in eine Maus vergrößert.</span><span class="sxs-lookup"><span data-stu-id="6111c-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="6111c-131">Legen Sie die `MouseRightButtonUp` Ereignishandler in Ihrem XAML:</span><span class="sxs-lookup"><span data-stu-id="6111c-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="6111c-132">In **Projektmappen-Explorer**, erweitern Sie "MainWindow.xaml", und öffnen Sie die CodeBehind-Datei ("MainWindow.Xaml.cs" oder "MainWindow.Xaml.vb").</span><span class="sxs-lookup"><span data-stu-id="6111c-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="6111c-133">Fügen Sie den folgenden Ereignishandlercode hinzu:</span><span class="sxs-lookup"><span data-stu-id="6111c-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="6111c-134">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="6111c-134">Run the application.</span></span> <span data-ttu-id="6111c-135">Einige Freihandeingaben, und klicken Sie dann mit der rechten Maustaste, oder führen Sie ein Äquivalent drücken und halten mit einem Stift.</span><span class="sxs-lookup"><span data-stu-id="6111c-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="6111c-136">Die Anzeige vergrößert jedes Mal, wenn Sie mit der rechten Maustaste klicken.</span><span class="sxs-lookup"><span data-stu-id="6111c-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="6111c-137">Prozeduralen Code statt XAML verwenden</span><span class="sxs-lookup"><span data-stu-id="6111c-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="6111c-138">Sie können alle WPF-Funktionen aus prozeduralen Code zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6111c-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="6111c-139">Um eine "Hello Freihand-World"-Anwendung für WPF erstellen, die alle XAML überhaupt nicht verwendet, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="6111c-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="6111c-140">Erstellen Sie ein neues Konsolenanwendungsprojekt in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6111c-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="6111c-141">In der **neues Projekt** Dialogfeld erweitern Sie die **installiert** > **Visual C#-** oder **Visual Basic**  >   **Windows-Desktop** Kategorie.</span><span class="sxs-lookup"><span data-stu-id="6111c-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="6111c-142">Wählen Sie dann die **Konsolen-App ((.NET Framework)** -app-Vorlage.</span><span class="sxs-lookup"><span data-stu-id="6111c-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="6111c-143">Geben Sie einen Namen ein, und wählen Sie dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="6111c-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="6111c-144">Fügen Sie den folgenden Code in der Datei Program.cs oder Program.vb-Datei ein:</span><span class="sxs-lookup"><span data-stu-id="6111c-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="6111c-145">Fügen Sie Verweise auf die Assemblys PresentationCore, PresentationFramework und WindowsBase hinzu, indem Sie mit der rechten Maustaste auf **Verweise** in **Projektmappen-Explorer** und **VerweisHinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6111c-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![Verweis-Manager angezeigt wird, PresentationCore und PresentationFramework getrennt](media/getting-started-with-ink/references.png)

1. <span data-ttu-id="6111c-147">Erstellen Sie die Anwendung durch Drücken von **F5**.</span><span class="sxs-lookup"><span data-stu-id="6111c-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6111c-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6111c-148">See Also</span></span>

- [<span data-ttu-id="6111c-149">Freihandeingaben</span><span class="sxs-lookup"><span data-stu-id="6111c-149">Digital Ink</span></span>](../../../../docs/framework/wpf/advanced/digital-ink.md)
- [<span data-ttu-id="6111c-150">Erfassen von Freihandeingaben</span><span class="sxs-lookup"><span data-stu-id="6111c-150">Collecting Ink</span></span>](../../../../docs/framework/wpf/advanced/collecting-ink.md)
- [<span data-ttu-id="6111c-151">Schrifterkennung</span><span class="sxs-lookup"><span data-stu-id="6111c-151">Handwriting Recognition</span></span>](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)
- [<span data-ttu-id="6111c-152">Speichern von Eingabehilfen</span><span class="sxs-lookup"><span data-stu-id="6111c-152">Storing Ink</span></span>](../../../../docs/framework/wpf/advanced/storing-ink.md)
