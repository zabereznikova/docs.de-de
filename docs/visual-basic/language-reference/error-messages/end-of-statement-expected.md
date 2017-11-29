---
title: end of-Anweisung erwartet.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords: BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4934952015cb4871bcd90cef982eab5425b1617f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="3aee0-102">end of-Anweisung erwartet.</span><span class="sxs-lookup"><span data-stu-id="3aee0-102">End of statement expected</span></span>
<span data-ttu-id="3aee0-103">Eine zusätzliche Programmierelement folgt das Element, das die Anweisung abgeschlossen ist, aber die Anweisung syntaktisch abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3aee0-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="3aee0-104">Ein Zeilenabschlusszeichen ist am Ende jeder Anweisung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3aee0-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="3aee0-105">Ein Zeilenabschlusszeichen teilt die Zeichen einer Visual Basic-Quelldatei in Zeilen.</span><span class="sxs-lookup"><span data-stu-id="3aee0-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="3aee0-106">Beispiele für Zeilenabschlusszeichen sind die Unicode-Carriage return Zeichen (& HD), die Unicode-Zeilenvorschub Zeichen (& HA), und die Unicode-Wagenrücklaufzeichen gefolgt von der Zeilenvorschubzeichen Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="3aee0-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="3aee0-107">Weitere Informationen zu Zeilenabschlusszeichen, finden Sie unter der [Visual Basic-Sprachspezifikation](../../../visual-basic/reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="3aee0-107">For more information about line terminators, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification/index.md).</span></span>
  
 <span data-ttu-id="3aee0-108">**Fehler-ID:** BC30205</span><span class="sxs-lookup"><span data-stu-id="3aee0-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3aee0-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="3aee0-109">To correct this error</span></span>
  
1.  <span data-ttu-id="3aee0-110">Überprüfen Sie, um festzustellen, ob die beiden andere Anweisungen in der gleichen Zeile versehentlich gestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3aee0-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2.  <span data-ttu-id="3aee0-111">Fügen Sie einem Zeilenabschluss nach dem Element, das die Anweisung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3aee0-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3aee0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3aee0-112">See Also</span></span>  
 [<span data-ttu-id="3aee0-113">Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code</span><span class="sxs-lookup"><span data-stu-id="3aee0-113">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [<span data-ttu-id="3aee0-114">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="3aee0-114">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
