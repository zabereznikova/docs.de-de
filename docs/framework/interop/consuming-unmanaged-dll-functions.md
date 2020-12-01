---
title: Verwenden nicht verwalteter DLL-Funktionen
description: Nutzen Sie nicht verwaltete DLL-Funktionen mithilfe des Diensts zum Aufrufen der Plattform, mit dem verwalteter Code nicht verwaltete Funktionen aufrufen kann, die in DLL-Bibliotheken implementiert sind.
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
ms.openlocfilehash: ea4008db59e580fc9d68135618f292496e96fce9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282937"
---
# <a name="consuming-unmanaged-dll-functions"></a><span data-ttu-id="57ee4-103">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="57ee4-103">Consuming Unmanaged DLL Functions</span></span>

<span data-ttu-id="57ee4-104">Der Plattformaufruf ist ein Dienst, der es verwaltetem Code ermöglicht, nicht verwaltete Funktionen aufzurufen, die in DLLs (Dynamic Link Library) implementiert sind, z.B. die in der Windows-API enthaltenen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="57ee4-104">Platform invoke is a service that enables managed code to call unmanaged functions implemented in dynamic link libraries (DLLs), such as those in the Windows API.</span></span> <span data-ttu-id="57ee4-105">Es sucht eine exportierte Funktion, ruft diese auf und marshallt ihre Argumente (ganze Zahlen, Zeichenfolgen, Arrays, Strukturen usw.) bei Bedarf über die Grenzen des dialogfähigen Betriebs hinaus.</span><span class="sxs-lookup"><span data-stu-id="57ee4-105">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="57ee4-106">In diesem Abschnitt werden Aufgaben beschrieben, die nicht verwalteten DLL-Funktionen zugeordnet sind. Zudem erhalten Sie Informationen zum Thema Plattformaufruf.</span><span class="sxs-lookup"><span data-stu-id="57ee4-106">This section introduces tasks associated with consuming unmanaged DLL functions and provides more information about platform invoke.</span></span> <span data-ttu-id="57ee4-107">Zusätzlich zu den folgenden Aufgaben sind allgemeine Überlegungen und ein Link enthalten, die weitere Informationen und Beispiele bieten.</span><span class="sxs-lookup"><span data-stu-id="57ee4-107">In addition to the following tasks, there are general considerations and a link providing additional information and examples.</span></span>  
  
#### <a name="to-consume-exported-dll-functions"></a><span data-ttu-id="57ee4-108">So verarbeiten Sie exportierte DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="57ee4-108">To consume exported DLL functions</span></span>  
  
1. <span data-ttu-id="57ee4-109">[Identifizieren von Funktionen in DLLs](identifying-functions-in-dlls.md).</span><span class="sxs-lookup"><span data-stu-id="57ee4-109">[Identify functions in DLLs](identifying-functions-in-dlls.md).</span></span>  
  
     <span data-ttu-id="57ee4-110">Sie müssen mindestens den Namen der Funktion und den Namen der DLL angeben, in der sie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="57ee4-110">Minimally, you must specify the name of the function and name of the DLL that contains it.</span></span>  
  
2. <span data-ttu-id="57ee4-111">[Erstellen einer Klasse zum Halten von DLL-Funktionen](creating-a-class-to-hold-dll-functions.md).</span><span class="sxs-lookup"><span data-stu-id="57ee4-111">[Create a class to hold DLL functions](creating-a-class-to-hold-dll-functions.md).</span></span>  
  
     <span data-ttu-id="57ee4-112">Sie können eine bestehende Klasse verwenden, eine einzelne Klasse für jede nicht verwaltete Funktion erstellen oder eine Klasse erstellen, die einen Satz zusammengehöriger, nicht verwalteter Funktionen enthält.</span><span class="sxs-lookup"><span data-stu-id="57ee4-112">You can use an existing class, create an individual class for each unmanaged function, or create one class that contains a set of related unmanaged functions.</span></span>  
  
