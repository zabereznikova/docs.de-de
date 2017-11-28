---
title: "&#39; Erweiterung &#39; Attribut kann nur für angewendet &#39; Modul &#39; &#39; Sub &#39; oder &#39; Function &#39; Deklarationen"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords: BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d77933c52484eb934501107d1ddad15f0eca826
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a><span data-ttu-id="ef48d-102">&#39; Erweiterung &#39; Attribut kann nur für angewendet &#39; Modul &#39; &#39; Sub &#39; oder &#39; Function &#39; Deklarationen</span><span class="sxs-lookup"><span data-stu-id="ef48d-102">&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations</span></span>
<span data-ttu-id="ef48d-103">Die einzige Möglichkeit zum Erweitern eines Datentyps in Visual Basic werden Erweiterungsmethoden innerhalb eines Moduls, standard definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ef48d-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="ef48d-104">Die Erweiterungsmethode kann eine `Sub` Prozedur oder eine `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="ef48d-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="ef48d-105">Alle Erweiterungsmethoden müssen mit dem Erweiterungsattribut markiert werden `<Extension()>`, aus der <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> Namespace.</span><span class="sxs-lookup"><span data-stu-id="ef48d-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="ef48d-106">Optional kann ein Modul, eine Erweiterungsmethode enthält, auf die gleiche Weise markiert werden.</span><span class="sxs-lookup"><span data-stu-id="ef48d-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="ef48d-107">Keine andere Verwendung von Extension-Attribut ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="ef48d-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="ef48d-108">**Fehler-ID:** BC36550</span><span class="sxs-lookup"><span data-stu-id="ef48d-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ef48d-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ef48d-109">To correct this error</span></span>  
  
-   <span data-ttu-id="ef48d-110">Entfernen Sie das Extension-Attribut.</span><span class="sxs-lookup"><span data-stu-id="ef48d-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="ef48d-111">Entwerfen Sie die Erweiterung als eine Methode, die in ein einschließendes Modul definiert.</span><span class="sxs-lookup"><span data-stu-id="ef48d-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef48d-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef48d-112">Example</span></span>  
 <span data-ttu-id="ef48d-113">Das folgende Beispiel definiert eine `Print` Methode für die `String` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="ef48d-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef48d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef48d-114">See Also</span></span>  
 [<span data-ttu-id="ef48d-115">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="ef48d-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="ef48d-116">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="ef48d-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [<span data-ttu-id="ef48d-117">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ef48d-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
