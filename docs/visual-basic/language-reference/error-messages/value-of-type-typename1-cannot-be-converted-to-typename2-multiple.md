---
title: Der Wert vom Typ '<typename1>' kann nicht in '<typename2>' konvertiert werden (Mehrere Dateiverweise)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 23c051e57014d7479d1c1c522b1a8da1ead52c19
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161386"
---
# <a name="bc30961-value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a><span data-ttu-id="ba4a5-102">BC30961: der Wert des Typs "" \<typename1> kann nicht in " \<typename2> " konvertiert werden (mehrere Datei Verweise).</span><span class="sxs-lookup"><span data-stu-id="ba4a5-102">BC30961: Value of type '\<typename1>' cannot be converted to '\<typename2>' (Multiple file references)</span></span>

<span data-ttu-id="ba4a5-103">Der Wert vom Typ "" \<typename1> kann nicht in " \<typename2> " konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="ba4a5-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="ba4a5-104">Typen Konflikt kann durch das Mischen eines Datei Verweises auf " \<filepath1> " in Projekt "" \<projectname1> mit einem Datei Verweis auf " \<filepath2> " in Projekt "" verursacht werden \<projectname2> .</span><span class="sxs-lookup"><span data-stu-id="ba4a5-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="ba4a5-105">Wenn die beiden Assemblys identisch sind, ersetzen Sie die beiden Verweise durch Verweise vom gleichen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="ba4a5-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>

 <span data-ttu-id="ba4a5-106">In einer Situation, in der ein Projekt mehr als einen Datei Verweis auf eine Assembly durchführt, kann der Compiler nicht garantieren, dass ein Typ in einen anderen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ba4a5-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>

 <span data-ttu-id="ba4a5-107">Jeder Datei Verweis gibt einen Dateipfad und-Namen für die Ausgabedatei eines Projekts an (in der Regel eine DLL-Datei).</span><span class="sxs-lookup"><span data-stu-id="ba4a5-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="ba4a5-108">Der Compiler kann nicht garantieren, dass die Ausgabedateien aus derselben Quelle stammen oder dass Sie dieselbe Version derselben Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="ba4a5-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="ba4a5-109">Daher kann nicht sichergestellt werden, dass die Typen in den verschiedenen verweisen denselben Typ aufweisen oder dass Sie in einen anderen konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="ba4a5-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>

 <span data-ttu-id="ba4a5-110">Sie können einen einzelnen Datei Verweis verwenden, wenn Sie wissen, dass die referenzierten Assemblys die gleiche Assemblyidentität aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ba4a5-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="ba4a5-111">Die *Assemblyidentität* enthält den Assemblynamen, die Version, den öffentlichen Schlüssel, sofern vorhanden, und die Kultur.</span><span class="sxs-lookup"><span data-stu-id="ba4a5-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="ba4a5-112">Diese Information kennzeichnet die Assembly eindeutig.</span><span class="sxs-lookup"><span data-stu-id="ba4a5-112">This information uniquely identifies the assembly.</span></span>

 <span data-ttu-id="ba4a5-113">**Fehler-ID:** BC30961</span><span class="sxs-lookup"><span data-stu-id="ba4a5-113">**Error ID:** BC30961</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ba4a5-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ba4a5-114">To correct this error</span></span>

- <span data-ttu-id="ba4a5-115">Wenn die Assemblys, auf die verwiesen wird, dieselbe Assemblyidentität aufweisen, entfernen oder ersetzen Sie einen der Datei Verweise, sodass es nur einen einzigen Datei Verweis gibt.</span><span class="sxs-lookup"><span data-stu-id="ba4a5-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>

- <span data-ttu-id="ba4a5-116">Wenn die Assemblys, auf die verwiesen wird, nicht die gleiche Assemblyidentität aufweisen, ändern Sie den Code so, dass er nicht versucht, einen Typ in einen Typ in einen anderen Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ba4a5-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba4a5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba4a5-117">See also</span></span>

- [<span data-ttu-id="ba4a5-118">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ba4a5-118">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="ba4a5-119">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="ba4a5-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
