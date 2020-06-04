---
title: Ungültiger Ordinalwert.
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 7b9bd8435b56dd5e33d14eb35d76aacc7d60c8b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413052"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="d0967-102">Ungültiger Ordinalwert.</span><span class="sxs-lookup"><span data-stu-id="d0967-102">Ordinal is not valid</span></span>
<span data-ttu-id="d0967-103">Durch den Aufrufe einer Dynamic Link Library (dll) wird angegeben, dass eine Zahl anstelle eines Prozedur namens verwendet werden soll. verwenden Sie dazu die `#num` Syntax.</span><span class="sxs-lookup"><span data-stu-id="d0967-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="d0967-104">Dieser Fehler kann folgende Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="d0967-104">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="d0967-105">Fehler beim Konvertieren des `#num` Ausdrucks in eine Ordinalzahl.</span><span class="sxs-lookup"><span data-stu-id="d0967-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
- <span data-ttu-id="d0967-106">Der `#num` angegebene gibt keine Funktion in der dll an.</span><span class="sxs-lookup"><span data-stu-id="d0967-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
- <span data-ttu-id="d0967-107">Eine Typbibliothek hat eine ungültige Deklaration, die zur internen Verwendung einer ungültigen Ordinalzahl führt.</span><span class="sxs-lookup"><span data-stu-id="d0967-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d0967-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d0967-108">To correct this error</span></span>  
  
1. <span data-ttu-id="d0967-109">Stellen Sie sicher, dass der Ausdruck eine gültige Zahl darstellt, oder nennen Sie die Prozedur mit dem Namen.</span><span class="sxs-lookup"><span data-stu-id="d0967-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="d0967-110">Stellen Sie sicher, dass `#num` eine gültige Funktion in der DLL identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d0967-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="d0967-111">Isolieren Sie den Prozedur Aufrufe, der das Problem verursacht, indem Sie den Code auskommentieren.</span><span class="sxs-lookup"><span data-stu-id="d0967-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="d0967-112">Schreiben `Declare` Sie eine-Anweisung für die Prozedur, und melden Sie das Problem dem Hersteller der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="d0967-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0967-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0967-113">See also</span></span>

- [<span data-ttu-id="d0967-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="d0967-114">Declare Statement</span></span>](../statements/declare-statement.md)
