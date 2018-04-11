---
title: Auto (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1e32c4c910567829a4f5c59b48020db4dfbbeb7b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="auto-visual-basic"></a><span data-ttu-id="ff482-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff482-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="ff482-103">Gibt an, dass Visual Basic Zeichenfolgen gemäß der .NET Framework-Regeln, die basierend auf den externen Namen der externen Prozedur, die deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="ff482-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="ff482-104">Wenn Sie eine Prozedur, die außerhalb des Projekts definiert aufrufen, Visual Basic-Compiler keinen Zugriff auf die Informationen, die sie zum ordnungsgemäßen Aufrufen der Prozedur benötigen.</span><span class="sxs-lookup"><span data-stu-id="ff482-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="ff482-105">Diese Informationen umfassen, auf dem sich die Prozedur befindet, wie festgestellt wird, werden der Aufrufsequenz und Rückgabetyp und die Zeichenfolge verwendeten Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="ff482-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="ff482-106">Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="ff482-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="ff482-107">Die `charsetmodifier` teilweise in die `Declare` Anweisung liefert die Informationen für das Marshalling von Zeichenfolgen bei einem Aufruf an die externe Prozedur Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ff482-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="ff482-108">Er wirkt sich auch, wie Visual Basic die externe Datei für den externen Prozedurnamen durchsucht.</span><span class="sxs-lookup"><span data-stu-id="ff482-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="ff482-109">Die `Auto` Modifizierer gibt an, dass Visual Basic Marshallen von Zeichenfolgen .NET Framework-Regeln entsprechend, und, dass die Basis Zeichensatz der Plattform zur Laufzeit und möglicherweise bestimmt werden soll, den Namen der externen Prozedur, ändern Wenn der anfänglichen Suche ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="ff482-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="ff482-110">Weitere Informationen finden Sie unter "Zeichensätze" in [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ff482-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="ff482-111">Wenn kein Modifizierer angegeben ist, `Ansi` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ff482-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff482-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff482-112">Remarks</span></span>  
 <span data-ttu-id="ff482-113">Die `Auto` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="ff482-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="ff482-114">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ff482-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="ff482-115">Entwicklerhinweise für intelligente Geräte</span><span class="sxs-lookup"><span data-stu-id="ff482-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="ff482-116">Dieses Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ff482-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff482-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff482-117">See Also</span></span>  
 [<span data-ttu-id="ff482-118">ANSI</span><span class="sxs-lookup"><span data-stu-id="ff482-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [<span data-ttu-id="ff482-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="ff482-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [<span data-ttu-id="ff482-120">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ff482-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
