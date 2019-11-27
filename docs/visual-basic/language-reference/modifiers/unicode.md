---
title: Unicode
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: c4286ed9e9d5fd768ae29b7050b3d1505ccca9dd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344224"
---
# <a name="unicode-visual-basic"></a><span data-ttu-id="00364-102">Unicode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00364-102">Unicode (Visual Basic)</span></span>
<span data-ttu-id="00364-103">Gibt an, dass Visual Basic alle Zeichen folgen in Unicode-Werte Mars Hallen soll, unabhängig vom Namen der externen Prozedur, die deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="00364-103">Specifies that Visual Basic should marshal all strings to Unicode values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="00364-104">Wenn Sie eine Prozedur aufrufen, die außerhalb des Projekts definiert ist, hat der Visual Basic Compiler keinen Zugriff auf die Informationen, die er benötigt, um die Prozedur ordnungsgemäß aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="00364-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have in order to call the procedure correctly.</span></span> <span data-ttu-id="00364-105">Diese Informationen umfassen den Speicherort der Prozedur, deren Identifizierung, die Aufruf Sequenz und den Rückgabetyp sowie den verwendeten Zeichen folgen Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="00364-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="00364-106">Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="00364-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="00364-107">Der `charsetmodifier` Teil in der `Declare`-Anweisung liefert die Zeichensatz Informationen, um Zeichen folgen während eines Aufrufens der externen Prozedur zu Mars Hallen.</span><span class="sxs-lookup"><span data-stu-id="00364-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information to marshal strings during a call to the external procedure.</span></span> <span data-ttu-id="00364-108">Es wirkt sich auch darauf aus, wie Visual Basic die externe Datei nach dem Namen der externen Prozedur durchsucht.</span><span class="sxs-lookup"><span data-stu-id="00364-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="00364-109">Der `Unicode` Modifizierer gibt an, dass Visual Basic alle Zeichen folgen in Unicode-Werte Mars Hallen und die Prozedur suchen soll, ohne den Namen während der Suche zu ändern.</span><span class="sxs-lookup"><span data-stu-id="00364-109">The `Unicode` modifier specifies that Visual Basic should marshal all strings to Unicode values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="00364-110">Wenn kein zeichensetmodifizierer angegeben ist, ist `Ansi` der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="00364-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00364-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00364-111">Remarks</span></span>  
 <span data-ttu-id="00364-112">Der `Unicode` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="00364-112">The `Unicode` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="00364-113">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="00364-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="00364-114">Entwickler Hinweise zu intelligenten Geräten</span><span class="sxs-lookup"><span data-stu-id="00364-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="00364-115">Dieses Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="00364-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00364-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00364-116">See also</span></span>

- [<span data-ttu-id="00364-117">ANSI</span><span class="sxs-lookup"><span data-stu-id="00364-117">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="00364-118">Auto</span><span class="sxs-lookup"><span data-stu-id="00364-118">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="00364-119">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="00364-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
