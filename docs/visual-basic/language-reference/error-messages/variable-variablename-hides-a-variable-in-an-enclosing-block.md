---
title: Die Variable "<variablename>" verbirgt eine Variable in einem einschließenden Block.
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 474a920c9cfdfba7a8157320d9c88b8677958425
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406520"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="778e5-102">Die Variable "\<variablename>" verbirgt eine Variable in einem einschließenden Block.</span><span class="sxs-lookup"><span data-stu-id="778e5-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>
<span data-ttu-id="778e5-103">Eine in einen-Block eingeschlossene Variable hat denselben Namen wie eine andere lokale Variable.</span><span class="sxs-lookup"><span data-stu-id="778e5-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="778e5-104">**Fehler-ID:** BC30616</span><span class="sxs-lookup"><span data-stu-id="778e5-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="778e5-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="778e5-105">To correct this error</span></span>  
  
- <span data-ttu-id="778e5-106">Benennen Sie die Variable im eingeschlossenen Block so um, dass Sie nicht mit allen anderen lokalen Variablen identisch ist.</span><span class="sxs-lookup"><span data-stu-id="778e5-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="778e5-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="778e5-107">For example:</span></span>  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- <span data-ttu-id="778e5-108">Eine häufige Ursache für diesen Fehler ist die Verwendung von `Catch e As Exception` innerhalb eines Ereignis Handlers.</span><span class="sxs-lookup"><span data-stu-id="778e5-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="778e5-109">Wenn dies der Fall ist, benennen Sie die `Catch` Block Variable `ex` anstelle von `e` .</span><span class="sxs-lookup"><span data-stu-id="778e5-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
- <span data-ttu-id="778e5-110">Eine weitere häufige Ursache für diesen Fehler ist der Versuch, auf eine lokale Variable zuzugreifen, die `Try` in einem Block in einem separaten Block deklariert ist `Catch` .</span><span class="sxs-lookup"><span data-stu-id="778e5-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="778e5-111">Um dies zu korrigieren, deklarieren Sie die Variable außerhalb der- `Try...Catch...Finally` Struktur.</span><span class="sxs-lookup"><span data-stu-id="778e5-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="778e5-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="778e5-112">See also</span></span>

- [<span data-ttu-id="778e5-113">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="778e5-113">Try...Catch...Finally Statement</span></span>](../statements/try-catch-finally-statement.md)
- [<span data-ttu-id="778e5-114">Variablen Deklaration</span><span class="sxs-lookup"><span data-stu-id="778e5-114">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
