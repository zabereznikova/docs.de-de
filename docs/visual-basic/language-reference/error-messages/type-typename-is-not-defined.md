---
title: Geben Sie &#39; &lt;Typename&gt;&#39; ist nicht definiert
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords: BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 68eb37f43600c51dc9117c3785a12e3c8ede1965
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="type-39lttypenamegt39-is-not-defined"></a><span data-ttu-id="ae126-102">Geben Sie &#39; &lt;Typename&gt;&#39; ist nicht definiert</span><span class="sxs-lookup"><span data-stu-id="ae126-102">Type &#39;&lt;typename&gt;&#39; is not defined</span></span>
<span data-ttu-id="ae126-103">Die Anweisung machte Verweis auf einen Typ, der nicht definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ae126-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="ae126-104">Sie können einen Typ wie z. B. in einer deklarationsanweisung definieren `Enum`, `Structure`, `Class`, oder `Interface`.</span><span class="sxs-lookup"><span data-stu-id="ae126-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="ae126-105">**Fehler-ID:** BC30002</span><span class="sxs-lookup"><span data-stu-id="ae126-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ae126-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ae126-106">To correct this error</span></span>  
  
-   <span data-ttu-id="ae126-107">Stellen Sie sicher, dass die Typdefinition und dessen Verweis beide die gleiche Schreibweise verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae126-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
-   <span data-ttu-id="ae126-108">Stellen Sie sicher, dass die Typdefinition für den Verweis zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="ae126-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="ae126-109">Wenn der Typ befindet sich in einem anderen Modul und deklariert wurde, z. B. `Private`, verschieben Sie die Typdefinition in das Verweismodul oder deklarieren Sie es `Public`.</span><span class="sxs-lookup"><span data-stu-id="ae126-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
-   <span data-ttu-id="ae126-110">Stellen Sie sicher, dass der Namespace des Typs nicht innerhalb des Projekts neu definiert wird.</span><span class="sxs-lookup"><span data-stu-id="ae126-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="ae126-111">Wenn dies der Fall, verwenden Sie die `Global` Schlüsselwort, um den Typnamen vollständig zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="ae126-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="ae126-112">Wenn ein Projekt einen Namespace mit dem Namen definiert, z. B. `System`, die <xref:System.Object?displayProperty=nameWithType> Typ kann nicht zugegriffen werden, es sei denn, es ist vollqualifizierte mit der `Global` Schlüsselwort: `Global.System.Object`.</span><span class="sxs-lookup"><span data-stu-id="ae126-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
-   <span data-ttu-id="ae126-113">Wenn der Typ definiert ist, aber nicht die Objekt- oder Typbibliothek, die in der sie definiert registriert [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], klicken Sie auf **Verweis hinzufügen** auf die **Projekt** Menü, und wählen Sie dann das entsprechende Objekt oder Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="ae126-113">If the type is defined, but the object library or type library in which it is defined is not registered in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
-   <span data-ttu-id="ae126-114">Stellen Sie sicher, dass der Typ in einer Assembly, die das Ziel .NET Framework-Profil gehört.</span><span class="sxs-lookup"><span data-stu-id="ae126-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="ae126-115">Weitere Informationen finden Sie unter [Problembehandlung bei .NET Framework-Zielversionsfehlern](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="ae126-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae126-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae126-116">See Also</span></span>  
 [<span data-ttu-id="ae126-117">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae126-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="ae126-118">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ae126-118">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="ae126-119">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ae126-119">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="ae126-120">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ae126-120">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="ae126-121">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ae126-121">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="ae126-122">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="ae126-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
