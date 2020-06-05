---
title: Das Extension-Attribut darf nur in Module-, Sub- oder Function-Deklarationen verwendet werden
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 9b8f49c498699a8f7d1c4b329e82258501aa0c47
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363097"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a><span data-ttu-id="86e5c-102">Das Extension-Attribut darf nur in Module-, Sub- oder Function-Deklarationen verwendet werden</span><span class="sxs-lookup"><span data-stu-id="86e5c-102">'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations</span></span>

<span data-ttu-id="86e5c-103">Die einzige Möglichkeit zum Erweitern eines Datentyps in Visual Basic besteht darin, eine Erweiterungsmethode in einem Standardmodul zu definieren.</span><span class="sxs-lookup"><span data-stu-id="86e5c-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="86e5c-104">Bei der Erweiterungsmethode kann es sich um eine `Sub` Prozedur oder eine `Function` Prozedur handeln.</span><span class="sxs-lookup"><span data-stu-id="86e5c-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="86e5c-105">Alle Erweiterungs Methoden müssen mit dem Erweiterungs Attribut, `<Extension()>` , aus dem- <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> Namespace gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="86e5c-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="86e5c-106">Optional kann ein Modul, das eine Erweiterungsmethode enthält, auf dieselbe Weise gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="86e5c-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="86e5c-107">Keine andere Verwendung des Erweiterungs Attributs ist gültig.</span><span class="sxs-lookup"><span data-stu-id="86e5c-107">No other use of the extension attribute is valid.</span></span>

<span data-ttu-id="86e5c-108">**Fehler-ID:** BC36550</span><span class="sxs-lookup"><span data-stu-id="86e5c-108">**Error ID:** BC36550</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="86e5c-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="86e5c-109">To correct this error</span></span>

- <span data-ttu-id="86e5c-110">Entfernen Sie das Erweiterungs Attribut.</span><span class="sxs-lookup"><span data-stu-id="86e5c-110">Remove the extension attribute.</span></span>

- <span data-ttu-id="86e5c-111">Entwerfen Sie Ihre Erweiterung als eine Methode, die in einem umschließenden Modul definiert ist.</span><span class="sxs-lookup"><span data-stu-id="86e5c-111">Redesign your extension as a method, defined in an enclosing module.</span></span>

## <a name="example"></a><span data-ttu-id="86e5c-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86e5c-112">Example</span></span>

<span data-ttu-id="86e5c-113">Im folgenden Beispiel wird eine- `Print` Methode für den- `String` Datentyp definiert.</span><span class="sxs-lookup"><span data-stu-id="86e5c-113">The following example defines a `Print` method for the `String` data type.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="86e5c-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86e5c-114">See also</span></span>

- [<span data-ttu-id="86e5c-115">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="86e5c-115">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="86e5c-116">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="86e5c-116">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="86e5c-117">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="86e5c-117">Module Statement</span></span>](../statements/module-statement.md)
