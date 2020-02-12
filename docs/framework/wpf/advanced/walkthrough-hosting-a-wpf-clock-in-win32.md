---
title: 'Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32'
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 0aecde96d182e12ab72b1a6cba129ab1d8a28391
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123778"
---
# <a name="walkthrough-host-a-wpf-clock-in-win32"></a><span data-ttu-id="1f71b-102">Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32</span><span class="sxs-lookup"><span data-stu-id="1f71b-102">Walkthrough: Host a WPF Clock in Win32</span></span>

<span data-ttu-id="1f71b-103">Wenn Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in Win32-Anwendungen einfügen möchten, verwenden Sie <xref:System.Windows.Interop.HwndSource>, der das HWND bereitstellt, das Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt enthält.</span><span class="sxs-lookup"><span data-stu-id="1f71b-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="1f71b-104">Erstellen Sie zunächst die <xref:System.Windows.Interop.HwndSource>, und geben Sie Ihr Parameter ähnlich wie bei "kreatewindow" an.</span><span class="sxs-lookup"><span data-stu-id="1f71b-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="1f71b-105">Dann informieren Sie den <xref:System.Windows.Interop.HwndSource> über den gewünschten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt.</span><span class="sxs-lookup"><span data-stu-id="1f71b-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="1f71b-106">Schließlich erhalten Sie das HWND aus dem <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="1f71b-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="1f71b-107">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie ein gemischtes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in einer Win32-Anwendung erstellt wird, die das Eigenschaften Dialogfeld des Betriebssystems für **Datum und Uhrzeit**</span><span class="sxs-lookup"><span data-stu-id="1f71b-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1f71b-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1f71b-108">Prerequisites</span></span>

