---
title: Error-Anweisung
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cd3245fd3e9e62b1b6443e9787c97808a0d179d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="error-statement"></a><span data-ttu-id="6b1ee-102">Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6b1ee-102">Error Statement</span></span>
<span data-ttu-id="6b1ee-103">Simuliert das Auftreten eines Fehlers.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b1ee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b1ee-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="6b1ee-105">Teile</span><span class="sxs-lookup"><span data-stu-id="6b1ee-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="6b1ee-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-106">Required.</span></span> <span data-ttu-id="6b1ee-107">Eine beliebige gültige Fehlernummer kann sein.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b1ee-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b1ee-108">Remarks</span></span>  
 <span data-ttu-id="6b1ee-109">Die `Error` Anweisung wird für die Abwärtskompatibilität unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="6b1ee-110">Verwenden Sie im neuen Code, besonders beim Erstellen von Objekten, die `Err` des Objekts `Raise` Methode, um Laufzeitfehler zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="6b1ee-111">Wenn `errornumber` definiert ist, die `Error` Anweisung ruft den Fehlerhandler nach den Eigenschaften der `Err` Objekt sind die folgenden Standardwerte zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="6b1ee-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="6b1ee-112">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6b1ee-112">Property</span></span>|<span data-ttu-id="6b1ee-113">Wert</span><span class="sxs-lookup"><span data-stu-id="6b1ee-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="6b1ee-114">Als Argument für die angegebene Wert `Error` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="6b1ee-115">Eine beliebige gültige Fehlernummer kann sein.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="6b1ee-116">Name des aktuellen Visual Basic-Projekt.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="6b1ee-117">Zeichenfolgenausdruck, des Rückgabewerts der entspricht der `Error` Funktion für den angegebenen `Number`, wenn diese Zeichenfolge vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="6b1ee-118">Wenn die Zeichenfolge nicht vorhanden ist, `Description` enthält eine leere Zeichenfolge ("").</span><span class="sxs-lookup"><span data-stu-id="6b1ee-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="6b1ee-119">Der vollqualifizierte Laufwerk, Pfad und Dateiname der entsprechenden Visual Basic-Hilfedatei.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="6b1ee-120">Die entsprechenden Visual Basic-Hilfedatei Kontext-ID für den Fehler, entspricht die `Number` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="6b1ee-121">0 (null).</span><span class="sxs-lookup"><span data-stu-id="6b1ee-121">Zero.</span></span>|  
  
 <span data-ttu-id="6b1ee-122">Wenn kein Fehlerhandler vorhanden oder aktiviert ist, wird eine Fehlermeldung erstellt und angezeigt werden, aus der `Err` -Objekteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b1ee-123">Einige Visual Basic-hostanwendungen können keine Objekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="6b1ee-124">Finden Sie in Ihrer hostanwendung-Dokumentation, um festzustellen, ob sie Klassen und Objekten erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b1ee-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b1ee-125">Example</span></span>  
 <span data-ttu-id="6b1ee-126">Dieses Beispiel verwendet die `Error` Anweisung Fehlernummer 11 generiert.</span><span class="sxs-lookup"><span data-stu-id="6b1ee-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="6b1ee-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b1ee-127">Requirements</span></span>  
 <span data-ttu-id="6b1ee-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="6b1ee-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="6b1ee-129">**Assembly:** Visual Basic-Laufzeitbibliothek (in "Microsoft.VisualBasic.dll")</span><span class="sxs-lookup"><span data-stu-id="6b1ee-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b1ee-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b1ee-130">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>  
 [<span data-ttu-id="6b1ee-131">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6b1ee-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [<span data-ttu-id="6b1ee-132">Resume-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6b1ee-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [<span data-ttu-id="6b1ee-133">Fehlermeldungen</span><span class="sxs-lookup"><span data-stu-id="6b1ee-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
