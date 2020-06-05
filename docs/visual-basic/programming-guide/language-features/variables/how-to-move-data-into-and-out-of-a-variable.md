---
title: 'Vorgehensweise: Verschieben von Daten in eine und aus einer Variablen'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: fe19a6160623aa9ea867becdf7a15b51319abf45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410437"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="3d078-102">Gewusst wie: Verschieben von Daten in und aus einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d078-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>

<span data-ttu-id="3d078-103">Sie speichern einen Wert in einer Variablen, indem Sie den Variablennamen auf der linken Seite einer Zuweisungsanweisung platzieren.</span><span class="sxs-lookup"><span data-stu-id="3d078-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>

## <a name="putting-data-in-a-variable"></a><span data-ttu-id="3d078-104">Einfügen von Daten in eine Variable</span><span class="sxs-lookup"><span data-stu-id="3d078-104">Putting Data in a Variable</span></span>

#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="3d078-105">So speichern Sie einen Wert in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="3d078-105">To store a value in a variable</span></span>

- <span data-ttu-id="3d078-106">Verwenden Sie den Variablennamen auf der linken Seite einer Zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="3d078-106">Use the variable name on the left side of an assignment statement.</span></span>

    <span data-ttu-id="3d078-107">Im folgenden Beispiel wird der Wert der-Variablen festgelegt `alpha` .</span><span class="sxs-lookup"><span data-stu-id="3d078-107">The following example sets the value of the variable `alpha`.</span></span>

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    <span data-ttu-id="3d078-108">Der auf der rechten Seite der Zuweisungsanweisung generierte Wert wird in der Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3d078-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>

## <a name="getting-data-from-a-variable"></a><span data-ttu-id="3d078-109">Erhalten von Daten aus einer Variablen</span><span class="sxs-lookup"><span data-stu-id="3d078-109">Getting Data from a Variable</span></span>

<span data-ttu-id="3d078-110">Sie rufen den Wert einer Variablen ab, indem Sie den Variablennamen in einen Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="3d078-110">You retrieve a variable's value by including the variable name in an expression.</span></span>

#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="3d078-111">So rufen Sie einen Wert aus einer Variablen ab</span><span class="sxs-lookup"><span data-stu-id="3d078-111">To retrieve a value from a variable</span></span>

- <span data-ttu-id="3d078-112">Verwenden Sie den Variablennamen in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="3d078-112">Use the variable name in an expression.</span></span> <span data-ttu-id="3d078-113">Sie können eine Variable überall dort verwenden, wo Sie eine Konstante oder einen Literalwert verwenden können, außer in einem Ausdruck, der den Wert einer Konstanten definiert.</span><span class="sxs-lookup"><span data-stu-id="3d078-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>

  <span data-ttu-id="3d078-114">\- oder -</span><span class="sxs-lookup"><span data-stu-id="3d078-114">\-or-</span></span>

- <span data-ttu-id="3d078-115">Verwenden Sie den Variablennamen nach dem Gleichheits `=` Zeichen () in einer Zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="3d078-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>

  <span data-ttu-id="3d078-116">Im folgenden Beispiel wird der Wert der-Variablen gelesen, `startValue` und anschließend wird der Wert der-Variablen `counter` in einem Ausdruck verwendet.</span><span class="sxs-lookup"><span data-stu-id="3d078-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  <span data-ttu-id="3d078-117">Der Wert der-Variablen ist an dem Ausdruck genau wie eine Konstante beteiligt und wird dann in der Variablen oder der Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3d078-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d078-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3d078-118">See also</span></span>

- [<span data-ttu-id="3d078-119">Variablen</span><span class="sxs-lookup"><span data-stu-id="3d078-119">Variables</span></span>](index.md)
- [<span data-ttu-id="3d078-120">Variablen Deklaration</span><span class="sxs-lookup"><span data-stu-id="3d078-120">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="3d078-121">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="3d078-121">Object Variables</span></span>](object-variables.md)
