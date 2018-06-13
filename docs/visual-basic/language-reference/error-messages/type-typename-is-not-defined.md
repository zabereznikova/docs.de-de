---
title: Typ &#39; &lt;Typename&gt; &#39; ist nicht definiert
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 20f36a06000d0197ad80b83766f6612a474d5758
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595185"
---
# <a name="type-39lttypenamegt39-is-not-defined"></a><span data-ttu-id="d0508-102">Typ &#39; &lt;Typename&gt; &#39; ist nicht definiert</span><span class="sxs-lookup"><span data-stu-id="d0508-102">Type &#39;&lt;typename&gt;&#39; is not defined</span></span>
<span data-ttu-id="d0508-103">Die Anweisung machte Verweis auf einen Typ, der nicht definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d0508-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="d0508-104">Sie können einen Typ wie z. B. in einer deklarationsanweisung definieren `Enum`, `Structure`, `Class`, oder `Interface`.</span><span class="sxs-lookup"><span data-stu-id="d0508-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="d0508-105">**Fehler-ID:** BC30002</span><span class="sxs-lookup"><span data-stu-id="d0508-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d0508-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d0508-106">To correct this error</span></span>  
  
-   <span data-ttu-id="d0508-107">Stellen Sie sicher, dass die Typdefinition und dessen Verweis beide die gleiche Schreibweise verwenden.</span><span class="sxs-lookup"><span data-stu-id="d0508-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
-   <span data-ttu-id="d0508-108">Stellen Sie sicher, dass die Typdefinition für den Verweis zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="d0508-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="d0508-109">Wenn der Typ befindet sich in einem anderen Modul und deklariert wurde, z. B. `Private`, verschieben Sie die Typdefinition in das Verweismodul oder deklarieren Sie es `Public`.</span><span class="sxs-lookup"><span data-stu-id="d0508-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
-   <span data-ttu-id="d0508-110">Stellen Sie sicher, dass der Namespace des Typs nicht innerhalb des Projekts neu definiert wird.</span><span class="sxs-lookup"><span data-stu-id="d0508-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="d0508-111">Wenn dies der Fall, verwenden Sie die `Global` Schlüsselwort, um den Typnamen vollständig zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="d0508-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="d0508-112">Wenn ein Projekt einen Namespace mit dem Namen definiert, z. B. `System`, die <xref:System.Object?displayProperty=nameWithType> Typ kann nicht zugegriffen werden, es sei denn, es ist vollqualifizierte mit der `Global` Schlüsselwort: `Global.System.Object`.</span><span class="sxs-lookup"><span data-stu-id="d0508-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
-   <span data-ttu-id="d0508-113">Wenn der Typ definiert ist, aber die Objekt- oder Typbibliothek, die in der sie definiert ist nicht registriert, klicken Sie in Visual Basic, auf **Verweis hinzufügen** auf die **Projekt** Menü, und wählen Sie dann das entsprechende Objekt oder Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="d0508-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
-   <span data-ttu-id="d0508-114">Stellen Sie sicher, dass der Typ in einer Assembly, die das Ziel .NET Framework-Profil gehört.</span><span class="sxs-lookup"><span data-stu-id="d0508-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="d0508-115">Weitere Informationen finden Sie unter [Problembehandlung bei .NET Framework-Zielversionsfehlern](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="d0508-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0508-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0508-116">See Also</span></span>  
 [<span data-ttu-id="d0508-117">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d0508-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="d0508-118">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d0508-118">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="d0508-119">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d0508-119">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="d0508-120">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d0508-120">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="d0508-121">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d0508-121">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="d0508-122">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="d0508-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
