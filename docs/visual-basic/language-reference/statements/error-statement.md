---
title: Error-Anweisung
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
ms.openlocfilehash: 35ba1f19654d1d23ac1ec73564bc36b0af4f6777
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404744"
---
# <a name="error-statement"></a><span data-ttu-id="fc516-102">Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fc516-102">Error Statement</span></span>
<span data-ttu-id="fc516-103">Simuliert das Auftreten eines Fehlers.</span><span class="sxs-lookup"><span data-stu-id="fc516-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc516-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc516-104">Syntax</span></span>  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="fc516-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="fc516-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="fc516-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fc516-106">Required.</span></span> <span data-ttu-id="fc516-107">Kann eine beliebige gültige Fehlernummer sein.</span><span class="sxs-lookup"><span data-stu-id="fc516-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc516-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fc516-108">Remarks</span></span>  
 <span data-ttu-id="fc516-109">Die- `Error` Anweisung wird aus Gründen der Abwärtskompatibilität unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fc516-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="fc516-110">Verwenden Sie in neuem Code, insbesondere beim Erstellen von-Objekten, die- `Err` Methode des-Objekts, `Raise` um Laufzeitfehler zu generieren.</span><span class="sxs-lookup"><span data-stu-id="fc516-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="fc516-111">Wenn `errornumber` definiert ist, ruft die- `Error` Anweisung den Fehlerhandler auf, nachdem den Eigenschaften des- `Err` Objekts die folgenden Standardwerte zugewiesen wurden:</span><span class="sxs-lookup"><span data-stu-id="fc516-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="fc516-112">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="fc516-112">Property</span></span>|<span data-ttu-id="fc516-113">Wert</span><span class="sxs-lookup"><span data-stu-id="fc516-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="fc516-114">Der als Argument für die `Error` Anweisung angegebene Wert.</span><span class="sxs-lookup"><span data-stu-id="fc516-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="fc516-115">Kann eine beliebige gültige Fehlernummer sein.</span><span class="sxs-lookup"><span data-stu-id="fc516-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="fc516-116">Der Name des aktuellen Visual Basic Projekts.</span><span class="sxs-lookup"><span data-stu-id="fc516-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="fc516-117">Zeichen folgen Ausdruck, der dem Rückgabewert der `Error` Funktion für das angegebene entspricht `Number` , wenn diese Zeichenfolge vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fc516-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="fc516-118">Wenn die Zeichenfolge nicht vorhanden ist, `Description` enthält eine Zeichenfolge der Länge 0 (null) ("").</span><span class="sxs-lookup"><span data-stu-id="fc516-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="fc516-119">Das voll qualifizierte Laufwerk, der Pfad und der Dateiname der entsprechenden Visual Basic Hilfedatei.</span><span class="sxs-lookup"><span data-stu-id="fc516-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="fc516-120">Die entsprechende Visual Basic Hilfedatei-Kontext-ID für den Fehler, der der- `Number` Eigenschaft entspricht.</span><span class="sxs-lookup"><span data-stu-id="fc516-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="fc516-121">Keinen.</span><span class="sxs-lookup"><span data-stu-id="fc516-121">Zero.</span></span>|  
  
 <span data-ttu-id="fc516-122">Wenn kein Fehlerhandler vorhanden ist oder keine aktiviert ist, wird eine Fehlermeldung erstellt und in den `Err` Objekteigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc516-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc516-123">Einige Visual Basic Host Anwendungen können keine Objekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc516-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="fc516-124">Informationen zum Erstellen von Klassen und Objekten finden Sie in der Dokumentation der Host Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fc516-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc516-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc516-125">Example</span></span>  
 <span data-ttu-id="fc516-126">In diesem Beispiel wird die- `Error` Anweisung verwendet, um Fehlernummer 11 zu generieren.</span><span class="sxs-lookup"><span data-stu-id="fc516-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="fc516-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fc516-127">Requirements</span></span>  
 <span data-ttu-id="fc516-128">**Namespace:** [Microsoft. VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="fc516-128">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="fc516-129">**Assembly:** Visual Basic-Lauf Zeit Bibliothek (in "Microsoft. VisualBasic. dll")</span><span class="sxs-lookup"><span data-stu-id="fc516-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc516-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc516-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="fc516-131">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fc516-131">On Error Statement</span></span>](on-error-statement.md)
- [<span data-ttu-id="fc516-132">Resume-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fc516-132">Resume Statement</span></span>](resume-statement.md)
- [<span data-ttu-id="fc516-133">Fehlermeldungen</span><span class="sxs-lookup"><span data-stu-id="fc516-133">Error Messages</span></span>](../error-messages/index.md)
