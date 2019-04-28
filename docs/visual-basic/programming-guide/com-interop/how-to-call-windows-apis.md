---
title: 'Vorgehensweise: Call Windows APIs (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: e7b76495b83cb9a1dfe7629a1d82695d2046eac2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61818715"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="58e90-102">Vorgehensweise: Call Windows APIs (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58e90-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="58e90-103">In diesem Beispiel definiert und ruft die `MessageBox` -Funktion in "User32.dll" und klicken Sie dann eine Zeichenfolge an diese übergibt.</span><span class="sxs-lookup"><span data-stu-id="58e90-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58e90-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58e90-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="58e90-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="58e90-105">Compiling the Code</span></span>  
 <span data-ttu-id="58e90-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="58e90-106">This example requires:</span></span>  
  
- <span data-ttu-id="58e90-107">Einen Verweis auf den <xref:System>-Namespace</span><span class="sxs-lookup"><span data-stu-id="58e90-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="58e90-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="58e90-108">Robust Programming</span></span>  
 <span data-ttu-id="58e90-109">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="58e90-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="58e90-110">Die Methode ist nicht statisch, abstrakt oder wurde bereits definiert.</span><span class="sxs-lookup"><span data-stu-id="58e90-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="58e90-111">Der übergeordnete Typ ist eine Schnittstelle oder die Länge des *Namen* oder *DllName* ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="58e90-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="58e90-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="58e90-112">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="58e90-113">Die *Namen* oder *DllName* ist `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="58e90-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="58e90-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="58e90-114">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="58e90-115">Der enthaltende Typ wurde zuvor mit `CreateType` erstellt.</span><span class="sxs-lookup"><span data-stu-id="58e90-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="58e90-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="58e90-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e90-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58e90-117">See also</span></span>

- [<span data-ttu-id="58e90-118">Genauere Betrachtung von Plattformaufrufen</span><span class="sxs-lookup"><span data-stu-id="58e90-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="58e90-119">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="58e90-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="58e90-120">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="58e90-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="58e90-121">[Definieren einer Methode mit Reflektionsausgabe](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="58e90-121">[Defining a Method with Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="58e90-122">Exemplarische Vorgehensweise: Aufrufen von Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="58e90-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="58e90-123">COM-Interop</span><span class="sxs-lookup"><span data-stu-id="58e90-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
