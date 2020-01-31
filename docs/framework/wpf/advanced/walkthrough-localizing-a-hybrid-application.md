---
title: 'Exemplarische Vorgehensweise: Lokalisieren einer Hybridanwendung'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: b406d539f2446824027e9462c8ecbe20c18cfb27
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794125"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="0dd74-102">Exemplarische Vorgehensweise: Lokalisieren einer Hybridanwendung</span><span class="sxs-lookup"><span data-stu-id="0dd74-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="0dd74-103">In dieser exemplarischen Vorgehensweise wird gezeigt, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente in einer Windows Forms basierten Hybrid Anwendung lokalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0dd74-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a Windows Forms-based hybrid application.</span></span>

<span data-ttu-id="0dd74-104">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0dd74-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="0dd74-105">Das Windows Forms Host Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="0dd74-105">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="0dd74-106">Lokalisierbaren Inhalt hinzufügen</span><span class="sxs-lookup"><span data-stu-id="0dd74-106">Adding localizable content.</span></span>

- <span data-ttu-id="0dd74-107">Lokalisierungsfunktionalität aktivieren</span><span class="sxs-lookup"><span data-stu-id="0dd74-107">Enabling localization.</span></span>

- <span data-ttu-id="0dd74-108">Ressourcenbezeichner zuweisen</span><span class="sxs-lookup"><span data-stu-id="0dd74-108">Assigning resource identifiers.</span></span>

- <span data-ttu-id="0dd74-109">Verwenden des LocBaml-Tools zum Erzeugen einer Satellitenassembly.</span><span class="sxs-lookup"><span data-stu-id="0dd74-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="0dd74-110">Eine komplette Code Auflistung der Aufgaben, die in dieser exemplarischen Vorgehensweise veranschaulicht werden, finden Sie unter Beispiel für das [Lokalisieren einer Hybrid Anwendung](https://go.microsoft.com/fwlink/?LinkID=160015).</span><span class="sxs-lookup"><span data-stu-id="0dd74-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="0dd74-111">Am Ende werden Sie eine lokalisierte Hybridanwendung haben.</span><span class="sxs-lookup"><span data-stu-id="0dd74-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0dd74-112">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="0dd74-112">Prerequisites</span></span>

<span data-ttu-id="0dd74-113">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="0dd74-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="0dd74-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0dd74-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="0dd74-115">Erstellen des Windows Forms-Hostprojekts</span><span class="sxs-lookup"><span data-stu-id="0dd74-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="0dd74-116">Der erste Schritt besteht darin, das Windows Forms Anwendungsprojekt zu erstellen und ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element mit Inhalt hinzuzufügen, den Sie lokalisieren werden.</span><span class="sxs-lookup"><span data-stu-id="0dd74-116">The first step is to create the Windows Forms application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="0dd74-117">So erstellen Sie das Hostprojekt</span><span class="sxs-lookup"><span data-stu-id="0dd74-117">To create the host project</span></span>

1. <span data-ttu-id="0dd74-118">Erstellen Sie ein **WPF-App** -Projekt mit dem Namen `LocalizingWpfInWf`.</span><span class="sxs-lookup"><span data-stu-id="0dd74-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="0dd74-119">(**Datei** > **neue** > **Projekt** > **Visual C#**  oder **Visual Basic** > **klassische Desktop** > **WPF-Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="0dd74-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="0dd74-120">Fügen Sie dem Projekt eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> Element mit dem Namen `SimpleControl` hinzu.</span><span class="sxs-lookup"><span data-stu-id="0dd74-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="0dd74-121">Verwenden Sie das <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement, um ein `SimpleControl` Element im Formular zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="0dd74-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="0dd74-122">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Hosting eines zusammengesetzten 3D-WPF-Steuer Elements in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0dd74-122">For more information, see [Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="0dd74-123">Hinzufügen von lokalisierbarem Inhalt</span><span class="sxs-lookup"><span data-stu-id="0dd74-123">Adding Localizable Content</span></span>

<span data-ttu-id="0dd74-124">Fügen Sie als nächstes ein Windows Forms Label-Steuerelement hinzu, und legen Sie den Inhalt des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elements auf eine lokalisierbare Zeichenfolge fest.</span><span class="sxs-lookup"><span data-stu-id="0dd74-124">Next, you will add a Windows Forms label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="0dd74-125">So fügen Sie lokalisierbaren Inhalt hinzu</span><span class="sxs-lookup"><span data-stu-id="0dd74-125">To add localizable content</span></span>

1. <span data-ttu-id="0dd74-126">Doppelklicken Sie in **Projektmappen-Explorer**auf **SimpleControl. XAML** , um es im WPF-Designer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0dd74-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the WPF Designer.</span></span>