3. <span data-ttu-id="57ee4-113">[Erstellen von Prototypen in verwaltetem Code](creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="57ee4-113">[Create prototypes in managed code](creating-prototypes-in-managed-code.md).</span></span>  
  
     <span data-ttu-id="57ee4-114">[Visual Basic] Verwenden Sie die **Declare**-Anweisung mit den Schlüsselwörtern **Function** und **Lib**.</span><span class="sxs-lookup"><span data-stu-id="57ee4-114">[Visual Basic] Use the **Declare** statement with the **Function** and **Lib** keywords.</span></span> <span data-ttu-id="57ee4-115">In seltenen Fällen können Sie **DllImportAttribute** mit den Schlüsselwörtern **Shared Function** verwenden.</span><span class="sxs-lookup"><span data-stu-id="57ee4-115">In some rare cases, you can use the **DllImportAttribute** with the **Shared Function** keywords.</span></span> <span data-ttu-id="57ee4-116">Diese Fälle werden weiter unten in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="57ee4-116">These cases are explained later in this section.</span></span>  
  
     <span data-ttu-id="57ee4-117">[C#] Verwenden Sie **DllImportAttribute**, um die DLL und die Funktion zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="57ee4-117">[C#] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="57ee4-118">Kennzeichnen Sie die Methode mit den Modifizierern **static** und **extern**.</span><span class="sxs-lookup"><span data-stu-id="57ee4-118">Mark the method with the **static** and **extern** modifiers.</span></span>  
  
     <span data-ttu-id="57ee4-119">[C++] Verwenden Sie **DllImportAttribute**, um die DLL und die Funktion zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="57ee4-119">[C++] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="57ee4-120">Kennzeichnen Sie die Wrappermethode oder Funktion mit **extern "C"** .</span><span class="sxs-lookup"><span data-stu-id="57ee4-120">Mark the wrapper method or function with **extern "C"**.</span></span>  
  
4. <span data-ttu-id="57ee4-121">[Aufrufen einer DLL-Funktion](calling-a-dll-function.md).</span><span class="sxs-lookup"><span data-stu-id="57ee4-121">[Call a DLL function](calling-a-dll-function.md).</span></span>  
  
     <span data-ttu-id="57ee4-122">Rufen Sie die Methode für Ihre verwaltete Klasse wie für jede andere verwaltete Methode auf.</span><span class="sxs-lookup"><span data-stu-id="57ee4-122">Call the method on your managed class as you would any other managed method.</span></span> <span data-ttu-id="57ee4-123">[Übergeben von Strukturen](passing-structures.md) und [Implementieren von Rückruffunktionen](callback-functions.md) sind spezielle Fälle.</span><span class="sxs-lookup"><span data-stu-id="57ee4-123">[Passing structures](passing-structures.md) and [implementing callback functions](callback-functions.md) are special cases.</span></span>  
  
 <span data-ttu-id="57ee4-124">Beispiele für die Vorgehensweise beim Erstellen von .NET-basierten Deklarationen, die mit dem Plattformaufruf verwendet werden können, finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mit Plattformaufruf)](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="57ee4-124">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="a-closer-look-at-platform-invoke"></a><span data-ttu-id="57ee4-125">Genauere Betrachtung von Plattformaufrufen</span><span class="sxs-lookup"><span data-stu-id="57ee4-125">A closer look at platform invoke</span></span>  

 <span data-ttu-id="57ee4-126">Plattformaufrufe beruhen auf Metadaten, um exportierte Funktionen zu suchen und ihre Argumente zur Laufzeit zu marshallen.</span><span class="sxs-lookup"><span data-stu-id="57ee4-126">Platform invoke relies on metadata to locate exported functions and marshal their arguments at run time.</span></span> <span data-ttu-id="57ee4-127">Die folgende Abbildung veranschaulicht diesen Prozess.</span><span class="sxs-lookup"><span data-stu-id="57ee4-127">The following illustration shows this process.</span></span>  
  
 ![Diagramm eines Plattformaufrufs](./media/consuming-unmanaged-dll-functions/platform-invoke-call.gif)  
  
 <span data-ttu-id="57ee4-129">Wenn der Plattformaufruf eine nicht verwaltete Funktion aufruft, werden die folgenden Aktionen nacheinander ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="57ee4-129">When platform invoke calls an unmanaged function, it performs the following sequence of actions:</span></span>  
  
1. <span data-ttu-id="57ee4-130">Suchen der DLL, die die Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="57ee4-130">Locates the DLL containing the function.</span></span>  
  
2. <span data-ttu-id="57ee4-131">Laden der DLL in den Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="57ee4-131">Loads the DLL into memory.</span></span>  
  
3. <span data-ttu-id="57ee4-132">Suchen der Adresse der Funktion im Arbeitsspeicher und Übertragen ihrer Argumente auf den Stapel, wobei die Daten bei Bedarf gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="57ee4-132">Locates the address of the function in memory and pushes its arguments onto the stack, marshaling data as required.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="57ee4-133">Das Suchen und Laden der DLL sowie das Suchen der Adresse der Funktion im Arbeitsspeicher erfolgen nur beim ersten Aufruf der Funktion.</span><span class="sxs-lookup"><span data-stu-id="57ee4-133">Locating and loading the DLL, and locating the address of the function in memory occur only on the first call to the function.</span></span>  
  
4. <span data-ttu-id="57ee4-134">Übertragen der Kontrolle an die nicht verwaltete Funktion.</span><span class="sxs-lookup"><span data-stu-id="57ee4-134">Transfers control to the unmanaged function.</span></span>  
  
 <span data-ttu-id="57ee4-135">Der Plattformaufruf löst Ausnahmen aus, die von der nicht verwalteten Funktion für den verwalteten Aufrufer generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="57ee4-135">Platform invoke throws exceptions generated by the unmanaged function to the managed caller.</span></span>

## <a name="see-also"></a><span data-ttu-id="57ee4-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57ee4-136">See also</span></span>

- [<span data-ttu-id="57ee4-137">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="57ee4-137">Interoperating with Unmanaged Code</span></span>](index.md)
- [<span data-ttu-id="57ee4-138">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="57ee4-138">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="57ee4-139">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="57ee4-139">Interop Marshaling</span></span>](interop-marshaling.md)
