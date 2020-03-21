---
title: Verwenden nicht verwalteter DLL-Funktionen
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- platform invoke, about platform invoke
- DLL functions, consuming unmanaged
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke
- DLL functions
ms.assetid: eca7606e-ebfb-4f47-b8d9-289903fdc045
ms.openlocfilehash: 7ec1f129dcc19300dd5a4e7c5e627d9e0edf29a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400950"
---
# <a name="consuming-unmanaged-dll-functions"></a><span data-ttu-id="d3887-102">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="d3887-102">Consuming Unmanaged DLL Functions</span></span>
<span data-ttu-id="d3887-103">Der Plattformaufruf ist ein Dienst, der es verwaltetem Code ermöglicht, nicht verwaltete Funktionen aufzurufen, die in DLLs (Dynamic Link Library) implementiert sind, z.B. die in der Windows-API enthaltenen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="d3887-103">Platform invoke is a service that enables managed code to call unmanaged functions implemented in dynamic link libraries (DLLs), such as those in the Windows API.</span></span> <span data-ttu-id="d3887-104">Es sucht eine exportierte Funktion, ruft diese auf und marshallt ihre Argumente (ganze Zahlen, Zeichenfolgen, Arrays, Strukturen usw.) bei Bedarf über die Grenzen des dialogfähigen Betriebs hinaus.</span><span class="sxs-lookup"><span data-stu-id="d3887-104">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="d3887-105">In diesem Abschnitt werden Aufgaben beschrieben, die nicht verwalteten DLL-Funktionen zugeordnet sind. Zudem erhalten Sie Informationen zum Thema Plattformaufruf.</span><span class="sxs-lookup"><span data-stu-id="d3887-105">This section introduces tasks associated with consuming unmanaged DLL functions and provides more information about platform invoke.</span></span> <span data-ttu-id="d3887-106">Zusätzlich zu den folgenden Aufgaben sind allgemeine Überlegungen und ein Link enthalten, die weitere Informationen und Beispiele bieten.</span><span class="sxs-lookup"><span data-stu-id="d3887-106">In addition to the following tasks, there are general considerations and a link providing additional information and examples.</span></span>  
  
#### <a name="to-consume-exported-dll-functions"></a><span data-ttu-id="d3887-107">So verarbeiten Sie exportierte DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="d3887-107">To consume exported DLL functions</span></span>  
  
1. <span data-ttu-id="d3887-108">[Identifizieren von Funktionen in DLLs](identifying-functions-in-dlls.md).</span><span class="sxs-lookup"><span data-stu-id="d3887-108">[Identify functions in DLLs](identifying-functions-in-dlls.md).</span></span>  
  
     <span data-ttu-id="d3887-109">Sie müssen mindestens den Namen der Funktion und den Namen der DLL angeben, in der sie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d3887-109">Minimally, you must specify the name of the function and name of the DLL that contains it.</span></span>  
  
2. <span data-ttu-id="d3887-110">[Erstellen einer Klasse zum Halten von DLL-Funktionen](creating-a-class-to-hold-dll-functions.md).</span><span class="sxs-lookup"><span data-stu-id="d3887-110">[Create a class to hold DLL functions](creating-a-class-to-hold-dll-functions.md).</span></span>  
  
     <span data-ttu-id="d3887-111">Sie können eine bestehende Klasse verwenden, eine einzelne Klasse für jede nicht verwaltete Funktion erstellen oder eine Klasse erstellen, die einen Satz zusammengehöriger, nicht verwalteter Funktionen enthält.</span><span class="sxs-lookup"><span data-stu-id="d3887-111">You can use an existing class, create an individual class for each unmanaged function, or create one class that contains a set of related unmanaged functions.</span></span>  
  
