---
title: Ansi (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aa5724eb9123b2776c3a579e4244c55b3129816b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="e461c-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e461c-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="e461c-103">Gibt an, dass Visual Basic alle Zeichenfolgen in American National Standards Institute (ANSI)-Werte unabhängig von den Namen der die deklarierte externe Prozedur marshallen soll.</span><span class="sxs-lookup"><span data-stu-id="e461c-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="e461c-104">Wenn Sie eine Prozedur, die außerhalb des Projekts definiert aufrufen, Visual Basic-Compiler keinen Zugriff auf die Informationen zum ordnungsgemäßen Aufrufen der Prozedur benötigt.</span><span class="sxs-lookup"><span data-stu-id="e461c-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="e461c-105">Diese Informationen umfassen, auf dem sich die Prozedur befindet, wie festgestellt wird, werden der Aufrufsequenz und Rückgabetyp und die Zeichenfolge verwendeten Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="e461c-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="e461c-106">Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="e461c-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="e461c-107">Die `charsetmodifier` teilweise in die `Declare` Anweisung liefert die Informationen für das Marshalling von Zeichenfolgen bei einem Aufruf an die externe Prozedur Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e461c-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="e461c-108">Er wirkt sich auch, wie Visual Basic die externe Datei für den externen Prozedurnamen durchsucht.</span><span class="sxs-lookup"><span data-stu-id="e461c-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="e461c-109">Die `Ansi` Modifizierer gibt an, dass Visual Basic alle Zeichenfolgen in ANSI-Werte marshallen und die Prozedur nachschlagen soll, ohne den Namen ändern, während der Suche.</span><span class="sxs-lookup"><span data-stu-id="e461c-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="e461c-110">Wenn kein Modifizierer angegeben ist, `Ansi` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="e461c-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e461c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e461c-111">Remarks</span></span>  
 <span data-ttu-id="e461c-112">Die `Ansi` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="e461c-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="e461c-113">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e461c-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="e461c-114">Entwicklerhinweise für intelligente Geräte</span><span class="sxs-lookup"><span data-stu-id="e461c-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="e461c-115">Dieses Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e461c-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e461c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e461c-116">See Also</span></span>  
 [<span data-ttu-id="e461c-117">Auto</span><span class="sxs-lookup"><span data-stu-id="e461c-117">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)  
 [<span data-ttu-id="e461c-118">Unicode</span><span class="sxs-lookup"><span data-stu-id="e461c-118">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [<span data-ttu-id="e461c-119">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e461c-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
