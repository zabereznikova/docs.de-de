---
title: Wert des Typs &quot;&lt;&quot;Typname1&quot;&gt;&quot;kann nicht konvertiert werden&quot;&lt;typename2&gt;&quot;(mehrere Dateiverweise) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
dev_langs:
- VB
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 299cc4bec00a4597a661c5da49135fe3b5357537
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a><span data-ttu-id="ab592-102">Wert des Typs '&lt;"Typname1"&gt;"kann nicht konvertiert werden"&lt;typename2&gt;"(mehrere Dateiverweise)</span><span class="sxs-lookup"><span data-stu-id="ab592-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)</span></span>
<span data-ttu-id="ab592-103">Wert des Typs '\<"Typname1" >' kann nicht konvertiert werden "\<typename2 >'.</span><span class="sxs-lookup"><span data-stu-id="ab592-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="ab592-104">Typenkonflikt möglicherweise aufgrund eines Dateiverweises auf '\<filepath1 > "im Projekt"\<projectname1 >' mit einem Verweis auf "\<filepath2 >" im Projekt "\<projectname2 >'.</span><span class="sxs-lookup"><span data-stu-id="ab592-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="ab592-105">Wenn die beiden Assemblys identisch sind, ersetzen Sie die beiden Verweise durch Verweise vom gleichen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="ab592-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="ab592-106">Ein Projekt mehr als ein Verweis auf eine Assembly enthält, kann der Compiler, dass ein Typ in einen anderen konvertiert werden kann nicht gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="ab592-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="ab592-107">Jeder Dateiverweis gibt einen Dateipfad und-Name für die Ausgabedatei eines Projekts (in der Regel eine DLL-Datei).</span><span class="sxs-lookup"><span data-stu-id="ab592-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="ab592-108">Der Compiler kann nicht garantieren, dass die Ausgabedateien aus derselben Quelle stammen, oder dass sie die gleiche Version derselben Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="ab592-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="ab592-109">Es kann nicht deshalb sicherstellen, dass die Typen in den verschiedenen verweisen, vom gleichen Typ sind, oder auch, dass eine in den anderen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ab592-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="ab592-110">Sie können einen einzigen Dateiverweis verwenden, wenn Sie wissen, dass die referenzierten Assemblys dieselbe Assemblyidentität.</span><span class="sxs-lookup"><span data-stu-id="ab592-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="ab592-111">Die *Identität der Assembly* enthält den Namen, die Version, ggf. den öffentlichen Schlüssel sowie die Kultur der Assembly.</span><span class="sxs-lookup"><span data-stu-id="ab592-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="ab592-112">Diese Information kennzeichnet die Assembly eindeutig.</span><span class="sxs-lookup"><span data-stu-id="ab592-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="ab592-113">**Fehler-ID:** BC30961</span><span class="sxs-lookup"><span data-stu-id="ab592-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ab592-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ab592-114">To correct this error</span></span>  
  
-   <span data-ttu-id="ab592-115">Wenn die referenzierten Assemblys dieselbe Assemblyidentität verfügen, entfernen Sie oder Ersetzen Sie eines der Dateiverweise, sodass nur ein einzelne Dateiverweis vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ab592-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="ab592-116">Wenn die referenzierten Assemblys nicht dieselbe Assemblyidentität verfügen, ändern Sie den Code, damit es nicht versucht, einen Typ in einem auf einen Typ in den anderen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ab592-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab592-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab592-117">See Also</span></span>  
 <span data-ttu-id="ab592-118">[Typumwandlungen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="ab592-118">[Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="ab592-119"> [Verwalten von Verweise in einem Projekt](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="ab592-119"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="ab592-120"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box (Vorgehensweise: Hinzufügen und Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“)](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span><span class="sxs-lookup"><span data-stu-id="ab592-120"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span></span>
