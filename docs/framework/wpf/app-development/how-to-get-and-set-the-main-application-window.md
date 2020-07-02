---
title: 'Gewusst wie: Einrichten und Festlegen des Haupt Anwendungsfensters'
description: Verwenden Sie dieses Beispiel, um das Hauptanwendungsfenster in Windows Presentation Foundation (WPF)-Anwendung zu erhalten und festzulegen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
ms.openlocfilehash: 9bb5bce9b90482796acd8c62e77dc8bd9a850eeb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622678"
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="921d3-103">Gewusst wie: Einrichten und Festlegen des Haupt Anwendungsfensters</span><span class="sxs-lookup"><span data-stu-id="921d3-103">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="921d3-104">In diesem Beispiel wird gezeigt, wie das Hauptanwendungsfenster von Get und festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="921d3-104">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="921d3-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="921d3-105">Example</span></span>  
 <span data-ttu-id="921d3-106">Der erste <xref:System.Windows.Window> , der in einer Windows Presentation Foundation (WPF)-Anwendung instanziiert wird, wird von automatisch <xref:System.Windows.Application> als Hauptanwendungsfenster festgelegt.</span><span class="sxs-lookup"><span data-stu-id="921d3-106">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="921d3-107">Der erste <xref:System.Windows.Window> zu instanziierte ist wahrscheinlich das Fenster, das als URI (Uniform Resource Identifier) für den Startup angegeben wird (siehe <xref:System.Windows.Application.StartupUri%2A> ).</span><span class="sxs-lookup"><span data-stu-id="921d3-107">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup uniform resource identifier (URI) (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="921d3-108">Der erste <xref:System.Windows.Window> kann auch mit Code instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="921d3-108">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="921d3-109">Ein Beispiel ist das Öffnen eines Fensters während des Anwendungs Starts, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="921d3-109">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="921d3-110">Manchmal ist die erste instanziierte <xref:System.Windows.Window> nicht tatsächlich das Hauptanwendungsfenster, z. b. ein Begrüßungsbildschirm.</span><span class="sxs-lookup"><span data-stu-id="921d3-110">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="921d3-111">In diesem Fall können Sie das Hauptanwendungsfenster mithilfe von Markup angeben, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="921d3-111">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="921d3-112">Unabhängig davon, ob das Hauptfenster automatisch oder manuell angegeben wird, können Sie das Hauptfenster <xref:System.Windows.Application.MainWindow%2A> wie folgt aus dem folgenden Code verwenden:</span><span class="sxs-lookup"><span data-stu-id="921d3-112">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
