---
title: Standardmarshallingverhalten
ms.date: 06/26/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, default
- interoperation with unmanaged code, marshaling
- marshaling behavior
ms.assetid: c0a9bcdf-3df8-4db3-b1b6-abbdb2af809a
ms.openlocfilehash: 18282d14540027e4fae4fe152d3867ad8c223c37
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181482"
---
# <a name="default-marshaling-behavior"></a><span data-ttu-id="cd55e-102">Standardmarshallingverhalten</span><span class="sxs-lookup"><span data-stu-id="cd55e-102">Default Marshaling Behavior</span></span>
<span data-ttu-id="cd55e-103">Das Interop-Marshalling basiert auf Regeln, die vorgeben, wie sich Daten, die Methodenparametern zugeordnet sind, verhalten, wenn sie zwischen verwaltetem und unverwaltetem Speicher übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-103">Interop marshaling operates on rules that dictate how data associated with method parameters behaves as it passes between managed and unmanaged memory.</span></span> <span data-ttu-id="cd55e-104">Mit diesen integrierten Regeln werden Marshalling-Aktivitäten wie Datentyptransformationen gesteuert, es wird gesteuert, ob eine aufrufende Instanz die Daten ändern kann, die an sie übergeben werden, und ob diese Änderungen an den Aufrufer zurückgegeben werden, und unter welchen Umständen der Marshaller Leistungsoptimierungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-104">These built-in rules control such marshaling activities as data type transformations, whether a callee can change data passed to it and return those changes to the caller, and under which circumstances the marshaler provides performance optimizations.</span></span>  
  
 <span data-ttu-id="cd55e-105">Dieser Abschnitt befasst sich mit den standardmäßigen Verhaltensmerkmalen des Interop-Marshalling-Diensts.</span><span class="sxs-lookup"><span data-stu-id="cd55e-105">This section identifies the default behavioral characteristics of the interop marshaling service.</span></span> <span data-ttu-id="cd55e-106">Er enthält detaillierte Informationen zum Marshallen von Arrays, booleschen Typen, Zeichentypen, Delegaten, Klassen, Objekten, Zeichenfolgen und Strukturen.</span><span class="sxs-lookup"><span data-stu-id="cd55e-106">It presents detailed information on marshaling arrays, Boolean types, char types, delegates, classes, objects, strings, and structures.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd55e-107">Das Marshalling von generischen Typen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-107">Marshaling of generic types is not supported.</span></span> <span data-ttu-id="cd55e-108">Weitere Informationen finden Sie unter [Interoperating Using Generic Types (Interoperation mit generischen Typen)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="cd55e-108">For more information see, [Interoperating Using Generic Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100)).</span></span>  
  
## <a name="memory-management-with-the-interop-marshaler"></a><span data-ttu-id="cd55e-109">Speicherverwaltung mit dem Interop-Marshaller</span><span class="sxs-lookup"><span data-stu-id="cd55e-109">Memory management with the interop marshaler</span></span>  
 <span data-ttu-id="cd55e-110">Der Interop-Marshaller versucht immer, den von nicht verwaltetem Code belegten Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="cd55e-110">The interop marshaler always attempts to free memory allocated by unmanaged code.</span></span> <span data-ttu-id="cd55e-111">Dieses Verhalten entspricht den COM-Speicherverwaltungsregeln, unterscheidet sich jedoch von den Regeln, die für systemeigenes C++ gelten.</span><span class="sxs-lookup"><span data-stu-id="cd55e-111">This behavior complies with COM memory management rules, but differs from the rules that govern native C++.</span></span>  
  
 <span data-ttu-id="cd55e-112">Es kann zu Missverständnissen kommen, wenn Sie das Verhalten von systemeigenem C++ (keine Speicherfreigabe) beim Plattformaufruf erwarten, bei dem automatisch Speicher für Zeiger freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cd55e-112">Confusion can arise if you anticipate native C++ behavior (no memory freeing) when using platform invoke, which automatically frees memory for pointers.</span></span> <span data-ttu-id="cd55e-113">Wenn Sie beispielsweise die folgende nicht verwaltete Methode aus einer C++-DLL aufrufen, wird kein Speicher automatisch freigegeben.</span><span class="sxs-lookup"><span data-stu-id="cd55e-113">For example, calling the following unmanaged method from a C++ DLL does not automatically free any memory.</span></span>  
  
### <a name="unmanaged-signature"></a><span data-ttu-id="cd55e-114">Nicht verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="cd55e-114">Unmanaged signature</span></span>  
  
```cpp  
BSTR MethodOne (BSTR b) {  
     return b;  
}  
```  
  
 <span data-ttu-id="cd55e-115">Wenn Sie die Methode jedoch als einen Prototyp zum Plattformaufruf definieren, jeden **BSTR**-Typ durch einen <xref:System.String>-Typ ersetzen und `MethodOne` aufrufen, versucht die Common Language Runtime `b` zweimal freizugeben.</span><span class="sxs-lookup"><span data-stu-id="cd55e-115">However, if you define the method as a platform invoke prototype, replace each **BSTR** type with a <xref:System.String> type, and call `MethodOne`, the common language runtime attempts to free `b` twice.</span></span> <span data-ttu-id="cd55e-116">Sie können das Marshalling-Verhalten ändern, indem Sie <xref:System.IntPtr>-Typen anstelle von **Zeichenfolgen**typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-116">You can change the marshaling behavior by using <xref:System.IntPtr> types rather than **String** types.</span></span>  
  
 <span data-ttu-id="cd55e-117">Zur Laufzeit wird immer die **CoTaskMemFree**-Methode zum Freigeben von Speicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd55e-117">The runtime always uses the **CoTaskMemFree** method to free memory.</span></span> <span data-ttu-id="cd55e-118">Wenn der Speicher, mit dem Sie arbeiten, nicht der **CoTaskMemAlloc**-Methode zugeordnet wurde, müssen Sie **IntPtr** verwenden und den Speicher manuell mit der geeigneten Methode freigeben.</span><span class="sxs-lookup"><span data-stu-id="cd55e-118">If the memory you are working with was not allocated with the **CoTaskMemAlloc** method, you must use an **IntPtr** and free the memory manually using the appropriate method.</span></span> <span data-ttu-id="cd55e-119">Ebenso können Sie in Situationen, in denen der Speicher niemals freigegeben werden soll, wie bei Verwendung der **GetCommandLine**-Funktion von Kernel32.dll, die einen Zeiger auf den Kernelspeicher zurückgibt, verhindern, dass Speicher automatisch freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cd55e-119">Similarly, you can avoid automatic memory freeing in situations where memory should never be freed, such as when using the **GetCommandLine** function from Kernel32.dll, which returns a pointer to kernel memory.</span></span> <span data-ttu-id="cd55e-120">Details zum manuellen Freigeben von Speicher finden Sie unter [Beispiel für Puffer](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="cd55e-120">For details on manually freeing memory, see the [Buffers Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100)).</span></span>  
  
