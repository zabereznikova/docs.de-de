---
title: Auto (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: e4beb320b3aa0cadb790dd3ab92255496bc32f05
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843837"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="3da04-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3da04-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="3da04-103">Gibt an, dass es sich bei Visual Basic Zeichenfolgen gemäß der .NET Framework-Regeln, die basierend auf den externen Namen der externen Prozedur deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="3da04-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="3da04-104">Wenn Sie eine Prozedur, die außerhalb des Projekts definiert aufrufen, Visual Basic-Compiler keinen Zugriff auf die Informationen, die sie benötigen, um die Prozedur aufrufen, ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="3da04-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="3da04-105">Diese Informationen umfassen, in dem die Prozedur befindet, wie dieses ermittelt wird, die Aufrufsequenz und Rückgabetyp und die Zeichenfolge festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="3da04-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="3da04-106">Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="3da04-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="3da04-107">Die `charsetmodifier` -Teil in die `Declare` -Anweisung gibt die Informationen für das Marshalling von Zeichenfolgen bei einem Aufruf der externen Prozedur Zeichen.</span><span class="sxs-lookup"><span data-stu-id="3da04-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="3da04-108">Es wirkt sich auch, wie Visual Basic die externe Datei für den externen Prozedurnamen durchsucht.</span><span class="sxs-lookup"><span data-stu-id="3da04-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="3da04-109">Die `Auto` %(Dateiname) gibt an, dass Visual Basic Zeichenfolgen gemäß der .NET Framework-Regeln marshallen, und, dass die Basis Zeichensatz der Laufzeit-Plattform und möglicherweise bestimmt werden soll den externen Prozedurnamen ändern, wenn es sich bei der anfänglichen Suche ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="3da04-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="3da04-110">Weitere Informationen finden Sie unter "Zeichensatz" in [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3da04-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="3da04-111">Wenn kein Modifizierer angegeben ist, `Ansi` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="3da04-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3da04-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3da04-112">Remarks</span></span>  
 <span data-ttu-id="3da04-113">Die `Auto` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="3da04-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="3da04-114">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3da04-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="3da04-115">Hinweise für Entwickler intelligente Geräte</span><span class="sxs-lookup"><span data-stu-id="3da04-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="3da04-116">Dieses Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3da04-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da04-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3da04-117">See also</span></span>

- [<span data-ttu-id="3da04-118">ANSI</span><span class="sxs-lookup"><span data-stu-id="3da04-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="3da04-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="3da04-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="3da04-120">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3da04-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
