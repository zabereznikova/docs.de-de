---
title: 'Gewusst wie: Einrichten und Festlegen des Haupt Anwendungsfensters'
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
ms.openlocfilehash: 5894761c4b6258cbf90d369a722ffc5abca51885
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582548"
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="b009a-102">Gewusst wie: Einrichten und Festlegen des Haupt Anwendungsfensters</span><span class="sxs-lookup"><span data-stu-id="b009a-102">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="b009a-103">In diesem Beispiel wird gezeigt, wie das Hauptanwendungsfenster von Get und festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="b009a-103">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b009a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b009a-104">Example</span></span>  
 <span data-ttu-id="b009a-105">Der erste <xref:System.Windows.Window>, der in einer Windows Presentation Foundation (WPF)-Anwendung instanziiert wird, wird automatisch von <xref:System.Windows.Application> als Hauptanwendungsfenster festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b009a-105">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="b009a-106">Der erste <xref:System.Windows.Window>, der instanziiert werden soll, ist wahrscheinlich das Fenster, das als URI (Uniform Resource Identifier) für den Startup angegeben wird (siehe <xref:System.Windows.Application.StartupUri%2A>).</span><span class="sxs-lookup"><span data-stu-id="b009a-106">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup uniform resource identifier (URI) (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="b009a-107">Der erste <xref:System.Windows.Window> kann auch mit Code instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="b009a-107">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="b009a-108">Ein Beispiel ist das Öffnen eines Fensters während des Anwendungs Starts, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b009a-108">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="b009a-109">Manchmal ist die erste instanziierte <xref:System.Windows.Window> nicht das Hauptanwendungsfenster, z. b. ein Begrüßungsbildschirm.</span><span class="sxs-lookup"><span data-stu-id="b009a-109">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="b009a-110">In diesem Fall können Sie das Hauptanwendungsfenster mithilfe von Markup angeben, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b009a-110">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="b009a-111">Unabhängig davon, ob das Hauptfenster automatisch oder manuell angegeben wird, können Sie das Hauptfenster aus <xref:System.Windows.Application.MainWindow%2A> mit dem folgenden Code erhalten, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b009a-111">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
