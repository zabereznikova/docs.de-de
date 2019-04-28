---
title: Unicode (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: b3c9452f8d144fb18ea3efcb35b85caed80e8692
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778676"
---
# <a name="unicode-visual-basic"></a><span data-ttu-id="3cb4b-102">Unicode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cb4b-102">Unicode (Visual Basic)</span></span>
<span data-ttu-id="3cb4b-103">Gibt an, dass es sich bei Visual Basic alle Zeichenfolgen in Unicode-Werten, unabhängig vom Namen des deklarierten der externen Prozedur marshallen soll.</span><span class="sxs-lookup"><span data-stu-id="3cb4b-103">Specifies that Visual Basic should marshal all strings to Unicode values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="3cb4b-104">Wenn Sie eine Prozedur, die außerhalb des Projekts definiert aufrufen, Visual Basic-Compiler keinen Zugriff auf die Informationen, die sie benötigen, um die Prozedur richtig aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3cb4b-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have in order to call the procedure correctly.</span></span> <span data-ttu-id="3cb4b-105">Diese Informationen umfassen, in dem die Prozedur befindet, wie dieses ermittelt wird, die Aufrufsequenz und Rückgabetyp und die Zeichenfolge festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="3cb4b-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="3cb4b-106">Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="3cb4b-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="3cb4b-107">Die `charsetmodifier` -Teil in die `Declare` -Anweisung gibt die Zeichen zum Marshallen von Zeichenfolgen bei einem Aufruf der externen Prozedur Informationen.</span><span class="sxs-lookup"><span data-stu-id="3cb4b-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information to marshal strings during a call to the external procedure.</span></span> <span data-ttu-id="3cb4b-108">Es wirkt sich auch, wie Visual Basic die externe Datei für den externen Prozedurnamen durchsucht.</span><span class="sxs-lookup"><span data-stu-id="3cb4b-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="3cb4b-109">Die `Unicode` %(Dateiname) gibt an, dass Visual Basic alle Zeichenfolgen in Unicode-Werte marshallen und die Prozedur suchen soll, ohne seinen Namen bei der Suche zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3cb4b-109">The `Unicode` modifier specifies that Visual Basic should marshal all strings to Unicode values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="3cb4b-110">Wenn kein Modifizierer angegeben ist, `Ansi` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="3cb4b-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cb4b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3cb4b-111">Remarks</span></span>  
 <span data-ttu-id="3cb4b-112">Die `Unicode` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="3cb4b-112">The `Unicode` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="3cb4b-113">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3cb4b-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="3cb4b-114">Hinweise für Entwickler intelligente Geräte</span><span class="sxs-lookup"><span data-stu-id="3cb4b-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="3cb4b-115">Dieses Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3cb4b-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb4b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cb4b-116">See also</span></span>

- [<span data-ttu-id="3cb4b-117">ANSI</span><span class="sxs-lookup"><span data-stu-id="3cb4b-117">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="3cb4b-118">Auto</span><span class="sxs-lookup"><span data-stu-id="3cb4b-118">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="3cb4b-119">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3cb4b-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
