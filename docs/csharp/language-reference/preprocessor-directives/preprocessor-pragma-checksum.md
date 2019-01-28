---
title: '#pragma-Prüfsumme – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: c52e93bcf5771fe556730a1d7cf45b8f1c9432b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513021"
---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="03bbf-102">#pragma checksum (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="03bbf-102">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="03bbf-103">Erstellt für Quelldateien Prüfsummen, um beim Debuggen von [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]-Seiten zu helfen.</span><span class="sxs-lookup"><span data-stu-id="03bbf-103">Generates checksums for source files to aid with debugging [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03bbf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03bbf-104">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03bbf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="03bbf-105">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="03bbf-106">Der Name der Datei, die die Überwachung von Änderungen oder Updates erfordert</span><span class="sxs-lookup"><span data-stu-id="03bbf-106">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="03bbf-107">GUID (Globally Unique Identifier, globaler eindeutiger Bezeichner) für den Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="03bbf-107">The Globally Unique Identifier (GUID) for the hash algorithm.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="03bbf-108">Die Zeichenfolge von hexadezimalen Ziffern, die die Bytes der Prüfsumme darstellt.</span><span class="sxs-lookup"><span data-stu-id="03bbf-108">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="03bbf-109">Dabei muss es sich um eine gerade Anzahl hexadezimaler Ziffern handeln.</span><span class="sxs-lookup"><span data-stu-id="03bbf-109">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="03bbf-110">Eine ungerade Anzahl von Ziffern führt zu einer Warnung zur Kompilierzeit, und die Anweisung wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="03bbf-110">An odd number of digits results in a compile-time warning, and the directive are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03bbf-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03bbf-111">Remarks</span></span>  
 <span data-ttu-id="03bbf-112">Der Visual Studio-Debugger verwendet eine Prüfsumme, um sicherzustellen, dass immer die richtige Quelle gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="03bbf-112">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="03bbf-113">Der Compiler berechnet die Prüfsumme für eine Quelldatei, und speichert das Ergebnis in der Program Database-Datei (PDB).</span><span class="sxs-lookup"><span data-stu-id="03bbf-113">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="03bbf-114">Der Debugger verwendet anschließend die PDB-Datei, um sie mit der Prüfsumme zu vergleichen, die für die Quelldatei berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="03bbf-114">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="03bbf-115">Diese Lösung funktioniert nicht bei [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]-Projekten, weil die berechnete Prüfsumme für die generierte Quelldatei anstatt für die ASPX-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="03bbf-115">This solution does not work for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="03bbf-116">`#pragma checksum` stellt für [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]-Seiten Unterstützung von Prüfsummen bereit, um dieses Problem zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="03bbf-116">To address this problem, `#pragma checksum` provides checksum support for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
 <span data-ttu-id="03bbf-117">Wenn Sie ein [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]-Projekt in Visual C# erstellen, enthält die generierte Quelldatei eine Prüfsumme für die ASPX-Datei, von der die Quelle erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="03bbf-117">When you create an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] project in Visual C#, the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="03bbf-118">Der Compiler schreibt anschließend diese Informationen in die PDB-Datei.</span><span class="sxs-lookup"><span data-stu-id="03bbf-118">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="03bbf-119">Wenn der Compiler keine `#pragma checksum`-Direktive in der Datei findet, berechnet er die Prüfsumme und schreibt den Wert in die PDB-Datei.</span><span class="sxs-lookup"><span data-stu-id="03bbf-119">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03bbf-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03bbf-120">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="03bbf-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03bbf-121">See also</span></span>

- [<span data-ttu-id="03bbf-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="03bbf-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="03bbf-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="03bbf-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="03bbf-124">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="03bbf-124">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
