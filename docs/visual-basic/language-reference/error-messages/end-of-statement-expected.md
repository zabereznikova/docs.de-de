---
title: end of-Anweisung erwartet.
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: ab6a4a0e6736e2af9c1fa0dd170b6aa4c42d9e4a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817153"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="3e1d2-102">end of-Anweisung erwartet.</span><span class="sxs-lookup"><span data-stu-id="3e1d2-102">End of statement expected</span></span>
<span data-ttu-id="3e1d2-103">Die Anweisung syntaktisch abgeschlossen ist, aber eine zusätzliche Programmierelement folgt auf das Element, das die Anweisung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3e1d2-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="3e1d2-104">Ein Zeilenabschlusszeichen ist am Ende jeder Anweisung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3e1d2-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="3e1d2-105">Ein Zeilenabschlusszeichen teilt die Zeichen einer Visual Basic-Quelldatei in Zeilen.</span><span class="sxs-lookup"><span data-stu-id="3e1d2-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="3e1d2-106">Beispiele für Zeilenabschlusszeichen sind, die Unicode-Carriage return Zeichen (& HD), die Unicode-Zeilenvorschub-Zeichen (& HA), und Unicode-Wagenrücklaufzeichen gefolgt von dem Unicode-Zeichen für Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="3e1d2-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="3e1d2-107">Weitere Informationen zu Zeilenabschlusszeichen, finden Sie unter den [Visual Basic-Sprachspezifikation](~/_vblang/spec/lexical-grammar.md#line-terminators).</span><span class="sxs-lookup"><span data-stu-id="3e1d2-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>
  
 <span data-ttu-id="3e1d2-108">**Fehler-ID:** BC30205</span><span class="sxs-lookup"><span data-stu-id="3e1d2-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3e1d2-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="3e1d2-109">To correct this error</span></span>
  
1.  <span data-ttu-id="3e1d2-110">Überprüfen Sie, wenn zwei verschiedene Anweisungen in der gleichen Zeile versehentlich gestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3e1d2-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2.  <span data-ttu-id="3e1d2-111">Fügen Sie einem Zeilenabschluss, nach das Element, das die Anweisung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3e1d2-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3e1d2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e1d2-112">See also</span></span>

- [<span data-ttu-id="3e1d2-113">Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code</span><span class="sxs-lookup"><span data-stu-id="3e1d2-113">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="3e1d2-114">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="3e1d2-114">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
