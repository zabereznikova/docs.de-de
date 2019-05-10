---
title: Das Extension-Attribut darf nur in Module-, Sub- oder Function-Deklarationen verwendet werden
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 88212fb2c04eab61b719a161ae01ccdda9a6110d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64640724"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a><span data-ttu-id="81db8-102">Das Extension-Attribut darf nur in Module-, Sub- oder Function-Deklarationen verwendet werden</span><span class="sxs-lookup"><span data-stu-id="81db8-102">'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations</span></span>
<span data-ttu-id="81db8-103">Die einzige Möglichkeit zum Erweitern von eines Datentyps in Visual Basic ist eine Erweiterungsmethode in einem Standardmodul definieren.</span><span class="sxs-lookup"><span data-stu-id="81db8-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="81db8-104">Die Erweiterungsmethode möglich ein `Sub` Prozedur oder ein `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="81db8-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="81db8-105">Alle Erweiterungsmethoden müssen mit dem Extension-Attribut markiert werden `<Extension()>`, aus der <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> Namespace.</span><span class="sxs-lookup"><span data-stu-id="81db8-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="81db8-106">Optional kann ein Modul, eine Erweiterungsmethode enthält, auf die gleiche Weise gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="81db8-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="81db8-107">Keine andere Verwendung der das Extension-Attribut ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="81db8-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="81db8-108">**Fehler-ID:** BC36550</span><span class="sxs-lookup"><span data-stu-id="81db8-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="81db8-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="81db8-109">To correct this error</span></span>  
  
- <span data-ttu-id="81db8-110">Entfernen Sie das Extension-Attribut.</span><span class="sxs-lookup"><span data-stu-id="81db8-110">Remove the extension attribute.</span></span>  
  
- <span data-ttu-id="81db8-111">Entwerfen Sie die Erweiterung als eine Methode, in ein einschließendes Modul definiert.</span><span class="sxs-lookup"><span data-stu-id="81db8-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81db8-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81db8-112">Example</span></span>  
 <span data-ttu-id="81db8-113">Das folgende Beispiel definiert eine `Print` -Methode für die `String` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="81db8-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="81db8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81db8-114">See also</span></span>

- [<span data-ttu-id="81db8-115">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="81db8-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="81db8-116">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="81db8-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="81db8-117">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="81db8-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