## <a name="default-marshaling-for-classes"></a><span data-ttu-id="cd55e-121">Standardmäßiges Marshalling für Klassen</span><span class="sxs-lookup"><span data-stu-id="cd55e-121">Default marshaling for classes</span></span>  
 <span data-ttu-id="cd55e-122">Klassen können nur durch COM-Interop gemarshallt werden und werden immer als Schnittstellen gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-122">Classes can be marshaled only by COM interop and are always marshaled as interfaces.</span></span> <span data-ttu-id="cd55e-123">In einigen Fällen wird die zum Marshallen der Klasse verwendete Schnittstelle als Klassenschnittstelle bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="cd55e-123">In some cases the interface used to marshal the class is known as the class interface.</span></span> <span data-ttu-id="cd55e-124">Informationen zum Überschreiben der Klassenschnittstelle mit einer beliebigen Schnittstelle finden Sie unter [Einführung in die Klassenschnittstelle](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span><span class="sxs-lookup"><span data-stu-id="cd55e-124">For information about overriding the class interface with an interface of your choice, see [Introducing the class interface](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span></span>  
  
### <a name="passing-classes-to-com"></a><span data-ttu-id="cd55e-125">Übergeben von Klassen an COM</span><span class="sxs-lookup"><span data-stu-id="cd55e-125">Passing Classes to COM</span></span>  
 <span data-ttu-id="cd55e-126">Wenn eine verwaltete Klasse an COM übergeben wird, umschließt der Interop-Marshaller die Klasse automatisch mit einem COM-Proxy und übergibt die vom Proxy erstellte Klassenschnittstelle an den COM-Methodenaufruf.</span><span class="sxs-lookup"><span data-stu-id="cd55e-126">When a managed class is passed to COM, the interop marshaler automatically wraps the class with a COM proxy and passes the class interface produced by the proxy to the COM method call.</span></span> <span data-ttu-id="cd55e-127">Der Proxy delegiert dann alle Aufrufe der Klassenschnittstelle zurück an das verwaltete Objekt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-127">The proxy then delegates all calls on the class interface back to the managed object.</span></span> <span data-ttu-id="cd55e-128">Der Proxy macht zudem auch weitere Schnittstellen verfügbar, die von der Klasse nicht explizit implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-128">The proxy also exposes other interfaces that are not explicitly implemented by the class.</span></span> <span data-ttu-id="cd55e-129">Der Proxy implementiert automatisch Schnittstellen wie **IUnknown** und **IDispatch** für die Klasse.</span><span class="sxs-lookup"><span data-stu-id="cd55e-129">The proxy automatically implements interfaces such as **IUnknown** and **IDispatch** on behalf of the class.</span></span>  
  
### <a name="passing-classes-to-net-code"></a><span data-ttu-id="cd55e-130">Übergeben von Klassen an .NET-Code</span><span class="sxs-lookup"><span data-stu-id="cd55e-130">Passing Classes to .NET Code</span></span>  
 <span data-ttu-id="cd55e-131">Co-Klassen werden in der Regel nicht als Methodenargumente in COM verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd55e-131">Coclasses are not typically used as method arguments in COM.</span></span> <span data-ttu-id="cd55e-132">Stattdessen wird normalerweise eine Standardschnittstelle anstelle der Co-Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd55e-132">Instead, a default interface is usually passed in place of the coclass.</span></span>  
  
 <span data-ttu-id="cd55e-133">Wenn eine Schnittstelle an verwalteten Code übergeben wird, ist der Interop-Marshaller für das Umschließen der Schnittstelle mit dem geeigneten Wrapper und das Übergeben des Wrappers an die verwaltete Methode zuständig.</span><span class="sxs-lookup"><span data-stu-id="cd55e-133">When an interface is passed into managed code, the interop marshaler is responsible for wrapping the interface with the proper wrapper and passing the wrapper to the managed method.</span></span> <span data-ttu-id="cd55e-134">Herauszufinden, welcher Wrapper verwendet werden sollte, kann schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="cd55e-134">Determining which wrapper to use can be difficult.</span></span> <span data-ttu-id="cd55e-135">Jede Instanz eines COM-Objekts verfügt über einen einzelnen, eindeutigen Wrapper, ganz gleich, wie viele Schnittstellen das Objekt implementiert.</span><span class="sxs-lookup"><span data-stu-id="cd55e-135">Every instance of a COM object has a single, unique wrapper, no matter how many interfaces the object implements.</span></span> <span data-ttu-id="cd55e-136">So hat ein einzelnes COM-Objekt, das fünf unterschiedliche Schnittstellen implementiert, nur einen einzigen Wrapper.</span><span class="sxs-lookup"><span data-stu-id="cd55e-136">For example, a single COM object that implements five distinct interfaces has only one wrapper.</span></span> <span data-ttu-id="cd55e-137">Der gleiche Wrapper macht alle fünf Schnittstellen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cd55e-137">The same wrapper exposes all five interfaces.</span></span> <span data-ttu-id="cd55e-138">Wenn zwei Instanzen des COM-Objekts erstellt werden, werden auch zwei Instanzen des Wrappers erstellt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-138">If two instances of the COM object are created, then two instances of the wrapper are created.</span></span>  
  
 <span data-ttu-id="cd55e-139">Damit der Wrapper über die gesamte Lebensdauer den gleichen Typ beibehält, muss der Interop-Marshaller den korrekten Wrapper beim ersten Mal identifizieren, wenn ein vom Objekt verfügbar gemachte Schnittstelle über den Marshaller übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="cd55e-139">For the wrapper to maintain the same type throughout its lifetime, the interop marshaler must identify the correct wrapper the first time an interface exposed by the object is passed through the marshaler.</span></span> <span data-ttu-id="cd55e-140">Der Marshaller identifiziert das Objekt anhand einer der Schnittstellen, die von dem Objekt implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-140">The marshaler identifies the object by looking at one of the interfaces the object implements.</span></span>  
  
 <span data-ttu-id="cd55e-141">So bestimmt der Marshaller beispielsweise, dass der Klassenwrapper zum Umschließen der Schnittstelle verwendet werden soll, die an verwalteten Code übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="cd55e-141">For example, the marshaler determines that the class wrapper should be used to wrap the interface that was passed into managed code.</span></span> <span data-ttu-id="cd55e-142">Wenn die Schnittstelle erstmals über den Marshaller übergeben wird, prüft der Marshaller, ob die Schnittstelle von einem bekannten Objekt stammt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-142">When the interface is first passed through the marshaler, the marshaler checks whether the interface is coming from a known object.</span></span> <span data-ttu-id="cd55e-143">Diese Überprüfung erfolgt in zwei Situationen:</span><span class="sxs-lookup"><span data-stu-id="cd55e-143">This check occurs in two situations:</span></span>  
  
