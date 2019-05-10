---
title: Der Membername eines anonymen Typs kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: f657048a8aa9748104e40503e727a5e6d90a87ad
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646855"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="83a6a-102">Der Membername eines anonymen Typs kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden</span><span class="sxs-lookup"><span data-stu-id="83a6a-102">Anonymous type member name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="83a6a-103">Einen anonymer Typmembernamen aus einem komplexen Ausdruck kann nicht abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="83a6a-103">You cannot infer an anonymous type member name from a complex expression.</span></span>  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 <span data-ttu-id="83a6a-104">Weitere Informationen zu Quellen, von dem anonyme Typen können, und können nicht abgeleitet, Membernamen und-Typen, finden Sie unter [Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span><span class="sxs-lookup"><span data-stu-id="83a6a-104">For more information about sources from which anonymous types can and cannot infer member names and types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
 <span data-ttu-id="83a6a-105">**Fehler-ID:** BC36556</span><span class="sxs-lookup"><span data-stu-id="83a6a-105">**Error ID:** BC36556</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="83a6a-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="83a6a-106">To correct this error</span></span>  
  
- <span data-ttu-id="83a6a-107">Weisen Sie den Ausdruck zu einem Elementnamen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="83a6a-107">Assign the expression to a member name, as shown in the following code:</span></span>  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="83a6a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83a6a-108">See also</span></span>

- [<span data-ttu-id="83a6a-109">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="83a6a-109">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="83a6a-110">Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen</span><span class="sxs-lookup"><span data-stu-id="83a6a-110">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