3. <span data-ttu-id="d3887-112">[Erstellen von Prototypen in verwaltetem Code](creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="d3887-112">[Create prototypes in managed code](creating-prototypes-in-managed-code.md).</span></span>  
  
     <span data-ttu-id="d3887-113">[Visual Basic] Verwenden Sie die **Declare**-Anweisung mit den Schlüsselwörtern **Function** und **Lib**.</span><span class="sxs-lookup"><span data-stu-id="d3887-113">[Visual Basic] Use the **Declare** statement with the **Function** and **Lib** keywords.</span></span> <span data-ttu-id="d3887-114">In seltenen Fällen können Sie **DllImportAttribute** mit den Schlüsselwörtern **Shared Function** verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3887-114">In some rare cases, you can use the **DllImportAttribute** with the **Shared Function** keywords.</span></span> <span data-ttu-id="d3887-115">Diese Fälle werden weiter unten in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="d3887-115">These cases are explained later in this section.</span></span>  
  
     <span data-ttu-id="d3887-116">[C'] Verwenden Sie **DllImportAttribute,** um die DLL und Funktion zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d3887-116">[C#] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="d3887-117">Kennzeichnen Sie die Methode mit den Modifizierern **static** und **extern**.</span><span class="sxs-lookup"><span data-stu-id="d3887-117">Mark the method with the **static** and **extern** modifiers.</span></span>  
  
     <span data-ttu-id="d3887-118">[C++] Verwenden Sie **DllImportAttribute**, um die DLL und die Funktion zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d3887-118">[C++] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="d3887-119">Kennzeichnen Sie die Wrappermethode oder Funktion mit **extern "C"**.</span><span class="sxs-lookup"><span data-stu-id="d3887-119">Mark the wrapper method or function with **extern "C"**.</span></span>  
  
4. <span data-ttu-id="d3887-120">[Aufrufen einer DLL-Funktion](calling-a-dll-function.md).</span><span class="sxs-lookup"><span data-stu-id="d3887-120">[Call a DLL function](calling-a-dll-function.md).</span></span>  
  
     <span data-ttu-id="d3887-121">Rufen Sie die Methode für Ihre verwaltete Klasse wie für jede andere verwaltete Methode auf.</span><span class="sxs-lookup"><span data-stu-id="d3887-121">Call the method on your managed class as you would any other managed method.</span></span> <span data-ttu-id="d3887-122">[Übergeben von Strukturen](passing-structures.md) und [Implementieren von Rückruffunktionen](callback-functions.md) sind spezielle Fälle.</span><span class="sxs-lookup"><span data-stu-id="d3887-122">[Passing structures](passing-structures.md) and [implementing callback functions](callback-functions.md) are special cases.</span></span>  
  
 <span data-ttu-id="d3887-123">Beispiele für die Vorgehensweise beim Erstellen von .NET-basierten Deklarationen, die mit dem Plattformaufruf verwendet werden, finden Sie unter [Marshallen von Daten mit Plattformaufruf](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="d3887-123">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="a-closer-look-at-platform-invoke"></a><span data-ttu-id="d3887-124">Genauere Betrachtung von Plattformaufrufen</span><span class="sxs-lookup"><span data-stu-id="d3887-124">A closer look at platform invoke</span></span>  
 <span data-ttu-id="d3887-125">Plattformaufrufe beruhen auf Metadaten, um exportierte Funktionen zu suchen und ihre Argumente zur Laufzeit zu marshallen.</span><span class="sxs-lookup"><span data-stu-id="d3887-125">Platform invoke relies on metadata to locate exported functions and marshal their arguments at run time.</span></span> <span data-ttu-id="d3887-126">Die folgende Abbildung veranschaulicht diesen Prozess:</span><span class="sxs-lookup"><span data-stu-id="d3887-126">The following illustration shows this process.</span></span>  
  
 ![Diagramm eines Plattformaufrufs](./media/consuming-unmanaged-dll-functions/platform-invoke-call.gif)  
  
 <span data-ttu-id="d3887-128">Wenn der Plattformaufruf eine nicht verwaltete Funktion aufruft, werden die folgenden Aktionen nacheinander ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="d3887-128">When platform invoke calls an unmanaged function, it performs the following sequence of actions:</span></span>  
  
1. <span data-ttu-id="d3887-129">Suchen der DLL, die die Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="d3887-129">Locates the DLL containing the function.</span></span>  
  
2. <span data-ttu-id="d3887-130">Laden der DLL in den Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="d3887-130">Loads the DLL into memory.</span></span>  
  
3. <span data-ttu-id="d3887-131">Suchen der Adresse der Funktion im Arbeitsspeicher und Übertragen ihrer Argumente auf den Stapel, wobei die Daten bei Bedarf gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="d3887-131">Locates the address of the function in memory and pushes its arguments onto the stack, marshaling data as required.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d3887-132">Das Suchen und Laden der DLL sowie das Suchen der Adresse der Funktion im Arbeitsspeicher erfolgen nur beim ersten Aufruf der Funktion.</span><span class="sxs-lookup"><span data-stu-id="d3887-132">Locating and loading the DLL, and locating the address of the function in memory occur only on the first call to the function.</span></span>  
  
4. <span data-ttu-id="d3887-133">Übertragen der Kontrolle an die nicht verwaltete Funktion.</span><span class="sxs-lookup"><span data-stu-id="d3887-133">Transfers control to the unmanaged function.</span></span>  
  
 <span data-ttu-id="d3887-134">Der Plattformaufruf löst Ausnahmen aus, die von der nicht verwalteten Funktion für den verwalteten Aufrufer generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d3887-134">Platform invoke throws exceptions generated by the unmanaged function to the managed caller.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3887-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3887-135">See also</span></span>

- [<span data-ttu-id="d3887-136">Interoperation mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="d3887-136">Interoperating with Unmanaged Code</span></span>](index.md)
- [<span data-ttu-id="d3887-137">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="d3887-137">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="d3887-138">Interop-Marshalling</span><span class="sxs-lookup"><span data-stu-id="d3887-138">Interop Marshaling</span></span>](interop-marshaling.md)
