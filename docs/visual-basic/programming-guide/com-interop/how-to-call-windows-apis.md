---
title: 'Vorgehensweise: Call Windows APIs (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 3769da28e1c9a27c8363b0d6ec639cedaf0f03be
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624852"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="97309-102">Vorgehensweise: Call Windows APIs (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97309-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="97309-103">In diesem Beispiel definiert und ruft die `MessageBox` -Funktion in "User32.dll" und klicken Sie dann eine Zeichenfolge an diese übergibt.</span><span class="sxs-lookup"><span data-stu-id="97309-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97309-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97309-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="97309-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="97309-105">Compiling the Code</span></span>  
 <span data-ttu-id="97309-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="97309-106">This example requires:</span></span>  
  
- <span data-ttu-id="97309-107">Einen Verweis auf den <xref:System>-Namespace</span><span class="sxs-lookup"><span data-stu-id="97309-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="97309-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="97309-108">Robust Programming</span></span>  
 <span data-ttu-id="97309-109">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="97309-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="97309-110">Die Methode ist nicht statisch, abstrakt oder wurde bereits definiert.</span><span class="sxs-lookup"><span data-stu-id="97309-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="97309-111">Der übergeordnete Typ ist eine Schnittstelle oder die Länge des *Namen* oder *DllName* ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="97309-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="97309-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="97309-112">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="97309-113">Die *Namen* oder *DllName* ist `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="97309-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="97309-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="97309-114">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="97309-115">Der enthaltende Typ wurde zuvor mit `CreateType` erstellt.</span><span class="sxs-lookup"><span data-stu-id="97309-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="97309-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="97309-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97309-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97309-117">See also</span></span>

- [<span data-ttu-id="97309-118">Genauere Betrachtung von Plattformaufrufen</span><span class="sxs-lookup"><span data-stu-id="97309-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="97309-119">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="97309-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="97309-120">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="97309-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="97309-121">[Definieren einer Methode mit Reflektionsausgabe](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="97309-121">[Defining a Method with Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="97309-122">Exemplarische Vorgehensweise: Aufrufen von Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="97309-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="97309-123">COM-Interop</span><span class="sxs-lookup"><span data-stu-id="97309-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