- <span data-ttu-id="cd55e-144">Eine Schnittstelle wird von einem anderen verwalteten Objekt implementiert, das an anderer Stelle an COM übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="cd55e-144">An interface is being implemented by another managed object that was passed to COM elsewhere.</span></span> <span data-ttu-id="cd55e-145">Der Marshaller kann die Schnittstellen, die von verwalteten Objekten verfügbar gemacht werden, leicht identifizieren und ist in der Lage, die Schnittstelle mit dem verwalteten Objekt zu vergleichen, das die Implementierung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-145">The marshaler can readily identify interfaces exposed by managed objects and is able to match the interface with the managed object that provides the implementation.</span></span> <span data-ttu-id="cd55e-146">Das verwaltete Objekt wird dann an die Methode übergeben, und es wird kein Wrapper benötigt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-146">The managed object is then passed to the method and no wrapper is needed.</span></span>  
  
- <span data-ttu-id="cd55e-147">Ein bereits umschlossenes Objekt implementiert die Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="cd55e-147">An object that has already been wrapped is implementing the interface.</span></span> <span data-ttu-id="cd55e-148">Um festzustellen, ob dies der Fall ist, fragt der Marshaller das Objekt nach seiner **IUnknown-Schnittstelle**, und vergleicht die zurückgegebene Schnittstelle mit den Schnittstellen von anderen Objekten, die bereits umschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="cd55e-148">To determine whether this is the case, the marshaler queries the object for its **IUnknown** interface and compares the returned interface to the interfaces of other objects that are already wrapped.</span></span> <span data-ttu-id="cd55e-149">Wenn die Schnittstelle die gleiche wie die des anderen Wrappers ist, haben die Objekte die gleiche Identität, und der vorhandene Wrapper wird an die Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd55e-149">If the interface is the same as that of another wrapper, the objects have the same identity and the existing wrapper is passed to the method.</span></span>  
  
 <span data-ttu-id="cd55e-150">Wenn die Schnittstelle nicht von einem bekannten Objekt stammt, geht der Marshaller folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="cd55e-150">If an interface is not from a known object, the marshaler does the following:</span></span>  
  
1. <span data-ttu-id="cd55e-151">Der Marshaller fragt das Objekt nach seiner **IProvideClassInfo2**-Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="cd55e-151">The marshaler queries the object for the **IProvideClassInfo2** interface.</span></span> <span data-ttu-id="cd55e-152">Wird diese zurückgegeben, verwendet der Marshaller die von **IProvideClassInfo2.GetGUID** zurückgegebene CLSID, um die Co-Klasse zu identifizieren, die die Schnittstelle bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-152">If provided, the marshaler uses the CLSID returned from **IProvideClassInfo2.GetGUID** to identify the coclass providing the interface.</span></span> <span data-ttu-id="cd55e-153">Mit der CLSID kann der Marshaller den Wrapper in der Registrierung finden, wenn die Assembly bereits registriert ist.</span><span class="sxs-lookup"><span data-stu-id="cd55e-153">With the CLSID, the marshaler can locate the wrapper from the registry if the assembly has previously been registered.</span></span>  
  
2. <span data-ttu-id="cd55e-154">Der Marshaller fragt die **IProvideClassInfo**-Schnittstelle der Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="cd55e-154">The marshaler queries the interface for the **IProvideClassInfo** interface.</span></span> <span data-ttu-id="cd55e-155">Wird diese zurückgegeben, verwendet der Marshaller die von **IProvideClassInfo.GetClassinfo** zurückgegebene **ITypeInfo**, um die CLSID der Klasse zu ermitteln, die die Schnittstelle verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="cd55e-155">If provided, the marshaler uses the **ITypeInfo** returned from **IProvideClassInfo.GetClassinfo** to determine the CLSID of the class exposing the interface.</span></span> <span data-ttu-id="cd55e-156">Der Marshaller kann die CLSID verwenden, um die Metadaten für den Wrapper zu finden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-156">The marshaler can use the CLSID to locate the metadata for the wrapper.</span></span>  
  
3. <span data-ttu-id="cd55e-157">Wenn der Marshaller die Klasse immer noch nicht identifizieren kann, umschließt er die Schnittstelle mit einer generischen Wrapperklasse mit Namen **System.__ComObject**.</span><span class="sxs-lookup"><span data-stu-id="cd55e-157">If the marshaler still cannot identify the class, it wraps the interface with a generic wrapper class called **System.__ComObject**.</span></span>  
  
## <a name="default-marshaling-for-delegates"></a><span data-ttu-id="cd55e-158">Standardmäßiges Marshalling für Delegaten</span><span class="sxs-lookup"><span data-stu-id="cd55e-158">Default marshaling for delegates</span></span>  
 <span data-ttu-id="cd55e-159">Ein verwalteter Delegat wird als COM-Schnittstelle oder als Funktionszeiger gemarshallt, und zwar basierend auf dem Aufrufmechanismus:</span><span class="sxs-lookup"><span data-stu-id="cd55e-159">A managed delegate is marshaled as a COM interface or as a function pointer, based on the calling mechanism:</span></span>  
  
- <span data-ttu-id="cd55e-160">Für Plattformaufrufe wird ein Delegat standardmäßig als unverwalteter Funktionszeiger gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-160">For platform invoke, a delegate is marshaled as an unmanaged function pointer by default.</span></span>  
  
- <span data-ttu-id="cd55e-161">Für COM-Interop wird ein Delegat standardmäßig als COM-Schnittstelle vom Typ **_Delegate** gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-161">For COM interop, a delegate is marshaled as a COM interface of type **_Delegate** by default.</span></span> <span data-ttu-id="cd55e-162">Die **_Delegate**-Schnittstelle ist in der Typbibliothek Mscorlib.tlb definiert und enthält die <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType>-Methode, mit der Sie in der Lage sind, die Methode aufzurufen, auf die der Delegat verweist.</span><span class="sxs-lookup"><span data-stu-id="cd55e-162">The **_Delegate** interface is defined in the Mscorlib.tlb type library and contains the <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType> method, which enables you to call the method that the delegate references.</span></span>  
  
 <span data-ttu-id="cd55e-163">Die folgende Tabelle zeigt die Marshalling-Optionen für den Datentyp "Verwalteter Delegat".</span><span class="sxs-lookup"><span data-stu-id="cd55e-163">The following table shows the marshaling options for the managed delegate data type.</span></span> <span data-ttu-id="cd55e-164">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Delegaten bereit.</span><span class="sxs-lookup"><span data-stu-id="cd55e-164">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal delegates.</span></span>  
  
