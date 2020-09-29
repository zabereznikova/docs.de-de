---
description: '#pragma-Prüfsumme – C#-Referenz'
title: '#pragma-Prüfsumme – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: df665704ac813adbbf6473e81fad0a1c7ff616d0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168568"
---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="47eed-103">#pragma checksum (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="47eed-103">#pragma checksum (C# Reference)</span></span>

<span data-ttu-id="47eed-104">Erstellt für Quelldateien Prüfsummen, um beim Debuggen von ASP.NET-Seiten zu helfen.</span><span class="sxs-lookup"><span data-stu-id="47eed-104">Generates checksums for source files to aid with debugging ASP.NET pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47eed-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="47eed-105">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
## <a name="parameters"></a><span data-ttu-id="47eed-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="47eed-106">Parameters</span></span>  

 `"filename"`  
 <span data-ttu-id="47eed-107">Der Name der Datei, die die Überwachung von Änderungen oder Updates erfordert</span><span class="sxs-lookup"><span data-stu-id="47eed-107">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="47eed-108">GUID (Globally Unique Identifier, globaler eindeutiger Bezeichner) für den Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="47eed-108">The Globally Unique Identifier (GUID) for the hash algorithm.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="47eed-109">Die Zeichenfolge von hexadezimalen Ziffern, die die Bytes der Prüfsumme darstellt.</span><span class="sxs-lookup"><span data-stu-id="47eed-109">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="47eed-110">Dabei muss es sich um eine gerade Anzahl hexadezimaler Ziffern handeln.</span><span class="sxs-lookup"><span data-stu-id="47eed-110">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="47eed-111">Eine ungerade Anzahl von Ziffern führt zu einer Warnung zur Kompilierzeit, und die Anweisung wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="47eed-111">An odd number of digits results in a compile-time warning, and the directive are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47eed-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="47eed-112">Remarks</span></span>  

 <span data-ttu-id="47eed-113">Der Visual Studio-Debugger verwendet eine Prüfsumme, um sicherzustellen, dass immer die richtige Quelle gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="47eed-113">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="47eed-114">Der Compiler berechnet die Prüfsumme für eine Quelldatei, und speichert das Ergebnis in der Program Database-Datei (PDB).</span><span class="sxs-lookup"><span data-stu-id="47eed-114">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="47eed-115">Der Debugger verwendet anschließend die PDB-Datei, um sie mit der Prüfsumme zu vergleichen, die für die Quelldatei berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="47eed-115">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="47eed-116">Diese Lösung funktioniert nicht bei ASP.NET-Projekten, weil die berechnete Prüfsumme für die generierte Quelldatei und nicht für die ASPX-Datei gilt.</span><span class="sxs-lookup"><span data-stu-id="47eed-116">This solution does not work for ASP.NET projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="47eed-117">`#pragma checksum` stellt für ASP.NET-Seiten Unterstützung von Prüfsummen bereit, um dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="47eed-117">To address this problem, `#pragma checksum` provides checksum support for ASP.NET pages.</span></span>  
  
 <span data-ttu-id="47eed-118">Wenn Sie ein ASP.NET-Projekt in Visual C# erstellen, enthält die generierte Quelldatei eine Prüfsumme für die ASPX-Datei, von der die Quelle generiert wird.</span><span class="sxs-lookup"><span data-stu-id="47eed-118">When you create an ASP.NET project in Visual C#, the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="47eed-119">Der Compiler schreibt anschließend diese Informationen in die PDB-Datei.</span><span class="sxs-lookup"><span data-stu-id="47eed-119">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="47eed-120">Wenn der Compiler keine `#pragma checksum`-Direktive in der Datei findet, berechnet er die Prüfsumme und schreibt den Wert in die PDB-Datei.</span><span class="sxs-lookup"><span data-stu-id="47eed-120">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47eed-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="47eed-121">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="47eed-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47eed-122">See also</span></span>

- [<span data-ttu-id="47eed-123">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="47eed-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="47eed-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="47eed-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="47eed-125">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="47eed-125">C# Preprocessor Directives</span></span>](./index.md)
