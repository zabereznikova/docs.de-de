---
title: '&#39;Wie ein anderer&#39; wird nicht unterstützt &#39;Declare&#39; Anweisungen'
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: 34beaeb7178645d5a167d1b7b969bb3e4f500e1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588225"
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a><span data-ttu-id="7bbc5-102">&#39;Wie ein anderer&#39; wird nicht unterstützt &#39;Declare&#39; Anweisungen</span><span class="sxs-lookup"><span data-stu-id="7bbc5-102">&#39;As Any&#39; is not supported in &#39;Declare&#39; statements</span></span>
<span data-ttu-id="7bbc5-103">Die `Any` wurde mit dem verwendet `Declare` Anweisungen in Visual Basic 6.0 und früheren Versionen gestatten die Verwendung von Argumenten, die beliebige Datentypen enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="7bbc5-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="7bbc5-104">Visual Basic unterstützt jedoch Überladen und ermöglicht die `Any` -Datentyp ab.</span><span class="sxs-lookup"><span data-stu-id="7bbc5-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="7bbc5-105">**Fehler-ID:** BC30828</span><span class="sxs-lookup"><span data-stu-id="7bbc5-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7bbc5-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="7bbc5-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="7bbc5-107">Deklarieren Sie die Parameter des angegebenen Typs, die Sie verwenden möchten. Zum Beispiel.</span><span class="sxs-lookup"><span data-stu-id="7bbc5-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  <span data-ttu-id="7bbc5-108">Verwenden der <xref:System.Runtime.InteropServices.MarshalAsAttribute> -Attribut angeben, `As Any` Wenn `Void*` wird von der aufgerufenen Prozedur erwartet.</span><span class="sxs-lookup"><span data-stu-id="7bbc5-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7bbc5-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bbc5-109">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="7bbc5-110">Exemplarische Vorgehensweise: Aufrufen von Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="7bbc5-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="7bbc5-111">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7bbc5-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="7bbc5-112">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="7bbc5-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
