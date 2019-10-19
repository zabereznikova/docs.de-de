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
ms.openlocfilehash: c7b2adfe7f6b6ff5e89598cb318a90c51595ff6f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583378"
---
# <a name="error-statement"></a><span data-ttu-id="e9211-102">Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e9211-102">Error Statement</span></span>
<span data-ttu-id="e9211-103">Simuliert das Auftreten eines Fehlers.</span><span class="sxs-lookup"><span data-stu-id="e9211-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9211-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9211-104">Syntax</span></span>  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="e9211-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e9211-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="e9211-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e9211-106">Required.</span></span> <span data-ttu-id="e9211-107">Kann eine beliebige gültige Fehlernummer sein.</span><span class="sxs-lookup"><span data-stu-id="e9211-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9211-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9211-108">Remarks</span></span>  
 <span data-ttu-id="e9211-109">Die `Error`-Anweisung wird aus Gründen der Abwärtskompatibilität unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e9211-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="e9211-110">Verwenden Sie in neuem Code, insbesondere beim Erstellen von-Objekten, die `Raise`-Methode des `Err` Objekts, um Laufzeitfehler zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e9211-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="e9211-111">Wenn `errornumber` definiert ist, ruft die `Error` Anweisung den Fehlerhandler auf, nachdem den Eigenschaften des `Err`-Objekts die folgenden Standardwerte zugewiesen wurden:</span><span class="sxs-lookup"><span data-stu-id="e9211-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="e9211-112">property</span><span class="sxs-lookup"><span data-stu-id="e9211-112">Property</span></span>|<span data-ttu-id="e9211-113">Wert</span><span class="sxs-lookup"><span data-stu-id="e9211-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="e9211-114">Der als Argument für `Error` Anweisung angegebene Wert.</span><span class="sxs-lookup"><span data-stu-id="e9211-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="e9211-115">Kann eine beliebige gültige Fehlernummer sein.</span><span class="sxs-lookup"><span data-stu-id="e9211-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="e9211-116">Der Name des aktuellen Visual Basic Projekts.</span><span class="sxs-lookup"><span data-stu-id="e9211-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="e9211-117">Zeichen folgen Ausdruck, der dem Rückgabewert der `Error`-Funktion für die angegebene `Number` entspricht, wenn diese Zeichenfolge vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e9211-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="e9211-118">Wenn die Zeichenfolge nicht vorhanden ist, enthält `Description` eine Zeichenfolge der Länge 0 ("").</span><span class="sxs-lookup"><span data-stu-id="e9211-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="e9211-119">Das voll qualifizierte Laufwerk, der Pfad und der Dateiname der entsprechenden Visual Basic Hilfedatei.</span><span class="sxs-lookup"><span data-stu-id="e9211-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="e9211-120">Die entsprechende Visual Basic Hilfedatei-Kontext-ID für den Fehler, der der `Number`-Eigenschaft entspricht.</span><span class="sxs-lookup"><span data-stu-id="e9211-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="e9211-121">Zins.</span><span class="sxs-lookup"><span data-stu-id="e9211-121">Zero.</span></span>|  
  
 <span data-ttu-id="e9211-122">Wenn kein Fehlerhandler vorhanden ist oder keine aktiviert ist, wird eine Fehlermeldung erstellt und in den Eigenschaften des `Err` Objekts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9211-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9211-123">Einige Visual Basic Host Anwendungen können keine Objekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="e9211-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="e9211-124">Informationen zum Erstellen von Klassen und Objekten finden Sie in der Dokumentation der Host Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e9211-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9211-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9211-125">Example</span></span>  
 <span data-ttu-id="e9211-126">In diesem Beispiel wird die `Error`-Anweisung verwendet, um die Fehlernummer 11 zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e9211-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="e9211-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9211-127">Requirements</span></span>  
 <span data-ttu-id="e9211-128">**Namespace:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="e9211-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="e9211-129">**Assembly:** Visual Basic-Lauf Zeit Bibliothek (in "Microsoft. VisualBasic. dll")</span><span class="sxs-lookup"><span data-stu-id="e9211-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9211-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9211-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="e9211-131">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e9211-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="e9211-132">Resume-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e9211-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="e9211-133">Fehlermeldungen</span><span class="sxs-lookup"><span data-stu-id="e9211-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
