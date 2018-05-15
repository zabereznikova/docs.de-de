---
title: Windows Forms und nicht verwaltete Anwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: c51645fb64f512b5974000f89e8e98f884a7381d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-and-unmanaged-applications"></a><span data-ttu-id="5e2b8-102">Windows Forms und nicht verwaltete Anwendungen</span><span class="sxs-lookup"><span data-stu-id="5e2b8-102">Windows Forms and Unmanaged Applications</span></span>
<span data-ttu-id="5e2b8-103">Windows Forms-Anwendungen und-Steuerelemente können mit einigen Einschränkungen mit nicht verwalteten Anwendungen zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-103">Windows Forms applications and controls can interoperate with unmanaged applications, with some caveats.</span></span> <span data-ttu-id="5e2b8-104">In den folgenden Abschnitten werden die von Windows Forms-Anwendungen und -Steuerelementen unterstützten und nicht unterstützten Szenarien und Konfigurationen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-104">The following sections describe the scenarios and configurations that Windows Forms applications and controls support and those that they do not support.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e2b8-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5e2b8-105">In This Section</span></span>  
 [<span data-ttu-id="5e2b8-106">Übersicht über Windows Forms und nicht verwaltete Anwendungen</span><span class="sxs-lookup"><span data-stu-id="5e2b8-106">Windows Forms and Unmanaged Applications Overview</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)  
 <span data-ttu-id="5e2b8-107">Bietet allgemeine Informationen zur Verwendung und Implementierung von Windows Forms-Steuerelementen, die in nicht verwalteten Anwendungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-107">Offers general information about how to use and implement Windows Forms controls that work with unmanaged applications.</span></span>  
  
 [<span data-ttu-id="5e2b8-108">Gewusst wie: Unterstützen von COM-Interop durch Anzeigen eines Windows Forms mit der ShowDialog-Methode</span><span class="sxs-lookup"><span data-stu-id="5e2b8-108">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 <span data-ttu-id="5e2b8-109">Enthält ein Codebeispiel für die Verwendung der <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>-Methode zum Ausführen eines Windows Forms in einer nicht verwalteten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-109">Provides a code example that shows how to use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to run a Windows Form in an unmanaged application.</span></span>  
  
 [<span data-ttu-id="5e2b8-110">Vorgehensweise: Unterstützen von COM-Interop durch Anzeigen jedes Windows Forms in einem eigenen Thread</span><span class="sxs-lookup"><span data-stu-id="5e2b8-110">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 <span data-ttu-id="5e2b8-111">Enthält ein Codebeispiel für die Ausführung eines Windows Forms in einem eigenen Thread.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-111">Provides a code example that shows how to run a Windows Form on its own thread.</span></span>  
  
 <span data-ttu-id="5e2b8-112">Siehe auch [Exemplarische Vorgehensweise: Unterstützen von COM-Interop durch das Anzeigen jedes Windows Forms in einem eigenen Thread](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="5e2b8-112">Also see [Walkthrough: Supporting COM Interop by Displaying Each Windows Form on Its Own Thread](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5e2b8-113">Referenz</span><span class="sxs-lookup"><span data-stu-id="5e2b8-113">Reference</span></span>  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 <span data-ttu-id="5e2b8-114">Wird zum Erstellen eines separaten Threads für ein Windows Form verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-114">Used to create a separate thread for a Windows Form.</span></span>  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 <span data-ttu-id="5e2b8-115">Startet eine Nachrichtenschleife für einen Thread.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-115">Starts a message loop for a thread.</span></span>  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 <span data-ttu-id="5e2b8-116">Marshallt Aufrufe von einer nicht verwalteten Anwendung für ein Formular.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-116">Marshals calls from an unmanaged application to a form.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5e2b8-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="5e2b8-117">Related Sections</span></span>  
 [<span data-ttu-id="5e2b8-118">Verfügbarmachen von .NET Framework-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="5e2b8-118">Exposing .NET Framework Components to COM</span></span>](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="5e2b8-119">Bietet allgemeine Informationen zur Verwendung von .NET Framework-Typen in nicht verwalteten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-119">Offers general information about how to use .NET Framework types in unmanaged applications.</span></span>
