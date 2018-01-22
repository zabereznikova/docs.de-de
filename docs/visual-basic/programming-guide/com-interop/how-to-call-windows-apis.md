---
title: "Gewusst wie: Aufrufen von Windows-APIs (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 772db789fba4552a4645d2c6a242ba01944652ee
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="6fed6-102">Gewusst wie: Aufrufen von Windows-APIs (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fed6-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="6fed6-103">In diesem Beispiel definiert und ruft die `MessageBox` -Funktion in "User32.dll" und dann eine Zeichenfolge an diese übergibt.</span><span class="sxs-lookup"><span data-stu-id="6fed6-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fed6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fed6-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6fed6-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6fed6-105">Compiling the Code</span></span>  
 <span data-ttu-id="6fed6-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6fed6-106">This example requires:</span></span>  
  
-   <span data-ttu-id="6fed6-107">Einen Verweis auf den <xref:System>-Namespace</span><span class="sxs-lookup"><span data-stu-id="6fed6-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6fed6-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="6fed6-108">Robust Programming</span></span>  
 <span data-ttu-id="6fed6-109">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="6fed6-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="6fed6-110">Die Methode ist nicht statisch, ist abstrakt oder wurde bereits definiert.</span><span class="sxs-lookup"><span data-stu-id="6fed6-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="6fed6-111">Der übergeordnete Typ ist eine Schnittstelle oder die Länge des *Namen* oder *DLL-Namen* 0 (null).</span><span class="sxs-lookup"><span data-stu-id="6fed6-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="6fed6-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="6fed6-112">(<xref:System.ArgumentException>)</span></span>  
  
-   <span data-ttu-id="6fed6-113">Die *Namen* oder *DLL-Namen* ist `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="6fed6-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="6fed6-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="6fed6-114">(<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="6fed6-115">Der enthaltende Typ wurde zuvor mit `CreateType` erstellt.</span><span class="sxs-lookup"><span data-stu-id="6fed6-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="6fed6-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="6fed6-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fed6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fed6-117">See Also</span></span>  
 [<span data-ttu-id="6fed6-118">Eine genauere Betrachtung von Plattformaufrufen</span><span class="sxs-lookup"><span data-stu-id="6fed6-118">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [<span data-ttu-id="6fed6-119">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="6fed6-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="6fed6-120">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="6fed6-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="6fed6-121">Definieren eine Methode mit Reflektionsausgabe</span><span class="sxs-lookup"><span data-stu-id="6fed6-121">Defining a Method with Reflection Emit</span></span>](http://msdn.microsoft.com/library/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [<span data-ttu-id="6fed6-122">Exemplarische Vorgehensweise: Aufrufen von Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="6fed6-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="6fed6-123">COM-Interop</span><span class="sxs-lookup"><span data-stu-id="6fed6-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
