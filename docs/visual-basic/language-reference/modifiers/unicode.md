---
title: Unicode (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 042908b8427de2de0de96bbb32df7be018bb915c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="unicode-visual-basic"></a><span data-ttu-id="6dd06-102">Unicode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6dd06-102">Unicode (Visual Basic)</span></span>
<span data-ttu-id="6dd06-103">Gibt an, dass Visual Basic alle Zeichenfolgen in Unicode-Werte unabhängig von den Namen der die deklarierte externe Prozedur marshallen soll.</span><span class="sxs-lookup"><span data-stu-id="6dd06-103">Specifies that Visual Basic should marshal all strings to Unicode values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="6dd06-104">Wenn Sie eine Prozedur, die außerhalb des Projekts definiert aufrufen, Visual Basic-Compiler keinen Zugriff auf die Informationen, die sie benötigen, um die Prozedur ordnungsgemäß aufrufen.</span><span class="sxs-lookup"><span data-stu-id="6dd06-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have in order to call the procedure correctly.</span></span> <span data-ttu-id="6dd06-105">Diese Informationen umfassen, auf dem sich die Prozedur befindet, wie festgestellt wird, werden der Aufrufsequenz und Rückgabetyp und die Zeichenfolge verwendeten Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="6dd06-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="6dd06-106">Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="6dd06-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="6dd06-107">Die `charsetmodifier` teilweise in die `Declare` -Anweisung gibt die Zeichen zum Marshallen von Zeichenfolgen während eines Aufrufs an die externe Prozedur Informationen.</span><span class="sxs-lookup"><span data-stu-id="6dd06-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information to marshal strings during a call to the external procedure.</span></span> <span data-ttu-id="6dd06-108">Er wirkt sich auch, wie Visual Basic die externe Datei für den externen Prozedurnamen durchsucht.</span><span class="sxs-lookup"><span data-stu-id="6dd06-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="6dd06-109">Die `Unicode` Modifizierer gibt an, dass Visual Basic alle Zeichenfolgen in Unicode-Werte marshallen und die Prozedur nachschlagen soll, ohne den Namen ändern, während der Suche.</span><span class="sxs-lookup"><span data-stu-id="6dd06-109">The `Unicode` modifier specifies that Visual Basic should marshal all strings to Unicode values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="6dd06-110">Wenn kein Modifizierer angegeben ist, `Ansi` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="6dd06-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dd06-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6dd06-111">Remarks</span></span>  
 <span data-ttu-id="6dd06-112">Die `Unicode` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="6dd06-112">The `Unicode` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="6dd06-113">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6dd06-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="6dd06-114">Entwicklerhinweise für intelligente Geräte</span><span class="sxs-lookup"><span data-stu-id="6dd06-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="6dd06-115">Dieses Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6dd06-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd06-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6dd06-116">See Also</span></span>  
 [<span data-ttu-id="6dd06-117">ANSI</span><span class="sxs-lookup"><span data-stu-id="6dd06-117">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [<span data-ttu-id="6dd06-118">Auto</span><span class="sxs-lookup"><span data-stu-id="6dd06-118">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)  
 [<span data-ttu-id="6dd06-119">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6dd06-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
