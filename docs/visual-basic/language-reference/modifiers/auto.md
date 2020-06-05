---
title: Automatisch
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: b9bdeed55788252c71b8fb1c995c140cbfdf60eb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373127"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="14662-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14662-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="14662-103">Gibt an, dass Visual Basic Zeichen folgen gemäß .NET Framework Regeln Mars Hallen soll, basierend auf dem externen Namen der zu deklarierten externen Prozedur.</span><span class="sxs-lookup"><span data-stu-id="14662-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="14662-104">Wenn Sie eine Prozedur aufrufen, die außerhalb des Projekts definiert ist, hat der Visual Basic Compiler keinen Zugriff auf die Informationen, die er benötigt, um die Prozedur ordnungsgemäß aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="14662-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="14662-105">Diese Informationen umfassen den Speicherort der Prozedur, deren Identifizierung, die Aufruf Sequenz und den Rückgabetyp sowie den verwendeten Zeichen folgen Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="14662-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="14662-106">Die [Declare-Anweisung](../statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="14662-106">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="14662-107">Der `charsetmodifier` Teil in der- `Declare` Anweisung liefert die Zeichensatz Informationen für das Mars Hallen von Zeichen folgen während eines Aufrufens der externen Prozedur.</span><span class="sxs-lookup"><span data-stu-id="14662-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="14662-108">Es wirkt sich auch darauf aus, wie Visual Basic die externe Datei nach dem Namen der externen Prozedur durchsucht.</span><span class="sxs-lookup"><span data-stu-id="14662-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="14662-109">Der- `Auto` Modifizierer gibt an, dass Visual Basic Zeichen folgen gemäß .NET Framework Regeln Mars Hallen und den Basis Zeichensatz der Laufzeitplattform bestimmen und ggf. den Namen der externen Prozedur ändern soll, wenn bei der ersten Suche ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="14662-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="14662-110">Weitere Informationen finden Sie unter "Zeichensätze" in der [Declare-Anweisung](../statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="14662-110">For more information, see "Character Sets" in [Declare Statement](../statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="14662-111">Wenn kein zeichensetmodifizierer angegeben wird, `Ansi` ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="14662-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14662-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="14662-112">Remarks</span></span>  
 <span data-ttu-id="14662-113">Der- `Auto` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="14662-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="14662-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="14662-114">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="14662-115">Entwickler Hinweise zu intelligenten Geräten</span><span class="sxs-lookup"><span data-stu-id="14662-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="14662-116">Dieses Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="14662-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14662-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14662-117">See also</span></span>

- [<span data-ttu-id="14662-118">Ansi</span><span class="sxs-lookup"><span data-stu-id="14662-118">Ansi</span></span>](ansi.md)
- [<span data-ttu-id="14662-119">Unicode-</span><span class="sxs-lookup"><span data-stu-id="14662-119">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="14662-120">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="14662-120">Keywords</span></span>](../keywords/index.md)
