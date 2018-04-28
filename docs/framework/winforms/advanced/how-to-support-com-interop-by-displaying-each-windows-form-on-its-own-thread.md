---
title: 'Gewusst wie: Unterstützen von COM-Interop durch das Anzeigen einzelner Windows Forms in einem eigenen Thread'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- vb
helpviewer_keywords:
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: a9e04765-d2de-4389-a494-a9a6d07aa6ee
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f5d8a0351fc206aad9d88f9ca3f7c930ff853ff7
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread"></a><span data-ttu-id="c7a88-102">Gewusst wie: Unterstützen von COM-Interop durch das Anzeigen einzelner Windows Forms in einem eigenen Thread</span><span class="sxs-lookup"><span data-stu-id="c7a88-102">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>
<span data-ttu-id="c7a88-103">Sie können Probleme mit der COM-Interoperabilität beheben, indem Sie das Formular in einer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Nachrichtenschleife anzeigen, die Sie mit der <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>-Methode erstellen können. </span><span class="sxs-lookup"><span data-stu-id="c7a88-103">You can resolve COM interoperability problems by displaying your form on a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop, which you can create by using the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="c7a88-104">Damit ein Windows Form aus einer COM-Clientanwendung heraus ordnungsgemäß funktioniert, müssen Sie das Formular in einer Windows Forms-Nachrichtenschleife ausführen.</span><span class="sxs-lookup"><span data-stu-id="c7a88-104">To make a Windows Form work correctly from a COM client application, you must run the form on a Windows Forms message loop.</span></span> <span data-ttu-id="c7a88-105">Hierzu können Sie einen der folgenden Ansätze verwenden:</span><span class="sxs-lookup"><span data-stu-id="c7a88-105">To do this, use one of the following approaches:</span></span>  
  
-   <span data-ttu-id="c7a88-106">Verwenden Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>-Methode, um das Windows Form anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c7a88-106">Use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the Windows Form.</span></span> <span data-ttu-id="c7a88-107">Weitere Informationen finden Sie unter [How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md).</span><span class="sxs-lookup"><span data-stu-id="c7a88-107">For more information, see [How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md).</span></span>  
  
-   <span data-ttu-id="c7a88-108">Zeigen Sie jedes Windows Form in einem separaten Thread an.</span><span class="sxs-lookup"><span data-stu-id="c7a88-108">Display each Windows Form on a separate thread.</span></span>  
  
 <span data-ttu-id="c7a88-109">Es gibt umfassende Unterstützung für dieses Feature in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c7a88-109">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="c7a88-110">Siehe auch [Exemplarische Vorgehensweise: Unterstützen von COM-Interop durch das Anzeigen jedes Windows Forms in einem eigenen Thread](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="c7a88-110">Also see [Walkthrough: Supporting COM Interop by Displaying Each Windows Form on Its Own Thread](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7a88-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7a88-111">Example</span></span>  
 <span data-ttu-id="c7a88-112">Im folgenden Codebeispiel wird veranschaulicht, wie Sie das Formular über einen separaten Thread anzeigen und die <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>-Methode aufrufen, um ein Windows Forms-Nachrichtensystem über diesen Thread zu starten</span><span class="sxs-lookup"><span data-stu-id="c7a88-112">The following code example demonstrates how to display the form on a separate thread and call the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method to start a Windows Forms message pump on that thread.</span></span> <span data-ttu-id="c7a88-113">Um diesen Ansatz zu verwenden, müssen Sie jeden Aufruf des Formulars aus der nicht verwalteten Anwendung marshallen, indem Sie die <xref:System.Windows.Forms.Control.Invoke%2A> Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7a88-113">To use this approach, you must marshal any calls to the form from the unmanaged application by using the <xref:System.Windows.Forms.Control.Invoke%2A> method.</span></span>  
  
 <span data-ttu-id="c7a88-114">Dieser Ansatz erfordert, dass jede Instanz eines Formulars über ihren eigenen Thread ausgeführt wird, indem sie ihre eigene Nachrichtenschleife verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7a88-114">This approach requires that each instance of a form runs on its own thread by using its own message loop.</span></span> <span data-ttu-id="c7a88-115">Es ist nicht möglich, mehrere Nachrichtenschleifen pro Thread auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c7a88-115">You cannot have more than one message loop running per thread.</span></span> <span data-ttu-id="c7a88-116">Daher können Sie die Nachrichtenschleife der Clientanwendung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="c7a88-116">Therefore, you cannot change the client application's message loop.</span></span> <span data-ttu-id="c7a88-117">Sie können jedoch die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Komponente ändern, um einen neuen Thread zu beginnen, der seine eigene Nachrichtenschleife verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7a88-117">However, you can modify the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] component to start a new thread that uses its own message loop.</span></span>  
  
 [!code-vb[System.Windows.Forms.ComInterop#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/COMForm.vb#1)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/FormManager.vb#10)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c7a88-118">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c7a88-118">Compiling the Code</span></span>  
  
-   <span data-ttu-id="c7a88-119">Kompilieren Sie die Typen `COMForm`, `Form1`und `FormManager` in eine Assembly namens `COMWinform.dll`.</span><span class="sxs-lookup"><span data-stu-id="c7a88-119">Compile the `COMForm`, `Form1`, and `FormManager` types into an assembly called `COMWinform.dll`.</span></span> <span data-ttu-id="c7a88-120">Registrieren Sie die Assembly für COM-Interop, indem Sie eine der Methoden verwenden, die unter [Packaging an Assembly for COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md)beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="c7a88-120">Register the assembly for COM interop by using one of the methods described in [Packaging an Assembly for COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md).</span></span> <span data-ttu-id="c7a88-121">Sie können die Assembly und deren entsprechende Typbibliotheksdatei (.tlb) in nicht verwalteten Anwendungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7a88-121">You can now use the assembly and its corresponding type library (.tlb) file in unmanaged applications.</span></span> <span data-ttu-id="c7a88-122">Beispielsweise können Sie die Typbibliothek als Verweis in einem ausführbaren Visual Basic 6.0-Projekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7a88-122">For example, you can use the type library as a reference in a Visual Basic 6.0 executable project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a88-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7a88-123">See Also</span></span>  
 [<span data-ttu-id="c7a88-124">Verfügbarmachen von .NET Framework-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="c7a88-124">Exposing .NET Framework Components to COM</span></span>](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [<span data-ttu-id="c7a88-125">Verpacken einer Assembly für COM</span><span class="sxs-lookup"><span data-stu-id="c7a88-125">Packaging an Assembly for COM</span></span>](../../../../docs/framework/interop/packaging-an-assembly-for-com.md)  
 [<span data-ttu-id="c7a88-126">Registrieren von Assemblys bei COM</span><span class="sxs-lookup"><span data-stu-id="c7a88-126">Registering Assemblies with COM</span></span>](../../../../docs/framework/interop/registering-assemblies-with-com.md)  
 [<span data-ttu-id="c7a88-127">Gewusst wie: Unterstützen von COM-Interop durch Anzeigen eines Windows Forms mit der ShowDialog-Methode</span><span class="sxs-lookup"><span data-stu-id="c7a88-127">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 [<span data-ttu-id="c7a88-128">Übersicht über Windows Forms und nicht verwaltete Anwendungen</span><span class="sxs-lookup"><span data-stu-id="c7a88-128">Windows Forms and Unmanaged Applications Overview</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)
