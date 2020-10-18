---
title: end of-Anweisung erwartet.
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 36883989fe5aa0b5c70aa9ab1f7c991fab99e778
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163128"
---
# <a name="bc30205-end-of-statement-expected"></a><span data-ttu-id="c419f-102">BC30205: Ende der Anweisung erwartet.</span><span class="sxs-lookup"><span data-stu-id="c419f-102">BC30205: End of statement expected</span></span>

<span data-ttu-id="c419f-103">Die-Anweisung ist syntaktisch abgeschlossen, aber ein zusätzliches Programmier Element folgt dem-Element, das die-Anweisung abschließt.</span><span class="sxs-lookup"><span data-stu-id="c419f-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="c419f-104">Am Ende jeder Anweisung ist ein Zeichen für den Zeilen Abschluss erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c419f-104">A line terminator is required at the end of every statement.</span></span>

 <span data-ttu-id="c419f-105">Ein Zeichen für den Zeilen Abschluss dividiert die Zeichen einer Visual Basic Quelldatei in Zeilen.</span><span class="sxs-lookup"><span data-stu-id="c419f-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="c419f-106">Beispiele für Zeilen Abschluss Zeichen sind das Unicode-Wagen Rücklauf Zeichen (&HD), das Unicode-Zeilenvorschub Zeichen (&ha) und das Unicode-Wagen Rücklauf Zeichen, gefolgt vom Unicode-Zeilenvorschub Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c419f-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="c419f-107">Weitere Informationen zu Zeilen Abschluss Zeichen finden Sie in der [Visual Basic-Sprachspezifikation](~/_vblang/spec/lexical-grammar.md#line-terminators).</span><span class="sxs-lookup"><span data-stu-id="c419f-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>

 <span data-ttu-id="c419f-108">**Fehler-ID:** BC30205</span><span class="sxs-lookup"><span data-stu-id="c419f-108">**Error ID:** BC30205</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c419f-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c419f-109">To correct this error</span></span>

1. <span data-ttu-id="c419f-110">Überprüfen Sie, ob zwei unterschiedliche Anweisungen versehentlich in derselben Zeile abgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="c419f-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>

2. <span data-ttu-id="c419f-111">Fügen Sie ein Zeilen Abschluss Zeichen nach dem Element ein, das die Anweisung abschließt.</span><span class="sxs-lookup"><span data-stu-id="c419f-111">Insert a line terminator after the element that completes the statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="c419f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c419f-112">See also</span></span>

- [<span data-ttu-id="c419f-113">Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code</span><span class="sxs-lookup"><span data-stu-id="c419f-113">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="c419f-114">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="c419f-114">Statements</span></span>](../../programming-guide/language-features/statements.md)