<span data-ttu-id="1f71b-109">Siehe [WPF-und Win32-Interoperation](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="1f71b-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="1f71b-110">Verwendung dieses Tutorials</span><span class="sxs-lookup"><span data-stu-id="1f71b-110">How to Use This Tutorial</span></span>

<span data-ttu-id="1f71b-111">Dieses Tutorial konzentriert sich auf die wichtigsten Schritte zum Erstellen einer interoperativen Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1f71b-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="1f71b-112">Das Lernprogramm wird durch ein Beispiel für ein Beispiel für die [Win32-Takt Interaktion](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)unterstützt, aber dieses Beispiel reflektiert das Endprodukt.</span><span class="sxs-lookup"><span data-stu-id="1f71b-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock), but that sample is reflective of the end product.</span></span> <span data-ttu-id="1f71b-113">In diesem Tutorial werden die Schritte so beschrieben, als würden Sie mit einem vorhandenen Win32-Projekt beginnen, das möglicherweise ein bereits vorhandenes Projekt ist, und Sie haben der Anwendung einen gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1f71b-113">This tutorial documents the steps as if you were starting with an existing Win32 project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="1f71b-114">Sie können Ihr Endprodukt mit dem [Beispiel für die Win32-Takt Interaktion](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)vergleichen.</span><span class="sxs-lookup"><span data-stu-id="1f71b-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="1f71b-115">Eine exemplarische Vorgehensweise für Windows Presentation Framework in Win32 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="1f71b-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="1f71b-116">Die folgende Grafik zeigt das angestrebte Endprodukt dieses Tutorials:</span><span class="sxs-lookup"><span data-stu-id="1f71b-116">The following graphic shows the intended end product of this tutorial:</span></span>

![Screenshot, der das Dialogfeld Datums-und Uhrzeit Eigenschaften anzeigt.](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="1f71b-118">Sie können dieses Dialogfeld neu erstellen, C++ indem Sie ein Win32-Projekt in Visual Studio erstellen und den Dialog-Editor verwenden, um Folgendes zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1f71b-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

![Dialogfeld "Eigenschaften für Datum und Uhrzeit neu erstellt"](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="1f71b-120">(Sie müssen Visual Studio nicht verwenden, um <xref:System.Windows.Interop.HwndSource>zu verwenden, und Sie müssen nicht zum Schreiben von C++ Win32-Programmen verwenden. Dies ist jedoch eine ziemlich typische Methode, um dies zu tun, und eignet sich gut für eine schrittweise Lernprogramm Erklärung).</span><span class="sxs-lookup"><span data-stu-id="1f71b-120">(You do not need to use Visual Studio to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write Win32 programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="1f71b-121">Sie müssen fünf bestimmte unter Schritte ausführen, um eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr in das Dialogfeld zu versetzen:</span><span class="sxs-lookup"><span data-stu-id="1f71b-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="1f71b-122">Aktivieren Sie das Win32-Projekt, um verwalteten Code ( **/CLR**) aufzurufen, indem Sie Projekteinstellungen in Visual Studio ändern.</span><span class="sxs-lookup"><span data-stu-id="1f71b-122">Enable your Win32 project to call managed code (**/clr**) by changing project settings in Visual Studio.</span></span>

2. <span data-ttu-id="1f71b-123">Erstellen Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in einer separaten dll.</span><span class="sxs-lookup"><span data-stu-id="1f71b-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="1f71b-124">Legen Sie diese [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in einem <xref:System.Windows.Interop.HwndSource>ab.</span><span class="sxs-lookup"><span data-stu-id="1f71b-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="1f71b-125">Verwenden Sie die <xref:System.Windows.Interop.HwndSource.Handle%2A>-Eigenschaft, um ein HWND für dieses <xref:System.Windows.Controls.Page> zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1f71b-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="1f71b-126">Verwenden Sie Win32, um zu entscheiden, wo das HWND in der größeren Win32-Anwendung platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1f71b-126">Use Win32 to decide where to place the HWND within the larger Win32 application</span></span>

## <a name="clr"></a><span data-ttu-id="1f71b-127">/clr</span><span class="sxs-lookup"><span data-stu-id="1f71b-127">/clr</span></span>

<span data-ttu-id="1f71b-128">Der erste Schritt besteht darin, dieses nicht verwaltete Win32-Projekt in ein solches zu verwandeln, das verwalteten Code abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="1f71b-128">The first step is to turn this unmanaged Win32 project into one that can call managed code.</span></span> <span data-ttu-id="1f71b-129">Verwenden Sie die/CLR-Compileroption, die mit den erforderlichen DLLs verknüpft wird, die Sie verwenden möchten, und passen Sie die Main-Methode für die Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]an.</span><span class="sxs-lookup"><span data-stu-id="1f71b-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="1f71b-130">So aktivieren Sie die Verwendung von verwaltetem Code C++ innerhalb des Projekts: Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="1f71b-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="1f71b-131">Ändern Sie auf der Eigenschaften Seite **Allgemein** (Standard) die Common Language Runtime-Unterstützung in `/clr`.</span><span class="sxs-lookup"><span data-stu-id="1f71b-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="1f71b-132">Fügen Sie als nächstes Verweise auf DLLs hinzu, die für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]erforderlich sind: presentationcore. dll, presentationframework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll und UIAutomationTypes. dll.</span><span class="sxs-lookup"><span data-stu-id="1f71b-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="1f71b-133">(Bei den nachfolgenden Anweisungen wird davon ausgegangen, dass das Betriebssystem auf Laufwerk C: installiert ist.)</span><span class="sxs-lookup"><span data-stu-id="1f71b-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="1f71b-134">Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Verweise...** und innerhalb dieses Dialog Felds:</span><span class="sxs-lookup"><span data-stu-id="1f71b-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="1f71b-135">Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Verweise**aus.</span><span class="sxs-lookup"><span data-stu-id="1f71b-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="1f71b-136">Klicken Sie auf **neuen Verweis hinzufügen**, klicken Sie auf die Registerkarte Durchsuchen, geben Sie c:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll ein, und klicken Sie auf OK.</span><span class="sxs-lookup"><span data-stu-id="1f71b-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="1f71b-137">Wiederholen Sie diesen Schritt für PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="1f71b-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="1f71b-138">Wiederholen Sie diesen Schritt für WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="1f71b-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="1f71b-139">Wiederholen Sie diesen Schritt für UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="1f71b-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="1f71b-140">Wiederholen Sie diesen Schritt für UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="1f71b-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="1f71b-141">Klicken Sie auf **neuen Verweis hinzufügen**, wählen Sie System. dll, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f71b-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="1f71b-142">Klicken Sie auf **OK** , um die Eigenschaften Seiten Mausklick das win32clock zum Hinzufügen von verweisen zu schließen.</span><span class="sxs-lookup"><span data-stu-id="1f71b-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="1f71b-143">Fügen Sie abschließend die `STAThreadAttribute` der `_tWinMain`-Methode für die Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]hinzu:</span><span class="sxs-lookup"><span data-stu-id="1f71b-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="1f71b-144">Dieses Attribut weist den Common Language Runtime (CLR) an, dass beim Initialisieren Component Object Model (com) ein Single Thread-Apartment Modell (STA) verwendet wird, das für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (und Windows Forms) erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1f71b-144">This attribute tells the common language runtime (CLR) that when it initializes Component Object Model (COM), it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and Windows Forms).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="1f71b-145">Erstellen einer Windows Presentation Framework-Seite</span><span class="sxs-lookup"><span data-stu-id="1f71b-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="1f71b-146">Als Nächstes erstellen Sie eine DLL, die eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>definiert.</span><span class="sxs-lookup"><span data-stu-id="1f71b-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="1f71b-147">Häufig ist es am einfachsten, den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> als eigenständige Anwendung zu erstellen und den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Teil auf diese Weise zu schreiben und zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="1f71b-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="1f71b-148">Anschließend kann das Projekt in eine DLL-Datei umgewandelt werden, indem Sie mit der rechten Maustaste auf das Projekt klicken, auf **Eigenschaften**klicken, die Anwendung aufrufen und den Ausgabetyp in Windows-Klassenbibliothek ändern.</span><span class="sxs-lookup"><span data-stu-id="1f71b-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="1f71b-149">Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] DLL-Projekt kann dann mit dem Win32-Projekt (eine Projekt Mappe, die zwei Projekte enthält) kombiniert werden – klicken Sie mit der rechten Maustaste auf die Projekt Mappe, und wählen Sie **add\vorhandenes Projekt**.</span><span class="sxs-lookup"><span data-stu-id="1f71b-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the Win32 project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="1f71b-150">Um diese [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll aus dem Win32-Projekt zu verwenden, müssen Sie einen Verweis hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="1f71b-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the Win32 project, you need to add a reference:</span></span>

1. <span data-ttu-id="1f71b-151">Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Verweise**aus.</span><span class="sxs-lookup"><span data-stu-id="1f71b-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="1f71b-152">Klicken Sie auf **neuen Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1f71b-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="1f71b-153">Klicken Sie auf die Registerkarte **Projekte** . Wählen Sie wpfclock und dann OK aus.</span><span class="sxs-lookup"><span data-stu-id="1f71b-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="1f71b-154">Klicken Sie auf **OK** , um die Eigenschaften Seiten Mausklick das win32clock zum Hinzufügen von verweisen zu schließen.</span><span class="sxs-lookup"><span data-stu-id="1f71b-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="1f71b-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="1f71b-155">HwndSource</span></span>

<span data-ttu-id="1f71b-156">Als nächstes verwenden Sie <xref:System.Windows.Interop.HwndSource>, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> wie ein HWND aussehen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="1f71b-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="1f71b-157">Sie fügen diesen Codeblock zu einer C++-Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="1f71b-157">You add this block of code to a C++ file:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;

    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
        HwndSource^ source = gcnew HwndSource(
            0, // class style
            WS_VISIBLE | WS_CHILD, // style
            0, // exstyle
            x, y, width, height,
            "hi", // NAME
            IntPtr(parent)        // parent window
            );

        UIElement^ page = gcnew WPFClock::Clock();
        source->RootVisual = page;
        return (HWND) source->Handle.ToPointer();
    }
}
}
```

 <span data-ttu-id="1f71b-158">Dies ist ein langer Codeabschnitt, der einiger Erklärungen bedarf.</span><span class="sxs-lookup"><span data-stu-id="1f71b-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="1f71b-159">Der erste Teil besteht aus verschiedenen Klauseln, die dafür sorgen, dass nicht alle Aufrufe vollständig qualifiziert werden müssen:</span><span class="sxs-lookup"><span data-stu-id="1f71b-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="1f71b-160">Dann definieren Sie eine Funktion, die den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt erstellt, eine <xref:System.Windows.Interop.HwndSource> um die Datei setzt und das HWND zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="1f71b-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="1f71b-161">Erstellen Sie zunächst eine <xref:System.Windows.Interop.HwndSource>, deren Parameter mit "kreatewindow" vergleichbar sind:</span><span class="sxs-lookup"><span data-stu-id="1f71b-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

```cpp
HwndSource^ source = gcnew HwndSource(
    0, // class style
    WS_VISIBLE | WS_CHILD, // style
    0, // exstyle
    x, y, width, height,
    "hi", // NAME
    IntPtr(parent) // parent window
);
```

<span data-ttu-id="1f71b-162">Anschließend erstellen Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts Klasse, indem Sie Ihren Konstruktor aufrufen:</span><span class="sxs-lookup"><span data-stu-id="1f71b-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="1f71b-163">Stellen Sie dann eine Verbindung zwischen der Seite und der <xref:System.Windows.Interop.HwndSource>her:</span><span class="sxs-lookup"><span data-stu-id="1f71b-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="1f71b-164">Und in der letzten Zeile wird das HWND für den <xref:System.Windows.Interop.HwndSource>zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="1f71b-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="1f71b-165">Positionieren des HWND</span><span class="sxs-lookup"><span data-stu-id="1f71b-165">Positioning the Hwnd</span></span>

<span data-ttu-id="1f71b-166">Nachdem Sie nun über ein HWND verfügen, das die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr enthält, müssen Sie das HWND in das Win32-Dialogfeld einfügen.</span><span class="sxs-lookup"><span data-stu-id="1f71b-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the Win32 dialog.</span></span> <span data-ttu-id="1f71b-167">Wenn Sie genau wissen, wo das HWND abgelegt werden soll, übergeben Sie einfach diese Größe und den Speicherort an die `GetHwnd` Funktion, die Sie zuvor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="1f71b-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="1f71b-168">Da Sie für die Definition des Dialogs aber eine Ressourcendatei verwendet haben, können Sie nicht sicher wissen, wo ein HWND jeweils platziert sein wird.</span><span class="sxs-lookup"><span data-stu-id="1f71b-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="1f71b-169">Sie können den Visual Studio-Dialog-Editor verwenden, um ein statisches Win32-Steuerelement zu platzieren, wo Sie die Uhr drehen möchten ("Uhr hier einfügen"), und dieses verwenden, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="1f71b-169">You can use the Visual Studio dialog editor to put a Win32 STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="1f71b-170">Wenn Sie WM_INITDIALOG behandeln, verwenden Sie `GetDlgItem`, um das HWND für den Platzhalter statisch abzurufen:</span><span class="sxs-lookup"><span data-stu-id="1f71b-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="1f71b-171">Anschließend berechnen Sie die Größe und Position des Platzhalters statisch, sodass Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr an dieser Stelle platzieren können:</span><span class="sxs-lookup"><span data-stu-id="1f71b-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="1f71b-172">RECT rectangle;</span><span class="sxs-lookup"><span data-stu-id="1f71b-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="1f71b-173">Blenden Sie anschließen den Platzhalter „STATIC” aus:</span><span class="sxs-lookup"><span data-stu-id="1f71b-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="1f71b-174">Und erstellen Sie das HWND der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr an diesem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="1f71b-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="1f71b-175">Um das Lernprogramm interessant zu machen und eine echte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr zu erzeugen, müssen Sie an dieser Stelle ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Clock-Steuerelement erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f71b-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="1f71b-176">Den größten Teil davon können Sie in Markup erledigen, mit nur einigen wenigen Ereignishandlern im CodeBehind.</span><span class="sxs-lookup"><span data-stu-id="1f71b-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="1f71b-177">Da es sich bei diesem Tutorial um Interoperabilität und nicht um das Design der Steuerelemente handelt, wird hier der gesamte Code für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr als Codeblock bereitgestellt, ohne diskrete Anweisungen für die Erstellung oder die Bedeutung der einzelnen Teile.</span><span class="sxs-lookup"><span data-stu-id="1f71b-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="1f71b-178">Experimentieren Sie ruhig mit diesem Code, um Aussehen, Verhalten oder Funktionalität des Steuerelements zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1f71b-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="1f71b-179">Dies ist das Markup:</span><span class="sxs-lookup"><span data-stu-id="1f71b-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="1f71b-180">Und hier das zugehörige CodeBehind:</span><span class="sxs-lookup"><span data-stu-id="1f71b-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="1f71b-181">Das Endergebnis sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="1f71b-181">The final result looks like:</span></span>

![Dialogfeld "endgültige Datums-und Uhrzeit Eigenschaften"](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="1f71b-183">Informationen zum Vergleichen des Ergebnisses mit dem Code, der diesen Screenshot erzeugt hat, finden Sie unter Beispiel für die [Win32-Takt Interaktion](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock).</span><span class="sxs-lookup"><span data-stu-id="1f71b-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock).</span></span>

## <a name="see-also"></a><span data-ttu-id="1f71b-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f71b-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="1f71b-185">Interaktion zwischen WPF und Win32</span><span class="sxs-lookup"><span data-stu-id="1f71b-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="1f71b-186">Beispiel für Interaktion mit der Win32-Uhr</span><span class="sxs-lookup"><span data-stu-id="1f71b-186">Win32 Clock Interoperation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)
