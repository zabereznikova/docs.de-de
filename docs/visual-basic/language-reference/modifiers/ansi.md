---
title: Ansi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: e474bd686cc753a0265df1fc2914a73d1b62f1b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737321"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="50527-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50527-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="50527-103">Gibt an, dass es sich bei Visual Basic alle Zeichenfolgen in Werte American National Standards Institute (ANSI), unabhängig vom Namen des die deklarierte externe Prozedur marshallen soll.</span><span class="sxs-lookup"><span data-stu-id="50527-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="50527-104">Wenn Sie eine Prozedur, die außerhalb des Projekts definiert aufrufen, Visual Basic-Compiler keinen Zugriff auf die Informationen, die die Prozedur richtig aufrufen muss.</span><span class="sxs-lookup"><span data-stu-id="50527-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="50527-105">Diese Informationen umfassen, in dem die Prozedur befindet, wie dieses ermittelt wird, die Aufrufsequenz und Rückgabetyp und die Zeichenfolge festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="50527-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="50527-106">Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="50527-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="50527-107">Die `charsetmodifier` -Teil in die `Declare` -Anweisung gibt die Informationen für das Marshalling von Zeichenfolgen bei einem Aufruf der externen Prozedur Zeichen.</span><span class="sxs-lookup"><span data-stu-id="50527-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="50527-108">Es wirkt sich auch, wie Visual Basic die externe Datei für den externen Prozedurnamen durchsucht.</span><span class="sxs-lookup"><span data-stu-id="50527-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="50527-109">Die `Ansi` %(Dateiname) gibt an, dass Visual Basic alle Zeichenfolgen in ANSI-Werte marshallen und die Prozedur suchen soll, ohne seinen Namen bei der Suche zu ändern.</span><span class="sxs-lookup"><span data-stu-id="50527-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="50527-110">Wenn kein Modifizierer angegeben ist, `Ansi` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="50527-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50527-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50527-111">Remarks</span></span>  
 <span data-ttu-id="50527-112">Die `Ansi` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="50527-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="50527-113">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="50527-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="50527-114">Hinweise für Entwickler intelligente Geräte</span><span class="sxs-lookup"><span data-stu-id="50527-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="50527-115">Dieses Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="50527-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50527-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50527-116">See also</span></span>
- [<span data-ttu-id="50527-117">Auto</span><span class="sxs-lookup"><span data-stu-id="50527-117">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="50527-118">Unicode</span><span class="sxs-lookup"><span data-stu-id="50527-118">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="50527-119">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="50527-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
