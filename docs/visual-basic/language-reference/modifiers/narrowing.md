---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: 77515357ac9dc972992df09c471695aad13985c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867933"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="2f552-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f552-102">Narrowing (Visual Basic)</span></span>

<span data-ttu-id="2f552-103">Gibt an, dass ein Konvertierungs Operator ( `CType` ) eine Klasse oder Struktur in einen Typ konvertiert, der möglicherweise nicht in der Lage ist, einige der möglichen Werte der ursprünglichen Klasse oder Struktur zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2f552-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="2f552-104">Umrechnen mit dem einschränkenden Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="2f552-104">Converting with the Narrowing Keyword</span></span>  

 <span data-ttu-id="2f552-105">Die Konvertierungs Prozedur muss `Public Shared` zusätzlich zu angeben `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="2f552-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="2f552-106">Einschränkende Konvertierungen sind zur Laufzeit nicht immer erfolgreich und können fehlschlagen oder Datenverluste verursachen.</span><span class="sxs-lookup"><span data-stu-id="2f552-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="2f552-107">Beispiele hierfür `Long` sind `Integer` , `String` `Date` und ein Basistyp für einen abgeleiteten Typ.</span><span class="sxs-lookup"><span data-stu-id="2f552-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="2f552-108">Diese letzte Konvertierung ist einschränkend, weil der Basistyp möglicherweise nicht alle Member des abgeleiteten Typs enthält und somit keine Instanz des abgeleiteten Typs ist.</span><span class="sxs-lookup"><span data-stu-id="2f552-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="2f552-109">Wenn `Option Strict` ist `On` , muss der Konsumierende Code `CType` für alle einschränkenden Konvertierungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f552-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="2f552-110">Das `Narrowing` Schlüsselwort kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="2f552-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="2f552-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="2f552-111">Operator Statement</span></span>](../statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f552-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f552-112">See also</span></span>

- [<span data-ttu-id="2f552-113">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="2f552-113">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="2f552-114">Widening</span><span class="sxs-lookup"><span data-stu-id="2f552-114">Widening</span></span>](widening.md)
- [<span data-ttu-id="2f552-115">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="2f552-115">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="2f552-116">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="2f552-116">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="2f552-117">CType Function</span><span class="sxs-lookup"><span data-stu-id="2f552-117">CType Function</span></span>](../functions/ctype-function.md)
- [<span data-ttu-id="2f552-118">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2f552-118">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
