---
title: Interoperabilität – C#-Programmierhandbuch
description: Die Interoperabilität unterstützt zusätzlich zu unter der Common Language Runtime ausgeführtem Code auch nicht verwalteten Code. Diese Ressourcen bringen Ihnen die Interoperabilitätsoptionen näher.
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: d85eb51107d50e023270fcbe1ef6e08a7788ae78
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302970"
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="c4fc7-104">Interoperabilität (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c4fc7-104">Interoperability (C# Programming Guide)</span></span>

<span data-ttu-id="c4fc7-105">Interoperabilität ermöglicht es Ihnen, vorhandene Investitionen in nicht verwalteten Code zu schützen und weiter zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-105">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="c4fc7-106">Code, der unter der Steuerung der Common Language Runtime (CLR) ausgeführt wird, wird als *verwalteter Code* bezeichnet. Code, der außerhalb der CLR ausgeführt wird, wird als *nicht verwalteter Code* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-106">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="c4fc7-107">COM, COM+, C++-Komponenten, ActiveX-Komponenten und die Microsoft Windows-API sind Beispiele für nicht verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-107">COM, COM+, C++ components, ActiveX components, and Microsoft Windows API are examples of unmanaged code.</span></span>  
  
<span data-ttu-id="c4fc7-108">.NET ermöglicht Interoperabilität mit nicht verwaltetem Code über Plattformaufrufdienste, dem <xref:System.Runtime.InteropServices>-Namespace, C++-Interoperabilität und COM-Interoperabilität (COM-Interop).</span><span class="sxs-lookup"><span data-stu-id="c4fc7-108">.NET enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4fc7-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c4fc7-109">In This Section</span></span>  
 [<span data-ttu-id="c4fc7-110">Überblick über die Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="c4fc7-110">Interoperability Overview</span></span>](./interoperability-overview.md)  
 <span data-ttu-id="c4fc7-111">Dieser Artikel beschreibt Methoden zum Ermöglichen der Interoperabilität zwischen von C#-verwaltetem und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-111">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="c4fc7-112">Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen</span><span class="sxs-lookup"><span data-stu-id="c4fc7-112">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="c4fc7-113">Dieser Artikel beschreibt Funktionen, die in Visual C# zur Erleichterung der Office-Programmierung eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-113">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="c4fc7-114">Indizierte Eigenschaften bei der COM-Interop-Programmierung</span><span class="sxs-lookup"><span data-stu-id="c4fc7-114">How to use indexed properties in COM interop programming</span></span>](./how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="c4fc7-115">Dieser Artikel beschreibt die Verwendung von indizierten Eigenschaften zum Zugriff auf COM-Eigenschaften, die über Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-115">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="c4fc7-116">Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei</span><span class="sxs-lookup"><span data-stu-id="c4fc7-116">How to use platform invoke to play a WAV file</span></span>](./how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="c4fc7-117">Dieser Artikel beschreibt die Verwendung von Plattformaufrufdiensten zum Abspielen einer WAV-Audiodatei im Windows-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-117">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="c4fc7-118">Exemplarische Vorgehensweise: Office-Programmierung</span><span class="sxs-lookup"><span data-stu-id="c4fc7-118">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)  
 <span data-ttu-id="c4fc7-119">Dieser Artikel zeigt das Erstellen einer Excel-Arbeitsmappe und eines Word-Dokuments, das einen Link zur Arbeitsmappe enthält.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-119">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="c4fc7-120">COM-Beispielklasse</span><span class="sxs-lookup"><span data-stu-id="c4fc7-120">Example COM Class</span></span>](./example-com-class.md)  
 <span data-ttu-id="c4fc7-121">Dieser Artikel veranschaulicht, wie eine C#-Klasse als COM-Objekt verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-121">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c4fc7-122">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="c4fc7-122">C# Language Specification</span></span>  

<span data-ttu-id="c4fc7-123">Weitere Informationen finden Sie in den [grundlegenden Konzepten](~/_csharplang/spec/unsafe-code.md) und der[C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="c4fc7-123">For more information, see [Basic concepts](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="c4fc7-124">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-124">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c4fc7-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4fc7-125">See also</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c4fc7-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c4fc7-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c4fc7-127">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="c4fc7-127">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
- [<span data-ttu-id="c4fc7-128">Exemplarische Vorgehensweise: Office-Programmierung</span><span class="sxs-lookup"><span data-stu-id="c4fc7-128">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
