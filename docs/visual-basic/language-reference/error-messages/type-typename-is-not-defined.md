---
title: Typ &quot;&lt;Typename&gt;&quot; ist nicht definiert | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
dev_langs:
- VB
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
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
ms.openlocfilehash: 55b76e9d080a2e2e9fe6e9737a713524ea6409f6
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="type-39lttypenamegt39-is-not-defined"></a><span data-ttu-id="49ca0-102">Typ '&lt;Typename&gt;' ist nicht definiert</span><span class="sxs-lookup"><span data-stu-id="49ca0-102">Type &#39;&lt;typename&gt;&#39; is not defined</span></span>
<span data-ttu-id="49ca0-103">Die Anweisung hat auf einen Typ verwiesen, die nicht definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="49ca0-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="49ca0-104">Sie können einen Typ wie z. B. in einer deklarationsanweisung definieren `Enum`, `Structure`, `Class`, oder `Interface`.</span><span class="sxs-lookup"><span data-stu-id="49ca0-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="49ca0-105">**Fehler-ID:** BC30002</span><span class="sxs-lookup"><span data-stu-id="49ca0-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="49ca0-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="49ca0-106">To correct this error</span></span>  
  
-   <span data-ttu-id="49ca0-107">Stellen Sie sicher, dass die Typdefinition und dessen Verweis derselben Schreibweise verwenden.</span><span class="sxs-lookup"><span data-stu-id="49ca0-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
-   <span data-ttu-id="49ca0-108">Stellen Sie sicher, dass die Typdefinition für den Verweis zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="49ca0-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="49ca0-109">Wenn der Typ in einem anderen Modul und deklariert wurde, z. B. `Private`, verschieben Sie die Typdefinition in das Verweismodul oder deklarieren Sie es `Public`.</span><span class="sxs-lookup"><span data-stu-id="49ca0-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
-   <span data-ttu-id="49ca0-110">Stellen Sie sicher, dass der Namespace des Typs nicht innerhalb des Projekts neu definiert wird.</span><span class="sxs-lookup"><span data-stu-id="49ca0-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="49ca0-111">Wenn dies der Fall, verwenden die `Global` -Schlüsselwort verwenden, um den Typnamen vollständig zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="49ca0-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="49ca0-112">Wenn ein Projekt einen Namespace mit dem Namen definiert, z. B. `System`, die <xref:System.Object?displayProperty=fullName>Typ kann nicht zugegriffen werden, es sei denn, es mit vollqualifiziert ist die `Global` Schlüsselwort: `Global.System.Object`.</xref:System.Object?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="49ca0-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=fullName> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
-   <span data-ttu-id="49ca0-113">Wenn der Typ definiert ist, aber die Objekt- oder Typbibliothek, in der er definiert ist, ist nicht registriert [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], klicken Sie auf **Verweis hinzufügen** auf der **Projekt** Menü, und wählen Sie dann die geeignete Objekt- oder Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="49ca0-113">If the type is defined, but the object library or type library in which it is defined is not registered in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
-   <span data-ttu-id="49ca0-114">Stellen Sie sicher, dass der Typ in einer Assembly, die Teil der entsprechenden .NET Framework-Profil ist.</span><span class="sxs-lookup"><span data-stu-id="49ca0-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="49ca0-115">Weitere Informationen finden Sie unter [Problembehandlung bei .NET Framework-Zielversionsfehlern](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="49ca0-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49ca0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49ca0-116">See Also</span></span>  
 <span data-ttu-id="49ca0-117">[Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="49ca0-117">[Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="49ca0-118"> [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md) </span><span class="sxs-lookup"><span data-stu-id="49ca0-118"> [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) </span></span>  
<span data-ttu-id="49ca0-119"> [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="49ca0-119"> [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="49ca0-120"> [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md) </span><span class="sxs-lookup"><span data-stu-id="49ca0-120"> [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) </span></span>  
<span data-ttu-id="49ca0-121"> [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md) </span><span class="sxs-lookup"><span data-stu-id="49ca0-121"> [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) </span></span>  
<span data-ttu-id="49ca0-122"> [Verwalten von Verweisen in einem Projekt](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)</span><span class="sxs-lookup"><span data-stu-id="49ca0-122"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)</span></span>