|<span data-ttu-id="cd55e-165">Enumerationstyp</span><span class="sxs-lookup"><span data-stu-id="cd55e-165">Enumeration type</span></span>|<span data-ttu-id="cd55e-166">Beschreibung des nicht verwalteten Formats</span><span class="sxs-lookup"><span data-stu-id="cd55e-166">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="cd55e-167">**UnmanagedType.FunctionPtr**</span><span class="sxs-lookup"><span data-stu-id="cd55e-167">**UnmanagedType.FunctionPtr**</span></span>|<span data-ttu-id="cd55e-168">Ein nicht verwaltete Funktionszeiger.</span><span class="sxs-lookup"><span data-stu-id="cd55e-168">An unmanaged function pointer.</span></span>|  
|<span data-ttu-id="cd55e-169">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="cd55e-169">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="cd55e-170">Eine Schnittstelle von Typ **_Delegate**, wie in Mscorlib.tlb definiert.</span><span class="sxs-lookup"><span data-stu-id="cd55e-170">An interface of type **_Delegate**, as defined in Mscorlib.tlb.</span></span>|  
  
 <span data-ttu-id="cd55e-171">Schauen Sie sich den folgenden Beispielcode an, in dem Methoden von `DelegateTestInterface` in eine COM-Typbibliothek exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-171">Consider the following example code in which the methods of `DelegateTestInterface` are exported to a COM type library.</span></span> <span data-ttu-id="cd55e-172">Beachten Sie, dass nur Delegaten, die mit dem Schlüsselwort **ref** (oder **ByRef**) gekennzeichnet sind, als In/Out-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-172">Notice that only delegates marked with the **ref** (or **ByRef**) keyword are passed as In/Out parameters.</span></span>  
  
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
  
### <a name="type-library-representation"></a><span data-ttu-id="cd55e-173">Darstellung der Typbibliothek</span><span class="sxs-lookup"><span data-stu-id="cd55e-173">Type library representation</span></span>  
  
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
  
 <span data-ttu-id="cd55e-174">Ein Funktionszeiger kann dereferenziert werden, wie jeder andere nicht verwaltete Funktionszeiger dereferenziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="cd55e-174">A function pointer can be dereferenced, just as any other unmanaged function pointer can be dereferenced.</span></span>  

<span data-ttu-id="cd55e-175">In diesem Beispiel ist das Ergebnis ein `int`-Typ und ein Zeiger auf einen `int`-Typ, wenn zwei Delegaten als <xref:System.Runtime.InteropServices.UnmanagedType.FunctionPtr?displayProperty=nameWithType> gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-175">In this example, when the two delegates are marshaled as <xref:System.Runtime.InteropServices.UnmanagedType.FunctionPtr?displayProperty=nameWithType>, the result is an `int` and a pointer to an `int`.</span></span> <span data-ttu-id="cd55e-176">Da Delegattypen gemarshallt werden, stellt `int` hier einen Zeiger auf einen `void*`-Typ dar, der der Adresse des Delegaten im Arbeitsspeicher entspricht.</span><span class="sxs-lookup"><span data-stu-id="cd55e-176">Because delegate types are being marshaled, `int` here represents a pointer to a void (`void*`), which is the address of the delegate in memory.</span></span> <span data-ttu-id="cd55e-177">Das Ergebnis bezieht sich also auf 32-Bit-Windows-Systeme, da `int` in diesem Fall die Größe des Funktionszeigers darstellt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-177">In other words, this result is specific to 32-bit Windows systems, since `int` here represents the size of the function pointer.</span></span>

> [!NOTE]
> <span data-ttu-id="cd55e-178">Ein Verweis auf den Funktionszeiger auf einen verwalteten Delegaten in nicht verwaltetem Code hindert die Common Language Runtime nicht daran, eine Garbage Collection für das verwaltete Objekt durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="cd55e-178">A reference to the function pointer to a managed delegate held by unmanaged code does not prevent the common language runtime from performing garbage collection on the managed object.</span></span>  
  
 <span data-ttu-id="cd55e-179">Der folgende Code ist beispielsweise falsch, da der Verweis auf das `cb`-Objekt, der an die `SetChangeHandler`-Methode übergeben wurde, `cb` nicht über die Lebensdauer der `Test`-Methode hinaus gültig hält.</span><span class="sxs-lookup"><span data-stu-id="cd55e-179">For example, the following code is incorrect because the reference to the `cb` object, passed to the `SetChangeHandler` method, does not keep `cb` alive beyond the life of the `Test` method.</span></span> <span data-ttu-id="cd55e-180">Nachdem die Garbage Collection des `cb`-Objekts erfolgt ist, ist der an `SetChangeHandler` übergebene Funktionszeiger nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="cd55e-180">Once the `cb` object is garbage collected, the function pointer passed to `SetChangeHandler` is no longer valid.</span></span>  
  
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
  
 <span data-ttu-id="cd55e-181">Um der unerwarteten Garbage Collection entgegenzuwirken, muss der Aufrufer sicherstellen, dass das `cb`-Objekt gültig bleibt, solange der nicht verwaltete Funktionszeiger verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd55e-181">To compensate for unexpected garbage collection, the caller must ensure that the `cb` object is kept alive as long as the unmanaged function pointer is in use.</span></span> <span data-ttu-id="cd55e-182">Optional können Sie dafür sorgen, dass der nicht verwaltete Code den verwalteten Code benachrichtigt, wenn der Funktionszeiger nicht mehr benötigt wird, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-182">Optionally, you can have the unmanaged code notify the managed code when the function pointer is no longer needed, as the following example shows.</span></span>  
  
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
  
