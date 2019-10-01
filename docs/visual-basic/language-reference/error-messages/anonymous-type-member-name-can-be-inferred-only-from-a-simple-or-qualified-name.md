---
title: Der Membername eines anonymen Typs kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: 38f669fe183ac79ebed6e5a122bc70aedc9bb753
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701225"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="a4111-102">Der Membername eines anonymen Typs kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden</span><span class="sxs-lookup"><span data-stu-id="a4111-102">Anonymous type member name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="a4111-103">Sie können den Namen eines anonymen Typmembers nicht aus einem komplexen Ausdruck ableiten.</span><span class="sxs-lookup"><span data-stu-id="a4111-103">You cannot infer an anonymous type member name from a complex expression.</span></span>  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 <span data-ttu-id="a4111-104">Weitere Informationen zu Quellen, aus denen anonyme Typen Elementnamen und-Typen ableiten können und nicht ableiten können, finden Sie unter [gewusst wie: Eigenschaften Namen und Typen in Deklarationen anonymer Typen @ no__t-0 ableiten.</span><span class="sxs-lookup"><span data-stu-id="a4111-104">For more information about sources from which anonymous types can and cannot infer member names and types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
 <span data-ttu-id="a4111-105">**Fehler-ID:** BC36556</span><span class="sxs-lookup"><span data-stu-id="a4111-105">**Error ID:** BC36556</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a4111-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a4111-106">To correct this error</span></span>  
  
- <span data-ttu-id="a4111-107">Weisen Sie den Ausdruck einem Elementnamen zu, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="a4111-107">Assign the expression to a member name, as shown in the following code:</span></span>  
  
    ```vb  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a4111-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4111-108">See also</span></span>

- [<span data-ttu-id="a4111-109">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="a4111-109">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- <span data-ttu-id="a4111-110">[Vorgehensweise: Eigenschaften Namen und Typen in Deklarationen anonymer Typen eingeben @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="a4111-110">[How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)</span></span>
