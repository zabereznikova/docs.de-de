---
title: Standardmarshallingverhalten
description: Erfahren Sie mehr zum standardmäßigen Marshallingverhalten in .NET. Überprüfen Sie die Speicherverwaltung mit Interop-Marshalling, und erfahren Sie mehr über das standardmäßige Marshalling für Klassen, Delegaten und Werttypen.
ms.date: 06/26/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, default
- interoperation with unmanaged code, marshaling
- marshaling behavior
ms.assetid: c0a9bcdf-3df8-4db3-b1b6-abbdb2af809a
ms.openlocfilehash: f2a508b87d2f4a9ad92bc0f27fc44d74d8e916d3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555275"
---
# <a name="default-marshaling-behavior"></a><span data-ttu-id="e4b88-104">Standardmarshallingverhalten</span><span class="sxs-lookup"><span data-stu-id="e4b88-104">Default Marshaling Behavior</span></span>
<span data-ttu-id="e4b88-105">Das Interop-Marshalling basiert auf Regeln, die vorgeben, wie sich Daten, die Methodenparametern zugeordnet sind, verhalten, wenn sie zwischen verwaltetem und unverwaltetem Speicher übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-105">Interop marshaling operates on rules that dictate how data associated with method parameters behaves as it passes between managed and unmanaged memory.</span></span> <span data-ttu-id="e4b88-106">Mit diesen integrierten Regeln werden Marshalling-Aktivitäten wie Datentyptransformationen gesteuert, es wird gesteuert, ob eine aufrufende Instanz die Daten ändern kann, die an sie übergeben werden, und ob diese Änderungen an den Aufrufer zurückgegeben werden, und unter welchen Umständen der Marshaller Leistungsoptimierungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-106">These built-in rules control such marshaling activities as data type transformations, whether a callee can change data passed to it and return those changes to the caller, and under which circumstances the marshaler provides performance optimizations.</span></span>  
  
 <span data-ttu-id="e4b88-107">Dieser Abschnitt befasst sich mit den standardmäßigen Verhaltensmerkmalen des Interop-Marshalling-Diensts.</span><span class="sxs-lookup"><span data-stu-id="e4b88-107">This section identifies the default behavioral characteristics of the interop marshaling service.</span></span> <span data-ttu-id="e4b88-108">Er enthält detaillierte Informationen zum Marshallen von Arrays, booleschen Typen, Zeichentypen, Delegaten, Klassen, Objekten, Zeichenfolgen und Strukturen.</span><span class="sxs-lookup"><span data-stu-id="e4b88-108">It presents detailed information on marshaling arrays, Boolean types, char types, delegates, classes, objects, strings, and structures.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4b88-109">Das Marshalling von generischen Typen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-109">Marshaling of generic types is not supported.</span></span> <span data-ttu-id="e4b88-110">Weitere Informationen finden Sie unter [Interoperating Using Generic Types (Interoperation mit generischen Typen)](/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e4b88-110">For more information see, [Interoperating Using Generic Types](/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100)).</span></span>  
  
## <a name="memory-management-with-the-interop-marshaler"></a><span data-ttu-id="e4b88-111">Speicherverwaltung mit dem Interop-Marshaller</span><span class="sxs-lookup"><span data-stu-id="e4b88-111">Memory management with the interop marshaler</span></span>  
 <span data-ttu-id="e4b88-112">Der Interop-Marshaller versucht immer, den von nicht verwaltetem Code belegten Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="e4b88-112">The interop marshaler always attempts to free memory allocated by unmanaged code.</span></span> <span data-ttu-id="e4b88-113">Dieses Verhalten entspricht den COM-Speicherverwaltungsregeln, unterscheidet sich jedoch von den Regeln, die für systemeigenes C++ gelten.</span><span class="sxs-lookup"><span data-stu-id="e4b88-113">This behavior complies with COM memory management rules, but differs from the rules that govern native C++.</span></span>  
  
 <span data-ttu-id="e4b88-114">Es kann zu Missverständnissen kommen, wenn Sie das Verhalten von systemeigenem C++ (keine Speicherfreigabe) beim Plattformaufruf erwarten, bei dem automatisch Speicher für Zeiger freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4b88-114">Confusion can arise if you anticipate native C++ behavior (no memory freeing) when using platform invoke, which automatically frees memory for pointers.</span></span> <span data-ttu-id="e4b88-115">Wenn Sie beispielsweise die folgende nicht verwaltete Methode aus einer C++-DLL aufrufen, wird kein Speicher automatisch freigegeben.</span><span class="sxs-lookup"><span data-stu-id="e4b88-115">For example, calling the following unmanaged method from a C++ DLL does not automatically free any memory.</span></span>  
  
### <a name="unmanaged-signature"></a><span data-ttu-id="e4b88-116">Nicht verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="e4b88-116">Unmanaged signature</span></span>  
  
```cpp  
BSTR MethodOne (BSTR b) {  
     return b;  
}  
```  
  
 <span data-ttu-id="e4b88-117">Wenn Sie die Methode jedoch als einen Prototyp zum Plattformaufruf definieren, jeden **BSTR**-Typ durch einen <xref:System.String>-Typ ersetzen und `MethodOne` aufrufen, versucht die Common Language Runtime `b` zweimal freizugeben.</span><span class="sxs-lookup"><span data-stu-id="e4b88-117">However, if you define the method as a platform invoke prototype, replace each **BSTR** type with a <xref:System.String> type, and call `MethodOne`, the common language runtime attempts to free `b` twice.</span></span> <span data-ttu-id="e4b88-118">Sie können das Marshalling-Verhalten ändern, indem Sie <xref:System.IntPtr>-Typen anstelle von **Zeichenfolgen**typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-118">You can change the marshaling behavior by using <xref:System.IntPtr> types rather than **String** types.</span></span>  
  
 <span data-ttu-id="e4b88-119">Zur Laufzeit wird immer die **CoTaskMemFree**-Methode zum Freigeben von Speicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4b88-119">The runtime always uses the **CoTaskMemFree** method to free memory.</span></span> <span data-ttu-id="e4b88-120">Wenn der Speicher, mit dem Sie arbeiten, nicht der **CoTaskMemAlloc**-Methode zugeordnet wurde, müssen Sie **IntPtr** verwenden und den Speicher manuell mit der geeigneten Methode freigeben.</span><span class="sxs-lookup"><span data-stu-id="e4b88-120">If the memory you are working with was not allocated with the **CoTaskMemAlloc** method, you must use an **IntPtr** and free the memory manually using the appropriate method.</span></span> <span data-ttu-id="e4b88-121">Ebenso können Sie in Situationen, in denen der Speicher niemals freigegeben werden soll, wie bei Verwendung der **GetCommandLine**-Funktion von Kernel32.dll, die einen Zeiger auf den Kernelspeicher zurückgibt, verhindern, dass Speicher automatisch freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4b88-121">Similarly, you can avoid automatic memory freeing in situations where memory should never be freed, such as when using the **GetCommandLine** function from Kernel32.dll, which returns a pointer to kernel memory.</span></span> <span data-ttu-id="e4b88-122">Details zum manuellen Freigeben von Speicher finden Sie unter [Beispiel für Puffer](/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e4b88-122">For details on manually freeing memory, see the [Buffers Sample](/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100)).</span></span>  
  
## <a name="default-marshaling-for-classes"></a><span data-ttu-id="e4b88-123">Standardmäßiges Marshalling für Klassen</span><span class="sxs-lookup"><span data-stu-id="e4b88-123">Default marshaling for classes</span></span>  
 <span data-ttu-id="e4b88-124">Klassen können nur durch COM-Interop gemarshallt werden und werden immer als Schnittstellen gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-124">Classes can be marshaled only by COM interop and are always marshaled as interfaces.</span></span> <span data-ttu-id="e4b88-125">In einigen Fällen wird die zum Marshallen der Klasse verwendete Schnittstelle als Klassenschnittstelle bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e4b88-125">In some cases the interface used to marshal the class is known as the class interface.</span></span> <span data-ttu-id="e4b88-126">Informationen zum Überschreiben der Klassenschnittstelle mit einer beliebigen Schnittstelle finden Sie unter [Einführung in die Klassenschnittstelle](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span><span class="sxs-lookup"><span data-stu-id="e4b88-126">For information about overriding the class interface with an interface of your choice, see [Introducing the class interface](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span></span>  
  
### <a name="passing-classes-to-com"></a><span data-ttu-id="e4b88-127">Übergeben von Klassen an COM</span><span class="sxs-lookup"><span data-stu-id="e4b88-127">Passing Classes to COM</span></span>  
 <span data-ttu-id="e4b88-128">Wenn eine verwaltete Klasse an COM übergeben wird, umschließt der Interop-Marshaller die Klasse automatisch mit einem COM-Proxy und übergibt die vom Proxy erstellte Klassenschnittstelle an den COM-Methodenaufruf.</span><span class="sxs-lookup"><span data-stu-id="e4b88-128">When a managed class is passed to COM, the interop marshaler automatically wraps the class with a COM proxy and passes the class interface produced by the proxy to the COM method call.</span></span> <span data-ttu-id="e4b88-129">Der Proxy delegiert dann alle Aufrufe der Klassenschnittstelle zurück an das verwaltete Objekt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-129">The proxy then delegates all calls on the class interface back to the managed object.</span></span> <span data-ttu-id="e4b88-130">Der Proxy macht zudem auch weitere Schnittstellen verfügbar, die von der Klasse nicht explizit implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-130">The proxy also exposes other interfaces that are not explicitly implemented by the class.</span></span> <span data-ttu-id="e4b88-131">Der Proxy implementiert automatisch Schnittstellen wie **IUnknown** und **IDispatch** für die Klasse.</span><span class="sxs-lookup"><span data-stu-id="e4b88-131">The proxy automatically implements interfaces such as **IUnknown** and **IDispatch** on behalf of the class.</span></span>  
  
### <a name="passing-classes-to-net-code"></a><span data-ttu-id="e4b88-132">Übergeben von Klassen an .NET-Code</span><span class="sxs-lookup"><span data-stu-id="e4b88-132">Passing Classes to .NET Code</span></span>  
 <span data-ttu-id="e4b88-133">Co-Klassen werden in der Regel nicht als Methodenargumente in COM verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4b88-133">Coclasses are not typically used as method arguments in COM.</span></span> <span data-ttu-id="e4b88-134">Stattdessen wird normalerweise eine Standardschnittstelle anstelle der Co-Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="e4b88-134">Instead, a default interface is usually passed in place of the coclass.</span></span>  
  
 <span data-ttu-id="e4b88-135">Wenn eine Schnittstelle an verwalteten Code übergeben wird, ist der Interop-Marshaller für das Umschließen der Schnittstelle mit dem geeigneten Wrapper und das Übergeben des Wrappers an die verwaltete Methode zuständig.</span><span class="sxs-lookup"><span data-stu-id="e4b88-135">When an interface is passed into managed code, the interop marshaler is responsible for wrapping the interface with the proper wrapper and passing the wrapper to the managed method.</span></span> <span data-ttu-id="e4b88-136">Herauszufinden, welcher Wrapper verwendet werden sollte, kann schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="e4b88-136">Determining which wrapper to use can be difficult.</span></span> <span data-ttu-id="e4b88-137">Jede Instanz eines COM-Objekts verfügt über einen einzelnen, eindeutigen Wrapper, ganz gleich, wie viele Schnittstellen das Objekt implementiert.</span><span class="sxs-lookup"><span data-stu-id="e4b88-137">Every instance of a COM object has a single, unique wrapper, no matter how many interfaces the object implements.</span></span> <span data-ttu-id="e4b88-138">So hat ein einzelnes COM-Objekt, das fünf unterschiedliche Schnittstellen implementiert, nur einen einzigen Wrapper.</span><span class="sxs-lookup"><span data-stu-id="e4b88-138">For example, a single COM object that implements five distinct interfaces has only one wrapper.</span></span> <span data-ttu-id="e4b88-139">Der gleiche Wrapper macht alle fünf Schnittstellen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e4b88-139">The same wrapper exposes all five interfaces.</span></span> <span data-ttu-id="e4b88-140">Wenn zwei Instanzen des COM-Objekts erstellt werden, werden auch zwei Instanzen des Wrappers erstellt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-140">If two instances of the COM object are created, then two instances of the wrapper are created.</span></span>  
  
 <span data-ttu-id="e4b88-141">Damit der Wrapper über die gesamte Lebensdauer den gleichen Typ beibehält, muss der Interop-Marshaller den korrekten Wrapper beim ersten Mal identifizieren, wenn ein vom Objekt verfügbar gemachte Schnittstelle über den Marshaller übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4b88-141">For the wrapper to maintain the same type throughout its lifetime, the interop marshaler must identify the correct wrapper the first time an interface exposed by the object is passed through the marshaler.</span></span> <span data-ttu-id="e4b88-142">Der Marshaller identifiziert das Objekt anhand einer der Schnittstellen, die von dem Objekt implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-142">The marshaler identifies the object by looking at one of the interfaces the object implements.</span></span>  
  
 <span data-ttu-id="e4b88-143">So bestimmt der Marshaller beispielsweise, dass der Klassenwrapper zum Umschließen der Schnittstelle verwendet werden soll, die an verwalteten Code übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="e4b88-143">For example, the marshaler determines that the class wrapper should be used to wrap the interface that was passed into managed code.</span></span> <span data-ttu-id="e4b88-144">Wenn die Schnittstelle erstmals über den Marshaller übergeben wird, prüft der Marshaller, ob die Schnittstelle von einem bekannten Objekt stammt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-144">When the interface is first passed through the marshaler, the marshaler checks whether the interface is coming from a known object.</span></span> <span data-ttu-id="e4b88-145">Diese Überprüfung erfolgt in zwei Situationen:</span><span class="sxs-lookup"><span data-stu-id="e4b88-145">This check occurs in two situations:</span></span>  
  
- <span data-ttu-id="e4b88-146">Eine Schnittstelle wird von einem anderen verwalteten Objekt implementiert, das an anderer Stelle an COM übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="e4b88-146">An interface is being implemented by another managed object that was passed to COM elsewhere.</span></span> <span data-ttu-id="e4b88-147">Der Marshaller kann die Schnittstellen, die von verwalteten Objekten verfügbar gemacht werden, leicht identifizieren und ist in der Lage, die Schnittstelle mit dem verwalteten Objekt zu vergleichen, das die Implementierung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-147">The marshaler can readily identify interfaces exposed by managed objects and is able to match the interface with the managed object that provides the implementation.</span></span> <span data-ttu-id="e4b88-148">Das verwaltete Objekt wird dann an die Methode übergeben, und es wird kein Wrapper benötigt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-148">The managed object is then passed to the method and no wrapper is needed.</span></span>  
  
- <span data-ttu-id="e4b88-149">Ein bereits umschlossenes Objekt implementiert die Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e4b88-149">An object that has already been wrapped is implementing the interface.</span></span> <span data-ttu-id="e4b88-150">Um festzustellen, ob dies der Fall ist, fragt der Marshaller das Objekt nach seiner **IUnknown-Schnittstelle**, und vergleicht die zurückgegebene Schnittstelle mit den Schnittstellen von anderen Objekten, die bereits umschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="e4b88-150">To determine whether this is the case, the marshaler queries the object for its **IUnknown** interface and compares the returned interface to the interfaces of other objects that are already wrapped.</span></span> <span data-ttu-id="e4b88-151">Wenn die Schnittstelle die gleiche wie die des anderen Wrappers ist, haben die Objekte die gleiche Identität, und der vorhandene Wrapper wird an die Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="e4b88-151">If the interface is the same as that of another wrapper, the objects have the same identity and the existing wrapper is passed to the method.</span></span>  
  
 <span data-ttu-id="e4b88-152">Wenn die Schnittstelle nicht von einem bekannten Objekt stammt, geht der Marshaller folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="e4b88-152">If an interface is not from a known object, the marshaler does the following:</span></span>  
  
1. <span data-ttu-id="e4b88-153">Der Marshaller fragt das Objekt nach seiner **IProvideClassInfo2**-Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="e4b88-153">The marshaler queries the object for the **IProvideClassInfo2** interface.</span></span> <span data-ttu-id="e4b88-154">Wird diese zurückgegeben, verwendet der Marshaller die von **IProvideClassInfo2.GetGUID** zurückgegebene CLSID, um die Co-Klasse zu identifizieren, die die Schnittstelle bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-154">If provided, the marshaler uses the CLSID returned from **IProvideClassInfo2.GetGUID** to identify the coclass providing the interface.</span></span> <span data-ttu-id="e4b88-155">Mit der CLSID kann der Marshaller den Wrapper in der Registrierung finden, wenn die Assembly bereits registriert ist.</span><span class="sxs-lookup"><span data-stu-id="e4b88-155">With the CLSID, the marshaler can locate the wrapper from the registry if the assembly has previously been registered.</span></span>  
  
2. <span data-ttu-id="e4b88-156">Der Marshaller fragt die **IProvideClassInfo**-Schnittstelle der Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="e4b88-156">The marshaler queries the interface for the **IProvideClassInfo** interface.</span></span> <span data-ttu-id="e4b88-157">Wird diese zurückgegeben, verwendet der Marshaller die von **IProvideClassInfo.GetClassinfo** zurückgegebene **ITypeInfo**, um die CLSID der Klasse zu ermitteln, die die Schnittstelle verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="e4b88-157">If provided, the marshaler uses the **ITypeInfo** returned from **IProvideClassInfo.GetClassinfo** to determine the CLSID of the class exposing the interface.</span></span> <span data-ttu-id="e4b88-158">Der Marshaller kann die CLSID verwenden, um die Metadaten für den Wrapper zu finden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-158">The marshaler can use the CLSID to locate the metadata for the wrapper.</span></span>  
  
3. <span data-ttu-id="e4b88-159">Wenn der Marshaller die Klasse immer noch nicht identifizieren kann, umschließt er die Schnittstelle mit einer generischen Wrapperklasse mit Namen **System.__ComObject**.</span><span class="sxs-lookup"><span data-stu-id="e4b88-159">If the marshaler still cannot identify the class, it wraps the interface with a generic wrapper class called **System.__ComObject**.</span></span>  
  
## <a name="default-marshaling-for-delegates"></a><span data-ttu-id="e4b88-160">Standardmäßiges Marshalling für Delegaten</span><span class="sxs-lookup"><span data-stu-id="e4b88-160">Default marshaling for delegates</span></span>  
 <span data-ttu-id="e4b88-161">Ein verwalteter Delegat wird als COM-Schnittstelle oder als Funktionszeiger gemarshallt, und zwar basierend auf dem Aufrufmechanismus:</span><span class="sxs-lookup"><span data-stu-id="e4b88-161">A managed delegate is marshaled as a COM interface or as a function pointer, based on the calling mechanism:</span></span>  
  
- <span data-ttu-id="e4b88-162">Für Plattformaufrufe wird ein Delegat standardmäßig als unverwalteter Funktionszeiger gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-162">For platform invoke, a delegate is marshaled as an unmanaged function pointer by default.</span></span>  
  
- <span data-ttu-id="e4b88-163">Für COM-Interop wird ein Delegat standardmäßig als COM-Schnittstelle vom Typ **_Delegate** gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-163">For COM interop, a delegate is marshaled as a COM interface of type **_Delegate** by default.</span></span> <span data-ttu-id="e4b88-164">Die **_Delegate**-Schnittstelle ist in der Typbibliothek Mscorlib.tlb definiert und enthält die <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType>-Methode, mit der Sie in der Lage sind, die Methode aufzurufen, auf die der Delegat verweist.</span><span class="sxs-lookup"><span data-stu-id="e4b88-164">The **_Delegate** interface is defined in the Mscorlib.tlb type library and contains the <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType> method, which enables you to call the method that the delegate references.</span></span>  
  
 <span data-ttu-id="e4b88-165">Die folgende Tabelle zeigt die Marshalling-Optionen für den Datentyp "Verwalteter Delegat".</span><span class="sxs-lookup"><span data-stu-id="e4b88-165">The following table shows the marshaling options for the managed delegate data type.</span></span> <span data-ttu-id="e4b88-166">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Delegaten bereit.</span><span class="sxs-lookup"><span data-stu-id="e4b88-166">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal delegates.</span></span>  
  
|<span data-ttu-id="e4b88-167">Enumerationstyp</span><span class="sxs-lookup"><span data-stu-id="e4b88-167">Enumeration type</span></span>|<span data-ttu-id="e4b88-168">Beschreibung des nicht verwalteten Formats</span><span class="sxs-lookup"><span data-stu-id="e4b88-168">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="e4b88-169">**UnmanagedType.FunctionPtr**</span><span class="sxs-lookup"><span data-stu-id="e4b88-169">**UnmanagedType.FunctionPtr**</span></span>|<span data-ttu-id="e4b88-170">Ein nicht verwaltete Funktionszeiger.</span><span class="sxs-lookup"><span data-stu-id="e4b88-170">An unmanaged function pointer.</span></span>|  
|<span data-ttu-id="e4b88-171">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="e4b88-171">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="e4b88-172">Eine Schnittstelle von Typ **_Delegate**, wie in Mscorlib.tlb definiert.</span><span class="sxs-lookup"><span data-stu-id="e4b88-172">An interface of type **_Delegate**, as defined in Mscorlib.tlb.</span></span>|  
  
 <span data-ttu-id="e4b88-173">Schauen Sie sich den folgenden Beispielcode an, in dem Methoden von `DelegateTestInterface` in eine COM-Typbibliothek exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-173">Consider the following example code in which the methods of `DelegateTestInterface` are exported to a COM type library.</span></span> <span data-ttu-id="e4b88-174">Beachten Sie, dass nur Delegaten, die mit dem Schlüsselwort **ref** (oder **ByRef**) gekennzeichnet sind, als In/Out-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-174">Notice that only delegates marked with the **ref** (or **ByRef**) keyword are passed as In/Out parameters.</span></span>  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public interface DelegateTest {  
void m1(Delegate d);  
void m2([MarshalAs(UnmanagedType.Interface)] Delegate d);
void m3([MarshalAs(UnmanagedType.Interface)] ref Delegate d);
void m4([MarshalAs(UnmanagedType.FunctionPtr)] Delegate d);
void m5([MarshalAs(UnmanagedType.FunctionPtr)] ref Delegate d);
}  
```  
  
### <a name="type-library-representation"></a><span data-ttu-id="e4b88-175">Darstellung der Typbibliothek</span><span class="sxs-lookup"><span data-stu-id="e4b88-175">Type library representation</span></span>  
  
```cpp  
importlib("mscorlib.tlb");  
interface DelegateTest : IDispatch {  
[id(…)] HRESULT m1([in] _Delegate* d);  
[id(…)] HRESULT m2([in] _Delegate* d);  
[id(…)] HRESULT m3([in, out] _Delegate** d);  
[id()] HRESULT m4([in] int d);  
[id()] HRESULT m5([in, out] int *d);  
   };  
```  
  
 <span data-ttu-id="e4b88-176">Ein Funktionszeiger kann dereferenziert werden, wie jeder andere nicht verwaltete Funktionszeiger dereferenziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4b88-176">A function pointer can be dereferenced, just as any other unmanaged function pointer can be dereferenced.</span></span>  

<span data-ttu-id="e4b88-177">In diesem Beispiel ist das Ergebnis ein `int`-Typ und ein Zeiger auf einen `int`-Typ, wenn zwei Delegaten als <xref:System.Runtime.InteropServices.UnmanagedType.FunctionPtr?displayProperty=nameWithType> gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-177">In this example, when the two delegates are marshaled as <xref:System.Runtime.InteropServices.UnmanagedType.FunctionPtr?displayProperty=nameWithType>, the result is an `int` and a pointer to an `int`.</span></span> <span data-ttu-id="e4b88-178">Da Delegattypen gemarshallt werden, stellt `int` hier einen Zeiger auf einen `void*`-Typ dar, der der Adresse des Delegaten im Arbeitsspeicher entspricht.</span><span class="sxs-lookup"><span data-stu-id="e4b88-178">Because delegate types are being marshaled, `int` here represents a pointer to a void (`void*`), which is the address of the delegate in memory.</span></span> <span data-ttu-id="e4b88-179">Das Ergebnis bezieht sich also auf 32-Bit-Windows-Systeme, da `int` in diesem Fall die Größe des Funktionszeigers darstellt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-179">In other words, this result is specific to 32-bit Windows systems, since `int` here represents the size of the function pointer.</span></span>

> [!NOTE]
> <span data-ttu-id="e4b88-180">Ein Verweis auf den Funktionszeiger auf einen verwalteten Delegaten in nicht verwaltetem Code hindert die Common Language Runtime nicht daran, eine Garbage Collection für das verwaltete Objekt durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="e4b88-180">A reference to the function pointer to a managed delegate held by unmanaged code does not prevent the common language runtime from performing garbage collection on the managed object.</span></span>  
  
 <span data-ttu-id="e4b88-181">Der folgende Code ist beispielsweise falsch, da der Verweis auf das `cb`-Objekt, der an die `SetChangeHandler`-Methode übergeben wurde, `cb` nicht über die Lebensdauer der `Test`-Methode hinaus gültig hält.</span><span class="sxs-lookup"><span data-stu-id="e4b88-181">For example, the following code is incorrect because the reference to the `cb` object, passed to the `SetChangeHandler` method, does not keep `cb` alive beyond the life of the `Test` method.</span></span> <span data-ttu-id="e4b88-182">Nachdem die Garbage Collection des `cb`-Objekts erfolgt ist, ist der an `SetChangeHandler` übergebene Funktionszeiger nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="e4b88-182">Once the `cb` object is garbage collected, the function pointer passed to `SetChangeHandler` is no longer valid.</span></span>  
  
```csharp  
public class ExternalAPI {  
   [DllImport("External.dll")]  
   public static extern void SetChangeHandler(  
      [MarshalAs(UnmanagedType.FunctionPtr)]ChangeDelegate d);  
}  
public delegate bool ChangeDelegate([MarshalAs(UnmanagedType.LPWStr) string S);  
public class CallBackClass {  
   public bool OnChange(string S){ return true;}  
}  
internal class DelegateTest {  
   public static void Test() {  
      CallBackClass cb = new CallBackClass();  
      // Caution: The following reference on the cb object does not keep the
      // object from being garbage collected after the Main method
      // executes.  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));
   }  
}  
```  
  
 <span data-ttu-id="e4b88-183">Um der unerwarteten Garbage Collection entgegenzuwirken, muss der Aufrufer sicherstellen, dass das `cb`-Objekt gültig bleibt, solange der nicht verwaltete Funktionszeiger verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e4b88-183">To compensate for unexpected garbage collection, the caller must ensure that the `cb` object is kept alive as long as the unmanaged function pointer is in use.</span></span> <span data-ttu-id="e4b88-184">Optional können Sie dafür sorgen, dass der nicht verwaltete Code den verwalteten Code benachrichtigt, wenn der Funktionszeiger nicht mehr benötigt wird, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-184">Optionally, you can have the unmanaged code notify the managed code when the function pointer is no longer needed, as the following example shows.</span></span>  
  
```csharp  
internal class DelegateTest {  
   CallBackClass cb;  
   // Called before ever using the callback function.  
   public static void SetChangeHandler() {  
      cb = new CallBackClass();  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));  
   }  
   // Called after using the callback function for the last time.  
   public static void RemoveChangeHandler() {  
      // The cb object can be collected now. The unmanaged code is
      // finished with the callback function.  
      cb = null;  
   }  
}  
```  
  
## <a name="default-marshaling-for-value-types"></a><span data-ttu-id="e4b88-185">Standardmäßiges Marshalling für Werttypen</span><span class="sxs-lookup"><span data-stu-id="e4b88-185">Default marshaling for value types</span></span>  
 <span data-ttu-id="e4b88-186">Die meisten Werttypen, wie ganze Zahlen und Gleitkommazahlen, sind [blitfähig](blittable-and-non-blittable-types.md) und müssen nicht gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-186">Most value types, such as integers and floating-point numbers, are [blittable](blittable-and-non-blittable-types.md) and do not require marshaling.</span></span> <span data-ttu-id="e4b88-187">Andere, [nicht blitfähige](blittable-and-non-blittable-types.md) Typen werden im verwalteten und im nicht verwalteten Speicher unterschiedlich dargestellt und müssen gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-187">Other [non-blittable](blittable-and-non-blittable-types.md) types have dissimilar representations in managed and unmanaged memory and do require marshaling.</span></span> <span data-ttu-id="e4b88-188">Wieder andere Typen erfordern eine explizite, über die Grenzen der Interoperation hinausgehende Formatierung.</span><span class="sxs-lookup"><span data-stu-id="e4b88-188">Still other types require explicit formatting across the interoperation boundary.</span></span>  
  
 <span data-ttu-id="e4b88-189">Dieser Abschnitt enthält Informationen zu den folgenden formatierten Werttypen:</span><span class="sxs-lookup"><span data-stu-id="e4b88-189">This section provides information on the following formatted value types:</span></span>  
  
- [<span data-ttu-id="e4b88-190">Im Plattformaufruf verwendete Werttypen</span><span class="sxs-lookup"><span data-stu-id="e4b88-190">Value Types Used in Platform Invoke</span></span>](#value-types-used-in-platform-invoke)  
  
- [<span data-ttu-id="e4b88-191">In COM-Interop verwendete Werttypen</span><span class="sxs-lookup"><span data-stu-id="e4b88-191">Value Types Used in COM Interop</span></span>](#value-types-used-in-com-interop)  
  
 <span data-ttu-id="e4b88-192">Neben einer Beschreibung formatierter Typen befasst sich dieses Thema mit [Systemwerttypen](#system-value-types), die ein ungewöhnliches Marshallingverhalten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e4b88-192">In addition to describing formatted types, this topic identifies [System Value Types](#system-value-types) that have unusual marshaling behavior.</span></span>  
  
 <span data-ttu-id="e4b88-193">Ein formatierter Typ ist ein komplexer Typ, der Informationen enthält, mit denen explizit das Layout seiner Member im Speicher gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="e4b88-193">A formatted type is a complex type that contains information that explicitly controls the layout of its members in memory.</span></span> <span data-ttu-id="e4b88-194">Informationen zum Memberlayout werden mit dem <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-194">The member layout information is provided using the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute.</span></span> <span data-ttu-id="e4b88-195">Das Layout kann einen der folgenden <xref:System.Runtime.InteropServices.LayoutKind>-Enumerationswerte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="e4b88-195">The layout can be one of the following <xref:System.Runtime.InteropServices.LayoutKind> enumeration values:</span></span>  
  
- <span data-ttu-id="e4b88-196">**LayoutKind.Auto**</span><span class="sxs-lookup"><span data-stu-id="e4b88-196">**LayoutKind.Auto**</span></span>  
  
     <span data-ttu-id="e4b88-197">Gibt an, dass die Common Language Runtime die Member dieses Typs aus Gründen der Effizienz frei neu anordnen kann.</span><span class="sxs-lookup"><span data-stu-id="e4b88-197">Indicates that the common language runtime is free to reorder the members of the type for efficiency.</span></span> <span data-ttu-id="e4b88-198">Wenn ein Werttyp allerdings an nicht verwalteten Code übergeben wird, ist das Layout der Member vorhersehbar.</span><span class="sxs-lookup"><span data-stu-id="e4b88-198">However, when a value type is passed to unmanaged code, the layout of the members is predictable.</span></span> <span data-ttu-id="e4b88-199">Der Versuch, eine solche Struktur automatisch zu marshallen, bewirkt eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="e4b88-199">An attempt to marshal such a structure automatically causes an exception.</span></span>  
  
- <span data-ttu-id="e4b88-200">**LayoutKind.Sequential**</span><span class="sxs-lookup"><span data-stu-id="e4b88-200">**LayoutKind.Sequential**</span></span>  
  
     <span data-ttu-id="e4b88-201">Gibt an, dass die Member des Typs im nicht verwalteten Speicher in der gleichen Reihenfolge angeordnet werden sollen, in der sie in der Definition des verwalteten Typs erscheinen.</span><span class="sxs-lookup"><span data-stu-id="e4b88-201">Indicates that the members of the type are to be laid out in unmanaged memory in the same order in which they appear in the managed type definition.</span></span>  
  
- <span data-ttu-id="e4b88-202">**LayoutKind.Explicit**</span><span class="sxs-lookup"><span data-stu-id="e4b88-202">**LayoutKind.Explicit**</span></span>  
  
     <span data-ttu-id="e4b88-203">Gibt an, dass die Member entsprechend dem <xref:System.Runtime.InteropServices.FieldOffsetAttribute> angeordnet werden, das mit jedem Feld angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4b88-203">Indicates that the members are laid out according to the <xref:System.Runtime.InteropServices.FieldOffsetAttribute> supplied with each field.</span></span>  
  
### <a name="value-types-used-in-platform-invoke"></a><span data-ttu-id="e4b88-204">Im Plattformaufruf verwendete Werttypen</span><span class="sxs-lookup"><span data-stu-id="e4b88-204">Value Types Used in Platform Invoke</span></span>  
 <span data-ttu-id="e4b88-205">Im folgenden Beispiel stellen die Typen `Point` und `Rect` Memberlayoutinformationen mithilfe von **StructLayoutAttribute** bereit.</span><span class="sxs-lookup"><span data-stu-id="e4b88-205">In the following example the `Point` and `Rect` types provide member layout information using the **StructLayoutAttribute**.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
   Public x As Integer  
   Public y As Integer  
End Structure  
<StructLayout(LayoutKind.Explicit)> Public Structure Rect  
   <FieldOffset(0)> Public left As Integer  
   <FieldOffset(4)> Public top As Integer  
   <FieldOffset(8)> Public right As Integer  
   <FieldOffset(12)> Public bottom As Integer  
End Structure  
```  
  
```csharp  
using System.Runtime.InteropServices;  
[StructLayout(LayoutKind.Sequential)]  
public struct Point {  
   public int x;  
   public int y;  
}
  
[StructLayout(LayoutKind.Explicit)]  
public struct Rect {  
   [FieldOffset(0)] public int left;  
   [FieldOffset(4)] public int top;  
   [FieldOffset(8)] public int right;  
   [FieldOffset(12)] public int bottom;  
}  
```  
  
 <span data-ttu-id="e4b88-206">Beim Marshallen an nicht verwalteten Code werden diese formatierten Typen als Strukturen im C-Stil gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-206">When marshaled to unmanaged code, these formatted types are marshaled as C-style structures.</span></span> <span data-ttu-id="e4b88-207">Dies bietet eine einfache Möglichkeit zum Aufrufen einer nicht verwalteten API, die über Strukturargumente verfügt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-207">This provides an easy way of calling an unmanaged API that has structure arguments.</span></span> <span data-ttu-id="e4b88-208">So können die Strukturen `POINT` und `RECT` beispielsweise folgendermaßen an die **PtInRect**-Funktion der Microsoft Windows-API übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="e4b88-208">For example, the `POINT` and `RECT` structures can be passed to the Microsoft Windows API **PtInRect** function as follows:</span></span>  
  
```cpp  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 <span data-ttu-id="e4b88-209">Sie können Strukturen unter Verwendung der folgenden Definition des Plattformaufrufs übergeben:</span><span class="sxs-lookup"><span data-stu-id="e4b88-209">You can pass structures using the following platform invoke definition:</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function PtInRect Lib "User32.dll" (
        ByRef r As Rect, p As Point) As Boolean
End Class
```
  
```csharp
internal static class NativeMethods
{
   [DllImport("User32.dll")]
   internal static extern bool PtInRect(ref Rect r, Point p);
}
```
  
 <span data-ttu-id="e4b88-210">Der Werttyp `Rect` muss mit einem Verweis übergeben werden, da die nicht verwaltete API einen Zeiger auf ein `RECT` erwartet, der an die Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4b88-210">The `Rect` value type must be passed by reference because the unmanaged API is expecting a pointer to a `RECT` to be passed to the function.</span></span> <span data-ttu-id="e4b88-211">Der Werttyp `Point` wird nach Wert übergeben, da die nicht verwaltete API erwartet, dass `POINT` im Stack übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4b88-211">The `Point` value type is passed by value because the unmanaged API expects the `POINT` to be passed on the stack.</span></span> <span data-ttu-id="e4b88-212">Dieser feine Unterschied ist sehr wichtig.</span><span class="sxs-lookup"><span data-stu-id="e4b88-212">This subtle difference is very important.</span></span> <span data-ttu-id="e4b88-213">Verweise werden als Zeiger an nicht verwalteten Code übergeben.</span><span class="sxs-lookup"><span data-stu-id="e4b88-213">References are passed to unmanaged code as pointers.</span></span> <span data-ttu-id="e4b88-214">Werte werden im Stack an nicht verwalteten Code übergeben.</span><span class="sxs-lookup"><span data-stu-id="e4b88-214">Values are passed to unmanaged code on the stack.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4b88-215">Wenn ein formatierter Typ als Struktur gemarshallt wird, kann nur auf die Felder im Typ zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-215">When a formatted type is marshaled as a structure, only the fields within the type are accessible.</span></span> <span data-ttu-id="e4b88-216">Wenn der Typ Methoden, Eigenschaften oder Ereignisse aufweist, kann auf diese vom nicht verwalteten Code nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-216">If the type has methods, properties, or events, they are inaccessible from unmanaged code.</span></span>  
  
 <span data-ttu-id="e4b88-217">Klassen können ebenfalls an nicht verwalteten Code als Strukturen im C-Stil gemarshallt werden, vorausgesetzt, sie weisen ein festes Memberlayout auf.</span><span class="sxs-lookup"><span data-stu-id="e4b88-217">Classes can also be marshaled to unmanaged code as C-style structures, provided they have fixed member layout.</span></span> <span data-ttu-id="e4b88-218">Die Memberlayoutinformationen für eine Klasse werden ebenfalls mit dem <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-218">The member layout information for a class is also provided with the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute.</span></span> <span data-ttu-id="e4b88-219">Der Hauptunterschied zwischen Werttypen mit festen Layout und Klassen mit festem Layout ist die Art und Weise, wie diese an nicht verwalteten Code gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-219">The main difference between value types with fixed layout and classes with fixed layout is the way in which they are marshaled to unmanaged code.</span></span> <span data-ttu-id="e4b88-220">Werttypen werden nach Wert (im Stack) übergeben, und dementsprechend werden Änderungen, die von der aufgerufenen Instanz an Membern dieses Typs vorgenommen werden, dem Aufrufer nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-220">Value types are passed by value (on the stack) and consequently any changes made to the members of the type by the callee are not seen by the caller.</span></span> <span data-ttu-id="e4b88-221">Verweistypen werden als Verweis übergeben (ein Verweis auf den Typ wird in den Stack übergeben); dementsprechend werden alle Änderungen, die von der aufgerufenen Instanz an blitfähigen Membern des Typs vorgenommen werden, für den Aufrufer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-221">Reference types are passed by reference (a reference to the type is passed on the stack); consequently, all changes made to blittable-type members of a type by the callee are seen by the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4b88-222">Wenn ein Verweistyp nicht blitfähige Typen als Member enthält, muss die Konvertierung zwei Mal erfolgen: Das erste Mal, wenn ein Argument an die nicht verwaltete Seite übergeben wird, zum zweiten Mal bei der Rückgabe aus dem Aufruf.</span><span class="sxs-lookup"><span data-stu-id="e4b88-222">If a reference type has members of non-blittable types, conversion is required twice: the first time when an argument is passed to the unmanaged side and the second time on return from the call.</span></span> <span data-ttu-id="e4b88-223">Aufgrund dieses zusätzlichen Aufwands müssen In/Out-Parameter explizit auf ein Argument angewendet werden, wenn der Aufrufer Änderungen sehen möchte, die von der aufgerufenen Instanz vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-223">Due to this added overhead, In/Out parameters must be explicitly applied to an argument if the caller wants to see changes made by the callee.</span></span>  
  
 <span data-ttu-id="e4b88-224">Im folgenden Beispiel hat die `SystemTime`-Klasse ein sequenzielles Memberlayout und kann an die **GetSystemTime**-Funktion der Windows-API übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-224">In the following example, the `SystemTime` class has sequential member layout and can be passed to the Windows API **GetSystemTime** function.</span></span>  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class SystemTime  
   Public wYear As System.UInt16  
   Public wMonth As System.UInt16  
   Public wDayOfWeek As System.UInt16  
   Public wDay As System.UInt16  
   Public wHour As System.UInt16  
   Public wMinute As System.UInt16  
   Public wSecond As System.UInt16  
   Public wMilliseconds As System.UInt16  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
   public class SystemTime {  
   public ushort wYear;
   public ushort wMonth;  
   public ushort wDayOfWeek;
   public ushort wDay;
   public ushort wHour;
   public ushort wMinute;
   public ushort wSecond;
   public ushort wMilliseconds;
}  
```  
  
 <span data-ttu-id="e4b88-225">Die **GetSystemTime**-Funktion ist wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="e4b88-225">The **GetSystemTime** function is defined as follows:</span></span>  
  
```cpp  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 <span data-ttu-id="e4b88-226">Die entsprechende Definition des Plattformaufrufs für **GetSystemTime** lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e4b88-226">The equivalent platform invoke definition for **GetSystemTime** is as follows:</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Sub GetSystemTime Lib "Kernel32.dll" (
        ByVal sysTime As SystemTime)
End Class
```
  
```csharp
internal static class NativeMethods
{
   [DllImport("Kernel32.dll", CharSet = CharSet.Auto)]
   internal static extern void GetSystemTime(SystemTime st);
}
```
  
 <span data-ttu-id="e4b88-227">Beachten Sie, dass das `SystemTime`-Argument nicht als Verweisargument typisiert ist, da `SystemTime` eine Klasse und kein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="e4b88-227">Notice that the `SystemTime` argument is not typed as a reference argument because `SystemTime` is a class, not a value type.</span></span> <span data-ttu-id="e4b88-228">Im Gegensatz zu Werttypen werden Klassen im durch Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="e4b88-228">Unlike value types, classes are always passed by reference.</span></span>  
  
 <span data-ttu-id="e4b88-229">Das folgende Codebeispiel zeigt eine andere `Point`-Klasse, die eine Methode mit Namen `SetXY` aufweist.</span><span class="sxs-lookup"><span data-stu-id="e4b88-229">The following code example shows a different `Point` class that has a method called `SetXY`.</span></span> <span data-ttu-id="e4b88-230">Der der Typ über ein sequenzielles Layout verfügt, kann er an nicht verwalteten Code übergeben und als Struktur gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-230">Because the type has sequential layout, it can be passed to unmanaged code and marshaled as a structure.</span></span> <span data-ttu-id="e4b88-231">Der `SetXY`-Member kann jedoch nicht von nicht verwaltetem Code aufgerufen werden, obwohl das Objekt durch Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4b88-231">However, the `SetXY` member is not callable from unmanaged code, even though the object is passed by reference.</span></span>  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class Point  
   Private x, y As Integer  
   Public Sub SetXY(x As Integer, y As Integer)  
      Me.x = x  
      Me.y = y  
   End Sub  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class Point {  
   int x, y;  
   public void SetXY(int x, int y){
      this.x = x;  
      this.y = y;  
   }  
}  
```  
  
### <a name="value-types-used-in-com-interop"></a><span data-ttu-id="e4b88-232">In COM-Interop verwendete Werttypen</span><span class="sxs-lookup"><span data-stu-id="e4b88-232">Value Types Used in COM Interop</span></span>  
 <span data-ttu-id="e4b88-233">Formatierte Typen können auch an COM-Interop-Methodenaufrufe übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-233">Formatted types can also be passed to COM interop method calls.</span></span> <span data-ttu-id="e4b88-234">Tatsache ist, dass Werttypen automatisch in Strukturen konvertiert werden, wenn sie in eine Typbibliothek exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-234">In fact, when exported to a type library, value types are automatically converted to structures.</span></span> <span data-ttu-id="e4b88-235">Wie im folgenden Beispiel gezeigt, wird der `Point`-Werttyp zu einer Typdefinition (typedef) mit Namen `Point`.</span><span class="sxs-lookup"><span data-stu-id="e4b88-235">As the following example shows, the `Point` value type becomes a type definition (typedef) with the name `Point`.</span></span> <span data-ttu-id="e4b88-236">Alle Verweise auf den `Point`-Werttyp an anderer Stelle in der Typbibliothek werden durch die `Point`-Typdefinition ersetzt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-236">All references to the `Point` value type elsewhere in the type library are replaced with the `Point` typedef.</span></span>  
  
 <span data-ttu-id="e4b88-237">**Darstellung der Typbibliothek**</span><span class="sxs-lookup"><span data-stu-id="e4b88-237">**Type library representation**</span></span>  
  
```cpp  
typedef struct tagPoint {  
   int x;  
   int y;  
} Point;  
interface _Graphics {  
   …  
   HRESULT SetPoint ([in] Point p)  
   HRESULT SetPointRef ([in,out] Point *p)  
   HRESULT GetPoint ([out,retval] Point *p)  
}  
```  
  
 <span data-ttu-id="e4b88-238">Die gleichen Regeln, die zum Marshallen von Werten und Verweisen an Plattformaufrufe gelten, gelten auch beim Marshallen über COM-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="e4b88-238">The same rules used to marshal values and references to platform invoke calls are used when marshaling through COM interfaces.</span></span> <span data-ttu-id="e4b88-239">Wenn eine Instanz des `Point`-Werttyps von .NET Framework an COM übergeben wird, wird der `Point` nach Wert übergeben.</span><span class="sxs-lookup"><span data-stu-id="e4b88-239">For example, when an instance of the `Point` value type is passed from the .NET Framework to COM, the `Point` is passed by value.</span></span> <span data-ttu-id="e4b88-240">Wenn der `Point`-Werttyp durch Verweis übergeben wird, wird ein Zeiger auf den `Point` in den Stack übergeben.</span><span class="sxs-lookup"><span data-stu-id="e4b88-240">If the `Point` value type is passed by reference, a pointer to a `Point` is passed on the stack.</span></span> <span data-ttu-id="e4b88-241">Der Interop-Marshaller unterstützt kein höheres Maß an Dereferenzierung (**Point** \*\*) in beide Richtungen.</span><span class="sxs-lookup"><span data-stu-id="e4b88-241">The interop marshaler does not support higher levels of indirection (**Point** \*\*) in either direction.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4b88-242">Strukturen, bei denen der <xref:System.Runtime.InteropServices.LayoutKind>-Enumerationswert auf **Explicit** (Explizit) festgelegt ist, können in COM-Interop nicht verwendet werden, da die exportierte Typbibliothek kein explizites Layout darstellen kann.</span><span class="sxs-lookup"><span data-stu-id="e4b88-242">Structures having the <xref:System.Runtime.InteropServices.LayoutKind> enumeration value set to **Explicit** cannot be used in COM interop because the exported type library cannot express an explicit layout.</span></span>  
  
### <a name="system-value-types"></a><span data-ttu-id="e4b88-243">Systemwerttypen</span><span class="sxs-lookup"><span data-stu-id="e4b88-243">System Value Types</span></span>  
 <span data-ttu-id="e4b88-244">Der <xref:System>-Namespace enthält mehrere Werttypen, die für die geschaltete Form von primitiven Datentypen der Laufzeit stehen.</span><span class="sxs-lookup"><span data-stu-id="e4b88-244">The <xref:System> namespace has several value types that represent the boxed form of the runtime primitive types.</span></span> <span data-ttu-id="e4b88-245">Beispielsweise steht die Werttypstruktur <xref:System.Int32?displayProperty=nameWithType> für die geschachtelte Form von **ELEMENT_TYPE_I4**.</span><span class="sxs-lookup"><span data-stu-id="e4b88-245">For example, the value type <xref:System.Int32?displayProperty=nameWithType> structure represents the boxed form of **ELEMENT_TYPE_I4**.</span></span> <span data-ttu-id="e4b88-246">Anstatt diese Typen als Strukturen zu marshallen, wie dies bei anderen formatierten Typen der Fall ist, marshallen Sie sie in der gleichen Weise wie die primitiven Datentypen, die sie schachteln.</span><span class="sxs-lookup"><span data-stu-id="e4b88-246">Instead of marshaling these types as structures, as other formatted types are, you marshal them in the same way as the primitive types they box.</span></span> <span data-ttu-id="e4b88-247">**System.Int32** wird daher als **ELEMENT_TYPE_I4** anstatt als eine Struktur gemarshallt, die ein einziges Mitglied vom Typ **long** enthält.</span><span class="sxs-lookup"><span data-stu-id="e4b88-247">**System.Int32** is therefore marshaled as **ELEMENT_TYPE_I4** instead of as a structure containing a single member of type **long**.</span></span> <span data-ttu-id="e4b88-248">Die folgende Tabelle enthält eine Liste der Werttypen im Namespace **System**, bei denen es sich um geschachtelte Darstellungen von primitiven Datentypen handelt.</span><span class="sxs-lookup"><span data-stu-id="e4b88-248">The following table contains a list of the value types in the **System** namespace that are boxed representations of primitive types.</span></span>  
  
|<span data-ttu-id="e4b88-249">Systemwerttyp</span><span class="sxs-lookup"><span data-stu-id="e4b88-249">System value type</span></span>|<span data-ttu-id="e4b88-250">Elementtyp</span><span class="sxs-lookup"><span data-stu-id="e4b88-250">Element type</span></span>|  
|-----------------------|------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="e4b88-251">**ELEMENT_TYPE_BOOLEAN**</span><span class="sxs-lookup"><span data-stu-id="e4b88-251">**ELEMENT_TYPE_BOOLEAN**</span></span>|  
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="e4b88-252">**ELEMENT_TYPE_I1**</span><span class="sxs-lookup"><span data-stu-id="e4b88-252">**ELEMENT_TYPE_I1**</span></span>|  
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="e4b88-253">**ELEMENT_TYPE_UI1**</span><span class="sxs-lookup"><span data-stu-id="e4b88-253">**ELEMENT_TYPE_UI1**</span></span>|  
|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="e4b88-254">**ELEMENT_TYPE_CHAR**</span><span class="sxs-lookup"><span data-stu-id="e4b88-254">**ELEMENT_TYPE_CHAR**</span></span>|  
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="e4b88-255">**ELEMENT_TYPE_I2**</span><span class="sxs-lookup"><span data-stu-id="e4b88-255">**ELEMENT_TYPE_I2**</span></span>|  
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="e4b88-256">**ELEMENT_TYPE_U2**</span><span class="sxs-lookup"><span data-stu-id="e4b88-256">**ELEMENT_TYPE_U2**</span></span>|  
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="e4b88-257">**ELEMENT_TYPE_I4**</span><span class="sxs-lookup"><span data-stu-id="e4b88-257">**ELEMENT_TYPE_I4**</span></span>|  
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="e4b88-258">**ELEMENT_TYPE_U4**</span><span class="sxs-lookup"><span data-stu-id="e4b88-258">**ELEMENT_TYPE_U4**</span></span>|  
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="e4b88-259">**ELEMENT_TYPE_I8**</span><span class="sxs-lookup"><span data-stu-id="e4b88-259">**ELEMENT_TYPE_I8**</span></span>|  
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="e4b88-260">**ELEMENT_TYPE_U8**</span><span class="sxs-lookup"><span data-stu-id="e4b88-260">**ELEMENT_TYPE_U8**</span></span>|  
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="e4b88-261">**ELEMENT_TYPE_R4**</span><span class="sxs-lookup"><span data-stu-id="e4b88-261">**ELEMENT_TYPE_R4**</span></span>|  
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="e4b88-262">**ELEMENT_TYPE_R8**</span><span class="sxs-lookup"><span data-stu-id="e4b88-262">**ELEMENT_TYPE_R8**</span></span>|  
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="e4b88-263">**ELEMENT_TYPE_STRING**</span><span class="sxs-lookup"><span data-stu-id="e4b88-263">**ELEMENT_TYPE_STRING**</span></span>|  
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="e4b88-264">**ELEMENT_TYPE_I**</span><span class="sxs-lookup"><span data-stu-id="e4b88-264">**ELEMENT_TYPE_I**</span></span>|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="e4b88-265">**ELEMENT_TYPE_U**</span><span class="sxs-lookup"><span data-stu-id="e4b88-265">**ELEMENT_TYPE_U**</span></span>|  
  
 <span data-ttu-id="e4b88-266">Einige andere Werttypen im Namespace **System** werden anders verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="e4b88-266">Some other value types in the **System** namespace are handled differently.</span></span> <span data-ttu-id="e4b88-267">Da der nicht verwaltete Code bereits über gut eingeführte Formate für diese Typen verfügt, geht der Marshaller nach speziellen Regel beim Marshallen dieser Typen vor.</span><span class="sxs-lookup"><span data-stu-id="e4b88-267">Because the unmanaged code already has well-established formats for these types, the marshaler has special rules for marshaling them.</span></span> <span data-ttu-id="e4b88-268">Die folgende Tabelle führt die speziellen Werttypen im Namespace **System** sowie den nicht verwalteten Typ auf, an den sie gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="e4b88-268">The following table lists the special value types in the **System** namespace, as well as the unmanaged type they are marshaled to.</span></span>  
  
|<span data-ttu-id="e4b88-269">Systemwerttyp</span><span class="sxs-lookup"><span data-stu-id="e4b88-269">System value type</span></span>|<span data-ttu-id="e4b88-270">IDL-Typ</span><span class="sxs-lookup"><span data-stu-id="e4b88-270">IDL type</span></span>|  
|-----------------------|--------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="e4b88-271">**DATE**</span><span class="sxs-lookup"><span data-stu-id="e4b88-271">**DATE**</span></span>|  
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="e4b88-272">**DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="e4b88-272">**DECIMAL**</span></span>|  
|<xref:System.Guid?displayProperty=nameWithType>|<span data-ttu-id="e4b88-273">**GUID**</span><span class="sxs-lookup"><span data-stu-id="e4b88-273">**GUID**</span></span>|  
|<xref:System.Drawing.Color?displayProperty=nameWithType>|<span data-ttu-id="e4b88-274">**OLE_COLOR**</span><span class="sxs-lookup"><span data-stu-id="e4b88-274">**OLE_COLOR**</span></span>|  
  
 <span data-ttu-id="e4b88-275">Der folgende Code zeigt die Definition der nicht verwalteten Typen **DATE**, **GUID**, **DECIMAL** und **OLE_COLOR** in der Stdole2-Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="e4b88-275">The following code shows the definition of the unmanaged types **DATE**, **GUID**, **DECIMAL**, and **OLE_COLOR** in the Stdole2 type library.</span></span>  
  
#### <a name="type-library-representation"></a><span data-ttu-id="e4b88-276">Darstellung der Typbibliothek</span><span class="sxs-lookup"><span data-stu-id="e4b88-276">Type library representation</span></span>  
  
```cpp  
typedef double DATE;  
typedef DWORD OLE_COLOR;  
  
typedef struct tagDEC {  
    USHORT    wReserved;  
    BYTE      scale;  
    BYTE      sign;  
    ULONG     Hi32;  
    ULONGLONG Lo64;  
} DECIMAL;  
  
typedef struct tagGUID {  
    DWORD Data1;  
    WORD  Data2;  
    WORD  Data3;  
    BYTE  Data4[ 8 ];  
} GUID;  
```  
  
 <span data-ttu-id="e4b88-277">Der folgende Code zeigt die entsprechenden Definitionen in der verwalteten `IValueTypes`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e4b88-277">The following code shows the corresponding definitions in the managed `IValueTypes` interface.</span></span>  
  
```vb  
Public Interface IValueTypes  
   Sub M1(d As System.DateTime)  
   Sub M2(d As System.Guid)  
   Sub M3(d As System.Decimal)  
   Sub M4(d As System.Drawing.Color)  
End Interface  
```  
  
```csharp  
public interface IValueTypes {  
   void M1(System.DateTime d);  
   void M2(System.Guid d);  
   void M3(System.Decimal d);  
   void M4(System.Drawing.Color d);  
}  
```  
  
#### <a name="type-library-representation"></a><span data-ttu-id="e4b88-278">Darstellung der Typbibliothek</span><span class="sxs-lookup"><span data-stu-id="e4b88-278">Type library representation</span></span>  
  
```cpp  
[…]  
interface IValueTypes : IDispatch {  
   HRESULT M1([in] DATE d);  
   HRESULT M2([in] GUID d);  
   HRESULT M3([in] DECIMAL d);  
   HRESULT M4([in] OLE_COLOR d);  
};  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4b88-279">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4b88-279">See also</span></span>

- [<span data-ttu-id="e4b88-280">Blitfähige und nicht blitfähige Typen</span><span class="sxs-lookup"><span data-stu-id="e4b88-280">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- [<span data-ttu-id="e4b88-281">Kopieren und Fixieren</span><span class="sxs-lookup"><span data-stu-id="e4b88-281">Copying and Pinning</span></span>](copying-and-pinning.md)
- [<span data-ttu-id="e4b88-282">Standardmäßiges Marshalling für Arrays</span><span class="sxs-lookup"><span data-stu-id="e4b88-282">Default Marshaling for Arrays</span></span>](default-marshaling-for-arrays.md)
- [<span data-ttu-id="e4b88-283">Standardmäßiges Marshalling für Objekte</span><span class="sxs-lookup"><span data-stu-id="e4b88-283">Default Marshaling for Objects</span></span>](default-marshaling-for-objects.md)
- [<span data-ttu-id="e4b88-284">Standardmäßiges Marshalling für Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="e4b88-284">Default Marshaling for Strings</span></span>](default-marshaling-for-strings.md)
