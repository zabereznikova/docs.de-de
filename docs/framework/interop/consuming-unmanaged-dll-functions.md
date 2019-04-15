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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2b2d5a935c2608b2315633538fc93dd62595558
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340034"
---
# <a name="consuming-unmanaged-dll-functions"></a><span data-ttu-id="67873-102">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="67873-102">Consuming Unmanaged DLL Functions</span></span>
<span data-ttu-id="67873-103">Der Plattformaufruf ist ein Dienst, der es verwaltetem Code ermöglicht, nicht verwaltete Funktionen aufzurufen, die in DLLs (Dynamic Link Library) implementiert sind, z.B. die in der Windows-API enthaltenen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="67873-103">Platform invoke is a service that enables managed code to call unmanaged functions implemented in dynamic link libraries (DLLs), such as those in the Windows API.</span></span> <span data-ttu-id="67873-104">Es sucht eine exportierte Funktion, ruft diese auf und marshallt ihre Argumente (ganze Zahlen, Zeichenfolgen, Arrays, Strukturen usw.) bei Bedarf über die Grenzen des dialogfähigen Betriebs hinaus.</span><span class="sxs-lookup"><span data-stu-id="67873-104">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="67873-105">In diesem Abschnitt werden Aufgaben beschrieben, die nicht verwalteten DLL-Funktionen zugeordnet sind. Zudem erhalten Sie Informationen zum Thema Plattformaufruf.</span><span class="sxs-lookup"><span data-stu-id="67873-105">This section introduces tasks associated with consuming unmanaged DLL functions and provides more information about platform invoke.</span></span> <span data-ttu-id="67873-106">Zusätzlich zu den folgenden Aufgaben sind allgemeine Überlegungen und ein Link enthalten, die weitere Informationen und Beispiele bieten.</span><span class="sxs-lookup"><span data-stu-id="67873-106">In addition to the following tasks, there are general considerations and a link providing additional information and examples.</span></span>  
  
#### <a name="to-consume-exported-dll-functions"></a><span data-ttu-id="67873-107">So verarbeiten Sie exportierte DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="67873-107">To consume exported DLL functions</span></span>  
  
1. <span data-ttu-id="67873-108">[Identifizieren von Funktionen in DLLs](../../../docs/framework/interop/identifying-functions-in-dlls.md).</span><span class="sxs-lookup"><span data-stu-id="67873-108">[Identify functions in DLLs](../../../docs/framework/interop/identifying-functions-in-dlls.md).</span></span>  
  
     <span data-ttu-id="67873-109">Sie müssen mindestens den Namen der Funktion und den Namen der DLL angeben, in der sie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="67873-109">Minimally, you must specify the name of the function and name of the DLL that contains it.</span></span>  
  
2. <span data-ttu-id="67873-110">[Erstellen einer Klasse zum Halten von DLL-Funktionen](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).</span><span class="sxs-lookup"><span data-stu-id="67873-110">[Create a class to hold DLL functions](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).</span></span>  
  
     <span data-ttu-id="67873-111">Sie können eine bestehende Klasse verwenden, eine einzelne Klasse für jede nicht verwaltete Funktion erstellen oder eine Klasse erstellen, die einen Satz zusammengehöriger, nicht verwalteter Funktionen enthält.</span><span class="sxs-lookup"><span data-stu-id="67873-111">You can use an existing class, create an individual class for each unmanaged function, or create one class that contains a set of related unmanaged functions.</span></span>  
  
