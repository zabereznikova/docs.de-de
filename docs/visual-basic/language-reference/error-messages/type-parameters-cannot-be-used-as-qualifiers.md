---
title: Typparameter können nicht als Qualifizierer verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 3ff4b189539bf119351a94dabadd596c336ac723
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250328"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="c73f7-102">Typparameter können nicht als Qualifizierer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c73f7-102">Type parameters cannot be used as qualifiers</span></span>

<span data-ttu-id="c73f7-103">Ein Programmier Element wird mit einer Qualifikations Zeichenfolge qualifiziert, die einen Typparameter enthält.</span><span class="sxs-lookup"><span data-stu-id="c73f7-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>

<span data-ttu-id="c73f7-104">Ein Typparameter stellt eine Anforderung für einen Typ dar, der beim Konstruieren des generischen Typs bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c73f7-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="c73f7-105">Sie stellt keinen bestimmten definierten Typ dar.</span><span class="sxs-lookup"><span data-stu-id="c73f7-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="c73f7-106">Eine Qualifizierungs Zeichenfolge darf nur Elemente enthalten, die zur Kompilierzeit definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c73f7-106">A qualification string must include only elements that are defined at compile time.</span></span>

<span data-ttu-id="c73f7-107">Dieser Fehler kann durch folgenden Code generiert werden:</span><span class="sxs-lookup"><span data-stu-id="c73f7-107">The following code can generate this error:</span></span>

```vb  
Public Function CheckText(Of c As System.Windows.Forms.Control)(
    badText As String) As Boolean
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.
End Function  
```  
  
 <span data-ttu-id="c73f7-108">**Fehler-ID:** BC32098</span><span class="sxs-lookup"><span data-stu-id="c73f7-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c73f7-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c73f7-109">To correct this error</span></span>  
  
1. <span data-ttu-id="c73f7-110">Entfernen Sie den Typparameter aus der Qualifikations Zeichenfolge, oder ersetzen Sie ihn durch einen definierten Typ.</span><span class="sxs-lookup"><span data-stu-id="c73f7-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2. <span data-ttu-id="c73f7-111">Wenn Sie einen konstruierten Typ verwenden müssen, um das zu qualifizierte Programmier Element zu suchen, müssen Sie zusätzliche Programmlogik verwenden.</span><span class="sxs-lookup"><span data-stu-id="c73f7-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c73f7-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c73f7-112">See also</span></span>

- [<span data-ttu-id="c73f7-113">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="c73f7-113">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="c73f7-114">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c73f7-114">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="c73f7-115">Typliste</span><span class="sxs-lookup"><span data-stu-id="c73f7-115">Type List</span></span>](../statements/type-list.md)