## <a name="default-marshaling-for-value-types"></a><span data-ttu-id="cd55e-183">Standardmäßiges Marshalling für Werttypen</span><span class="sxs-lookup"><span data-stu-id="cd55e-183">Default marshaling for value types</span></span>  
 <span data-ttu-id="cd55e-184">Die meisten Werttypen, wie ganze Zahlen und Gleitkommazahlen, sind [blitfähig](blittable-and-non-blittable-types.md) und müssen nicht gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-184">Most value types, such as integers and floating-point numbers, are [blittable](blittable-and-non-blittable-types.md) and do not require marshaling.</span></span> <span data-ttu-id="cd55e-185">Andere, [nicht blitfähige](blittable-and-non-blittable-types.md) Typen werden im verwalteten und im nicht verwalteten Speicher unterschiedlich dargestellt und müssen gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-185">Other [non-blittable](blittable-and-non-blittable-types.md) types have dissimilar representations in managed and unmanaged memory and do require marshaling.</span></span> <span data-ttu-id="cd55e-186">Wieder andere Typen erfordern eine explizite, über die Grenzen der Interoperation hinausgehende Formatierung.</span><span class="sxs-lookup"><span data-stu-id="cd55e-186">Still other types require explicit formatting across the interoperation boundary.</span></span>  
  
 <span data-ttu-id="cd55e-187">Dieser Abschnitt enthält Informationen zu den folgenden formatierten Werttypen:</span><span class="sxs-lookup"><span data-stu-id="cd55e-187">This section provides information on the following formatted value types:</span></span>  
  
