---
title: 'Gewusst wie: Aufrufen einer überladenen Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: d983f5f6183c33141079ed35171f7a73f254450f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340205"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="f7cb5-102">Gewusst wie: Aufrufen einer überladenen Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7cb5-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="f7cb5-103">Der Vorteil beim Überladen einer Prozedur ist die Flexibilität des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="f7cb5-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="f7cb5-104">Der aufrufende Code kann die Informationen abrufen, die er an die Prozedur übergeben muss, und dann einen einzelnen Prozedur Namen aufrufen, unabhängig davon, welche Argumente er übergibt.</span><span class="sxs-lookup"><span data-stu-id="f7cb5-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="f7cb5-105">So wenden Sie eine Prozedur an, für die mehr als eine Version definiert ist</span><span class="sxs-lookup"><span data-stu-id="f7cb5-105">To call a procedure that has more than one version defined</span></span>  
  
1. <span data-ttu-id="f7cb5-106">Legen Sie im aufrufenden Code fest, welche Daten an die Prozedur übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f7cb5-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2. <span data-ttu-id="f7cb5-107">Schreiben Sie den Prozedur Befehl auf die normale Weise, und stellen Sie die Daten in der Argumentliste dar.</span><span class="sxs-lookup"><span data-stu-id="f7cb5-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="f7cb5-108">Stellen Sie sicher, dass die Argumente der Parameterliste in einer der für die Prozedur definierten Versionen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f7cb5-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3. <span data-ttu-id="f7cb5-109">Sie müssen nicht ermitteln, welche Version der Prozedur aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7cb5-109">You do not have to determine which version of the procedure to call.</span></span> <span data-ttu-id="f7cb5-110">Visual Basic übergibt die Steuerung an die Version, die mit der Argumentliste übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="f7cb5-110">Visual Basic passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="f7cb5-111">Im folgenden Beispiel wird die in Gewusst [wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)deklarierte `post` Prozedur aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f7cb5-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="f7cb5-112">Er ruft die Kundenidentifikation ab, bestimmt, ob es sich um eine `String` oder eine `Integer`handelt, und ruft dann in beiden Fällen dieselbe Prozedur auf.</span><span class="sxs-lookup"><span data-stu-id="f7cb5-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a><span data-ttu-id="f7cb5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7cb5-113">See also</span></span>

- [<span data-ttu-id="f7cb5-114">Verfahren</span><span class="sxs-lookup"><span data-stu-id="f7cb5-114">Procedures</span></span>](./index.md)
- [<span data-ttu-id="f7cb5-115">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f7cb5-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f7cb5-116">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="f7cb5-116">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="f7cb5-117">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f7cb5-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="f7cb5-118">Gewusst wie: Definieren mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="f7cb5-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="f7cb5-119">Gewusst wie: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="f7cb5-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="f7cb5-120">Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="f7cb5-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="f7cb5-121">Überlegungen zur Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="f7cb5-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="f7cb5-122">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="f7cb5-122">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="f7cb5-123">Overloads</span><span class="sxs-lookup"><span data-stu-id="f7cb5-123">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
