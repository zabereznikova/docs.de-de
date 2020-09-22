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
ms.openlocfilehash: f3f9f5ecb96686fe525e98cf64672d81a3145796
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873277"
---
# <a name="error-statement"></a><span data-ttu-id="9434b-102">Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9434b-102">Error Statement</span></span>

<span data-ttu-id="9434b-103">Simuliert das Auftreten eines Fehlers.</span><span class="sxs-lookup"><span data-stu-id="9434b-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9434b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9434b-104">Syntax</span></span>  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="9434b-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="9434b-105">Parts</span></span>  

 `errornumber`  
 <span data-ttu-id="9434b-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9434b-106">Required.</span></span> <span data-ttu-id="9434b-107">Kann eine beliebige gültige Fehlernummer sein.</span><span class="sxs-lookup"><span data-stu-id="9434b-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9434b-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9434b-108">Remarks</span></span>  

 <span data-ttu-id="9434b-109">Die- `Error` Anweisung wird aus Gründen der Abwärtskompatibilität unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9434b-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="9434b-110">Verwenden Sie in neuem Code, insbesondere beim Erstellen von-Objekten, die- `Err` Methode des-Objekts, `Raise` um Laufzeitfehler zu generieren.</span><span class="sxs-lookup"><span data-stu-id="9434b-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="9434b-111">Wenn `errornumber` definiert ist, ruft die- `Error` Anweisung den Fehlerhandler auf, nachdem den Eigenschaften des- `Err` Objekts die folgenden Standardwerte zugewiesen wurden:</span><span class="sxs-lookup"><span data-stu-id="9434b-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="9434b-112">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9434b-112">Property</span></span>|<span data-ttu-id="9434b-113">Wert</span><span class="sxs-lookup"><span data-stu-id="9434b-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="9434b-114">Der als Argument für die `Error` Anweisung angegebene Wert.</span><span class="sxs-lookup"><span data-stu-id="9434b-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="9434b-115">Kann eine beliebige gültige Fehlernummer sein.</span><span class="sxs-lookup"><span data-stu-id="9434b-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="9434b-116">Der Name des aktuellen Visual Basic Projekts.</span><span class="sxs-lookup"><span data-stu-id="9434b-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="9434b-117">Zeichen folgen Ausdruck, der dem Rückgabewert der `Error` Funktion für das angegebene entspricht `Number` , wenn diese Zeichenfolge vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9434b-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="9434b-118">Wenn die Zeichenfolge nicht vorhanden ist, `Description` enthält eine Zeichenfolge der Länge 0 (null) ("").</span><span class="sxs-lookup"><span data-stu-id="9434b-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="9434b-119">Das voll qualifizierte Laufwerk, der Pfad und der Dateiname der entsprechenden Visual Basic Hilfedatei.</span><span class="sxs-lookup"><span data-stu-id="9434b-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="9434b-120">Die entsprechende Visual Basic Hilfedatei-Kontext-ID für den Fehler, der der- `Number` Eigenschaft entspricht.</span><span class="sxs-lookup"><span data-stu-id="9434b-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="9434b-121">Keinen.</span><span class="sxs-lookup"><span data-stu-id="9434b-121">Zero.</span></span>|  
  
 <span data-ttu-id="9434b-122">Wenn kein Fehlerhandler vorhanden ist oder keine aktiviert ist, wird eine Fehlermeldung erstellt und in den `Err` Objekteigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9434b-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9434b-123">Einige Visual Basic Host Anwendungen können keine Objekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="9434b-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="9434b-124">Informationen zum Erstellen von Klassen und Objekten finden Sie in der Dokumentation der Host Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9434b-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9434b-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9434b-125">Example</span></span>  

 <span data-ttu-id="9434b-126">In diesem Beispiel wird die- `Error` Anweisung verwendet, um Fehlernummer 11 zu generieren.</span><span class="sxs-lookup"><span data-stu-id="9434b-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="9434b-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9434b-127">Requirements</span></span>  

 <span data-ttu-id="9434b-128">**Namespace:** [Microsoft. VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="9434b-128">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="9434b-129">**Assembly:** Visual Basic Lauf Zeit Bibliothek (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="9434b-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9434b-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9434b-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="9434b-131">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9434b-131">On Error Statement</span></span>](on-error-statement.md)
- [<span data-ttu-id="9434b-132">Resume-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9434b-132">Resume Statement</span></span>](resume-statement.md)
- [<span data-ttu-id="9434b-133">Fehlermeldungen</span><span class="sxs-lookup"><span data-stu-id="9434b-133">Error Messages</span></span>](../error-messages/index.md)
