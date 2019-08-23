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
ms.openlocfilehash: 7b926214d3be7f5f57783a8599acf1bb1042f956
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944453"
---
# <a name="error-statement"></a><span data-ttu-id="cb34d-102">Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cb34d-102">Error Statement</span></span>
<span data-ttu-id="cb34d-103">Simuliert das Auftreten eines Fehlers.</span><span class="sxs-lookup"><span data-stu-id="cb34d-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb34d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb34d-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="cb34d-105">Teile</span><span class="sxs-lookup"><span data-stu-id="cb34d-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="cb34d-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cb34d-106">Required.</span></span> <span data-ttu-id="cb34d-107">Kann eine beliebige gültige Fehlernummer sein.</span><span class="sxs-lookup"><span data-stu-id="cb34d-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb34d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cb34d-108">Remarks</span></span>  
 <span data-ttu-id="cb34d-109">Die `Error` -Anweisung wird aus Gründen der Abwärtskompatibilität unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb34d-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="cb34d-110">Verwenden Sie in neuem Code, insbesondere beim Erstellen von- `Err` Objekten, `Raise` die-Methode des-Objekts, um Laufzeitfehler zu generieren.</span><span class="sxs-lookup"><span data-stu-id="cb34d-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="cb34d-111">Wenn `errornumber` definiert ist, ruft `Error` die-Anweisung den Fehlerhandler auf, `Err` nachdem den Eigenschaften des-Objekts die folgenden Standardwerte zugewiesen wurden:</span><span class="sxs-lookup"><span data-stu-id="cb34d-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="cb34d-112">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="cb34d-112">Property</span></span>|<span data-ttu-id="cb34d-113">Wert</span><span class="sxs-lookup"><span data-stu-id="cb34d-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="cb34d-114">Der als Argument für die `Error` Anweisung angegebene Wert.</span><span class="sxs-lookup"><span data-stu-id="cb34d-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="cb34d-115">Kann eine beliebige gültige Fehlernummer sein.</span><span class="sxs-lookup"><span data-stu-id="cb34d-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="cb34d-116">Der Name des aktuellen Visual Basic Projekts.</span><span class="sxs-lookup"><span data-stu-id="cb34d-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="cb34d-117">Zeichen folgen Ausdruck, der dem Rückgabewert der `Error` Funktion für das angegebene `Number`entspricht, wenn diese Zeichenfolge vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cb34d-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="cb34d-118">Wenn die Zeichenfolge nicht vorhanden ist `Description` , enthält eine Zeichenfolge der Länge 0 (null) ("").</span><span class="sxs-lookup"><span data-stu-id="cb34d-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="cb34d-119">Das voll qualifizierte Laufwerk, der Pfad und der Dateiname der entsprechenden Visual Basic Hilfedatei.</span><span class="sxs-lookup"><span data-stu-id="cb34d-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="cb34d-120">Die entsprechende Visual Basic Hilfedatei-Kontext-ID für den Fehler, `Number` der der-Eigenschaft entspricht.</span><span class="sxs-lookup"><span data-stu-id="cb34d-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="cb34d-121">Zins.</span><span class="sxs-lookup"><span data-stu-id="cb34d-121">Zero.</span></span>|  
  
 <span data-ttu-id="cb34d-122">Wenn kein Fehlerhandler vorhanden ist oder keine aktiviert ist, wird eine Fehlermeldung erstellt und in den `Err` Objekteigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb34d-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cb34d-123">Einige Visual Basic Host Anwendungen können keine Objekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb34d-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="cb34d-124">Informationen zum Erstellen von Klassen und Objekten finden Sie in der Dokumentation der Host Anwendung.</span><span class="sxs-lookup"><span data-stu-id="cb34d-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb34d-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb34d-125">Example</span></span>  
 <span data-ttu-id="cb34d-126">In diesem Beispiel wird `Error` die-Anweisung verwendet, um Fehlernummer 11 zu generieren.</span><span class="sxs-lookup"><span data-stu-id="cb34d-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="cb34d-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cb34d-127">Requirements</span></span>  
 <span data-ttu-id="cb34d-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="cb34d-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="cb34d-129">**Stadtverordneten** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="cb34d-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb34d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb34d-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="cb34d-131">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cb34d-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="cb34d-132">Resume-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cb34d-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="cb34d-133">Fehlermeldungen</span><span class="sxs-lookup"><span data-stu-id="cb34d-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
