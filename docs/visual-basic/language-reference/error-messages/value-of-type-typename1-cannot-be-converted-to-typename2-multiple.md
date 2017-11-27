---
title: Ein Wert vom Typ &#39; &lt;Typname1&gt;&#39; kann nicht konvertiert werden, um &#39;&lt; Typname2&gt;&#39; (Mehrere Dateiverweise)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords: BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cc6138c7a7ca7d50a56fdd1f536e8d2dc3462a08
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a><span data-ttu-id="c6c25-102">Ein Wert vom Typ &#39; &lt;Typname1&gt;&#39; kann nicht konvertiert werden, um &#39;&lt; Typname2&gt;&#39; (Mehrere Dateiverweise)</span><span class="sxs-lookup"><span data-stu-id="c6c25-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)</span></span>
<span data-ttu-id="c6c25-103">Wert vom Typ "\<Typname1 >' kann nicht konvertiert werden, um"\<Typname2 > ".</span><span class="sxs-lookup"><span data-stu-id="c6c25-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="c6c25-104">Typenkonflikt möglicherweise aufgrund eines Dateiverweises auf "\<dateipfad1 >' in-Projekt"\<projektname1 > "mit einem Dateiverweis auf"\<dateipfad2 >' in-Projekt "\<projektname2 >".</span><span class="sxs-lookup"><span data-stu-id="c6c25-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="c6c25-105">Wenn die beiden Assemblys identisch sind, ersetzen Sie die beiden Verweise durch Verweise vom gleichen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="c6c25-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="c6c25-106">In einer Situation, in denen ein Projekt mehr als einen Dateiverweis auf eine Assembly erstellt, wird, kann der Compiler nicht garantieren, einem Typ in einen anderen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c6c25-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="c6c25-107">Jeder Dateiverweis gibt einen Dateipfad und einen Namen für die Ausgabedatei eines Projekts (in der Regel eine DLL-Datei).</span><span class="sxs-lookup"><span data-stu-id="c6c25-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="c6c25-108">Der Compiler kann nicht garantieren, dass die Ausgabedateien aus der gleichen Quelle stammen oder dass sie die gleiche Version derselben Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="c6c25-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="c6c25-109">Es kann keine somit sicherstellen, dass die Typen in den verschiedenen verweisen identisch sind, oder auch, dass eine in den anderen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c6c25-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="c6c25-110">Wenn Sie wissen, dass die betreffenden Assemblys der gleichen Identität der Assembly, können Sie einen einzelnen Dateiverweis verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6c25-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="c6c25-111">Die *Identität der Assembly* enthält den Namen, die Version, ggf. den öffentlichen Schlüssel sowie die Kultur der Assembly.</span><span class="sxs-lookup"><span data-stu-id="c6c25-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="c6c25-112">Diese Information kennzeichnet die Assembly eindeutig.</span><span class="sxs-lookup"><span data-stu-id="c6c25-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="c6c25-113">**Fehler-ID:** BC30961</span><span class="sxs-lookup"><span data-stu-id="c6c25-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c6c25-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c6c25-114">To correct this error</span></span>  
  
-   <span data-ttu-id="c6c25-115">Wenn die betreffenden Assemblys der gleichen Identität der Assembly verfügen, entfernen Sie oder Ersetzen Sie eines der Dateiverweise, sodass nur ein einzelne Dateiverweis vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c6c25-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="c6c25-116">Wenn die referenzierten Assemblys nicht die Identität der gleichen Assembly verfügen, ändern Sie den Code, damit er nicht versucht, einen Typ in einem auf einen Typ in den anderen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="c6c25-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c25-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6c25-117">See Also</span></span>  
 [<span data-ttu-id="c6c25-118">Konvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c6c25-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="c6c25-119">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="c6c25-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="c6c25-120">NIB: Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds "Verweis hinzufügen"</span><span class="sxs-lookup"><span data-stu-id="c6c25-120">NIB How to: Add or Remove References By Using the Add Reference Dialog Box</span></span>](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
