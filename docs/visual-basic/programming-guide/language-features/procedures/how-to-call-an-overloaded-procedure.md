---
title: 'Vorgehensweise: Aufrufen einer überladenen Prozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: d325c09516b4ce03facedce86f17ea49480b997a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317805"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="ca819-102">Vorgehensweise: Aufrufen einer überladenen Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca819-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="ca819-103">Der Vorteil der überladen einer Prozedur ist die Flexibilität des Aufrufs.</span><span class="sxs-lookup"><span data-stu-id="ca819-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="ca819-104">Der aufrufende Code kann die Informationen abrufen, die er an die Prozedur übergeben, und rufen Sie dann auf einen einzelnen Prozedurnamen, unabhängig davon, welche Argumente übergeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="ca819-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="ca819-105">Zum Aufrufen einer Prozedur, die mehr als eine Version, die definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ca819-105">To call a procedure that has more than one version defined</span></span>  
  
1. <span data-ttu-id="ca819-106">Bestimmen Sie im aufrufenden Code, welche Daten an die Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="ca819-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2. <span data-ttu-id="ca819-107">Schreiben Sie den Aufruf der Prozedur, auf die übliche Weise, die darstellen der Daten in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="ca819-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="ca819-108">Achten Sie darauf, dass die Argumente die Parameterliste in einer der Versionen für die Prozedur definierten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ca819-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3. <span data-ttu-id="ca819-109">Sie müssen nicht festlegen, welche Version der Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ca819-109">You do not have to determine which version of the procedure to call.</span></span> <span data-ttu-id="ca819-110">Visual Basic übergibt die Steuerung an die Version, die angegebene Argumentliste passt.</span><span class="sxs-lookup"><span data-stu-id="ca819-110">Visual Basic passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="ca819-111">Im folgenden Beispiel wird die `post` Prozedur deklariert [Vorgehensweise: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="ca819-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="ca819-112">Es ruft die Kunden-ID, die bestimmt, ob es eine `String` oder `Integer`, und ruft dann in beiden Fällen das gleiche Verfahren.</span><span class="sxs-lookup"><span data-stu-id="ca819-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a><span data-ttu-id="ca819-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca819-113">See also</span></span>

- [<span data-ttu-id="ca819-114">Verfahren</span><span class="sxs-lookup"><span data-stu-id="ca819-114">Procedures</span></span>](./index.md)
- [<span data-ttu-id="ca819-115">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="ca819-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="ca819-116">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="ca819-116">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="ca819-117">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="ca819-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="ca819-118">Vorgehensweise: Definieren Sie mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="ca819-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="ca819-119">Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="ca819-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="ca819-120">Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="ca819-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="ca819-121">Überlegungen zur Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="ca819-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="ca819-122">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="ca819-122">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="ca819-123">Overloads</span><span class="sxs-lookup"><span data-stu-id="ca819-123">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
