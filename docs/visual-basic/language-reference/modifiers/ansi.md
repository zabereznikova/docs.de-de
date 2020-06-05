---
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 67792e52c21555bef46548e9ab0a6ebd32061071
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373199"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="b988f-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b988f-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="b988f-103">Gibt an, dass Visual Basic alle Zeichen folgen in American National Standards Institute (ANSI)-Werte Mars Hallen soll, unabhängig vom Namen der zu deklarier enden externen Prozedur.</span><span class="sxs-lookup"><span data-stu-id="b988f-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="b988f-104">Wenn Sie eine Prozedur aufrufen, die außerhalb des Projekts definiert ist, hat der Visual Basic Compiler keinen Zugriff auf die Informationen, die er benötigt, um die Prozedur ordnungsgemäß aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b988f-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="b988f-105">Diese Informationen umfassen den Speicherort der Prozedur, deren Identifizierung, die Aufruf Sequenz und den Rückgabetyp sowie den verwendeten Zeichen folgen Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="b988f-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="b988f-106">Die [Declare-Anweisung](../statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="b988f-106">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="b988f-107">Der `charsetmodifier` Teil in der- `Declare` Anweisung liefert die Zeichensatz Informationen für das Mars Hallen von Zeichen folgen während eines Aufrufens der externen Prozedur.</span><span class="sxs-lookup"><span data-stu-id="b988f-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="b988f-108">Es wirkt sich auch darauf aus, wie Visual Basic die externe Datei nach dem Namen der externen Prozedur durchsucht.</span><span class="sxs-lookup"><span data-stu-id="b988f-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="b988f-109">Der `Ansi` -Modifizierer gibt an, dass Visual Basic alle Zeichen folgen in ANSI-Werte Mars Hallen und die Prozedur suchen soll, ohne den Namen während der Suche zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b988f-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="b988f-110">Wenn kein zeichensetmodifizierer angegeben wird, `Ansi` ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="b988f-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b988f-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b988f-111">Remarks</span></span>  
 <span data-ttu-id="b988f-112">Der- `Ansi` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="b988f-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="b988f-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="b988f-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="b988f-114">Entwickler Hinweise zu intelligenten Geräten</span><span class="sxs-lookup"><span data-stu-id="b988f-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="b988f-115">Dieses Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b988f-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b988f-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b988f-116">See also</span></span>

- [<span data-ttu-id="b988f-117">Auto</span><span class="sxs-lookup"><span data-stu-id="b988f-117">Auto</span></span>](auto.md)
- [<span data-ttu-id="b988f-118">Unicode-</span><span class="sxs-lookup"><span data-stu-id="b988f-118">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="b988f-119">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b988f-119">Keywords</span></span>](../keywords/index.md)
