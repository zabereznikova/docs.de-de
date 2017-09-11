---
title: Das Extension-Attribut kann nur auf &quot;Module&quot;, &quot;Sub&quot; oder &quot;Function&quot; Deklarationen angewendet werden | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
dev_langs:
- VB
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e88241180fe1320bfd1db90a38a9a7560ae3dead
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a><span data-ttu-id="fe8d1-102">Das Extension-Attribut kann nur auf "Module", "Sub" oder "Function" Deklarationen angewendet werden</span><span class="sxs-lookup"><span data-stu-id="fe8d1-102">&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations</span></span>
<span data-ttu-id="fe8d1-103">Die einzige Möglichkeit zum Erweitern von eines Datentyps in Visual Basic ist eine Erweiterungsmethode innerhalb eines Standardmoduls definieren.</span><span class="sxs-lookup"><span data-stu-id="fe8d1-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="fe8d1-104">Die Erweiterungsmethode kann eine `Sub` Prozedur oder ein `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="fe8d1-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="fe8d1-105">Alle Erweiterungsmethoden müssen mit dem Extension-Attribut markiert werden `<Extension()>`, aus der <xref:System.Runtime.CompilerServices?displayProperty=fullName>Namespace.</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fe8d1-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="fe8d1-106">Optional kann ein Modul, das eine Erweiterungsmethode enthält, auf die gleiche Weise markiert werden.</span><span class="sxs-lookup"><span data-stu-id="fe8d1-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="fe8d1-107">Eine andere Verwendung des Extension-Attribut ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="fe8d1-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="fe8d1-108">**Fehler-ID:** BC36550</span><span class="sxs-lookup"><span data-stu-id="fe8d1-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fe8d1-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fe8d1-109">To correct this error</span></span>  
  
-   <span data-ttu-id="fe8d1-110">Entfernen Sie das Extension-Attribut.</span><span class="sxs-lookup"><span data-stu-id="fe8d1-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="fe8d1-111">Entwerfen Sie die Erweiterung als eine Methode, die in einem einschließenden Modul definiert.</span><span class="sxs-lookup"><span data-stu-id="fe8d1-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe8d1-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe8d1-112">Example</span></span>  
 <span data-ttu-id="fe8d1-113">Das folgende Beispiel definiert eine `Print` Methode für die `String` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="fe8d1-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fe8d1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe8d1-114">See Also</span></span>  
 <span data-ttu-id="fe8d1-115">[Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="fe8d1-115">[Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="fe8d1-116"> [Erweiterungsmethoden](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) </span><span class="sxs-lookup"><span data-stu-id="fe8d1-116"> [Extension Methods](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) </span></span>  
<span data-ttu-id="fe8d1-117"> [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)</span><span class="sxs-lookup"><span data-stu-id="fe8d1-117"> [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)</span></span>