3. <span data-ttu-id="67873-112">[Erstellen von Prototypen in verwaltetem Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="67873-112">[Create prototypes in managed code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span></span>  
  
     <span data-ttu-id="67873-113">[Visual Basic] Verwenden Sie die **Declare**-Anweisung mit den Schlüsselwörtern **Function** und **Lib**.</span><span class="sxs-lookup"><span data-stu-id="67873-113">[Visual Basic] Use the **Declare** statement with the **Function** and **Lib** keywords.</span></span> <span data-ttu-id="67873-114">In seltenen Fällen können Sie **DllImportAttribute** mit den Schlüsselwörtern **Shared Function** verwenden.</span><span class="sxs-lookup"><span data-stu-id="67873-114">In some rare cases, you can use the **DllImportAttribute** with the **Shared Function** keywords.</span></span> <span data-ttu-id="67873-115">Diese Fälle werden weiter unten in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="67873-115">These cases are explained later in this section.</span></span>  
  
     <span data-ttu-id="67873-116">[C#] Verwenden Sie **DllImportAttribute**, um die DLL und die Funktion zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="67873-116">[C#] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="67873-117">Kennzeichnen Sie die Methode mit den Modifizierern **static** und **extern**.</span><span class="sxs-lookup"><span data-stu-id="67873-117">Mark the method with the **static** and **extern** modifiers.</span></span>  
  
     <span data-ttu-id="67873-118">[C++] Verwenden Sie **DllImportAttribute**, um die DLL und die Funktion zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="67873-118">[C++] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="67873-119">Kennzeichnen Sie die Wrappermethode oder Funktion mit **extern "C"**.</span><span class="sxs-lookup"><span data-stu-id="67873-119">Mark the wrapper method or function with **extern "C"**.</span></span>  
  
4. <span data-ttu-id="67873-120">[Aufrufen einer DLL-Funktion](../../../docs/framework/interop/calling-a-dll-function.md).</span><span class="sxs-lookup"><span data-stu-id="67873-120">[Call a DLL function](../../../docs/framework/interop/calling-a-dll-function.md).</span></span>  
  
     <span data-ttu-id="67873-121">Rufen Sie die Methode für Ihre verwaltete Klasse wie für jede andere verwaltete Methode auf.</span><span class="sxs-lookup"><span data-stu-id="67873-121">Call the method on your managed class as you would any other managed method.</span></span> <span data-ttu-id="67873-122">[Übergeben von Strukturen](../../../docs/framework/interop/passing-structures.md) und [Implementieren von Rückruffunktionen](../../../docs/framework/interop/callback-functions.md) sind spezielle Fälle.</span><span class="sxs-lookup"><span data-stu-id="67873-122">[Passing structures](../../../docs/framework/interop/passing-structures.md) and [implementing callback functions](../../../docs/framework/interop/callback-functions.md) are special cases.</span></span>  
  
 <span data-ttu-id="67873-123">Beispiele für die Vorgehensweise beim Erstellen von .NET-basierten Deklarationen, die mit dem Plattformaufruf verwendet werden können, finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mit Plattformaufruf)](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="67873-123">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="a-closer-look-at-platform-invoke"></a><span data-ttu-id="67873-124">Genauere Betrachtung von Plattformaufrufen</span><span class="sxs-lookup"><span data-stu-id="67873-124">A closer look at platform invoke</span></span>  
 <span data-ttu-id="67873-125">Plattformaufrufe beruhen auf Metadaten, um exportierte Funktionen zu suchen und ihre Argumente zur Laufzeit zu marshallen.</span><span class="sxs-lookup"><span data-stu-id="67873-125">Platform invoke relies on metadata to locate exported functions and marshal their arguments at run time.</span></span> <span data-ttu-id="67873-126">Die folgende Abbildung veranschaulicht diesen Prozess.</span><span class="sxs-lookup"><span data-stu-id="67873-126">The following illustration shows this process.</span></span>  
  
 ![Diagramm eines Plattformaufrufs](./media/consuming-unmanaged-dll-functions/platform-invoke-call.gif)  
  
 <span data-ttu-id="67873-128">Wenn der Plattformaufruf eine nicht verwaltete Funktion aufruft, werden die folgenden Aktionen nacheinander ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="67873-128">When platform invoke calls an unmanaged function, it performs the following sequence of actions:</span></span>  
  
1. <span data-ttu-id="67873-129">Suchen der DLL, die die Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="67873-129">Locates the DLL containing the function.</span></span>  
  
2. <span data-ttu-id="67873-130">Laden der DLL in den Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="67873-130">Loads the DLL into memory.</span></span>  
  
3. <span data-ttu-id="67873-131">Suchen der Adresse der Funktion im Arbeitsspeicher und Übertragen ihrer Argumente auf den Stapel, wobei die Daten bei Bedarf gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="67873-131">Locates the address of the function in memory and pushes its arguments onto the stack, marshaling data as required.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="67873-132">Das Suchen und Laden der DLL sowie das Suchen der Adresse der Funktion im Arbeitsspeicher erfolgen nur beim ersten Aufruf der Funktion.</span><span class="sxs-lookup"><span data-stu-id="67873-132">Locating and loading the DLL, and locating the address of the function in memory occur only on the first call to the function.</span></span>  
  
4. <span data-ttu-id="67873-133">Übertragen der Kontrolle an die nicht verwaltete Funktion.</span><span class="sxs-lookup"><span data-stu-id="67873-133">Transfers control to the unmanaged function.</span></span>  
  
 <span data-ttu-id="67873-134">Der Plattformaufruf löst Ausnahmen aus, die von der nicht verwalteten Funktion für den verwalteten Aufrufer generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="67873-134">Platform invoke throws exceptions generated by the unmanaged function to the managed caller.</span></span>

## <a name="see-also"></a><span data-ttu-id="67873-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67873-135">See also</span></span>

- [<span data-ttu-id="67873-136">Interoperation mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="67873-136">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)
- [<span data-ttu-id="67873-137">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="67873-137">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="67873-138">Interop-Marshalling</span><span class="sxs-lookup"><span data-stu-id="67873-138">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
