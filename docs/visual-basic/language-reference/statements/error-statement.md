---
title: Error-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 8ac7cee2f9959bc75df165d00d3a0a67e1dd9af0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837532"
---
# <a name="error-statement"></a><span data-ttu-id="eedcb-102">Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="eedcb-102">Error Statement</span></span>
<span data-ttu-id="eedcb-103">Simuliert das Auftreten eines Fehlers.</span><span class="sxs-lookup"><span data-stu-id="eedcb-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eedcb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eedcb-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="eedcb-105">Teile</span><span class="sxs-lookup"><span data-stu-id="eedcb-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="eedcb-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eedcb-106">Required.</span></span> <span data-ttu-id="eedcb-107">Eine beliebige gültige Fehlernummer kann sein.</span><span class="sxs-lookup"><span data-stu-id="eedcb-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eedcb-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eedcb-108">Remarks</span></span>  
 <span data-ttu-id="eedcb-109">Die `Error` -Anweisung wird für die Abwärtskompatibilität unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eedcb-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="eedcb-110">Verwenden Sie in neuem Code, besonders beim Erstellen von Objekten, die `Err` des Objekts `Raise` Methode, um Laufzeitfehler zu generieren.</span><span class="sxs-lookup"><span data-stu-id="eedcb-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="eedcb-111">Wenn `errornumber` definiert ist, die `Error` Anweisung ruft den Fehlerhandler nach dem die Eigenschaften der `Err` Objekt werden die folgenden Standardwerte zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="eedcb-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="eedcb-112">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="eedcb-112">Property</span></span>|<span data-ttu-id="eedcb-113">Wert</span><span class="sxs-lookup"><span data-stu-id="eedcb-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="eedcb-114">Als Argument angegebene Wert `Error` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="eedcb-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="eedcb-115">Eine beliebige gültige Fehlernummer kann sein.</span><span class="sxs-lookup"><span data-stu-id="eedcb-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="eedcb-116">Name der aktuellen Visual Basic-Projekt.</span><span class="sxs-lookup"><span data-stu-id="eedcb-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="eedcb-117">Ausdruck für den Rückgabewert der entsprechenden Zeichenfolge die `Error` Funktion für den angegebenen `Number`, wenn diese Zeichenfolge vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="eedcb-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="eedcb-118">Wenn die Zeichenfolge nicht vorhanden ist, `Description` enthält eine leere Zeichenfolge ("").</span><span class="sxs-lookup"><span data-stu-id="eedcb-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="eedcb-119">Die vollqualifizierten Laufwerks-, Pfad und Dateiname der entsprechende Visual Basic-Hilfedatei.</span><span class="sxs-lookup"><span data-stu-id="eedcb-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="eedcb-120">Die entsprechende Visual Basic-Hilfedatei Kontext-ID für den Fehler, entspricht die `Number` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="eedcb-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="eedcb-121">0 (null).</span><span class="sxs-lookup"><span data-stu-id="eedcb-121">Zero.</span></span>|  
  
 <span data-ttu-id="eedcb-122">Wenn kein Fehlerhandler vorhanden und aktiviert ist, wird eine Fehlermeldung erstellt und angezeigt werden, aus der `Err` Objekteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="eedcb-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eedcb-123">Einige Visual Basic-hostanwendungen können keine Objekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="eedcb-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="eedcb-124">Finden Sie in der hostanwendung Dokumentation zu bestimmen, ob sie Klassen und Objekten erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="eedcb-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eedcb-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eedcb-125">Example</span></span>  
 <span data-ttu-id="eedcb-126">Dieses Beispiel verwendet die `Error` Anweisung, um den Fehlernummer 11 generiert.</span><span class="sxs-lookup"><span data-stu-id="eedcb-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="eedcb-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eedcb-127">Requirements</span></span>  
 <span data-ttu-id="eedcb-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="eedcb-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="eedcb-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="eedcb-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eedcb-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eedcb-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="eedcb-131">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="eedcb-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="eedcb-132">Resume-Anweisung</span><span class="sxs-lookup"><span data-stu-id="eedcb-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="eedcb-133">Fehlermeldungen</span><span class="sxs-lookup"><span data-stu-id="eedcb-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
