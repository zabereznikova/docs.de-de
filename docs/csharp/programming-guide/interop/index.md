---
title: Interoperabilität (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: e854c51bd80809b92bb538475a407422b2eba7c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="c3afc-102">Interoperabilität (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c3afc-102">Interoperability (C# Programming Guide)</span></span>
<span data-ttu-id="c3afc-103">Interoperabilität ermöglicht es Ihnen, vorhandene Investitionen in nicht verwalteten Code zu schützen und weiter zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="c3afc-103">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="c3afc-104">Code, der unter der Steuerung der Common Language Runtime (CLR) ausgeführt wird, wird als *verwalteter Code* bezeichnet. Code, der außerhalb der CLR ausgeführt wird, wird als *nicht verwalteter Code* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c3afc-104">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="c3afc-105">COM, COM+, C++-Komponenten, ActiveX-Komponenten und die Microsoft Win32-API sind Beispiele für nicht verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="c3afc-105">COM, COM+, C++ components, ActiveX components, and Microsoft Win32 API are examples of unmanaged code.</span></span>  
  
 <span data-ttu-id="c3afc-106">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ermöglicht Interoperabilität mit nicht verwaltetem Code über Plattformaufrufdienste, den <xref:System.Runtime.InteropServices>-Namespace, C++-Interoperabilität und COM-Interoperabilität (COM-Interop).</span><span class="sxs-lookup"><span data-stu-id="c3afc-106">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3afc-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c3afc-107">In This Section</span></span>  
 [<span data-ttu-id="c3afc-108">Überblick über die Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="c3afc-108">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 <span data-ttu-id="c3afc-109">Dieser Artikel beschreibt Methoden zum Ermöglichen der Interoperabilität zwischen von C#-verwaltetem und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="c3afc-109">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="c3afc-110">Gewusst wie: Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen</span><span class="sxs-lookup"><span data-stu-id="c3afc-110">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="c3afc-111">Dieser Artikel beschreibt Funktionen, die in Visual C# zur Erleichterung der Office-Programmierung eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="c3afc-111">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="c3afc-112">Gewusst wie: Indizierte Eigenschaften bei der COM-Interop-Programmierung</span><span class="sxs-lookup"><span data-stu-id="c3afc-112">How to: Use Indexed Properties in COM Interop Programming</span></span>](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="c3afc-113">Dieser Artikel beschreibt die Verwendung von indizierten Eigenschaften zum Zugriff auf COM-Eigenschaften, die über Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="c3afc-113">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="c3afc-114">Gewusst wie: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei</span><span class="sxs-lookup"><span data-stu-id="c3afc-114">How to: Use Platform Invoke to Play a Wave File</span></span>](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="c3afc-115">Dieser Artikel beschreibt die Verwendung von Plattformaufrufdiensten zum Abspielen einer WAV-Audiodatei im Windows-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="c3afc-115">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="c3afc-116">Exemplarische Vorgehensweise: Office-Programmierung</span><span class="sxs-lookup"><span data-stu-id="c3afc-116">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)  
 <span data-ttu-id="c3afc-117">Dieser Artikel zeigt das Erstellen einer Excel-Arbeitsmappe und eines Word-Dokuments, das einen Link zur Arbeitsmappe enthält.</span><span class="sxs-lookup"><span data-stu-id="c3afc-117">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="c3afc-118">COM-Beispielklasse</span><span class="sxs-lookup"><span data-stu-id="c3afc-118">Example COM Class</span></span>](../../../csharp/programming-guide/interop/example-com-class.md)  
 <span data-ttu-id="c3afc-119">Dieser Artikel veranschaulicht, wie eine C#-Klasse als COM-Objekt verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="c3afc-119">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c3afc-120">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="c3afc-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c3afc-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3afc-121">See Also</span></span>  
 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="c3afc-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c3afc-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c3afc-123">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="c3afc-123">Interoperating with Unmanaged Code</span></span>](../../../../docs/framework/interop/index.md)  
 [<span data-ttu-id="c3afc-124">Exemplarische Vorgehensweise: Office-Programmierung</span><span class="sxs-lookup"><span data-stu-id="c3afc-124">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
