---
title: Ungültiger Ordinalwert.
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 64f56b2ecace0ceafb310a175ea605e6959b7256
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871391"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="37a4f-102">Ungültiger Ordinalwert.</span><span class="sxs-lookup"><span data-stu-id="37a4f-102">Ordinal is not valid</span></span>

<span data-ttu-id="37a4f-103">Durch den Aufrufe einer Dynamic Link Library (dll) wird angegeben, dass eine Zahl anstelle eines Prozedur namens verwendet werden soll. verwenden Sie dazu die `#num` Syntax.</span><span class="sxs-lookup"><span data-stu-id="37a4f-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="37a4f-104">Dieser Fehler kann folgende Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="37a4f-104">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="37a4f-105">Fehler beim Konvertieren des `#num` Ausdrucks in eine Ordinalzahl.</span><span class="sxs-lookup"><span data-stu-id="37a4f-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
- <span data-ttu-id="37a4f-106">Der `#num` angegebene gibt keine Funktion in der dll an.</span><span class="sxs-lookup"><span data-stu-id="37a4f-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
- <span data-ttu-id="37a4f-107">Eine Typbibliothek hat eine ungültige Deklaration, die zur internen Verwendung einer ungültigen Ordinalzahl führt.</span><span class="sxs-lookup"><span data-stu-id="37a4f-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="37a4f-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="37a4f-108">To correct this error</span></span>  
  
1. <span data-ttu-id="37a4f-109">Stellen Sie sicher, dass der Ausdruck eine gültige Zahl darstellt, oder nennen Sie die Prozedur mit dem Namen.</span><span class="sxs-lookup"><span data-stu-id="37a4f-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="37a4f-110">Stellen Sie sicher, dass `#num` eine gültige Funktion in der DLL identifiziert.</span><span class="sxs-lookup"><span data-stu-id="37a4f-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="37a4f-111">Isolieren Sie den Prozedur Aufrufe, der das Problem verursacht, indem Sie den Code auskommentieren.</span><span class="sxs-lookup"><span data-stu-id="37a4f-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="37a4f-112">Schreiben `Declare` Sie eine-Anweisung für die Prozedur, und melden Sie das Problem dem Hersteller der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="37a4f-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37a4f-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37a4f-113">See also</span></span>

- [<span data-ttu-id="37a4f-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="37a4f-114">Declare Statement</span></span>](../statements/declare-statement.md)
