---
title: "Gewusst wie: Aufrufen einer überladenen Prozedur (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ff5967c1b09ad59f249297b1cf0a4ed900faf4a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="90570-102">Gewusst wie: Aufrufen einer überladenen Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90570-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="90570-103">Der Vorteil der überladen einer Prozedur ist die Flexibilität des Aufrufs.</span><span class="sxs-lookup"><span data-stu-id="90570-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="90570-104">Der aufrufende Code erhalten die Informationen, die sie an die Prozedur übergeben, und rufen Sie anschließend auf einen einzelnen Prozedurnamen, unabhängig davon, welche Argumente übergeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="90570-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="90570-105">Zum Aufrufen einer Prozedur, die mehr als eine Version definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="90570-105">To call a procedure that has more than one version defined</span></span>  
  
1.  <span data-ttu-id="90570-106">Bestimmen Sie in den aufrufenden Code, welche Daten an die Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="90570-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2.  <span data-ttu-id="90570-107">Schreiben des Prozeduraufrufs auf normale Weise darstellen der Daten in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="90570-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="90570-108">Achten Sie darauf, dass die Argumente die Parameterliste in einer der Versionen für die Prozedur definierten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="90570-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3.  <span data-ttu-id="90570-109">Sie müssen keinen bestimmen, welche Version der Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="90570-109">You do not have to determine which version of the procedure to call.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="90570-110">übergibt die Steuerung an die Version, die Ihre Argumentliste entspricht.</span><span class="sxs-lookup"><span data-stu-id="90570-110"> passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="90570-111">Im folgenden Beispiel wird die `post` Prozedur deklariert [wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="90570-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="90570-112">Es ruft die Kunden-ID, bestimmt, ob es ist ein `String` oder ein `Integer`, und ruft dann in beiden Fällen das gleiche Verfahren.</span><span class="sxs-lookup"><span data-stu-id="90570-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="90570-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90570-113">See Also</span></span>  
 [<span data-ttu-id="90570-114">Verfahren</span><span class="sxs-lookup"><span data-stu-id="90570-114">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="90570-115">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="90570-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="90570-116">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="90570-116">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="90570-117">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="90570-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="90570-118">Gewusst wie: Definieren mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="90570-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="90570-119">Gewusst wie: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="90570-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="90570-120">Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="90570-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="90570-121">Überlegungen zur Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="90570-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="90570-122">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="90570-122">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="90570-123">Overloads</span><span class="sxs-lookup"><span data-stu-id="90570-123">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
