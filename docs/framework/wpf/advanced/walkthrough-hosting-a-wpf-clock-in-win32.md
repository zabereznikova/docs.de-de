---
title: 'Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 98e48060bbb82764e1e541797c666ca33f247c39
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400477"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="0c4f6-102">Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32</span><span class="sxs-lookup"><span data-stu-id="0c4f6-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>

<span data-ttu-id="0c4f6-103">Verwenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Sie zum Einfügen in Anwendungen, das das HWND bereitstellt, das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ihren Inhalt enthält. <xref:System.Windows.Interop.HwndSource></span><span class="sxs-lookup"><span data-stu-id="0c4f6-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="0c4f6-104">Erstellen Sie zunächst das <xref:System.Windows.Interop.HwndSource>, und geben Sie ihm Parameter ähnlich "kreatewindow".</span><span class="sxs-lookup"><span data-stu-id="0c4f6-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="0c4f6-105">Dann geben Sie die <xref:System.Windows.Interop.HwndSource> Informationen über [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] den gewünschten Inhalt an.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="0c4f6-106">Schließlich erhalten Sie das HWND aus dem <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="0c4f6-107">In dieser exemplarischen Vorgehensweise wird veranschaulicht, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wie [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ein gemischtes innerhalb der Anwendung erstellt wird, die das **Datum und die Uhrzeit-Eigenschaften** Dialogfeld des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="0c4f6-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0c4f6-108">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0c4f6-108">Prerequisites</span></span>

<span data-ttu-id="0c4f6-109">Siehe [WPF-und Win32-Interoperation](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="0c4f6-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="0c4f6-110">Verwendung dieses Tutorials</span><span class="sxs-lookup"><span data-stu-id="0c4f6-110">How to Use This Tutorial</span></span>

<span data-ttu-id="0c4f6-111">Dieses Tutorial konzentriert sich auf die wichtigsten Schritte zum Erstellen einer interoperativen Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="0c4f6-112">Das Lernprogramm wird durch ein Beispiel für ein Beispiel für die [Win32-Takt Interaktion](https://go.microsoft.com/fwlink/?LinkID=160051)unterstützt, aber dieses Beispiel reflektiert das Endprodukt.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="0c4f6-113">In diesem Tutorial werden die Schritte so dokumentiert, als würden Sie mit [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] einem vorhandenen Projekt, möglicherweise mit einem bereits vorhandenen Projekt, beginnen, und Sie haben eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gehostete zu Ihrer Anwendung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="0c4f6-114">Sie können Ihr Endprodukt mit dem [Beispiel für die Win32-Takt Interaktion](https://go.microsoft.com/fwlink/?LinkID=160051)vergleichen.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="0c4f6-115">Eine exemplarische Vorgehensweise für Windows Presentation Framework in Win32 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="0c4f6-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="0c4f6-116">Die folgende Grafik zeigt das angestrebte Endprodukt dieses Tutorials:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-116">The following graphic shows the intended end product of this tutorial:</span></span>

![Screenshot, der das Dialogfeld Datums-und Uhrzeit Eigenschaften anzeigt.](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="0c4f6-118">Sie können dieses Dialogfeld neu erstellen, C++ indem Sie ein Win32-Projekt in Visual Studio erstellen und den Dialog-Editor verwenden, um Folgendes zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

![Dialogfeld "Eigenschaften für Datum und Uhrzeit neu erstellt"](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="0c4f6-120">(Sie müssen [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] nicht verwenden <xref:System.Windows.Interop.HwndSource>, um zu verwenden, und Sie müssen nicht C++ zum Schreiben [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] von Programmen verwenden. Dies ist jedoch eine ziemlich typische Methode, um dies zu tun, und eignet sich gut für eine schrittweise Lernprogramm Erklärung).</span><span class="sxs-lookup"><span data-stu-id="0c4f6-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="0c4f6-121">Sie müssen fünf bestimmte unter Schritte ausführen, um eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr in den Dialog zu versetzen:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="0c4f6-122">Aktivieren Sie [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] das Projekt, um verwalteten Code ( **/CLR**) aufzurufen, indem [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]Sie die Projekteinstellungen in ändern.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>

2. <span data-ttu-id="0c4f6-123">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ErstellenSie<xref:System.Windows.Controls.Page> in einer separaten dll.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="0c4f6-124">Fügen Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das <xref:System.Windows.Controls.Page> in <xref:System.Windows.Interop.HwndSource>eine ein.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="0c4f6-125">Verwenden Sie die <xref:System.Windows.Controls.Page> <xref:System.Windows.Interop.HwndSource.Handle%2A> -Eigenschaft, um ein HWND zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="0c4f6-126">Verwenden [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Sie, um zu entscheiden, wo das HWND in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] der größeren Anwendung platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>

## <a name="clr"></a><span data-ttu-id="0c4f6-127">/clr</span><span class="sxs-lookup"><span data-stu-id="0c4f6-127">/clr</span></span>

<span data-ttu-id="0c4f6-128">Der erste Schritt besteht darin, dieses nicht verwaltete [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt in eines zu verwandeln, das verwalteten Code abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span> <span data-ttu-id="0c4f6-129">Verwenden Sie die/CLR-Compileroption, die mit den erforderlichen DLLs verknüpft wird, die Sie verwenden möchten, und passen Sie die Main [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Methode für die Verwendung mit an.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="0c4f6-130">So aktivieren Sie die Verwendung von verwaltetem Code C++ innerhalb des Projekts: Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="0c4f6-131">Ändern Sie auf der Eigenschaften Seite **Allgemein** (Standard) die Common Language Runtime-unter `/clr`Stützung in.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="0c4f6-132">Fügen Sie als nächstes Verweise auf DLLs hinzu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], die für erforderlich sind: "PresentationCore. dll", "presentationframework. dll", "System. dll", "WindowsBase. dll", "UIAutomationProvider. dll" und "UIAutomationTypes. dll".</span><span class="sxs-lookup"><span data-stu-id="0c4f6-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="0c4f6-133">(Bei den nachfolgenden Anweisungen wird davon ausgegangen, dass das Betriebssystem auf Laufwerk C: installiert ist.)</span><span class="sxs-lookup"><span data-stu-id="0c4f6-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="0c4f6-134">Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Verweise...** und innerhalb dieses Dialog Felds:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="0c4f6-135">Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Verweise**aus.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="0c4f6-136">Klicken Sie auf **neuen Verweis hinzufügen**, klicken Sie auf die Registerkarte Durchsuchen, geben Sie c:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll ein, und klicken Sie auf OK.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="0c4f6-137">Wiederholen Sie diesen Schritt für presentationframework. dll: C:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="0c4f6-138">Wiederholen Sie diesen Schritt für "WindowsBase. dll: C:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="0c4f6-139">Wiederholen Sie diesen Schritt für UIAutomationTypes. dll: C:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="0c4f6-140">Wiederholen Sie diesen Schritt für UIAutomationProvider. dll: C:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\uiautomationprovider.dll.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="0c4f6-141">Klicken Sie auf **neuen Verweis hinzufügen**, wählen Sie System. dll, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="0c4f6-142">Klicken Sie auf **OK** , um die Eigenschaften Seiten Mausklick das win32clock zum Hinzufügen von verweisen zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="0c4f6-143">Fügen Sie abschließend der `STAThreadAttribute` `_tWinMain` -Methode zur Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]hinzu:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="0c4f6-144">Dieses Attribut teilt dem Common Language Runtime (CLR) mit, dass es beim [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)]initialisieren ein Single Thread-Apartment-Modell (STA) verwenden sollte, das für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]) erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-144">This attribute tells the common language runtime (CLR) that when it initializes [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="0c4f6-145">Erstellen einer Windows Presentation Framework-Seite</span><span class="sxs-lookup"><span data-stu-id="0c4f6-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="0c4f6-146">Als Nächstes erstellen Sie eine DLL, die eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>definiert.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="0c4f6-147">Häufig ist es am [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> einfachsten, als eigenständige Anwendung zu erstellen und den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Teil auf diese Weise zu schreiben und zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="0c4f6-148">Anschließend kann das Projekt in eine DLL-Datei umgewandelt werden, indem Sie mit der rechten Maustaste auf das Projekt klicken, auf **Eigenschaften**klicken, die Anwendung aufrufen und den Ausgabetyp in Windows-Klassenbibliothek ändern.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="0c4f6-149">Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] DLL-Projekt kann dann mit dem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt kombiniert werden (eine Projekt Mappe, die zwei Projekte enthält) – klicken Sie mit der rechten Maustaste auf die Projekt Mappe, und wählen Sie **add\vorhandenes Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="0c4f6-150">Um diese [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll aus dem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt zu verwenden, müssen Sie einen Verweis hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>

1. <span data-ttu-id="0c4f6-151">Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Verweise**aus.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="0c4f6-152">Klicken Sie auf **neuen Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="0c4f6-153">Klicken Sie auf die Registerkarte **Projekte**. Wählen Sie „WPFClock” aus und klicken Sie auf OK.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="0c4f6-154">Klicken Sie auf **OK** , um die Eigenschaften Seiten Mausklick das win32clock zum Hinzufügen von verweisen zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="0c4f6-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="0c4f6-155">HwndSource</span></span>

<span data-ttu-id="0c4f6-156">Als nächstes verwenden <xref:System.Windows.Interop.HwndSource> Sie, um das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> aussehen wie ein HWND zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="0c4f6-157">Sie fügen diesen Codeblock zu einer C++-Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-157">You add this block of code to a C++ file:</span></span>

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

 <span data-ttu-id="0c4f6-158">Dies ist ein langer Codeabschnitt, der einiger Erklärungen bedarf.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="0c4f6-159">Der erste Teil besteht aus verschiedenen Klauseln, die dafür sorgen, dass nicht alle Aufrufe vollständig qualifiziert werden müssen:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="0c4f6-160">Dann definieren Sie eine Funktion, die den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt erstellt, eine <xref:System.Windows.Interop.HwndSource> umschließt und den HWND zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="0c4f6-161">Erstellen Sie zunächst eine <xref:System.Windows.Interop.HwndSource>, deren Parameter mit "kreatewindow" vergleichbar sind:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

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

<span data-ttu-id="0c4f6-162">Anschließend erstellen Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts Klasse, indem Sie Ihren Konstruktor aufrufen:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="0c4f6-163">Anschließend verbinden Sie die Seite mit dem <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="0c4f6-164">Und in der letzten Zeile das HWND für den <xref:System.Windows.Interop.HwndSource>zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="0c4f6-165">Positionieren des HWND</span><span class="sxs-lookup"><span data-stu-id="0c4f6-165">Positioning the Hwnd</span></span>

<span data-ttu-id="0c4f6-166">Nachdem Sie nun über ein HWND verfügen, das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Uhr enthält, müssen Sie dieses HWND in das [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Dialogfeld einfügen.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span> <span data-ttu-id="0c4f6-167">Wenn Sie genau wissen, wo das HWND abgelegt werden soll, übergeben Sie einfach diese Größe und den Speicherort an die Funktion, die `GetHwnd` Sie zuvor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="0c4f6-168">Da Sie für die Definition des Dialogs aber eine Ressourcendatei verwendet haben, können Sie nicht sicher wissen, wo ein HWND jeweils platziert sein wird.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="0c4f6-169">Sie können den [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] Dialog-Editor verwenden, um [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ein statisches Steuerelement zu platzieren, wo Sie die Uhr verschieben möchten ("Uhr hier einfügen"), und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dieses verwenden, um die Uhr zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="0c4f6-170">Mit WM_INITDIALOG können Sie `GetDlgItem` das HWND für den Platzhalter STATIC abrufen:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="0c4f6-171">Anschließend berechnen Sie die Größe und Position des Platzhalters statisch, sodass Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr an dieser Stelle platzieren können:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="0c4f6-172">RECT rectangle;</span><span class="sxs-lookup"><span data-stu-id="0c4f6-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="0c4f6-173">Blenden Sie anschließen den Platzhalter „STATIC” aus:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="0c4f6-174">Und erstellen Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das HWND der Uhr an diesem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="0c4f6-175">Damit das Lernprogramm interessant wird und eine echte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr erzeugt werden kann, müssen Sie an dieser Stelle ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Clock-Steuerelement erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="0c4f6-176">Den größten Teil davon können Sie in Markup erledigen, mit nur einigen wenigen Ereignishandlern im CodeBehind.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="0c4f6-177">Da es sich bei diesem Tutorial um die Interoperabilität handelt und nicht um das Design der Steuer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente, wird der gesamte Code für die Uhr hier als Codeblock bereitgestellt, ohne diskrete Anweisungen für die Erstellung oder die Bedeutung der einzelnen Teile.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="0c4f6-178">Experimentieren Sie ruhig mit diesem Code, um Aussehen, Verhalten oder Funktionalität des Steuerelements zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0c4f6-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="0c4f6-179">Dies ist das Markup:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="0c4f6-180">Und hier das zugehörige CodeBehind:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="0c4f6-181">Das Endergebnis sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="0c4f6-181">The final result looks like:</span></span>

![Dialogfeld "endgültige Datums-und Uhrzeit Eigenschaften"](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="0c4f6-183">Informationen zum Vergleichen des Ergebnisses mit dem Code, der diesen Screenshot erzeugt hat, finden Sie unter Beispiel für die [Win32-Takt Interaktion](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="0c4f6-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="see-also"></a><span data-ttu-id="0c4f6-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c4f6-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="0c4f6-185">Interaktion zwischen WPF und Win32</span><span class="sxs-lookup"><span data-stu-id="0c4f6-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="0c4f6-186">Beispiel für Interaktion mit der Win32-Uhr</span><span class="sxs-lookup"><span data-stu-id="0c4f6-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
