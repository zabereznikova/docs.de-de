---
title: Der Typ '<typename>' ist nicht definiert.
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 1f66b86a61fb0344a449bf0aa46b7655813c7c30
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664244"
---
# <a name="type-typename-is-not-defined"></a><span data-ttu-id="ab9f6-102">Typ '\<Typname >' ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="ab9f6-102">Type '\<typename>' is not defined</span></span>
<span data-ttu-id="ab9f6-103">Die Anweisung hat auf einen Typ verwiesen, die nicht definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ab9f6-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="ab9f6-104">Sie können einen Typ wie z. B. in einer deklarationsanweisung definieren `Enum`, `Structure`, `Class`, oder `Interface`.</span><span class="sxs-lookup"><span data-stu-id="ab9f6-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="ab9f6-105">**Fehler-ID:** BC30002</span><span class="sxs-lookup"><span data-stu-id="ab9f6-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ab9f6-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ab9f6-106">To correct this error</span></span>  
  
- <span data-ttu-id="ab9f6-107">Stellen Sie sicher, dass es sich bei der Definition des Typs und dessen Verweis beide die gleiche Schreibweise verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab9f6-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
- <span data-ttu-id="ab9f6-108">Stellen Sie sicher, dass die Typdefinition für den Verweis zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="ab9f6-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="ab9f6-109">Wenn der Typ in einem anderen Modul und deklariert wurde, z. B. `Private`, verschieben Sie die Typdefinition in der Verweismodul oder deklarieren sie `Public`.</span><span class="sxs-lookup"><span data-stu-id="ab9f6-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
- <span data-ttu-id="ab9f6-110">Stellen Sie sicher, dass der Namespace des Typs in Ihrem Projekt nicht neu definiert wird.</span><span class="sxs-lookup"><span data-stu-id="ab9f6-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="ab9f6-111">Wenn es sich handelt, verwenden Sie die `Global` Schlüsselwort, um den Namen vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="ab9f6-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="ab9f6-112">Wenn ein Projekt einen Namespace mit dem Namen definiert, z. B. `System`, <xref:System.Object?displayProperty=nameWithType> Typ kann nicht zugegriffen werden, es sei denn, es mit vollqualifiziert ist die `Global` Schlüsselwort: `Global.System.Object`.</span><span class="sxs-lookup"><span data-stu-id="ab9f6-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
- <span data-ttu-id="ab9f6-113">Wenn der Typ definiert ist, aber die Objekt- oder Typbibliothek, die in der sie definiert ist nicht registriert, klicken Sie in Visual Basic auf **Verweis hinzufügen** auf die **Projekt** Menü, und wählen Sie dann das entsprechende Objekt oder Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="ab9f6-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
- <span data-ttu-id="ab9f6-114">Stellen Sie sicher, dass der Typ in einer Assembly, die das Ziel .NET Framework-Profil gehört.</span><span class="sxs-lookup"><span data-stu-id="ab9f6-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="ab9f6-115">Weitere Informationen finden Sie unter [Problembehandlung bei .NET Framework-Zielversionsfehlern](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="ab9f6-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab9f6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab9f6-116">See also</span></span>

- [<span data-ttu-id="ab9f6-117">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab9f6-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="ab9f6-118">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ab9f6-118">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="ab9f6-119">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ab9f6-119">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="ab9f6-120">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ab9f6-120">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="ab9f6-121">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ab9f6-121">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="ab9f6-122">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="ab9f6-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
