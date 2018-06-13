---
title: Ungültiger Ordinalwert.
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 12d73b33e3c025b40c98d84e3507af7be1e1e91a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593602"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="3250d-102">Ungültiger Ordinalwert.</span><span class="sxs-lookup"><span data-stu-id="3250d-102">Ordinal is not valid</span></span>
<span data-ttu-id="3250d-103">Rufen Sie eine Dynamic Link Library (DLL) angegeben wird, eine Zahl statt einem Prozedurnamen verwenden mithilfe der `#num` Syntax.</span><span class="sxs-lookup"><span data-stu-id="3250d-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="3250d-104">Dieser Fehler hat die folgenden möglichen Ursachen:</span><span class="sxs-lookup"><span data-stu-id="3250d-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="3250d-105">Ein Versuch, konvertieren die `#num` Ausdruck, der eine Ordinalzahl ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="3250d-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="3250d-106">Die `#num` angegebenen gibt keine Funktion in der DLL.</span><span class="sxs-lookup"><span data-stu-id="3250d-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="3250d-107">Eine Typbibliothek weist eine ungültige Deklaration in die interne Verwendung des eine ungültige Ordinalzahl.</span><span class="sxs-lookup"><span data-stu-id="3250d-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3250d-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="3250d-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="3250d-109">Stellen Sie sicher, dass der Ausdruck eine gültige Zahl darstellt, oder rufen Sie die Prozedur nach Namen.</span><span class="sxs-lookup"><span data-stu-id="3250d-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2.  <span data-ttu-id="3250d-110">Stellen Sie sicher, dass `#num` identifiziert eine gültige Funktion in der DLL.</span><span class="sxs-lookup"><span data-stu-id="3250d-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3.  <span data-ttu-id="3250d-111">Isolieren Sie den Aufruf der Prozedur das Problem verursacht, indem Sie den Code auskommentieren.</span><span class="sxs-lookup"><span data-stu-id="3250d-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="3250d-112">Schreiben einer `Declare` -Anweisung für die Prozedur, und klicken Sie auf Bericht des Problems an den Hersteller der Typbibliothek weiter.</span><span class="sxs-lookup"><span data-stu-id="3250d-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3250d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3250d-113">See Also</span></span>  
 [<span data-ttu-id="3250d-114">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3250d-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
