---
title: Erstellen von InkCanvas in Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: b8087d6db04f7024b9ee48f28002bee04045a14b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737890"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="72cb6-102">Ersten Einstieg in WPF</span><span class="sxs-lookup"><span data-stu-id="72cb6-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="72cb6-103">Windows Presentation Foundation (WPF) verfügt über eine Ink-Funktion, die das Integrieren von digitalem frei Hand Eingaben in Ihre APP erleichtert.</span><span class="sxs-lookup"><span data-stu-id="72cb6-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="72cb6-104">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="72cb6-104">Prerequisites</span></span>

<span data-ttu-id="72cb6-105">Wenn Sie die folgenden Beispiele verwenden möchten, installieren Sie zunächst [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="72cb6-105">To use the following examples, first install [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="72cb6-106">Außerdem ist es hilfreich zu wissen, wie Sie grundlegende WPF-apps schreiben können.</span><span class="sxs-lookup"><span data-stu-id="72cb6-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="72cb6-107">Hilfe zu den ersten Schritten mit WPF finden Sie unter Exemplarische Vorgehensweise [: meine erste WPF-Desktop Anwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="72cb6-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="72cb6-108">-Schnelleinstieg</span><span class="sxs-lookup"><span data-stu-id="72cb6-108">Quick Start</span></span>

<span data-ttu-id="72cb6-109">Dieser Abschnitt unterstützt Sie beim Schreiben einer einfachen WPF-Anwendung, die frei Hand Eingaben sammelt.</span><span class="sxs-lookup"><span data-stu-id="72cb6-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="72cb6-110">Sie haben Freihand?</span><span class="sxs-lookup"><span data-stu-id="72cb6-110">Got Ink?</span></span>

<span data-ttu-id="72cb6-111">So erstellen Sie eine WPF-App, die frei Hand Eingaben unterstützt</span><span class="sxs-lookup"><span data-stu-id="72cb6-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="72cb6-112">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="72cb6-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="72cb6-113">Erstellen Sie eine neue **WPF-App**.</span><span class="sxs-lookup"><span data-stu-id="72cb6-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="72cb6-114">Erweitern Sie im Dialogfeld **Neues Projekt** die Kategorie **installierter** >  **C# Visual** oder **Visual Basic** > **Windows-Desktop** .</span><span class="sxs-lookup"><span data-stu-id="72cb6-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="72cb6-115">Wählen Sie dann die APP-Vorlage **WPF-App (.NET Framework)** aus.</span><span class="sxs-lookup"><span data-stu-id="72cb6-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="72cb6-116">Geben Sie einen Namen ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="72cb6-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="72cb6-117">Visual Studio erstellt das Projekt, und *MainWindow. XAML* wird im Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="72cb6-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="72cb6-118">Geben Sie `<InkCanvas/>` zwischen den `<Grid>`-Tags ein.</span><span class="sxs-lookup"><span data-stu-id="72cb6-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![XAML-Designer mit InkCanvas-Tag](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="72cb6-120">Drücken Sie **F5** , um die Anwendung im Debugger zu starten.</span><span class="sxs-lookup"><span data-stu-id="72cb6-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="72cb6-121">Schreiben Sie mit einem **Tablettstift** oder einer Maus im Fenster "Hello World".</span><span class="sxs-lookup"><span data-stu-id="72cb6-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="72cb6-122">Sie haben die Ink-Entsprechung einer "Hello World"-Anwendung mit nur 12 Keystrokes geschrieben!</span><span class="sxs-lookup"><span data-stu-id="72cb6-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="72cb6-123">Hochskalieren der APP</span><span class="sxs-lookup"><span data-stu-id="72cb6-123">Spice Up Your App</span></span>

<span data-ttu-id="72cb6-124">Wir nutzen einige Features von WPF.</span><span class="sxs-lookup"><span data-stu-id="72cb6-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="72cb6-125">Ersetzen Sie alles zwischen dem öffnenden und dem schließenden \<Fenster > Tags durch das folgende Markup:</span><span class="sxs-lookup"><span data-stu-id="72cb6-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

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

<span data-ttu-id="72cb6-126">Dieser XAML-Code erstellt einen Hintergrund für den Farbverlaufs Pinsel auf der Eingangs Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="72cb6-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![Farbverlaufs Farben auf der Erstellungs Oberfläche in der WPF-App](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="72cb6-128">Code hinter dem XAML hinzufügen</span><span class="sxs-lookup"><span data-stu-id="72cb6-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="72cb6-129">Obwohl XAML das Entwerfen der Benutzeroberfläche vereinfacht, muss jede reale Anwendung Code zum Behandeln von Ereignissen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="72cb6-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="72cb6-130">Im folgenden finden Sie ein einfaches Beispiel, das als Reaktion auf einen Rechtsklick mit der Maus auf die frei Hand Eingabe zoomt.</span><span class="sxs-lookup"><span data-stu-id="72cb6-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="72cb6-131">Legen Sie den `MouseRightButtonUp` Handler in Ihrem XAML-Code fest:</span><span class="sxs-lookup"><span data-stu-id="72cb6-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="72cb6-132">Erweitern Sie in **Projektmappen-Explorer**den Eintrag MainWindow. XAML, und öffnen Sie die Code Behind-Datei (MainWindow.XAML.cs oder MainWindow. XAML. vb).</span><span class="sxs-lookup"><span data-stu-id="72cb6-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="72cb6-133">Fügen Sie den folgenden Ereignishandlercode hinzu:</span><span class="sxs-lookup"><span data-stu-id="72cb6-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="72cb6-134">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="72cb6-134">Run the application.</span></span> <span data-ttu-id="72cb6-135">Fügen Sie frei Hand Eingaben hinzu, klicken Sie dann mit der rechten Maustaste auf die Maus, oder führen Sie eine Press-and-Hold-Entsprechung mit einem Tablettstift</span><span class="sxs-lookup"><span data-stu-id="72cb6-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="72cb6-136">Wenn Sie mit der rechten Maustaste klicken, wird die Anzeige vergrößert.</span><span class="sxs-lookup"><span data-stu-id="72cb6-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="72cb6-137">Verwenden von prozeduralem Code anstelle von XAML</span><span class="sxs-lookup"><span data-stu-id="72cb6-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="72cb6-138">Sie können auf alle WPF-Funktionen über prozeduralen Code zugreifen.</span><span class="sxs-lookup"><span data-stu-id="72cb6-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="72cb6-139">Führen Sie die folgenden Schritte aus, um eine "Hello Ink World"-Anwendung für WPF zu erstellen, die überhaupt kein XAML verwendet.</span><span class="sxs-lookup"><span data-stu-id="72cb6-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="72cb6-140">Erstellen Sie in Visual Studio ein neues Konsolen Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="72cb6-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="72cb6-141">Erweitern Sie im Dialogfeld **Neues Projekt** die Kategorie **installierter** >  **C# Visual** oder **Visual Basic** > **Windows-Desktop** .</span><span class="sxs-lookup"><span data-stu-id="72cb6-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="72cb6-142">Wählen Sie dann die APP-Vorlage für **Konsolen-app (.NET Framework)** aus.</span><span class="sxs-lookup"><span data-stu-id="72cb6-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="72cb6-143">Geben Sie einen Namen ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="72cb6-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="72cb6-144">Fügen Sie den folgenden Code in die Datei Program.cs oder Program. vb ein:</span><span class="sxs-lookup"><span data-stu-id="72cb6-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="72cb6-145">Fügen Sie Verweise auf die Assemblys PresentationCore, presentationframework und WindowsBase hinzu, indem Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **Verweise** klicken und **Verweis hinzufügen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="72cb6-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![Verweis-Manager mit "PresentationCore" und "PresentationFramework"](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. <span data-ttu-id="72cb6-147">Erstellen Sie die Anwendung, indem Sie **F5**drücken.</span><span class="sxs-lookup"><span data-stu-id="72cb6-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="72cb6-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72cb6-148">See also</span></span>

- [<span data-ttu-id="72cb6-149">Freihandeingaben</span><span class="sxs-lookup"><span data-stu-id="72cb6-149">Digital Ink</span></span>](digital-ink.md)
- [<span data-ttu-id="72cb6-150">Erfassen von Freihandeingaben</span><span class="sxs-lookup"><span data-stu-id="72cb6-150">Collecting Ink</span></span>](collecting-ink.md)
- [<span data-ttu-id="72cb6-151">Schrifterkennung</span><span class="sxs-lookup"><span data-stu-id="72cb6-151">Handwriting Recognition</span></span>](handwriting-recognition.md)
- [<span data-ttu-id="72cb6-152">Speichern von Eingabehilfen</span><span class="sxs-lookup"><span data-stu-id="72cb6-152">Storing Ink</span></span>](storing-ink.md)
