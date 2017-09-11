---
title: "Gewusst wie: Aufrufen einer überladenen Prozedur (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, overloading
- procedures, calling
- procedures, multiple versions
- procedure calls, overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 777df0cc81a4e0518773a0e8cc98d590d1c0cf0d
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="cbef9-102">Gewusst wie: Aufrufen einer überladenen Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbef9-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="cbef9-103">Der Vorteil der überladen einer Prozedur ist die Flexibilität des Aufrufs.</span><span class="sxs-lookup"><span data-stu-id="cbef9-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="cbef9-104">Der aufrufende Code kann die Informationen abrufen, die an die Prozedur übergeben, und rufen Sie dann einen einzelnen Prozedurnamen, unabhängig davon, welche Argumente übergeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="cbef9-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="cbef9-105">Zum Aufrufen einer Prozedur, die mehr als eine Version definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="cbef9-105">To call a procedure that has more than one version defined</span></span>  
  
1.  <span data-ttu-id="cbef9-106">Bestimmen Sie in den aufrufenden Code, welche Daten an die Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="cbef9-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2.  <span data-ttu-id="cbef9-107">Schreiben Sie den Prozeduraufruf auf die übliche Weise, die Präsentation von Daten in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="cbef9-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="cbef9-108">Werden Sie sicher, dass die Argumente der Parameterliste einer der Versionen für die Prozedur definiert übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cbef9-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3.  <span data-ttu-id="cbef9-109">Sie müssen keinen bestimmen, welche Version der Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cbef9-109">You do not have to determine which version of the procedure to call.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="cbef9-110">übergibt die Steuerung an die Version der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="cbef9-110"> passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="cbef9-111">Im folgenden Beispiel wird die `post` Prozedur deklariert [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="cbef9-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="cbef9-112">Es ruft die Kunden-ID, bestimmt, ob es ein `String` oder `Integer`, und ruft dann in beiden Fällen das gleiche Verfahren.</span><span class="sxs-lookup"><span data-stu-id="cbef9-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     <span data-ttu-id="cbef9-113">[!code-vb[VbVbcnProcedures&#56;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cbef9-113">[!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="cbef9-114">[!code-vb[VbVbcnProcedures&#57;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="cbef9-114">[!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbef9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbef9-115">See Also</span></span>  
 <span data-ttu-id="cbef9-116">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="cbef9-116">[Procedures](./index.md) </span></span>  
<span data-ttu-id="cbef9-117"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="cbef9-117"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="cbef9-118"> [Prozedurüberladung](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="cbef9-118"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="cbef9-119"> [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="cbef9-119"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="cbef9-120"> [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="cbef9-120"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="cbef9-121"> [Gewusst wie: überladen eine Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="cbef9-121"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="cbef9-122"> [Gewusst wie: überladen eine Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="cbef9-122"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="cbef9-123"> [Überlegungen zur prozedurüberladung](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="cbef9-123"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="cbef9-124"> [Überladungsauflösung](./overload-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="cbef9-124"> [Overload Resolution](./overload-resolution.md) </span></span>  
<span data-ttu-id="cbef9-125"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)</span><span class="sxs-lookup"><span data-stu-id="cbef9-125"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)</span></span>
