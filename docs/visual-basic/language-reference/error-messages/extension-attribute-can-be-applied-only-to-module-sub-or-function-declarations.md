---
title: Das Extension-Attribut darf nur in Module-, Sub- oder Function-Deklarationen verwendet werden
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 95a67a552efacf9e77dc3ebc3e0187817a6d82e2
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698585"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a><span data-ttu-id="f453b-102">Das Extension-Attribut darf nur in Module-, Sub- oder Function-Deklarationen verwendet werden</span><span class="sxs-lookup"><span data-stu-id="f453b-102">'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations</span></span>
<span data-ttu-id="f453b-103">Die einzige Möglichkeit zum Erweitern eines Datentyps in Visual Basic besteht darin, eine Erweiterungsmethode in einem Standardmodul zu definieren.</span><span class="sxs-lookup"><span data-stu-id="f453b-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="f453b-104">Bei der Erweiterungsmethode kann es sich um eine `Sub`-Prozedur oder um eine `Function`-Prozedur handeln.</span><span class="sxs-lookup"><span data-stu-id="f453b-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="f453b-105">Alle Erweiterungs Methoden müssen mit dem Erweiterungs Attribut `<Extension()>` aus dem <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>-Namespace gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="f453b-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="f453b-106">Optional kann ein Modul, das eine Erweiterungsmethode enthält, auf dieselbe Weise gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="f453b-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="f453b-107">Keine andere Verwendung des Erweiterungs Attributs ist gültig.</span><span class="sxs-lookup"><span data-stu-id="f453b-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="f453b-108">**Fehler-ID:** BC36550</span><span class="sxs-lookup"><span data-stu-id="f453b-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f453b-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f453b-109">To correct this error</span></span>  
  
- <span data-ttu-id="f453b-110">Entfernen Sie das Erweiterungs Attribut.</span><span class="sxs-lookup"><span data-stu-id="f453b-110">Remove the extension attribute.</span></span>  
  
- <span data-ttu-id="f453b-111">Entwerfen Sie Ihre Erweiterung als eine Methode, die in einem umschließenden Modul definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f453b-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f453b-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f453b-112">Example</span></span>  
 <span data-ttu-id="f453b-113">Im folgenden Beispiel wird eine `Print`-Methode für den `String`-Datentyp definiert.</span><span class="sxs-lookup"><span data-stu-id="f453b-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
```vb  
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
  
## <a name="see-also"></a><span data-ttu-id="f453b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f453b-114">See also</span></span>

- [<span data-ttu-id="f453b-115">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="f453b-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="f453b-116">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="f453b-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="f453b-117">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f453b-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