2. <span data-ttu-id="0dd74-127">Legen Sie den Inhalt des Steuer Elements <xref:System.Windows.Controls.Button> mithilfe des folgenden Codes fest.</span><span class="sxs-lookup"><span data-stu-id="0dd74-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="0dd74-128">Doppelklicken Sie in **Projektmappen-Explorer**auf **Form1** , um es im Windows Forms-Designer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0dd74-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="0dd74-129">Öffnen Sie die **Toolbox** , und doppelklicken Sie auf **Bezeichnung** , um dem Formular ein Label-Steuerelement hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0dd74-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="0dd74-130">Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft auf `"Hello"` fest.</span><span class="sxs-lookup"><span data-stu-id="0dd74-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="0dd74-131">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0dd74-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="0dd74-132">Sowohl das `SimpleControl`-Element als auch das Label-Steuerelement zeigen den Text **"Hello"** an.</span><span class="sxs-lookup"><span data-stu-id="0dd74-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="0dd74-133">Aktivieren der Lokalisierungsfunktionalität</span><span class="sxs-lookup"><span data-stu-id="0dd74-133">Enabling Localization</span></span>

<span data-ttu-id="0dd74-134">Windows Forms-Designer bietet Einstellungen für das Aktivieren der Lokalisierungsfunktionalität in einer Satellitenassembly.</span><span class="sxs-lookup"><span data-stu-id="0dd74-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="0dd74-135">So aktivieren Sie die Lokalisierungsfunktionalität</span><span class="sxs-lookup"><span data-stu-id="0dd74-135">To enable localization</span></span>

