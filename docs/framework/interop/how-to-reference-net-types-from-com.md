---
title: 'Vorgehensweise: Verweisen auf .NET-Typen in COM'
description: Verweisen Sie auf .NET-Typen in COM. VB-Clients können ein .NET-Objekt im Objektbrowser anzeigen. C++-Clients müssen hingegen mit der Importanweisung \# auf eine TLB-Datei verweisen.
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
ms.openlocfilehash: f8d052c7b9bac9c4bab61ab1950e9e89a7c73912
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618960"
---
# <a name="how-to-reference-net-types-from-com"></a><span data-ttu-id="f04f5-104">Vorgehensweise: Verweisen auf .NET-Typen in COM</span><span class="sxs-lookup"><span data-stu-id="f04f5-104">How to: Reference .NET Types from COM</span></span>
<span data-ttu-id="f04f5-105">Hinsichtlich Clientcode und Servercode bestehen kaum Unterschiede zwischen COM und .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f04f5-105">From the point of view of client and server code, the differences between COM and the .NET Framework are largely invisible.</span></span> <span data-ttu-id="f04f5-106">Microsoft Visual Basic-Clients können ein .NET-Objekt im Objektkatalog anzeigen. Dort werden Objektmethoden und –syntax sowie Eigenschaften und Felder in gleicher Weise angegeben wie für ein beliebiges anderes COM-Objekt.</span><span class="sxs-lookup"><span data-stu-id="f04f5-106">Microsoft Visual Basic clients can view a .NET object in the object browser, which exposes the object methods and syntax, properties, and fields exactly as if it were any other COM object.</span></span>  
  
 <span data-ttu-id="f04f5-107">Der Prozess zum Importieren einer Typbibliothek ist etwas komplizierter für C++-Clients, obwohl dieselben Tools verwendet werden wie beim Exportieren von Metadaten in eine COM-Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="f04f5-107">The process for importing a type library is slightly more complicated for C++ clients, although you use the same tools to export metadata to a COM type library.</span></span> <span data-ttu-id="f04f5-108">Zum Verweisen auf .NET-Objektmember von einem nicht verwalteten C++-Client aus verweisen Sie auf die TLB-Datei (die mit Tlbexp.exe erstellt wurde) mit der **#import**-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f04f5-108">To reference .NET object members from an unmanaged C++ client, reference the TLB file (produced with Tlbexp.exe) with the **#import** directive.</span></span> <span data-ttu-id="f04f5-109">Zum Verweisen auf eine Typbibliothek von C++ müssen Sie entweder die **raw_interfaces_only**-Option angeben oder die Definitionen in die Basisklassenbibliothek Mscorlib.tlb importieren.</span><span class="sxs-lookup"><span data-stu-id="f04f5-109">When referencing a type library from C++, you must either specify the **raw_interfaces_only** option or import the definitions in the base class library, Mscorlib.tlb.</span></span>  
  
### <a name="to-import-a-library"></a><span data-ttu-id="f04f5-110">So importieren Sie eine Bibliothek</span><span class="sxs-lookup"><span data-stu-id="f04f5-110">To import a library</span></span>  
  
- <span data-ttu-id="f04f5-111">Geben Sie die **raw_interfaces_only**-Option in der **#import**-Anweisung an.</span><span class="sxs-lookup"><span data-stu-id="f04f5-111">Specify the **raw_interfaces_only** option in the **#import** directive.</span></span> <span data-ttu-id="f04f5-112">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f04f5-112">For example:</span></span>  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     <span data-ttu-id="f04f5-113">- oder -</span><span class="sxs-lookup"><span data-stu-id="f04f5-113">-or-</span></span>  
  
- <span data-ttu-id="f04f5-114">Schließen Sie eine #import-Anweisung für Mscorlib.tlb ein.</span><span class="sxs-lookup"><span data-stu-id="f04f5-114">Include an #import directive for Mscorlib.tlb.</span></span> <span data-ttu-id="f04f5-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f04f5-115">For example:</span></span>  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f04f5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f04f5-116">See also</span></span>

- [<span data-ttu-id="f04f5-117">Verfügbarmachen von .NET Framework-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="f04f5-117">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="f04f5-118">Registrieren von Assemblys bei COM</span><span class="sxs-lookup"><span data-stu-id="f04f5-118">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="f04f5-119">[Aufrufen eines .NET-Objekts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f04f5-119">[Calling a .NET Object](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span></span>
- <span data-ttu-id="f04f5-120">[Deploying an Application for COM Access (Bereitstellen einer Anwendung für COM-Zugriff)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f04f5-120">[Deploying an Application for COM Access](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span></span>
