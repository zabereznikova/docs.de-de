---
title: Der Wert vom Typ '<typename1>' kann nicht in '<typename2>' konvertiert werden (Mehrere Dateiverweise)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 58b334eb5e6db443bcfaba72729d59cb1d798e70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833528"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a><span data-ttu-id="9610e-102">Wert vom Typ "\<Typname1 >' kann nicht konvertiert werden, um"\<Typname2 >' (mehrere Dateiverweise)</span><span class="sxs-lookup"><span data-stu-id="9610e-102">Value of type '\<typename1>' cannot be converted to '\<typename2>' (Multiple file references)</span></span>
<span data-ttu-id="9610e-103">Wert vom Typ "\<Typname1 >' kann nicht konvertiert werden, um"\<Typname2 >'.</span><span class="sxs-lookup"><span data-stu-id="9610e-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="9610e-104">Typenkonflikt möglicherweise aufgrund eines Dateiverweises auf '\<dateipfad1 >' im Projekt "\<projektname1 >" mit einem Dateiverweis auf "\<dateipfad2 >' im Projekt"\<projektname2 > ".</span><span class="sxs-lookup"><span data-stu-id="9610e-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="9610e-105">Wenn die beiden Assemblys identisch sind, ersetzen Sie die beiden Verweise durch Verweise vom gleichen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="9610e-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="9610e-106">In einer Situation, in denen ein Projekt mehr als eine Datei auf eine Assembly verweist, garantiert der Compiler nicht, dass es sich bei einem Typ in einen anderen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9610e-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="9610e-107">Jeder Dateiverweis gibt einen Pfad und Name der Ausgabedatei eines Projekts (i. d. r. eine DLL-Datei).</span><span class="sxs-lookup"><span data-stu-id="9610e-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="9610e-108">Der Compiler garantieren nicht, dass die Ausgabedateien aus derselben Quelle stammen, oder, dass sie dieselbe Version derselben Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="9610e-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="9610e-109">Es kann nicht aus diesem Grund garantieren, dass die Typen in die verschiedenen Verweise desselben Typs, oder dass ein in den anderen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9610e-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="9610e-110">Sie können einen Einzeldatei-Verweis verwenden, wenn Sie wissen, dass die referenzierten Assemblys über dieselbe Assemblyidentität verfügen.</span><span class="sxs-lookup"><span data-stu-id="9610e-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="9610e-111">Die *Identität der Assembly* enthält den Namen, die Version, ggf. den öffentlichen Schlüssel sowie die Kultur der Assembly.</span><span class="sxs-lookup"><span data-stu-id="9610e-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="9610e-112">Diese Information kennzeichnet die Assembly eindeutig.</span><span class="sxs-lookup"><span data-stu-id="9610e-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="9610e-113">**Fehler-ID:** BC30961</span><span class="sxs-lookup"><span data-stu-id="9610e-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9610e-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9610e-114">To correct this error</span></span>  
  
-   <span data-ttu-id="9610e-115">Wenn die referenzierten Assemblys über dieselbe Assemblyidentität verfügen, entfernen Sie oder Ersetzen Sie einen der Dateiverweise, sodass nur ein einzelne Dateiverweis vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9610e-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="9610e-116">Wenn die referenzierten Assemblys nicht über dieselbe Assemblyidentität verfügen, ändern Sie den Code, damit es nicht versucht, einen Typ in einem auf einen Typ in der anderen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="9610e-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9610e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9610e-117">See also</span></span>

- [<span data-ttu-id="9610e-118">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9610e-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="9610e-119">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="9610e-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
