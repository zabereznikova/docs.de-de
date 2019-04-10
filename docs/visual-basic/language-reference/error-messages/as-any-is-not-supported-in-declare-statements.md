---
title: As Any wird in Declare-Anweisungen nicht unterstützt.
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: 3593f238c72cbcce911c72e42552d6a75188b628
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310693"
---
# <a name="as-any-is-not-supported-in-declare-statements"></a><span data-ttu-id="72452-102">As Any wird in Declare-Anweisungen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="72452-102">'As Any' is not supported in 'Declare' statements</span></span>
<span data-ttu-id="72452-103">Die `Any` Datentyp wurde verwendet, mit `Declare` Anweisungen in Visual Basic 6.0 und früheren Versionen, um die Verwendung von Argumenten zu ermöglichen, die beliebige Datentypen enthalten könnte.</span><span class="sxs-lookup"><span data-stu-id="72452-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="72452-104">Überladen zulässt, jedoch von Visual Basic unterstützt und löst so die `Any` -Datentyp ab.</span><span class="sxs-lookup"><span data-stu-id="72452-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="72452-105">**Fehler-ID:** BC30828</span><span class="sxs-lookup"><span data-stu-id="72452-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="72452-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="72452-106">To correct this error</span></span>  
  
1. <span data-ttu-id="72452-107">Deklarieren Sie die Parameter des angegebenen Typs, die Sie verwenden möchten; Zum Beispiel.</span><span class="sxs-lookup"><span data-stu-id="72452-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#95)]  
  
2. <span data-ttu-id="72452-108">Verwenden der <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut an `As Any` beim `Void*` wird von der aufgerufenen Prozedur erwartet.</span><span class="sxs-lookup"><span data-stu-id="72452-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#96)]  
  
## <a name="see-also"></a><span data-ttu-id="72452-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72452-109">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="72452-110">Exemplarische Vorgehensweise: Aufrufen von Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="72452-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="72452-111">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="72452-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="72452-112">Erstellen von Prototypen in verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="72452-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
