---
title: Der Typ "<typename>" ist nicht definiert.
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 89e2d1d18b456c96f62d6b9ee1dd8dc9d41bf665
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386931"
---
# <a name="type-typename-is-not-defined"></a><span data-ttu-id="fcad7-102">Der Typ "\<typename>" ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="fcad7-102">Type '\<typename>' is not defined</span></span>
<span data-ttu-id="fcad7-103">Die-Anweisung hat einen Verweis auf einen Typ vorgenommen, der nicht definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fcad7-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="fcad7-104">Sie können einen Typ in einer Deklarations Anweisung definieren `Enum` , z `Structure` . b.,, `Class` oder `Interface` .</span><span class="sxs-lookup"><span data-stu-id="fcad7-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="fcad7-105">**Fehler-ID:** BC30002</span><span class="sxs-lookup"><span data-stu-id="fcad7-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fcad7-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fcad7-106">To correct this error</span></span>  
  
- <span data-ttu-id="fcad7-107">Stellen Sie sicher, dass für die Typdefinition und deren Verweis dieselbe Schreibweise verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fcad7-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
- <span data-ttu-id="fcad7-108">Stellen Sie sicher, dass die Typdefinition für den Verweis zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="fcad7-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="fcad7-109">Wenn der Typ z. b. in einem anderen Modul ist und deklariert wurde `Private` , verschieben Sie die Typdefinition in das verweisende Modul, oder deklarieren Sie Sie `Public` .</span><span class="sxs-lookup"><span data-stu-id="fcad7-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
- <span data-ttu-id="fcad7-110">Stellen Sie sicher, dass der Namespace des Typs nicht innerhalb des Projekts neu definiert wird.</span><span class="sxs-lookup"><span data-stu-id="fcad7-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="fcad7-111">Ist dies der Fall, verwenden Sie das `Global` Schlüsselwort, um den Typnamen vollständig zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="fcad7-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="fcad7-112">Wenn ein Projekt beispielsweise einen Namespace mit dem Namen definiert `System` , <xref:System.Object?displayProperty=nameWithType> kann nicht auf den Typ zugegriffen werden, es sei denn, er ist mit dem `Global` Schlüsselwort voll qualifiziert: `Global.System.Object` .</span><span class="sxs-lookup"><span data-stu-id="fcad7-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
- <span data-ttu-id="fcad7-113">Wenn der Typ definiert ist, aber die Objektbibliothek oder die Typbibliothek, in der er definiert ist, nicht in Visual Basic registriert ist, klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** , und wählen Sie dann die entsprechende Objektbibliothek oder Typbibliothek aus.</span><span class="sxs-lookup"><span data-stu-id="fcad7-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
- <span data-ttu-id="fcad7-114">Stellen Sie sicher, dass der Typ in einer Assembly enthalten ist, die Teil des Ziel .NET Framework Profils ist.</span><span class="sxs-lookup"><span data-stu-id="fcad7-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="fcad7-115">Weitere Informationen finden Sie unter [Problembehandlung .NET Framework Ziel Fehler](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="fcad7-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcad7-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fcad7-116">See also</span></span>

- [<span data-ttu-id="fcad7-117">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fcad7-117">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="fcad7-118">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fcad7-118">Enum Statement</span></span>](../statements/enum-statement.md)
- [<span data-ttu-id="fcad7-119">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="fcad7-119">Structure Statement</span></span>](../statements/structure-statement.md)
- [<span data-ttu-id="fcad7-120">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fcad7-120">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="fcad7-121">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fcad7-121">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="fcad7-122">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="fcad7-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
