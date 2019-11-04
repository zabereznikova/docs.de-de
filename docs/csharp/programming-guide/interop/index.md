---
title: Interoperabilität – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: 560218361f470266654734971a12de7862722a46
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423181"
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="9528e-102">Interoperabilität (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9528e-102">Interoperability (C# Programming Guide)</span></span>
<span data-ttu-id="9528e-103">Interoperabilität ermöglicht es Ihnen, vorhandene Investitionen in nicht verwalteten Code zu schützen und weiter zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="9528e-103">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="9528e-104">Code, der unter der Steuerung der Common Language Runtime (CLR) ausgeführt wird, wird als *verwalteter Code* bezeichnet. Code, der außerhalb der CLR ausgeführt wird, wird als *nicht verwalteter Code* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9528e-104">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="9528e-105">COM, COM+, C++-Komponenten, ActiveX-Komponenten und die Microsoft Windows-API sind Beispiele für nicht verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="9528e-105">COM, COM+, C++ components, ActiveX components, and Microsoft Windows API are examples of unmanaged code.</span></span>  
  
 <span data-ttu-id="9528e-106">.NET Framework ermöglicht Interoperabilität mit nicht verwaltetem Code über Plattformaufrufdienste, den <xref:System.Runtime.InteropServices>-Namespace, C++-Interoperabilität und COM-Interoperabilität (COM-Interop).</span><span class="sxs-lookup"><span data-stu-id="9528e-106">The .NET Framework enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9528e-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9528e-107">In This Section</span></span>  
 [<span data-ttu-id="9528e-108">Überblick über die Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="9528e-108">Interoperability Overview</span></span>](./interoperability-overview.md)  
 <span data-ttu-id="9528e-109">Dieser Artikel beschreibt Methoden zum Ermöglichen der Interoperabilität zwischen von C#-verwaltetem und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="9528e-109">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="9528e-110">Vorgehensweise: Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen</span><span class="sxs-lookup"><span data-stu-id="9528e-110">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](./how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="9528e-111">Dieser Artikel beschreibt Funktionen, die in Visual C# zur Erleichterung der Office-Programmierung eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="9528e-111">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="9528e-112">Vorgehensweise: Verwenden von indizierten Eigenschaften bei der COM-Interop-Programmierung</span><span class="sxs-lookup"><span data-stu-id="9528e-112">How to: Use Indexed Properties in COM Interop Programming</span></span>](./how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="9528e-113">Dieser Artikel beschreibt die Verwendung von indizierten Eigenschaften zum Zugriff auf COM-Eigenschaften, die über Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="9528e-113">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="9528e-114">Vorgehensweise: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei</span><span class="sxs-lookup"><span data-stu-id="9528e-114">How to: Use Platform Invoke to Play a Wave File</span></span>](./how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="9528e-115">Dieser Artikel beschreibt die Verwendung von Plattformaufrufdiensten zum Abspielen einer WAV-Audiodatei im Windows-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="9528e-115">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="9528e-116">Exemplarische Vorgehensweise: Office-Programmierung</span><span class="sxs-lookup"><span data-stu-id="9528e-116">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)  
 <span data-ttu-id="9528e-117">Dieser Artikel zeigt das Erstellen einer Excel-Arbeitsmappe und eines Word-Dokuments, das einen Link zur Arbeitsmappe enthält.</span><span class="sxs-lookup"><span data-stu-id="9528e-117">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="9528e-118">COM-Beispielklasse</span><span class="sxs-lookup"><span data-stu-id="9528e-118">Example COM Class</span></span>](./example-com-class.md)  
 <span data-ttu-id="9528e-119">Dieser Artikel veranschaulicht, wie eine C#-Klasse als COM-Objekt verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="9528e-119">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9528e-120">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="9528e-120">C# Language Specification</span></span>  

<span data-ttu-id="9528e-121">Weitere Informationen finden Sie in den [grundlegenden Konzepten](~/_csharplang/spec/unsafe-code.md) und der[C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="9528e-121">For more information, see [Basic concepts](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="9528e-122">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="9528e-122">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9528e-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9528e-123">See also</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9528e-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9528e-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9528e-125">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="9528e-125">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
- [<span data-ttu-id="9528e-126">Exemplarische Vorgehensweise: Office-Programmierung</span><span class="sxs-lookup"><span data-stu-id="9528e-126">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