1. <span data-ttu-id="0dd74-136">Doppelklicken Sie in **Projektmappen-Explorer**auf **Form1.cs** , um es im Windows Forms-Designer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0dd74-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="0dd74-137">Legen Sie im Fenster **Eigenschaften** den Wert der **Lokalisier** baren Eigenschaft des Formulars auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="0dd74-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="0dd74-138">Legen Sie im Fenster **Eigenschaften** den Wert der **Language** -Eigenschaft auf **Spanisch (Spanien)** fest.</span><span class="sxs-lookup"><span data-stu-id="0dd74-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="0dd74-139">Wählen Sie im Windows Forms-Designer das Steuerelement „Label”.</span><span class="sxs-lookup"><span data-stu-id="0dd74-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="0dd74-140">Legen Sie im Fenster **Eigenschaften** den Wert der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft auf `"Hola"`fest.</span><span class="sxs-lookup"><span data-stu-id="0dd74-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="0dd74-141">Dem Projekt wird eine neue Ressourcendatei mit dem Namen Form1.es-ES.resx hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0dd74-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="0dd74-142">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **Form1.cs** , und klicken Sie auf **Code anzeigen** , um ihn im Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0dd74-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="0dd74-143">Kopieren Sie den folgenden Code in den `Form1`-Konstruktor, bevor Sie `InitializeComponent`aufgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="0dd74-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="0dd74-144">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **LocalizingWpfInWf** , und klicken Sie dann auf **Projekt entladen**.</span><span class="sxs-lookup"><span data-stu-id="0dd74-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="0dd74-145">Der Projektname hat die Bezeichnung **(nicht verfügbar)** .</span><span class="sxs-lookup"><span data-stu-id="0dd74-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="0dd74-146">Klicken Sie mit der rechten Maustaste auf **LocalizingWpfInWf**, und klicken Sie auf **LocalizingWpfInWf. csproj bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0dd74-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="0dd74-147">Die Projektdatei wird im Code-Editor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dd74-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="0dd74-148">Kopieren Sie die folgende Zeile in die erste `PropertyGroup` in der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="0dd74-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="0dd74-149">Speichern Sie die Projektdatei und schließen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="0dd74-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="0dd74-150">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **LocalizingWpfInWf** , und klicken Sie auf **Projekt erneut laden**.</span><span class="sxs-lookup"><span data-stu-id="0dd74-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="0dd74-151">Ressourcenbezeichner zuweisen</span><span class="sxs-lookup"><span data-stu-id="0dd74-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="0dd74-152">Sie können mithilfe von Ressourcenbezeichnern eine Zuordnung von lokalisierbarem Inhalt zu Ressourcenassemblys erstellen.</span><span class="sxs-lookup"><span data-stu-id="0dd74-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="0dd74-153">Die Anwendung MSBuild. exe weist automatisch Ressourcen Bezeichner zu, wenn Sie die Option `updateuid` angeben.</span><span class="sxs-lookup"><span data-stu-id="0dd74-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="0dd74-154">So weisen Sie Ressourcenbezeichner zu</span><span class="sxs-lookup"><span data-stu-id="0dd74-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="0dd74-155">Öffnen Sie im Startmenü die Developer-Eingabeaufforderung für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0dd74-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="0dd74-156">Verwenden Sie den folgenden Befehl, um ihrem lokalisierbaren Inhalt Ressourcenbezeichner zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0dd74-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="0dd74-157">Doppelklicken Sie in **Projektmappen-Explorer**auf **SimpleControl. XAML** , um die Datei im Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0dd74-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="0dd74-158">Sie sehen, dass der `msbuild`-Befehl allen Elementen das `Uid`-Attribut hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="0dd74-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="0dd74-159">Dies erleichtert die Lokalisierung durch Zuweisung von Ressourcenbezeichnern.</span><span class="sxs-lookup"><span data-stu-id="0dd74-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="0dd74-160">Drücken Sie **F6** , um die Projekt Mappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0dd74-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="0dd74-161">Verwenden des LocBaml-Tools zum Erzeugen einer Satellitenassembly</span><span class="sxs-lookup"><span data-stu-id="0dd74-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="0dd74-162">Der lokalisierte Inhalt wird in einer *Satellitenassembly*gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0dd74-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="0dd74-163">Verwenden Sie das Befehlszeilen Tool "LocBaml. exe", um eine lokalisierte Assembly für Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalte zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="0dd74-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="0dd74-164">So erzeugen Sie eine Satellitenassembly</span><span class="sxs-lookup"><span data-stu-id="0dd74-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="0dd74-165">Kopieren Sie LocBaml.exe in den Projektordner obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="0dd74-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="0dd74-166">Weitere Informationen finden Sie unter [Lokalisieren einer Anwendung](how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="0dd74-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="0dd74-167">Führen Sie im Eingabeaufforderungsfenster den folgenden Befehl aus, um Ressourcenzeichenfolgen in eine temporäre Datei zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="0dd74-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="0dd74-168">Öffnen Sie die Datei "Temp. csv" mit Visual Studio oder einem anderen Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="0dd74-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="0dd74-169">Ersetzen Sie die Zeichenfolge `"Hello"` durch die spanische Übersetzung `"Hola"`.</span><span class="sxs-lookup"><span data-stu-id="0dd74-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="0dd74-170">Speichern Sie die Datei „temp.csv”.</span><span class="sxs-lookup"><span data-stu-id="0dd74-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="0dd74-171">Verwenden Sie den folgenden Befehl, um die lokalisierte Ressourcendatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0dd74-171">Use the following command to generate the localized resource file.</span></span>

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="0dd74-172">Die Datei „LocalizingWpfInWf.g.es-es.resources” wird im Ordner obj\Debug erstellt.</span><span class="sxs-lookup"><span data-stu-id="0dd74-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="0dd74-173">Verwenden Sie den folgenden Befehl, um die lokalisierte Satellitenassembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0dd74-173">Use the following command to build the localized satellite assembly.</span></span>

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="0dd74-174">Die Datei „LocalizingWpfInWf.resources.dll” wird im Ordner obj\Debug erstellt.</span><span class="sxs-lookup"><span data-stu-id="0dd74-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="0dd74-175">Kopieren Sie die Datei LocalizingWpfInWf.Resources.dll in den Projektordner nach \bin\Debug\es-ES.</span><span class="sxs-lookup"><span data-stu-id="0dd74-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="0dd74-176">Ersetzen Sie die vorhandene Datei.</span><span class="sxs-lookup"><span data-stu-id="0dd74-176">Replace the existing file.</span></span>

8. <span data-ttu-id="0dd74-177">Führen Sie die Datei „LocalizingWpfInWf.exe” aus, die sich im Projektordner unter "\bin\Debug" befindet.</span><span class="sxs-lookup"><span data-stu-id="0dd74-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="0dd74-178">Erstellen Sie die Anwendung nicht neu, da dies die Satellitenassembly überschreiben würde.</span><span class="sxs-lookup"><span data-stu-id="0dd74-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="0dd74-179">Die Anwendung zeigt nun die lokalisierten Zeichenfolgen statt der englischen Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="0dd74-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dd74-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0dd74-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="0dd74-181">Lokalisieren einer Anwendung</span><span class="sxs-lookup"><span data-stu-id="0dd74-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- <span data-ttu-id="0dd74-182">[Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0dd74-182">[Walkthrough: Localizing Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span></span>
- [<span data-ttu-id="0dd74-183">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0dd74-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
