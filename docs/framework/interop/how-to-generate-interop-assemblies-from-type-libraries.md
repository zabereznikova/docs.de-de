---
title: 'Vorgehensweise: Generieren von Interopassemblys aus Typbibliotheken'
description: Generieren Sie Interopassemblys aus Typbibliotheken. Konvertieren Sie mit dem Type Library Importer-Tool (Tlbimp.exe) Co-Klassen und Schnittstellen aus einer COM-Typbibliothek in Metadaten.
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
ms.openlocfilehash: 3146d607392a590974f452e06eb5a8b125e58e69
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236363"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a><span data-ttu-id="c5fc9-104">Vorgehensweise: Generieren von Interopassemblys aus Typbibliotheken</span><span class="sxs-lookup"><span data-stu-id="c5fc9-104">How to: Generate Interop Assemblies from Type Libraries</span></span>

<span data-ttu-id="c5fc9-105">[Type Library Importer (Tlbexp.exe)](../tools/tlbimp-exe-type-library-importer.md) ist ein Befehlszeilentool, das die Co-Klassen- und Schnittstellen einer COM-Typbibliothek in Metadaten konvertiert.</span><span class="sxs-lookup"><span data-stu-id="c5fc9-105">The [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) is a command-line tool that converts the coclasses and interfaces contained in a COM type library to metadata.</span></span> <span data-ttu-id="c5fc9-106">Dieses Tool erstellt automatisch eine Interop-Assembly und den Namespace für die Typinformationen.</span><span class="sxs-lookup"><span data-stu-id="c5fc9-106">This tool creates an interop assembly and namespace for the type information automatically.</span></span> <span data-ttu-id="c5fc9-107">Nachdem die Metadaten einer Klasse verfügbar sind, können verwaltete Clients Instanzen des COM-Typs erstellen und seine Methoden aufrufen, als ob es sich um eine .NET-Instanz handeln würde.</span><span class="sxs-lookup"><span data-stu-id="c5fc9-107">After the metadata of a class is available, managed clients can create instances of the COM type and call its methods, just as if it were a .NET instance.</span></span> <span data-ttu-id="c5fc9-108">„Tlbimp.exe“ konvertiert eine ganze Typbibliothek auf einmal in Metadaten und kann keine Typinformationen für eine Teilmenge der in einer Typbibliothek definierten Typen generieren.</span><span class="sxs-lookup"><span data-stu-id="c5fc9-108">Tlbimp.exe converts an entire type library to metadata at once and cannot generate type information for a subset of the types defined in a type library.</span></span>  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a><span data-ttu-id="c5fc9-109">Generieren einer Interop-Assembly aus einer Typbibliothek</span><span class="sxs-lookup"><span data-stu-id="c5fc9-109">To generate an interop assembly from a type library</span></span>  
  
1. <span data-ttu-id="c5fc9-110">Verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="c5fc9-110">Use the following command:</span></span>  
  
     <span data-ttu-id="c5fc9-111">**tlbimp** \<*type-library-file*></span><span class="sxs-lookup"><span data-stu-id="c5fc9-111">**tlbimp** \<*type-library-file*></span></span>  
  
     <span data-ttu-id="c5fc9-112">Das Hinzufügen des **/out:** -Schalters erzeugt eine Interop-Assembly mit einem geänderten Namen, z.B. „LOANLib.dll“.</span><span class="sxs-lookup"><span data-stu-id="c5fc9-112">Adding the **/out:** switch produces an interop assembly with an altered name, such as LOANLib.dll.</span></span> <span data-ttu-id="c5fc9-113">Das Ändern des Namens der Interop-Assembly kann dabei helfen, sie von der ursprünglichen COM-DLL zu unterscheiden und Probleme zu verhindern, die aufgrund der doppelten Namen auftreten können.</span><span class="sxs-lookup"><span data-stu-id="c5fc9-113">Altering the interop assembly name can help distinguish it from the original COM DLL and prevent problems that can occur from having duplicate names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5fc9-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5fc9-114">Example</span></span>  

 <span data-ttu-id="c5fc9-115">Der folgende Befehl erstellt die „Loanlib.dll“-Assembly im `Loanlib`-Namespace.</span><span class="sxs-lookup"><span data-stu-id="c5fc9-115">The following command produces the Loanlib.dll assembly in the `Loanlib` namespace.</span></span>  
  
```console  
tlbimp Loanlib.tlb  
```  
  
 <span data-ttu-id="c5fc9-116">Der folgende Befehl erzeugt eine Interop-Assembly mit einem geänderten Namen (LOANLib.dll).</span><span class="sxs-lookup"><span data-stu-id="c5fc9-116">The following command produces an interop assembly with an altered name (LOANLib.dll).</span></span>  
  
```console  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5fc9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5fc9-117">See also</span></span>

- [<span data-ttu-id="c5fc9-118">Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)</span><span class="sxs-lookup"><span data-stu-id="c5fc9-118">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="c5fc9-119">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c5fc9-119">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
