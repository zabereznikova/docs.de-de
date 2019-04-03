---
title: Typparameter können nicht als Qualifizierer verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 974d2935e64151109b688f576229fb008b59b229
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819800"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="7e8b9-102">Typparameter können nicht als Qualifizierer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e8b9-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="7e8b9-103">Ein Programmierelement wird mit einem Qualifizierungspfad qualifiziert, die einen Typparameter enthält.</span><span class="sxs-lookup"><span data-stu-id="7e8b9-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="7e8b9-104">Einen Typparameter darstellt, eine Anforderung für einen Typ, der bereitgestellt werden, wenn der generische Typ konstruiert wird.</span><span class="sxs-lookup"><span data-stu-id="7e8b9-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="7e8b9-105">Es stellt keinen bestimmten definierten Typ dar.</span><span class="sxs-lookup"><span data-stu-id="7e8b9-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="7e8b9-106">Ein Qualifizierungspfad muss es sich um nur Elemente enthalten, die zum Zeitpunkt der Kompilierung definiert sind.</span><span class="sxs-lookup"><span data-stu-id="7e8b9-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="7e8b9-107">Dieser Fehler kann durch die folgenden Anweisungen generiert werden.</span><span class="sxs-lookup"><span data-stu-id="7e8b9-107">The following statements can generate this error.</span></span>  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="7e8b9-108">**Fehler-ID:** BC32098</span><span class="sxs-lookup"><span data-stu-id="7e8b9-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7e8b9-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="7e8b9-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="7e8b9-110">Entfernen Sie den Typparameter in der qualifizierungszeichenfolge oder Ersetzen Sie ihn durch einen definierten Typ.</span><span class="sxs-lookup"><span data-stu-id="7e8b9-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2.  <span data-ttu-id="7e8b9-111">Wenn Sie einen konstruierten Typ zu verwenden, um die qualifizierenden Programmierelements suchen möchten, müssen Sie zusätzliche Programmlogik verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e8b9-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e8b9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e8b9-112">See also</span></span>

- [<span data-ttu-id="7e8b9-113">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="7e8b9-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="7e8b9-114">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7e8b9-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="7e8b9-115">Typliste</span><span class="sxs-lookup"><span data-stu-id="7e8b9-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