- [<span data-ttu-id="cd55e-188">Im Plattformaufruf verwendete Werttypen</span><span class="sxs-lookup"><span data-stu-id="cd55e-188">Value Types Used in Platform Invoke</span></span>](#value-types-used-in-platform-invoke)  
  
- [<span data-ttu-id="cd55e-189">In COM-Interop verwendete Werttypen</span><span class="sxs-lookup"><span data-stu-id="cd55e-189">Value Types Used in COM Interop</span></span>](#value-types-used-in-com-interop)  
  
 <span data-ttu-id="cd55e-190">Neben einer Beschreibung formatierter Typen befasst sich dieses Thema mit [Systemwerttypen](#system-value-types), die ein ungewöhnliches Marshallingverhalten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cd55e-190">In addition to describing formatted types, this topic identifies [System Value Types](#system-value-types) that have unusual marshaling behavior.</span></span>  
  
 <span data-ttu-id="cd55e-191">Ein formatierter Typ ist ein komplexer Typ, der Informationen enthält, mit denen explizit das Layout seiner Member im Speicher gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="cd55e-191">A formatted type is a complex type that contains information that explicitly controls the layout of its members in memory.</span></span> <span data-ttu-id="cd55e-192">Informationen zum Memberlayout werden mit dem <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-192">The member layout information is provided using the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute.</span></span> <span data-ttu-id="cd55e-193">Das Layout kann einen der folgenden <xref:System.Runtime.InteropServices.LayoutKind>-Enumerationswerte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="cd55e-193">The layout can be one of the following <xref:System.Runtime.InteropServices.LayoutKind> enumeration values:</span></span>  
  
- <span data-ttu-id="cd55e-194">**LayoutKind.Automatic**</span><span class="sxs-lookup"><span data-stu-id="cd55e-194">**LayoutKind.Automatic**</span></span>  
  
     <span data-ttu-id="cd55e-195">Gibt an, dass die Common Language Runtime die Member dieses Typs aus Gründen der Effizienz frei neu anordnen kann.</span><span class="sxs-lookup"><span data-stu-id="cd55e-195">Indicates that the common language runtime is free to reorder the members of the type for efficiency.</span></span> <span data-ttu-id="cd55e-196">Wenn ein Werttyp allerdings an nicht verwalteten Code übergeben wird, ist das Layout der Member vorhersehbar.</span><span class="sxs-lookup"><span data-stu-id="cd55e-196">However, when a value type is passed to unmanaged code, the layout of the members is predictable.</span></span> <span data-ttu-id="cd55e-197">Der Versuch, eine solche Struktur automatisch zu marshallen, bewirkt eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="cd55e-197">An attempt to marshal such a structure automatically causes an exception.</span></span>  
  
- <span data-ttu-id="cd55e-198">**LayoutKind.Sequential**</span><span class="sxs-lookup"><span data-stu-id="cd55e-198">**LayoutKind.Sequential**</span></span>  
  
     <span data-ttu-id="cd55e-199">Gibt an, dass die Member des Typs im nicht verwalteten Speicher in der gleichen Reihenfolge angeordnet werden sollen, in der sie in der Definition des verwalteten Typs erscheinen.</span><span class="sxs-lookup"><span data-stu-id="cd55e-199">Indicates that the members of the type are to be laid out in unmanaged memory in the same order in which they appear in the managed type definition.</span></span>  
  
- <span data-ttu-id="cd55e-200">**LayoutKind.Explicit**</span><span class="sxs-lookup"><span data-stu-id="cd55e-200">**LayoutKind.Explicit**</span></span>  
  
     <span data-ttu-id="cd55e-201">Gibt an, dass die Member entsprechend dem <xref:System.Runtime.InteropServices.FieldOffsetAttribute> angeordnet werden, das mit jedem Feld angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cd55e-201">Indicates that the members are laid out according to the <xref:System.Runtime.InteropServices.FieldOffsetAttribute> supplied with each field.</span></span>  
  
### <a name="value-types-used-in-platform-invoke"></a><span data-ttu-id="cd55e-202">Im Plattformaufruf verwendete Werttypen</span><span class="sxs-lookup"><span data-stu-id="cd55e-202">Value Types Used in Platform Invoke</span></span>  
 <span data-ttu-id="cd55e-203">Im folgenden Beispiel stellen die Typen `Point` und `Rect` Memberlayoutinformationen mithilfe von **StructLayoutAttribute** bereit.</span><span class="sxs-lookup"><span data-stu-id="cd55e-203">In the following example the `Point` and `Rect` types provide member layout information using the **StructLayoutAttribute**.</span></span>  
  
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
  
 <span data-ttu-id="cd55e-204">Beim Marshallen an nicht verwalteten Code werden diese formatierten Typen als Strukturen im C-Stil gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-204">When marshaled to unmanaged code, these formatted types are marshaled as C-style structures.</span></span> <span data-ttu-id="cd55e-205">Dies bietet eine einfache Möglichkeit zum Aufrufen einer nicht verwalteten API, die über Strukturargumente verfügt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-205">This provides an easy way of calling an unmanaged API that has structure arguments.</span></span> <span data-ttu-id="cd55e-206">So können die Strukturen `POINT` und `RECT` beispielsweise folgendermaßen an die **PtInRect**-Funktion der Microsoft Windows-API übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="cd55e-206">For example, the `POINT` and `RECT` structures can be passed to the Microsoft Windows API **PtInRect** function as follows:</span></span>  
  
```cpp  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 <span data-ttu-id="cd55e-207">Sie können Strukturen unter Verwendung der folgenden Definition des Plattformaufrufs übergeben:</span><span class="sxs-lookup"><span data-stu-id="cd55e-207">You can pass structures using the following platform invoke definition:</span></span>  
  
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
  
 <span data-ttu-id="cd55e-208">Der Werttyp `Rect` muss mit einem Verweis übergeben werden, da die nicht verwaltete API einen Zeiger auf ein `RECT` erwartet, der an die Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="cd55e-208">The `Rect` value type must be passed by reference because the unmanaged API is expecting a pointer to a `RECT` to be passed to the function.</span></span> <span data-ttu-id="cd55e-209">Der Werttyp `Point` wird nach Wert übergeben, da die nicht verwaltete API erwartet, dass `POINT` im Stack übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="cd55e-209">The `Point` value type is passed by value because the unmanaged API expects the `POINT` to be passed on the stack.</span></span> <span data-ttu-id="cd55e-210">Dieser feine Unterschied ist sehr wichtig.</span><span class="sxs-lookup"><span data-stu-id="cd55e-210">This subtle difference is very important.</span></span> <span data-ttu-id="cd55e-211">Verweise werden als Zeiger an nicht verwalteten Code übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd55e-211">References are passed to unmanaged code as pointers.</span></span> <span data-ttu-id="cd55e-212">Werte werden im Stack an nicht verwalteten Code übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd55e-212">Values are passed to unmanaged code on the stack.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd55e-213">Wenn ein formatierter Typ als Struktur gemarshallt wird, kann nur auf die Felder im Typ zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-213">When a formatted type is marshaled as a structure, only the fields within the type are accessible.</span></span> <span data-ttu-id="cd55e-214">Wenn der Typ Methoden, Eigenschaften oder Ereignisse aufweist, kann auf diese vom nicht verwalteten Code nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-214">If the type has methods, properties, or events, they are inaccessible from unmanaged code.</span></span>  
  
 <span data-ttu-id="cd55e-215">Klassen können ebenfalls an nicht verwalteten Code als Strukturen im C-Stil gemarshallt werden, vorausgesetzt, sie weisen ein festes Memberlayout auf.</span><span class="sxs-lookup"><span data-stu-id="cd55e-215">Classes can also be marshaled to unmanaged code as C-style structures, provided they have fixed member layout.</span></span> <span data-ttu-id="cd55e-216">Die Memberlayoutinformationen für eine Klasse werden ebenfalls mit dem <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-216">The member layout information for a class is also provided with the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute.</span></span> <span data-ttu-id="cd55e-217">Der Hauptunterschied zwischen Werttypen mit festen Layout und Klassen mit festem Layout ist die Art und Weise, wie diese an nicht verwalteten Code gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-217">The main difference between value types with fixed layout and classes with fixed layout is the way in which they are marshaled to unmanaged code.</span></span> <span data-ttu-id="cd55e-218">Werttypen werden nach Wert (im Stack) übergeben, und dementsprechend werden Änderungen, die von der aufgerufenen Instanz an Membern dieses Typs vorgenommen werden, dem Aufrufer nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-218">Value types are passed by value (on the stack) and consequently any changes made to the members of the type by the callee are not seen by the caller.</span></span> <span data-ttu-id="cd55e-219">Verweistypen werden als Verweis übergeben (ein Verweis auf den Typ wird in den Stack übergeben); dementsprechend werden alle Änderungen, die von der aufgerufenen Instanz an blitfähigen Membern des Typs vorgenommen werden, für den Aufrufer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-219">Reference types are passed by reference (a reference to the type is passed on the stack); consequently, all changes made to blittable-type members of a type by the callee are seen by the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd55e-220">Wenn ein Verweistyp nicht blitfähige Typen als Member enthält, muss die Konvertierung zwei Mal erfolgen: Das erste Mal, wenn ein Argument an die nicht verwaltete Seite übergeben wird, zum zweiten Mal bei der Rückgabe aus dem Aufruf.</span><span class="sxs-lookup"><span data-stu-id="cd55e-220">If a reference type has members of non-blittable types, conversion is required twice: the first time when an argument is passed to the unmanaged side and the second time on return from the call.</span></span> <span data-ttu-id="cd55e-221">Aufgrund dieses zusätzlichen Aufwands müssen In/Out-Parameter explizit auf ein Argument angewendet werden, wenn der Aufrufer Änderungen sehen möchte, die von der aufgerufenen Instanz vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-221">Due to this added overhead, In/Out parameters must be explicitly applied to an argument if the caller wants to see changes made by the callee.</span></span>  
  
 <span data-ttu-id="cd55e-222">Im folgenden Beispiel hat die `SystemTime`-Klasse ein sequenzielles Memberlayout und kann an die **GetSystemTime**-Funktion der Windows-API übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-222">In the following example, the `SystemTime` class has sequential member layout and can be passed to the Windows API **GetSystemTime** function.</span></span>  
  
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
  
 <span data-ttu-id="cd55e-223">Die **GetSystemTime**-Funktion ist wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="cd55e-223">The **GetSystemTime** function is defined as follows:</span></span>  
  
```cpp  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 <span data-ttu-id="cd55e-224">Die entsprechende Definition des Plattformaufrufs für **GetSystemTime** lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cd55e-224">The equivalent platform invoke definition for **GetSystemTime** is as follows:</span></span>  
  
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
  
 <span data-ttu-id="cd55e-225">Beachten Sie, dass das `SystemTime`-Argument nicht als Verweisargument typisiert ist, da `SystemTime` eine Klasse und kein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="cd55e-225">Notice that the `SystemTime` argument is not typed as a reference argument because `SystemTime` is a class, not a value type.</span></span> <span data-ttu-id="cd55e-226">Im Gegensatz zu Werttypen werden Klassen im durch Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd55e-226">Unlike value types, classes are always passed by reference.</span></span>  
  
 <span data-ttu-id="cd55e-227">Das folgende Codebeispiel zeigt eine andere `Point`-Klasse, die eine Methode mit Namen `SetXY` aufweist.</span><span class="sxs-lookup"><span data-stu-id="cd55e-227">The following code example shows a different `Point` class that has a method called `SetXY`.</span></span> <span data-ttu-id="cd55e-228">Der der Typ über ein sequenzielles Layout verfügt, kann er an nicht verwalteten Code übergeben und als Struktur gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-228">Because the type has sequential layout, it can be passed to unmanaged code and marshaled as a structure.</span></span> <span data-ttu-id="cd55e-229">Der `SetXY`-Member kann jedoch nicht von nicht verwaltetem Code aufgerufen werden, obwohl das Objekt durch Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="cd55e-229">However, the `SetXY` member is not callable from unmanaged code, even though the object is passed by reference.</span></span>  
  
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
  
### <a name="value-types-used-in-com-interop"></a><span data-ttu-id="cd55e-230">In COM-Interop verwendete Werttypen</span><span class="sxs-lookup"><span data-stu-id="cd55e-230">Value Types Used in COM Interop</span></span>  
 <span data-ttu-id="cd55e-231">Formatierte Typen können auch an COM-Interop-Methodenaufrufe übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-231">Formatted types can also be passed to COM interop method calls.</span></span> <span data-ttu-id="cd55e-232">Tatsache ist, dass Werttypen automatisch in Strukturen konvertiert werden, wenn sie in eine Typbibliothek exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-232">In fact, when exported to a type library, value types are automatically converted to structures.</span></span> <span data-ttu-id="cd55e-233">Wie im folgenden Beispiel gezeigt, wird der `Point`-Werttyp zu einer Typdefinition (typedef) mit Namen `Point`.</span><span class="sxs-lookup"><span data-stu-id="cd55e-233">As the following example shows, the `Point` value type becomes a type definition (typedef) with the name `Point`.</span></span> <span data-ttu-id="cd55e-234">Alle Verweise auf den `Point`-Werttyp an anderer Stelle in der Typbibliothek werden durch die `Point`-Typdefinition ersetzt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-234">All references to the `Point` value type elsewhere in the type library are replaced with the `Point` typedef.</span></span>  
  
 <span data-ttu-id="cd55e-235">**Darstellung der Typbibliothek**</span><span class="sxs-lookup"><span data-stu-id="cd55e-235">**Type library representation**</span></span>  
  
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
  
 <span data-ttu-id="cd55e-236">Die gleichen Regeln, die zum Marshallen von Werten und Verweisen an Plattformaufrufe gelten, gelten auch beim Marshallen über COM-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="cd55e-236">The same rules used to marshal values and references to platform invoke calls are used when marshaling through COM interfaces.</span></span> <span data-ttu-id="cd55e-237">Wenn eine Instanz des `Point`-Werttyps von .NET Framework an COM übergeben wird, wird der `Point` nach Wert übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd55e-237">For example, when an instance of the `Point` value type is passed from the .NET Framework to COM, the `Point` is passed by value.</span></span> <span data-ttu-id="cd55e-238">Wenn der `Point`-Werttyp durch Verweis übergeben wird, wird ein Zeiger auf den `Point` in den Stack übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd55e-238">If the `Point` value type is passed by reference, a pointer to a `Point` is passed on the stack.</span></span> <span data-ttu-id="cd55e-239">Der Interop-Marshaller unterstützt kein höheres Maß an Dereferenzierung (**Point** \*\*) in beide Richtungen.</span><span class="sxs-lookup"><span data-stu-id="cd55e-239">The interop marshaler does not support higher levels of indirection (**Point** \*\*) in either direction.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd55e-240">Strukturen, bei denen der <xref:System.Runtime.InteropServices.LayoutKind>-Enumerationswert auf **Explicit** (Explizit) festgelegt ist, können in COM-Interop nicht verwendet werden, da die exportierte Typbibliothek kein explizites Layout darstellen kann.</span><span class="sxs-lookup"><span data-stu-id="cd55e-240">Structures having the <xref:System.Runtime.InteropServices.LayoutKind> enumeration value set to **Explicit** cannot be used in COM interop because the exported type library cannot express an explicit layout.</span></span>  
  
### <a name="system-value-types"></a><span data-ttu-id="cd55e-241">Systemwerttypen</span><span class="sxs-lookup"><span data-stu-id="cd55e-241">System Value Types</span></span>  
 <span data-ttu-id="cd55e-242">Der <xref:System>-Namespace enthält mehrere Werttypen, die für die geschaltete Form von primitiven Datentypen der Laufzeit stehen.</span><span class="sxs-lookup"><span data-stu-id="cd55e-242">The <xref:System> namespace has several value types that represent the boxed form of the runtime primitive types.</span></span> <span data-ttu-id="cd55e-243">Beispielsweise steht die Werttypstruktur <xref:System.Int32?displayProperty=nameWithType> für die geschachtelte Form von **ELEMENT_TYPE_I4**.</span><span class="sxs-lookup"><span data-stu-id="cd55e-243">For example, the value type <xref:System.Int32?displayProperty=nameWithType> structure represents the boxed form of **ELEMENT_TYPE_I4**.</span></span> <span data-ttu-id="cd55e-244">Anstatt diese Typen als Strukturen zu marshallen, wie dies bei anderen formatierten Typen der Fall ist, marshallen Sie sie in der gleichen Weise wie die primitiven Datentypen, die sie schachteln.</span><span class="sxs-lookup"><span data-stu-id="cd55e-244">Instead of marshaling these types as structures, as other formatted types are, you marshal them in the same way as the primitive types they box.</span></span> <span data-ttu-id="cd55e-245">**System.Int32** wird daher als **ELEMENT_TYPE_I4** anstatt als eine Struktur gemarshallt, die ein einziges Mitglied vom Typ **long** enthält.</span><span class="sxs-lookup"><span data-stu-id="cd55e-245">**System.Int32** is therefore marshaled as **ELEMENT_TYPE_I4** instead of as a structure containing a single member of type **long**.</span></span> <span data-ttu-id="cd55e-246">Die folgende Tabelle enthält eine Liste der Werttypen im Namespace **System**, bei denen es sich um geschachtelte Darstellungen von primitiven Datentypen handelt.</span><span class="sxs-lookup"><span data-stu-id="cd55e-246">The following table contains a list of the value types in the **System** namespace that are boxed representations of primitive types.</span></span>  
  
|<span data-ttu-id="cd55e-247">Systemwerttyp</span><span class="sxs-lookup"><span data-stu-id="cd55e-247">System value type</span></span>|<span data-ttu-id="cd55e-248">Elementtyp</span><span class="sxs-lookup"><span data-stu-id="cd55e-248">Element type</span></span>|  
|-----------------------|------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="cd55e-249">**ELEMENT_TYPE_BOOLEAN**</span><span class="sxs-lookup"><span data-stu-id="cd55e-249">**ELEMENT_TYPE_BOOLEAN**</span></span>|  
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="cd55e-250">**ELEMENT_TYPE_I1**</span><span class="sxs-lookup"><span data-stu-id="cd55e-250">**ELEMENT_TYPE_I1**</span></span>|  
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="cd55e-251">**ELEMENT_TYPE_UI1**</span><span class="sxs-lookup"><span data-stu-id="cd55e-251">**ELEMENT_TYPE_UI1**</span></span>|  
|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="cd55e-252">**ELEMENT_TYPE_CHAR**</span><span class="sxs-lookup"><span data-stu-id="cd55e-252">**ELEMENT_TYPE_CHAR**</span></span>|  
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="cd55e-253">**ELEMENT_TYPE_I2**</span><span class="sxs-lookup"><span data-stu-id="cd55e-253">**ELEMENT_TYPE_I2**</span></span>|  
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="cd55e-254">**ELEMENT_TYPE_U2**</span><span class="sxs-lookup"><span data-stu-id="cd55e-254">**ELEMENT_TYPE_U2**</span></span>|  
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="cd55e-255">**ELEMENT_TYPE_I4**</span><span class="sxs-lookup"><span data-stu-id="cd55e-255">**ELEMENT_TYPE_I4**</span></span>|  
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="cd55e-256">**ELEMENT_TYPE_U4**</span><span class="sxs-lookup"><span data-stu-id="cd55e-256">**ELEMENT_TYPE_U4**</span></span>|  
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="cd55e-257">**ELEMENT_TYPE_I8**</span><span class="sxs-lookup"><span data-stu-id="cd55e-257">**ELEMENT_TYPE_I8**</span></span>|  
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="cd55e-258">**ELEMENT_TYPE_U8**</span><span class="sxs-lookup"><span data-stu-id="cd55e-258">**ELEMENT_TYPE_U8**</span></span>|  
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="cd55e-259">**ELEMENT_TYPE_R4**</span><span class="sxs-lookup"><span data-stu-id="cd55e-259">**ELEMENT_TYPE_R4**</span></span>|  
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="cd55e-260">**ELEMENT_TYPE_R8**</span><span class="sxs-lookup"><span data-stu-id="cd55e-260">**ELEMENT_TYPE_R8**</span></span>|  
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="cd55e-261">**ELEMENT_TYPE_STRING**</span><span class="sxs-lookup"><span data-stu-id="cd55e-261">**ELEMENT_TYPE_STRING**</span></span>|  
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="cd55e-262">**ELEMENT_TYPE_I**</span><span class="sxs-lookup"><span data-stu-id="cd55e-262">**ELEMENT_TYPE_I**</span></span>|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="cd55e-263">**ELEMENT_TYPE_U**</span><span class="sxs-lookup"><span data-stu-id="cd55e-263">**ELEMENT_TYPE_U**</span></span>|  
  
 <span data-ttu-id="cd55e-264">Einige andere Werttypen im Namespace **System** werden anders verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="cd55e-264">Some other value types in the **System** namespace are handled differently.</span></span> <span data-ttu-id="cd55e-265">Da der nicht verwaltete Code bereits über gut eingeführte Formate für diese Typen verfügt, geht der Marshaller nach speziellen Regel beim Marshallen dieser Typen vor.</span><span class="sxs-lookup"><span data-stu-id="cd55e-265">Because the unmanaged code already has well-established formats for these types, the marshaler has special rules for marshaling them.</span></span> <span data-ttu-id="cd55e-266">Die folgende Tabelle führt die speziellen Werttypen im Namespace **System** sowie den nicht verwalteten Typ auf, an den sie gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="cd55e-266">The following table lists the special value types in the **System** namespace, as well as the unmanaged type they are marshaled to.</span></span>  
  
|<span data-ttu-id="cd55e-267">Systemwerttyp</span><span class="sxs-lookup"><span data-stu-id="cd55e-267">System value type</span></span>|<span data-ttu-id="cd55e-268">IDL-Typ</span><span class="sxs-lookup"><span data-stu-id="cd55e-268">IDL type</span></span>|  
|-----------------------|--------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="cd55e-269">**Datum**</span><span class="sxs-lookup"><span data-stu-id="cd55e-269">**DATE**</span></span>|  
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="cd55e-270">**Decimal**</span><span class="sxs-lookup"><span data-stu-id="cd55e-270">**DECIMAL**</span></span>|  
|<xref:System.Guid?displayProperty=nameWithType>|<span data-ttu-id="cd55e-271">**Guid**</span><span class="sxs-lookup"><span data-stu-id="cd55e-271">**GUID**</span></span>|  
|<xref:System.Drawing.Color?displayProperty=nameWithType>|<span data-ttu-id="cd55e-272">**OLE_COLOR**</span><span class="sxs-lookup"><span data-stu-id="cd55e-272">**OLE_COLOR**</span></span>|  
  
 <span data-ttu-id="cd55e-273">Der folgende Code zeigt die Definition der nicht verwalteten Typen **DATE**, **GUID**, **DECIMAL** und **OLE_COLOR** in der Stdole2-Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="cd55e-273">The following code shows the definition of the unmanaged types **DATE**, **GUID**, **DECIMAL**, and **OLE_COLOR** in the Stdole2 type library.</span></span>  
  
#### <a name="type-library-representation"></a><span data-ttu-id="cd55e-274">Darstellung der Typbibliothek</span><span class="sxs-lookup"><span data-stu-id="cd55e-274">Type library representation</span></span>  
  
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
  
 <span data-ttu-id="cd55e-275">Der folgende Code zeigt die entsprechenden Definitionen in der verwalteten `IValueTypes`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="cd55e-275">The following code shows the corresponding definitions in the managed `IValueTypes` interface.</span></span>  
  
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
  
#### <a name="type-library-representation"></a><span data-ttu-id="cd55e-276">Darstellung der Typbibliothek</span><span class="sxs-lookup"><span data-stu-id="cd55e-276">Type library representation</span></span>  
  
```cpp  
[…]  
interface IValueTypes : IDispatch {  
   HRESULT M1([in] DATE d);  
   HRESULT M2([in] GUID d);  
   HRESULT M3([in] DECIMAL d);  
   HRESULT M4([in] OLE_COLOR d);  
};  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd55e-277">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd55e-277">See also</span></span>

- [<span data-ttu-id="cd55e-278">Blitfähige und nicht blitfähige Typen</span><span class="sxs-lookup"><span data-stu-id="cd55e-278">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- [<span data-ttu-id="cd55e-279">Kopieren und Fixieren</span><span class="sxs-lookup"><span data-stu-id="cd55e-279">Copying and Pinning</span></span>](copying-and-pinning.md)
- [<span data-ttu-id="cd55e-280">Standardmäßiges Marshalling für Arrays</span><span class="sxs-lookup"><span data-stu-id="cd55e-280">Default Marshaling for Arrays</span></span>](default-marshaling-for-arrays.md)
- [<span data-ttu-id="cd55e-281">Standardmäßiges Marshalling für Objekte</span><span class="sxs-lookup"><span data-stu-id="cd55e-281">Default Marshaling for Objects</span></span>](default-marshaling-for-objects.md)
- [<span data-ttu-id="cd55e-282">Standardmäßiges Marshalling für Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="cd55e-282">Default Marshaling for Strings</span></span>](default-marshaling-for-strings.md)
