---
title: 'Gewusst wie: Aufrufen von Windows-APIs'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 9de9f0fbcca291af0b6aadfd8e3fe7033708fbc6
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347536"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="180e2-102">Gewusst wie: Aufrufen von Windows-APIs (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="180e2-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="180e2-103">In diesem Beispiel wird die `MessageBox`-Funktion in User32. dll definiert und aufgerufen und dann eine Zeichenfolge an Sie weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="180e2-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="180e2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="180e2-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="180e2-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="180e2-105">Compile the code</span></span>  
 <span data-ttu-id="180e2-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="180e2-106">This example requires:</span></span>  
  
- <span data-ttu-id="180e2-107">Einen Verweis auf den <xref:System>-Namespace</span><span class="sxs-lookup"><span data-stu-id="180e2-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="180e2-108">Robuste Programmierung</span><span class="sxs-lookup"><span data-stu-id="180e2-108">Robust Programming</span></span>  
 <span data-ttu-id="180e2-109">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="180e2-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="180e2-110">Die Methode ist nicht statisch, ist abstrakt oder wurde zuvor definiert.</span><span class="sxs-lookup"><span data-stu-id="180e2-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="180e2-111">Der übergeordnete Typ ist eine Schnittstelle, oder die Länge von *Name* oder *dllName* ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="180e2-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="180e2-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="180e2-112">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="180e2-113">Der *Name* oder der *dllName* ist `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="180e2-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="180e2-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="180e2-114">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="180e2-115">Der enthaltende Typ wurde zuvor mit `CreateType` erstellt.</span><span class="sxs-lookup"><span data-stu-id="180e2-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="180e2-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="180e2-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="180e2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="180e2-117">See also</span></span>

- [<span data-ttu-id="180e2-118">Genauere Betrachtung von Plattformaufrufen</span><span class="sxs-lookup"><span data-stu-id="180e2-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="180e2-119">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="180e2-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="180e2-120">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="180e2-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="180e2-121">[Definieren einer Methode mit Reflektionsausgabe](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="180e2-121">[Defining a Method with Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="180e2-122">Exemplarische Vorgehensweise: Aufrufen von Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="180e2-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="180e2-123">COM-Interop</span><span class="sxs-lookup"><span data-stu-id="180e2-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
