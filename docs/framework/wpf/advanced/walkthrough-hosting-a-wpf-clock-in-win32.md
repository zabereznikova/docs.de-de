---
title: 'Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 5cccc89c8346358bc4f719e1b089a181dd81f970
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54579770"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="2c36a-102">Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32</span><span class="sxs-lookup"><span data-stu-id="2c36a-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>
<span data-ttu-id="2c36a-103">Einzufügenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Anwendungen verwenden <xref:System.Windows.Interop.HwndSource>, das bietet des HWND, das enthält Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt.</span><span class="sxs-lookup"><span data-stu-id="2c36a-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="2c36a-104">Erstellen Sie zunächst die <xref:System.Windows.Interop.HwndSource>, legen sie Parameter, die denen von CreateWindow ähneln.</span><span class="sxs-lookup"><span data-stu-id="2c36a-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span>  <span data-ttu-id="2c36a-105">Sie weisen die <xref:System.Windows.Interop.HwndSource> über die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt darin enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="2c36a-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span>  <span data-ttu-id="2c36a-106">Schließlich erhalten Sie das HWND aus der <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="2c36a-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="2c36a-107">Diese exemplarische Vorgehensweise veranschaulicht, wie Sie ein gemischtes erstellen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] -Anwendung, die das Betriebssystemdialogfeld **Datums- und Uhrzeiteigenschaften** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="2c36a-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2c36a-108">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2c36a-108">Prerequisites</span></span>  
 <span data-ttu-id="2c36a-109">Finden Sie unter [WPF und Win32-Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="2c36a-109">See [WPF and Win32 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span></span>  
  
## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="2c36a-110">Verwendung dieses Tutorials</span><span class="sxs-lookup"><span data-stu-id="2c36a-110">How to Use This Tutorial</span></span>  
 <span data-ttu-id="2c36a-111">Dieses Tutorial konzentriert sich auf die wichtigsten Schritte zum Erstellen einer interoperativen Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2c36a-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="2c36a-112">Ein Beispiel, das Tutorial stützt [Beispiel für die Interaktion von Win32-Uhr](https://go.microsoft.com/fwlink/?LinkID=160051), aber dieses Beispiel ist das Endprodukt repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="2c36a-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="2c36a-113">In diesem Tutorial werden die Schritte aus, als ob Sie mit einem vorhandenen starten [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] eigenes Projekt, z. B. einem vorhandenen Projekt und ein gehostetes hinzufügen wurden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2c36a-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="2c36a-114">Sie können Ihr Endprodukt mit vergleichen [Beispiel für die Interaktion von Win32-Uhr](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="2c36a-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="2c36a-115">Eine exemplarische Vorgehensweise für Windows Presentation Framework in Win32 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="2c36a-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>  
 <span data-ttu-id="2c36a-116">Die folgende Grafik zeigt das angestrebte Endprodukt dieses Tutorials:</span><span class="sxs-lookup"><span data-stu-id="2c36a-116">The following graphic shows the intended end product of this tutorial:</span></span>  
  
 <span data-ttu-id="2c36a-117">![Dialogfeld Datums- und Uhrzeiteigenschaften](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")</span><span class="sxs-lookup"><span data-stu-id="2c36a-117">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")</span></span>  
  
 <span data-ttu-id="2c36a-118">Sie können dieses Dialogfeld reproduzieren, durch das Erstellen von C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], und Verwenden des Dialog-Editors Folgendes erstellen:</span><span class="sxs-lookup"><span data-stu-id="2c36a-118">You can recreate this dialog by creating C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and using the dialog editor to create the following:</span></span>  
  
 <span data-ttu-id="2c36a-119">![Dialogfeld Datums- und Uhrzeiteigenschaften](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")</span><span class="sxs-lookup"><span data-stu-id="2c36a-119">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")</span></span>  
  
 <span data-ttu-id="2c36a-120">(Sie müssen nicht mit [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] verwenden <xref:System.Windows.Interop.HwndSource>, und Sie müssen nicht C++ verwenden, um das Schreiben von [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Programme, aber dies ist eine durchaus übliche Vorgehensweise und eignet sich gut für eine schrittweise Erklärung des Tutorials).</span><span class="sxs-lookup"><span data-stu-id="2c36a-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>  
  
 <span data-ttu-id="2c36a-121">Sie müssen fünf bestimmte Teilschritte zu erreichen, um die put ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr in das Dialogfeld:</span><span class="sxs-lookup"><span data-stu-id="2c36a-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>  
  
1.  <span data-ttu-id="2c36a-122">Aktivieren Sie Ihre [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt, um verwalteten Code aufrufen (**"/ CLR"**) durch Ändern von projekteinstellungen in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c36a-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="2c36a-123">Erstellen Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> in einer separaten DLL.</span><span class="sxs-lookup"><span data-stu-id="2c36a-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>  
  
3.  <span data-ttu-id="2c36a-124">Einfügen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> innerhalb einer <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="2c36a-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>  
  
4.  <span data-ttu-id="2c36a-125">Rufen Sie ein HWND für diesen <xref:System.Windows.Controls.Page> mithilfe der <xref:System.Windows.Interop.HwndSource.Handle%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2c36a-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>  
  
5.  <span data-ttu-id="2c36a-126">Verwendung [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] entscheiden, wo das HWND innerhalb der größeren [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Anwendung</span><span class="sxs-lookup"><span data-stu-id="2c36a-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>  
  
## <a name="clr"></a><span data-ttu-id="2c36a-127">/clr</span><span class="sxs-lookup"><span data-stu-id="2c36a-127">/clr</span></span>  
 <span data-ttu-id="2c36a-128">Der erste Schritt ist, dieses nicht verwaltete [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt in eine, die aufgerufen wird, können von verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="2c36a-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span>  <span data-ttu-id="2c36a-129">Sie verwenden die Compileroption "/ CLR", die die erforderlichen DLLs verknüpft werden, Sie verwenden möchten, und passen Sie die Main-Methode für die Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c36a-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="2c36a-130">So aktivieren Sie die Verwendung von verwaltetem Code im C++-Projekt: Mit der rechten Maustaste auf das win32clock-Projekt, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2c36a-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span>  <span data-ttu-id="2c36a-131">Auf der **allgemeine** Eigenschaftenseite (Standardeinstellung), ändern Sie Common Language Runtime-Unterstützung in `/clr`.</span><span class="sxs-lookup"><span data-stu-id="2c36a-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>  
  
 <span data-ttu-id="2c36a-132">Fügen Sie Verweise auf DLLs für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="2c36a-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="2c36a-133">(Bei den nachfolgenden Anweisungen wird davon ausgegangen, dass das Betriebssystem auf Laufwerk C: installiert ist.)</span><span class="sxs-lookup"><span data-stu-id="2c36a-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>  
  
1.  <span data-ttu-id="2c36a-134">Mit der rechten Maustaste win32clock-Projekt, und wählen Sie **Verweise...** , und klicken Sie in diesem Dialogfeld:</span><span class="sxs-lookup"><span data-stu-id="2c36a-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>  
  
2.  <span data-ttu-id="2c36a-135">Mit der rechten Maustaste win32clock-Projekt, und wählen Sie **Verweise...** .</span><span class="sxs-lookup"><span data-stu-id="2c36a-135">Right-click win32clock project and select **References...**.</span></span>  
  
3.  <span data-ttu-id="2c36a-136">Klicken Sie auf **neuen Verweis hinzufügen**, klicken Sie auf die Registerkarte "Durchsuchen", geben Sie c:\Programme\Microsoft c:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll aus, und klicken Sie auf OK.</span><span class="sxs-lookup"><span data-stu-id="2c36a-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>  
  
4.  <span data-ttu-id="2c36a-137">Wiederholen Sie für "PresentationFramework.dll": C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="2c36a-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>  
  
5.  <span data-ttu-id="2c36a-138">Wiederholen Sie für "WindowsBase.dll": C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="2c36a-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>  
  
6.  <span data-ttu-id="2c36a-139">Wiederholen Sie für UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="2c36a-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>  
  
7.  <span data-ttu-id="2c36a-140">Wiederholen Sie für "UIAutomationProvider.dll": C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="2c36a-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>  
  
8.  <span data-ttu-id="2c36a-141">Klicken Sie auf **neuen Verweis hinzufügen**, wählen Sie "System.dll" aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c36a-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>  
  
9. <span data-ttu-id="2c36a-142">Klicken Sie auf **OK** um die win32clock-Eigenschaftenseiten zum Hinzufügen von Verweisen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="2c36a-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
 <span data-ttu-id="2c36a-143">Fügen Sie abschließend die `STAThreadAttribute` auf die `_tWinMain` Methode für die Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="2c36a-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 <span data-ttu-id="2c36a-144">Dieses Attribut teilt die [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] , die bei der Initialisierung [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], muss bei Verwendung ein Modells für Singlethread-Apartment (STA), der erforderlich ist [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="2c36a-144">This attribute tells the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] that when it initializes [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>  
  
## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="2c36a-145">Erstellen einer Windows Presentation Framework-Seite</span><span class="sxs-lookup"><span data-stu-id="2c36a-145">Create a Windows Presentation Framework Page</span></span>  
 <span data-ttu-id="2c36a-146">Als Nächstes erstellen Sie eine DLL, definiert ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="2c36a-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="2c36a-147">Es ist häufig am einfachsten, erstellen die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> als eigenständige Anwendung, und Schreiben und Debuggen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Codeabschnitte darin.</span><span class="sxs-lookup"><span data-stu-id="2c36a-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span>  <span data-ttu-id="2c36a-148">Danach kann das Projekt in eine DLL aktiviert werden, mit der rechten Maustaste auf das Projekt **Eigenschaften**, zur Anwendung wechseln und das Ändern der Ausgabetyp für Windows-Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="2c36a-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>  
  
 <span data-ttu-id="2c36a-149">Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Dll-Projekt kann dann mit kombiniert werden die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt (eine Projektmappe, die zwei Projekte enthält) – mit der rechten Maustaste auf die Projektmappe, wählen **hinzufügen\vorhandenes Projekt**.</span><span class="sxs-lookup"><span data-stu-id="2c36a-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>  
  
 <span data-ttu-id="2c36a-150">Verwendet werden soll, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Dll aus dem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] -Projekt müssen Sie einen Verweis hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="2c36a-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>  
  
1.  <span data-ttu-id="2c36a-151">Mit der rechten Maustaste win32clock-Projekt, und wählen Sie **Verweise...** .</span><span class="sxs-lookup"><span data-stu-id="2c36a-151">Right-click win32clock project and select **References...**.</span></span>  
  
2.  <span data-ttu-id="2c36a-152">Klicken Sie auf **neuen Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2c36a-152">Click **Add New Reference**.</span></span>  
  
3.  <span data-ttu-id="2c36a-153">Klicken Sie auf die Registerkarte **Projekte**.  Wählen Sie „WPFClock” aus und klicken Sie auf OK.</span><span class="sxs-lookup"><span data-stu-id="2c36a-153">Click the **Projects** tab.  Select WPFClock, click OK.</span></span>  
  
4.  <span data-ttu-id="2c36a-154">Klicken Sie auf **OK** um die win32clock-Eigenschaftenseiten zum Hinzufügen von Verweisen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="2c36a-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
## <a name="hwndsource"></a><span data-ttu-id="2c36a-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="2c36a-155">HwndSource</span></span>  
 <span data-ttu-id="2c36a-156">Verwenden Sie als Nächstes <xref:System.Windows.Interop.HwndSource> vornehmen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> ein HWND aussehen.</span><span class="sxs-lookup"><span data-stu-id="2c36a-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span>  <span data-ttu-id="2c36a-157">Sie fügen diesen Codeblock zu einer C++-Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="2c36a-157">You add this block of code to a C++ file:</span></span>  
  
```  
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
  
 <span data-ttu-id="2c36a-158">Dies ist ein langer Codeabschnitt, der einiger Erklärungen bedarf.</span><span class="sxs-lookup"><span data-stu-id="2c36a-158">This is a long piece of code that could use some explanation.</span></span>  <span data-ttu-id="2c36a-159">Der erste Teil besteht aus verschiedenen Klauseln, die dafür sorgen, dass nicht alle Aufrufe vollständig qualifiziert werden müssen:</span><span class="sxs-lookup"><span data-stu-id="2c36a-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 <span data-ttu-id="2c36a-160">Anschließend definieren Sie eine Funktion, die erstellt die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt, fügt ein <xref:System.Windows.Interop.HwndSource> Rand, und gibt den HWND zurück:</span><span class="sxs-lookup"><span data-stu-id="2c36a-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 <span data-ttu-id="2c36a-161">Erstellen Sie zunächst eine <xref:System.Windows.Interop.HwndSource>, denen von CreateWindow ähneln, deren Parameter:</span><span class="sxs-lookup"><span data-stu-id="2c36a-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>  
  
```  
HwndSource^ source = gcnew HwndSource(  
    0, // class style  
    WS_VISIBLE | WS_CHILD, // style  
    0, // exstyle  
    x, y, width, height,  
    "hi", // NAME  
    IntPtr(parent) // parent window   
    );  
```  
  
 <span data-ttu-id="2c36a-162">Anschließend Sie erstellen die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhaltsklasse, indem Sie ihren Konstruktor aufrufen:</span><span class="sxs-lookup"><span data-stu-id="2c36a-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 <span data-ttu-id="2c36a-163">Verbinden Sie Sie dann die Seite, um die <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="2c36a-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
source->RootVisual = page;  
```  
  
 <span data-ttu-id="2c36a-164">Und geben Sie in der letzten Zeile zurück HWND für den <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="2c36a-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a><span data-ttu-id="2c36a-165">Positionieren des HWND</span><span class="sxs-lookup"><span data-stu-id="2c36a-165">Positioning the Hwnd</span></span>  
 <span data-ttu-id="2c36a-166">Nun, Sie verfügen über ein HWND mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr, müssen Sie das HWND platziert die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="2c36a-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span>  <span data-ttu-id="2c36a-167">Wenn Sie wissen, dass nur, wo das HWND, nur übergeben Sie dessen Größe und Position, an die `GetHwnd` Funktion, die Sie zuvor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="2c36a-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span>  <span data-ttu-id="2c36a-168">Da Sie für die Definition des Dialogs aber eine Ressourcendatei verwendet haben, können Sie nicht sicher wissen, wo ein HWND jeweils platziert sein wird.</span><span class="sxs-lookup"><span data-stu-id="2c36a-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span>  <span data-ttu-id="2c36a-169">Können Sie die [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] Dialog-Editor Platzieren einer [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] statische steuern, in dem Sie die Uhr haben möchten ("Uhr hier einfügen"), und positionieren Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr.</span><span class="sxs-lookup"><span data-stu-id="2c36a-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>  
  
 <span data-ttu-id="2c36a-170">Bei der Sie WM_INITDIALOG handeln, verwenden Sie `GetDlgItem` das HWND für den Platzhalter statische abrufen:</span><span class="sxs-lookup"><span data-stu-id="2c36a-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 <span data-ttu-id="2c36a-171">Klicken Sie dann berechnet die Größe und Position des Platzhalters "STATIC", und Sie nehmen können die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Uhr an dieser Stelle:</span><span class="sxs-lookup"><span data-stu-id="2c36a-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>  
  
 <span data-ttu-id="2c36a-172">RECT rectangle;</span><span class="sxs-lookup"><span data-stu-id="2c36a-172">RECT rectangle;</span></span>  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 <span data-ttu-id="2c36a-173">Blenden Sie anschließen den Platzhalter „STATIC” aus:</span><span class="sxs-lookup"><span data-stu-id="2c36a-173">Then you hide the placeholder STATIC:</span></span>  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 <span data-ttu-id="2c36a-174">Und erstellen Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND an diesem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="2c36a-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 <span data-ttu-id="2c36a-175">Um das Tutorial etwas interessanter zu machen, und um eine echte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr, Sie benötigen zum Erstellen einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr-Steuerelement an diesem Punkt.</span><span class="sxs-lookup"><span data-stu-id="2c36a-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="2c36a-176">Den größten Teil davon können Sie in Markup erledigen, mit nur einigen wenigen Ereignishandlern im CodeBehind.</span><span class="sxs-lookup"><span data-stu-id="2c36a-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="2c36a-177">Da in diesem Tutorial zu Interoperabilität und Design von Steuerelementen beschäftigt ist, wird der vollständige Code für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr dient hier als Codeblock, ohne Einzelschritte Aufbau oder die Bedeutung der einzelnen Teile.</span><span class="sxs-lookup"><span data-stu-id="2c36a-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="2c36a-178">Experimentieren Sie ruhig mit diesem Code, um Aussehen, Verhalten oder Funktionalität des Steuerelements zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2c36a-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>  
  
 <span data-ttu-id="2c36a-179">Dies ist das Markup:</span><span class="sxs-lookup"><span data-stu-id="2c36a-179">Here is the markup:</span></span>  
  
 [!code-xaml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 <span data-ttu-id="2c36a-180">Und hier das zugehörige CodeBehind:</span><span class="sxs-lookup"><span data-stu-id="2c36a-180">And here is the accompanying code-behind:</span></span>  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 <span data-ttu-id="2c36a-181">Das Endergebnis sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="2c36a-181">The final result looks like:</span></span>  
  
 <span data-ttu-id="2c36a-182">![Dialogfeld Datums- und Uhrzeiteigenschaften](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")</span><span class="sxs-lookup"><span data-stu-id="2c36a-182">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")</span></span>  
  
 <span data-ttu-id="2c36a-183">Um Ihr Ergebnis mit den Code zu vergleichen, die diese Abbildung produzierte, finden Sie unter [Beispiel für die Interaktion von Win32-Uhr](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="2c36a-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c36a-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c36a-184">See also</span></span>
- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="2c36a-185">Interaktion zwischen WPF und Win32</span><span class="sxs-lookup"><span data-stu-id="2c36a-185">WPF and Win32 Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
- [<span data-ttu-id="2c36a-186">Beispiel für Interaktion mit der Win32-Uhr</span><span class="sxs-lookup"><span data-stu-id="2c36a-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
