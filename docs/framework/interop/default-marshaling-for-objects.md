---
title: Standardmäßiges Marshalling für Objekte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- objects, interop marshaling
- interop marshaling, objects
ms.assetid: c2ef0284-b061-4e12-b6d3-6a502b9cc558
ms.openlocfilehash: e0de715a3ed33eedf212fc3e0e9930c9cbaa0a38
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123590"
---
# <a name="default-marshaling-for-objects"></a><span data-ttu-id="5eac7-102">Standardmäßiges Marshalling für Objekte</span><span class="sxs-lookup"><span data-stu-id="5eac7-102">Default Marshaling for Objects</span></span>

<span data-ttu-id="5eac7-103">Parameter und Felder, die als <xref:System.Object?displayProperty=nameWithType> typisiert sind, können für nicht verwalteten Code als einer der folgenden Typen verfügbar gemacht werden:</span><span class="sxs-lookup"><span data-stu-id="5eac7-103">Parameters and fields typed as <xref:System.Object?displayProperty=nameWithType> can be exposed to unmanaged code as one of the following types:</span></span>

- <span data-ttu-id="5eac7-104">Als Variante, wenn das Objekt ein Parameter ist.</span><span class="sxs-lookup"><span data-stu-id="5eac7-104">A variant when the object is a parameter.</span></span>

- <span data-ttu-id="5eac7-105">Als Schnittstelle, wenn das Objekt ein Strukturfeld ist.</span><span class="sxs-lookup"><span data-stu-id="5eac7-105">An interface when the object is a structure field.</span></span>

<span data-ttu-id="5eac7-106">Nur COM-Interop unterstützt das Marshallen von Objekttypen.</span><span class="sxs-lookup"><span data-stu-id="5eac7-106">Only COM interop supports marshaling for object types.</span></span> <span data-ttu-id="5eac7-107">Standardmäßig werden Objekte an COM-Varianten gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-107">The default behavior is to marshal objects to COM variants.</span></span> <span data-ttu-id="5eac7-108">Diese Regeln gelten nur für den Typ **Objekt** und gelten nicht für stark typisierte Objekte, die von der **Objekt**-Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="5eac7-108">These rules apply only to the type **Object** and do not apply to strongly typed objects that derive from the **Object** class.</span></span>

## <a name="marshaling-options"></a><span data-ttu-id="5eac7-109">Marshallingoptionen</span><span class="sxs-lookup"><span data-stu-id="5eac7-109">Marshaling Options</span></span>

<span data-ttu-id="5eac7-110">Die folgende Tabelle zeigt die Marshalling-Optionen für den **Objekt**-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="5eac7-110">The following table shows the marshaling options for the **Object** data type.</span></span> <span data-ttu-id="5eac7-111">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Objekten bereit.</span><span class="sxs-lookup"><span data-stu-id="5eac7-111">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal objects.</span></span>

|<span data-ttu-id="5eac7-112">Enumerationstyp</span><span class="sxs-lookup"><span data-stu-id="5eac7-112">Enumeration type</span></span>|<span data-ttu-id="5eac7-113">Beschreibung des nicht verwalteten Formats</span><span class="sxs-lookup"><span data-stu-id="5eac7-113">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|<span data-ttu-id="5eac7-114">**UnmanagedType.Struct**</span><span class="sxs-lookup"><span data-stu-id="5eac7-114">**UnmanagedType.Struct**</span></span><br /><br /> <span data-ttu-id="5eac7-115">(Standard für Parameter)</span><span class="sxs-lookup"><span data-stu-id="5eac7-115">(default for parameters)</span></span>|<span data-ttu-id="5eac7-116">Eine Variante im COM-Stil.</span><span class="sxs-lookup"><span data-stu-id="5eac7-116">A COM-style variant.</span></span>|
|<span data-ttu-id="5eac7-117">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="5eac7-117">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="5eac7-118">Eine **IDispatch**-Schnittstelle, wenn möglich, andernfalls eine **IUnknown**-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5eac7-118">An **IDispatch** interface, if possible; otherwise, an **IUnknown** interface.</span></span>|
|<span data-ttu-id="5eac7-119">**UnmanagedType.IUnknown**</span><span class="sxs-lookup"><span data-stu-id="5eac7-119">**UnmanagedType.IUnknown**</span></span><br /><br /> <span data-ttu-id="5eac7-120">(Standard für Felder)</span><span class="sxs-lookup"><span data-stu-id="5eac7-120">(default for fields)</span></span>|<span data-ttu-id="5eac7-121">Eine **IUnknown**-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5eac7-121">An **IUnknown** interface.</span></span>|
|<span data-ttu-id="5eac7-122">**UnmanagedType.IDispatch**</span><span class="sxs-lookup"><span data-stu-id="5eac7-122">**UnmanagedType.IDispatch**</span></span>|<span data-ttu-id="5eac7-123">Eine **IDispatch**-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5eac7-123">An **IDispatch** interface.</span></span>|

<span data-ttu-id="5eac7-124">Das folgende Beispiel zeigt die verwaltete Schnittstellendefinition für `MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="5eac7-124">The following example shows the managed interface definition for `MarshalObject`.</span></span>

```vb
Interface MarshalObject
   Sub SetVariant(o As Object)
   Sub SetVariantRef(ByRef o As Object)
   Function GetVariant() As Object

   Sub SetIDispatch( <MarshalAs(UnmanagedType.IDispatch)> o As Object)
   Sub SetIDispatchRef(ByRef <MarshalAs(UnmanagedType.IDispatch)> o _
      As Object)
   Function GetIDispatch() As <MarshalAs(UnmanagedType.IDispatch)> Object
   Sub SetIUnknown( <MarshalAs(UnmanagedType.IUnknown)> o As Object)
   Sub SetIUnknownRef(ByRef <MarshalAs(UnmanagedType.IUnknown)> o _
      As Object)
   Function GetIUnknown() As <MarshalAs(UnmanagedType.IUnknown)> Object
End Interface
```

```csharp
interface MarshalObject {
   void SetVariant(Object o);
   void SetVariantRef(ref Object o);
   Object GetVariant();

   void SetIDispatch ([MarshalAs(UnmanagedType.IDispatch)]Object o);
   void SetIDispatchRef([MarshalAs(UnmanagedType.IDispatch)]ref Object o);
   [MarshalAs(UnmanagedType.IDispatch)] Object GetIDispatch();
   void SetIUnknown ([MarshalAs(UnmanagedType.IUnknown)]Object o);
   void SetIUnknownRef([MarshalAs(UnmanagedType.IUnknown)]ref Object o);
   [MarshalAs(UnmanagedType.IUnknown)] Object GetIUnknown();
}
```

<span data-ttu-id="5eac7-125">Der folgende Code exportiert die `MarshalObject` Schnittstelle in eine Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="5eac7-125">The following code exports the `MarshalObject` interface to a type library.</span></span>

```cpp
interface MarshalObject {
   HRESULT SetVariant([in] VARIANT o);
   HRESULT SetVariantRef([in,out] VARIANT *o);
   HRESULT GetVariant([out,retval] VARIANT *o)
   HRESULT SetIDispatch([in] IDispatch *o);
   HRESULT SetIDispatchRef([in,out] IDispatch **o);
   HRESULT GetIDispatch([out,retval] IDispatch **o)
   HRESULT SetIUnknown([in] IUnknown *o);
   HRESULT SetIUnknownRef([in,out] IUnknown **o);
   HRESULT GetIUnknown([out,retval] IUnknown **o)
}
```

> [!NOTE]
> <span data-ttu-id="5eac7-126">Der Interop-Marshaller gibt nach dem Aufruf automatisch alle zugeordneten Objekte innerhalb der Variante frei.</span><span class="sxs-lookup"><span data-stu-id="5eac7-126">The interop marshaler automatically frees any allocated object inside the variant after the call.</span></span>

<span data-ttu-id="5eac7-127">Das folgende Beispiel zeigt einen formatierten Werttypen.</span><span class="sxs-lookup"><span data-stu-id="5eac7-127">The following example shows a formatted value type.</span></span>

```vb
Public Structure ObjectHolder
   Dim o1 As Object
   <MarshalAs(UnmanagedType.IDispatch)> Public o2 As Object
End Structure
```

```csharp
public struct ObjectHolder {
   Object o1;
   [MarshalAs(UnmanagedType.IDispatch)]public Object o2;
}
```

<span data-ttu-id="5eac7-128">Der folgende Code exportiert den formatierten Typ in eine Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="5eac7-128">The following code exports the formatted type to a type library.</span></span>

```cpp
struct ObjectHolder {
   VARIANT o1;
   IDispatch *o2;
}
```

## <a name="marshaling-object-to-interface"></a><span data-ttu-id="5eac7-129">Marshalling eines Objekts an eine Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5eac7-129">Marshaling Object to Interface</span></span>

<span data-ttu-id="5eac7-130">Wenn ein Objekt in COM als Schnittstelle verfügbar gemacht wird, ist diese Schnittstelle die Klassenschnittstelle für den verwalteten Typ <xref:System.Object> (die **_Object**-Schnittstelle).</span><span class="sxs-lookup"><span data-stu-id="5eac7-130">When an object is exposed to COM as an interface, that interface is the class interface for the managed type <xref:System.Object> (the **_Object** interface).</span></span> <span data-ttu-id="5eac7-131">Diese Schnittstelle wird als **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) oder als **IUnknown** (**UnmanagedType.IUnknown**) in der resultierenden Typbibliothek typisiert.</span><span class="sxs-lookup"><span data-stu-id="5eac7-131">This interface is typed as an **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) or an **IUnknown** (**UnmanagedType.IUnknown**) in the resulting type library.</span></span> <span data-ttu-id="5eac7-132">COM-Clients können die Mitglieder der verwalteten Klasse, oder irgendwelche Mitglieder, die durch die abgeleiteten Klassen über die **_Object**-Schnittstelle implementiert wurden dynamisch abrufen.</span><span class="sxs-lookup"><span data-stu-id="5eac7-132">COM clients can dynamically invoke the members of the managed class or any members implemented by its derived classes through the **_Object** interface.</span></span> <span data-ttu-id="5eac7-133">Der Client kann auch **QueryInterface** aufrufen, um irgendeine andere Schnittstelle zu erhalten, die vom verwalteten Typ explizit implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5eac7-133">The client can also call **QueryInterface** to obtain any other interface explicitly implemented by the managed type.</span></span>

## <a name="marshaling-object-to-variant"></a><span data-ttu-id="5eac7-134">Marshalling eines Objekts an eine Variante</span><span class="sxs-lookup"><span data-stu-id="5eac7-134">Marshaling Object to Variant</span></span>

<span data-ttu-id="5eac7-135">Wenn ein Objekt an eine Variante gemarshallt wird, wird der interne Varianttyp zur Laufzeit anhand der folgenden Regeln bestimmt:</span><span class="sxs-lookup"><span data-stu-id="5eac7-135">When an object is marshaled to a variant, the internal variant type is determined at run time, based on the following rules:</span></span>

- <span data-ttu-id="5eac7-136">Wenn der Objektverweis NULL ist (**Nothing** (nichts) in Visual Basic), wird das Objekt an eine Variante des Typs **VT_EMPTY** gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-136">If the object reference is null (**Nothing** in Visual Basic), the object is marshaled to a variant of type **VT_EMPTY**.</span></span>

- <span data-ttu-id="5eac7-137">Wenn das Objekt eine Instanz eines beliebigen Typs ist, die in der folgenden Tabelle aufgeführt ist, wird der resultierende Varianttyp durch die im Marshaller integrierten und in der Tabelle aufgeführten Regeln bestimmt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-137">If the object is an instance of any type listed in the following table, the resulting variant type is determined by the rules built into the marshaler and shown in the table.</span></span>

- <span data-ttu-id="5eac7-138">Andere Objekte, die das Marshalling-Verhalten explizit steuern müssen, können die <xref:System.IConvertible>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="5eac7-138">Other objects that need to explicitly control the marshaling behavior can implement the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="5eac7-139">In diesem Fall wird der Varianttyp durch den Typcode bestimmt, der von der <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5eac7-139">In that case, the variant type is determined by the type code returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5eac7-140">Andernfalls wird das Objekt als eine Variante des Typs **VT_UNKNOWN** gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-140">Otherwise, the object is marshaled as a variant of type **VT_UNKNOWN**.</span></span>

### <a name="marshaling-system-types-to-variant"></a><span data-ttu-id="5eac7-141">Marshalling von Systemtypen an Varianten</span><span class="sxs-lookup"><span data-stu-id="5eac7-141">Marshaling System Types to Variant</span></span>

<span data-ttu-id="5eac7-142">Die folgende Tabelle zeigt verwaltete Objekttypen und ihre entsprechenden COM-Varianttypen.</span><span class="sxs-lookup"><span data-stu-id="5eac7-142">The following table shows managed object types and their corresponding COM variant types.</span></span> <span data-ttu-id="5eac7-143">Diese Typen werden nur konvertiert, wenn die Signatur der aufgerufenen Methode vom Typ <xref:System.Object?displayProperty=nameWithType> ist.</span><span class="sxs-lookup"><span data-stu-id="5eac7-143">These types are converted only when the signature of the method being called is of type <xref:System.Object?displayProperty=nameWithType>.</span></span>

|<span data-ttu-id="5eac7-144">Objekttyp</span><span class="sxs-lookup"><span data-stu-id="5eac7-144">Object type</span></span>|<span data-ttu-id="5eac7-145">COM-Varianttyp</span><span class="sxs-lookup"><span data-stu-id="5eac7-145">COM variant type</span></span>|
|-----------------|----------------------|
|<span data-ttu-id="5eac7-146">NULL-Objektverweis (**Nothing** (nichts) in Visual&#160;Basic).</span><span class="sxs-lookup"><span data-stu-id="5eac7-146">Null object reference (**Nothing** in Visual Basic).</span></span>|<span data-ttu-id="5eac7-147">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="5eac7-147">**VT_EMPTY**</span></span>|
|<xref:System.DBNull?displayProperty=nameWithType>|<span data-ttu-id="5eac7-148">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="5eac7-148">**VT_NULL**</span></span>|
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|<span data-ttu-id="5eac7-149">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="5eac7-149">**VT_ERROR**</span></span>|
|<xref:System.Reflection.Missing?displayProperty=nameWithType>|<span data-ttu-id="5eac7-150">**VT_ERROR** mit **E_PARAMNOTFOUND**</span><span class="sxs-lookup"><span data-stu-id="5eac7-150">**VT_ERROR** with **E_PARAMNOTFOUND**</span></span>|
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|<span data-ttu-id="5eac7-151">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="5eac7-151">**VT_DISPATCH**</span></span>|
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|<span data-ttu-id="5eac7-152">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="5eac7-152">**VT_UNKNOWN**</span></span>|
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|<span data-ttu-id="5eac7-153">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="5eac7-153">**VT_CY**</span></span>|
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="5eac7-154">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="5eac7-154">**VT_BOOL**</span></span>|
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="5eac7-155">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="5eac7-155">**VT_I1**</span></span>|
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="5eac7-156">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="5eac7-156">**VT_UI1**</span></span>|
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="5eac7-157">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="5eac7-157">**VT_I2**</span></span>|
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="5eac7-158">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="5eac7-158">**VT_UI2**</span></span>|
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="5eac7-159">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="5eac7-159">**VT_I4**</span></span>|
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="5eac7-160">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="5eac7-160">**VT_UI4**</span></span>|
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="5eac7-161">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="5eac7-161">**VT_I8**</span></span>|
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="5eac7-162">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="5eac7-162">**VT_UI8**</span></span>|
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="5eac7-163">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="5eac7-163">**VT_R4**</span></span>|
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="5eac7-164">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="5eac7-164">**VT_R8**</span></span>|
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="5eac7-165">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="5eac7-165">**VT_DECIMAL**</span></span>|
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="5eac7-166">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="5eac7-166">**VT_DATE**</span></span>|
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="5eac7-167">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="5eac7-167">**VT_BSTR**</span></span>|
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="5eac7-168">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="5eac7-168">**VT_INT**</span></span>|
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="5eac7-169">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="5eac7-169">**VT_UINT**</span></span>|
|<xref:System.Array?displayProperty=nameWithType>|<span data-ttu-id="5eac7-170">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="5eac7-170">**VT_ARRAY**</span></span>|

<span data-ttu-id="5eac7-171">Mithilfe der im vorherigen Beispiel definierten `MarshalObject`-Schnittstelle, veranschaulicht das folgende Codebeispiel, wie unterschiedliche Varianttypen an einen COM-Server übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="5eac7-171">Using the `MarshalObject` interface defined in the previous example, the following code example demonstrates how to pass various types of variants to a COM server.</span></span>

```vb
Dim mo As New MarshalObject()
mo.SetVariant(Nothing)         ' Marshal as variant of type VT_EMPTY.
mo.SetVariant(System.DBNull.Value) ' Marshal as variant of type VT_NULL.
mo.SetVariant(CInt(27))        ' Marshal as variant of type VT_I2.
mo.SetVariant(CLng(27))        ' Marshal as variant of type VT_I4.
mo.SetVariant(CSng(27.0))      ' Marshal as variant of type VT_R4.
mo.SetVariant(CDbl(27.0))      ' Marshal as variant of type VT_R8.
```

```csharp
MarshalObject mo = new MarshalObject();
mo.SetVariant(null);            // Marshal as variant of type VT_EMPTY.
mo.SetVariant(System.DBNull.Value); // Marshal as variant of type VT_NULL.
mo.SetVariant((int)27);          // Marshal as variant of type VT_I2.
mo.SetVariant((long)27);          // Marshal as variant of type VT_I4.
mo.SetVariant((single)27.0);   // Marshal as variant of type VT_R4.
mo.SetVariant((double)27.0);   // Marshal as variant of type VT_R8.
```

<span data-ttu-id="5eac7-172">COM-Typen, die keine entsprechenden verwalteten Typen aufweisen, können mithilfe von Wrapperklassen, z.B. <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, und <xref:System.Runtime.InteropServices.CurrencyWrapper> gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="5eac7-172">COM types that do not have corresponding managed types can be marshaled using wrapper classes such as <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, and <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span></span> <span data-ttu-id="5eac7-173">Das folgende Codebeispiel veranschaulicht, wie diese unterschiedlichen Wrapper verwendet werden, um verschiedene Varianttypen an einen COM-Server zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="5eac7-173">The following code example demonstrates how to use these wrappers to pass various types of variants to a COM server.</span></span>

```vb
Imports System.Runtime.InteropServices
' Pass inew as a variant of type VT_UNKNOWN interface.
mo.SetVariant(New UnknownWrapper(inew))
' Pass inew as a variant of type VT_DISPATCH interface.
mo.SetVariant(New DispatchWrapper(inew))
' Pass a value as a variant of type VT_ERROR interface.
mo.SetVariant(New ErrorWrapper(&H80054002))
' Pass a value as a variant of type VT_CURRENCY interface.
mo.SetVariant(New CurrencyWrapper(New Decimal(5.25)))
```

```csharp
using System.Runtime.InteropServices;
// Pass inew as a variant of type VT_UNKNOWN interface.
mo.SetVariant(new UnknownWrapper(inew));
// Pass inew as a variant of type VT_DISPATCH interface.
mo.SetVariant(new DispatchWrapper(inew));
// Pass a value as a variant of type VT_ERROR interface.
mo.SetVariant(new ErrorWrapper(0x80054002));
// Pass a value as a variant of type VT_CURRENCY interface.
mo.SetVariant(new CurrencyWrapper(new Decimal(5.25)));
```

<span data-ttu-id="5eac7-174">Die Wrapperklassen werden im <xref:System.Runtime.InteropServices>-Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="5eac7-174">The wrapper classes are defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>

### <a name="marshaling-the-iconvertible-interface-to-variant"></a><span data-ttu-id="5eac7-175">Marshalling der IConvertible-Schnittstelle an eine Variante</span><span class="sxs-lookup"><span data-stu-id="5eac7-175">Marshaling the IConvertible Interface to Variant</span></span>

<span data-ttu-id="5eac7-176">Typen, die im vorherigen Abschnitt nicht aufgeführt werden, können durch Implementierung der <xref:System.IConvertible>-Schnittstelle steuern, wie sie gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="5eac7-176">Types other than those listed in the previous section can control how they are marshaled by implementing the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="5eac7-177">Wenn das Objekt die **IConvertible**-Schnittstelle implementiert, wird der COM-Varianttyp zur Laufzeit durch den Wert der durch die <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>-Methode zurückgegeben <xref:System.TypeCode>-Enumeration bestimmt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-177">If the object implements the **IConvertible** interface, the COM variant type is determined at run time by the value of the <xref:System.TypeCode> enumeration returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="5eac7-178">Die folgende Tabelle zeigt die möglichen Werte für die **TypeCode**-Enumeration und die entsprechenden COM-Varianttypen für jeden Wert.</span><span class="sxs-lookup"><span data-stu-id="5eac7-178">The following table shows the possible values for the **TypeCode** enumeration and the corresponding COM variant type for each value.</span></span>

|<span data-ttu-id="5eac7-179">TypeCode</span><span class="sxs-lookup"><span data-stu-id="5eac7-179">TypeCode</span></span>|<span data-ttu-id="5eac7-180">COM-Varianttyp</span><span class="sxs-lookup"><span data-stu-id="5eac7-180">COM variant type</span></span>|
|--------------|----------------------|
|<span data-ttu-id="5eac7-181">**TypeCode.Empty**</span><span class="sxs-lookup"><span data-stu-id="5eac7-181">**TypeCode.Empty**</span></span>|<span data-ttu-id="5eac7-182">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="5eac7-182">**VT_EMPTY**</span></span>|
|<span data-ttu-id="5eac7-183">**TypeCode.Object**</span><span class="sxs-lookup"><span data-stu-id="5eac7-183">**TypeCode.Object**</span></span>|<span data-ttu-id="5eac7-184">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="5eac7-184">**VT_UNKNOWN**</span></span>|
|<span data-ttu-id="5eac7-185">**TypeCode.DBNULL**</span><span class="sxs-lookup"><span data-stu-id="5eac7-185">**TypeCode.DBNull**</span></span>|<span data-ttu-id="5eac7-186">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="5eac7-186">**VT_NULL**</span></span>|
|<span data-ttu-id="5eac7-187">**TypeCode.Boolean**</span><span class="sxs-lookup"><span data-stu-id="5eac7-187">**TypeCode.Boolean**</span></span>|<span data-ttu-id="5eac7-188">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="5eac7-188">**VT_BOOL**</span></span>|
|<span data-ttu-id="5eac7-189">**TypeCode.Char**</span><span class="sxs-lookup"><span data-stu-id="5eac7-189">**TypeCode.Char**</span></span>|<span data-ttu-id="5eac7-190">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="5eac7-190">**VT_UI2**</span></span>|
|<span data-ttu-id="5eac7-191">**TypeCode.Sbyte**</span><span class="sxs-lookup"><span data-stu-id="5eac7-191">**TypeCode.Sbyte**</span></span>|<span data-ttu-id="5eac7-192">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="5eac7-192">**VT_I1**</span></span>|
|<span data-ttu-id="5eac7-193">**TypeCode.Byte**</span><span class="sxs-lookup"><span data-stu-id="5eac7-193">**TypeCode.Byte**</span></span>|<span data-ttu-id="5eac7-194">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="5eac7-194">**VT_UI1**</span></span>|
|<span data-ttu-id="5eac7-195">**TypeCode.Int16**</span><span class="sxs-lookup"><span data-stu-id="5eac7-195">**TypeCode.Int16**</span></span>|<span data-ttu-id="5eac7-196">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="5eac7-196">**VT_I2**</span></span>|
|<span data-ttu-id="5eac7-197">**TypeCode.UInt16**</span><span class="sxs-lookup"><span data-stu-id="5eac7-197">**TypeCode.UInt16**</span></span>|<span data-ttu-id="5eac7-198">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="5eac7-198">**VT_UI2**</span></span>|
|<span data-ttu-id="5eac7-199">**TypeCode.Int32**</span><span class="sxs-lookup"><span data-stu-id="5eac7-199">**TypeCode.Int32**</span></span>|<span data-ttu-id="5eac7-200">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="5eac7-200">**VT_I4**</span></span>|
|<span data-ttu-id="5eac7-201">**TypeCode.UInt32**</span><span class="sxs-lookup"><span data-stu-id="5eac7-201">**TypeCode.UInt32**</span></span>|<span data-ttu-id="5eac7-202">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="5eac7-202">**VT_UI4**</span></span>|
|<span data-ttu-id="5eac7-203">**TypeCode.Int64**</span><span class="sxs-lookup"><span data-stu-id="5eac7-203">**TypeCode.Int64**</span></span>|<span data-ttu-id="5eac7-204">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="5eac7-204">**VT_I8**</span></span>|
|<span data-ttu-id="5eac7-205">**TypeCode.UInt64**</span><span class="sxs-lookup"><span data-stu-id="5eac7-205">**TypeCode.UInt64**</span></span>|<span data-ttu-id="5eac7-206">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="5eac7-206">**VT_UI8**</span></span>|
|<span data-ttu-id="5eac7-207">**TypeCode.Single**</span><span class="sxs-lookup"><span data-stu-id="5eac7-207">**TypeCode.Single**</span></span>|<span data-ttu-id="5eac7-208">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="5eac7-208">**VT_R4**</span></span>|
|<span data-ttu-id="5eac7-209">**TypeCode.Double**</span><span class="sxs-lookup"><span data-stu-id="5eac7-209">**TypeCode.Double**</span></span>|<span data-ttu-id="5eac7-210">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="5eac7-210">**VT_R8**</span></span>|
|<span data-ttu-id="5eac7-211">**TypeCode.Decimal**</span><span class="sxs-lookup"><span data-stu-id="5eac7-211">**TypeCode.Decimal**</span></span>|<span data-ttu-id="5eac7-212">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="5eac7-212">**VT_DECIMAL**</span></span>|
|<span data-ttu-id="5eac7-213">**TypeCode.DateTime**</span><span class="sxs-lookup"><span data-stu-id="5eac7-213">**TypeCode.DateTime**</span></span>|<span data-ttu-id="5eac7-214">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="5eac7-214">**VT_DATE**</span></span>|
|<span data-ttu-id="5eac7-215">**TypeCode.String**</span><span class="sxs-lookup"><span data-stu-id="5eac7-215">**TypeCode.String**</span></span>|<span data-ttu-id="5eac7-216">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="5eac7-216">**VT_BSTR**</span></span>|
|<span data-ttu-id="5eac7-217">Wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-217">Not supported.</span></span>|<span data-ttu-id="5eac7-218">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="5eac7-218">**VT_INT**</span></span>|
|<span data-ttu-id="5eac7-219">Wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-219">Not supported.</span></span>|<span data-ttu-id="5eac7-220">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="5eac7-220">**VT_UINT**</span></span>|
|<span data-ttu-id="5eac7-221">Wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-221">Not supported.</span></span>|<span data-ttu-id="5eac7-222">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="5eac7-222">**VT_ARRAY**</span></span>|
|<span data-ttu-id="5eac7-223">Wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-223">Not supported.</span></span>|<span data-ttu-id="5eac7-224">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="5eac7-224">**VT_RECORD**</span></span>|
|<span data-ttu-id="5eac7-225">Wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-225">Not supported.</span></span>|<span data-ttu-id="5eac7-226">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="5eac7-226">**VT_CY**</span></span>|
|<span data-ttu-id="5eac7-227">Wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-227">Not supported.</span></span>|<span data-ttu-id="5eac7-228">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="5eac7-228">**VT_VARIANT**</span></span>|

<span data-ttu-id="5eac7-229">Der Wert der COM-Variante wird durch Aufruf der **IConvertible.To** *Type*-Schnittstelle bestimmt, wobei **To** *Type* die Konvertierungsroutine ist, die dem Typ entspricht, der von **IConvertible.GetTypeCode** zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="5eac7-229">The value of the COM variant is determined by calling the **IConvertible.To** *Type* interface, where **To** *Type* is the conversion routine that corresponds to the type that was returned from **IConvertible.GetTypeCode**.</span></span> <span data-ttu-id="5eac7-230">Beispielsweise ist ein Objekt, das **TypeCode.Double** aus **IConvertible.GetTypeCode** zurückgibt, als COM-Variante des Typs **VT_R8** gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-230">For example, an object that returns **TypeCode.Double** from **IConvertible.GetTypeCode** is marshaled as a COM variant of type **VT_R8**.</span></span> <span data-ttu-id="5eac7-231">Sie erhalten den Wert der Variante (gespeichert im **DblVal**-Feld der COM-Variante), indem Sie eine Umwandlung in die **IConvertible**-Schnittstelle durchführen und die <xref:System.IConvertible.ToDouble%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5eac7-231">You can obtain the value of the variant (stored in the **dblVal** field of the COM variant) by casting to the **IConvertible** interface and calling the <xref:System.IConvertible.ToDouble%2A> method.</span></span>

## <a name="marshaling-variant-to-object"></a><span data-ttu-id="5eac7-232">Marshalling einer Variante an ein Objekt</span><span class="sxs-lookup"><span data-stu-id="5eac7-232">Marshaling Variant to Object</span></span>

<span data-ttu-id="5eac7-233">Beim Marshallen einer Variante an ein Objekt bestimmt der Typ und in einigen Fällen der Wert der gemarshallten Variante den Typ des erstellten Objekts.</span><span class="sxs-lookup"><span data-stu-id="5eac7-233">When marshaling a variant to an object, the type, and sometimes the value, of the marshaled variant determines the type of object produced.</span></span> <span data-ttu-id="5eac7-234">In der folgenden Tabelle sind die einzelnen Varianttypen und die entsprechenden Objekttypen aufgelistet, die der Marshaller erstellt, wenn eine Variante aus COM an .NET Framework übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5eac7-234">The following table identifies each variant type and the corresponding object type that the marshaler creates when a variant is passed from COM to the .NET Framework.</span></span>

|<span data-ttu-id="5eac7-235">COM-Varianttyp</span><span class="sxs-lookup"><span data-stu-id="5eac7-235">COM variant type</span></span>|<span data-ttu-id="5eac7-236">Objekttyp</span><span class="sxs-lookup"><span data-stu-id="5eac7-236">Object type</span></span>|
|----------------------|-----------------|
|<span data-ttu-id="5eac7-237">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="5eac7-237">**VT_EMPTY**</span></span>|<span data-ttu-id="5eac7-238">NULL-Objektverweis (**Nothing** (nichts) in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="5eac7-238">Null object reference (**Nothing** in Visual Basic).</span></span>|
|<span data-ttu-id="5eac7-239">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="5eac7-239">**VT_NULL**</span></span>|<xref:System.DBNull?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-240">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="5eac7-240">**VT_DISPATCH**</span></span>|<span data-ttu-id="5eac7-241">**System.__ComObject** oder NULL wenn (pdispVal == NULL)</span><span class="sxs-lookup"><span data-stu-id="5eac7-241">**System.__ComObject** or null if (pdispVal == null)</span></span>|
|<span data-ttu-id="5eac7-242">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="5eac7-242">**VT_UNKNOWN**</span></span>|<span data-ttu-id="5eac7-243">**System.__ComObject** oder NULL wenn (punkVal == NULL)</span><span class="sxs-lookup"><span data-stu-id="5eac7-243">**System.__ComObject** or null if (punkVal == null)</span></span>|
|<span data-ttu-id="5eac7-244">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="5eac7-244">**VT_ERROR**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-245">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="5eac7-245">**VT_BOOL**</span></span>|<xref:System.Boolean?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-246">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="5eac7-246">**VT_I1**</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-247">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="5eac7-247">**VT_UI1**</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-248">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="5eac7-248">**VT_I2**</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-249">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="5eac7-249">**VT_UI2**</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-250">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="5eac7-250">**VT_I4**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-251">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="5eac7-251">**VT_UI4**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-252">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="5eac7-252">**VT_I8**</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-253">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="5eac7-253">**VT_UI8**</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-254">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="5eac7-254">**VT_R4**</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-255">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="5eac7-255">**VT_R8**</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-256">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="5eac7-256">**VT_DECIMAL**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-257">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="5eac7-257">**VT_DATE**</span></span>|<xref:System.DateTime?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-258">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="5eac7-258">**VT_BSTR**</span></span>|<xref:System.String?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-259">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="5eac7-259">**VT_INT**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-260">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="5eac7-260">**VT_UINT**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-261">**VT_ARRAY** &#124; **VT_** \*</span><span class="sxs-lookup"><span data-stu-id="5eac7-261">**VT_ARRAY** &#124; **VT_**\*</span></span>|<xref:System.Array?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-262">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="5eac7-262">**VT_CY**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|
|<span data-ttu-id="5eac7-263">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="5eac7-263">**VT_RECORD**</span></span>|<span data-ttu-id="5eac7-264">Entsprechender geschachtelter Werttyp.</span><span class="sxs-lookup"><span data-stu-id="5eac7-264">Corresponding boxed value type.</span></span>|
|<span data-ttu-id="5eac7-265">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="5eac7-265">**VT_VARIANT**</span></span>|<span data-ttu-id="5eac7-266">Wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-266">Not supported.</span></span>|

<span data-ttu-id="5eac7-267">Varianttypen aus COM, die an verwalteten Code übergeben und dann an COM zurückgegeben werden, behalten für die Dauer des Aufrufs möglicherweise nicht denselben Varianttypen bei.</span><span class="sxs-lookup"><span data-stu-id="5eac7-267">Variant types passed from COM to managed code and then back to COM might not retain the same variant type for the duration of the call.</span></span> <span data-ttu-id="5eac7-268">Beachten Sie, was geschieht, wenn eine Variante des Typs **VT_DISPATCH** von COM an .NET Framework übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5eac7-268">Consider what happens when a variant of type **VT_DISPATCH** is passed from COM to the .NET Framework.</span></span> <span data-ttu-id="5eac7-269">Während des Marshallens wird die Variante in ein <xref:System.Object?displayProperty=nameWithType> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5eac7-269">During marshaling, the variant is converted to a <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5eac7-270">Wenn das **Objekt** dann an COM übergeben wird, wird es wieder auf eine Variante des Typs **VT_UNKNOWN** gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-270">If the **Object** is then passed back to COM, it is marshaled back to a variant of type **VT_UNKNOWN**.</span></span> <span data-ttu-id="5eac7-271">Es gibt keine Garantie dafür, dass die erzeugte Variante, wenn ein Objekt an COM aus verwaltetem Code gemarshallt wird vom selben Typ ist, wie die ursprünglich zur Erstellung des Objekts verwendete Variante.</span><span class="sxs-lookup"><span data-stu-id="5eac7-271">There is no guarantee that the variant produced when an object is marshaled from managed code to COM will be the same type as the variant initially used to produce the object.</span></span>

## <a name="marshaling-byref-variants"></a><span data-ttu-id="5eac7-272">Marshalling von ByRef-Varianten</span><span class="sxs-lookup"><span data-stu-id="5eac7-272">Marshaling ByRef Variants</span></span>

<span data-ttu-id="5eac7-273">Obwohl Varianten selbst durch einen Wert oder durch einen Verweis übergeben werden können, kann das **VT_BYREF**-Flag auch mit einem beliebigen Varianttyp verwendet werden, um anzugeben, dass die Inhalte der Variante durch Verweis und nicht durch einen Wert übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="5eac7-273">Although variants themselves can be passed by value or by reference, the **VT_BYREF** flag can also be used with any variant type to indicate that the contents of the variant are being passed by reference instead of by value.</span></span> <span data-ttu-id="5eac7-274">Der Unterschied zwischen dem Marshalling von Varianten durch einen Verweis und dem Marshalling von Varianten mit eingerichtetem **VT_BYREF**-Flag kann verwirrend sein.</span><span class="sxs-lookup"><span data-stu-id="5eac7-274">The difference between marshaling variants by reference and marshaling a variant with the **VT_BYREF** flag set can be confusing.</span></span> <span data-ttu-id="5eac7-275">Die folgende Abbildung verdeutlicht die Unterschiede:</span><span class="sxs-lookup"><span data-stu-id="5eac7-275">The following illustration clarifies the differences:</span></span>

<span data-ttu-id="5eac7-276">![Diagramm einer an den Stapel übergebenen Variante](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)</span><span class="sxs-lookup"><span data-stu-id="5eac7-276">![Diagram that shows variant passed on the stack.](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)</span></span>
<span data-ttu-id="5eac7-277">Durch einen Wert und durch einen Verweis übergebene Varianten</span><span class="sxs-lookup"><span data-stu-id="5eac7-277">Variants passed by value and by reference</span></span>

<span data-ttu-id="5eac7-278">**Standardmäßiges Verhalten beim Marshalling von Objekten und Varianten durch einen Wert**</span><span class="sxs-lookup"><span data-stu-id="5eac7-278">**Default behavior for marshaling objects and variants by value**</span></span>

- <span data-ttu-id="5eac7-279">Wenn Objekte aus verwaltetem Code an COM übergeben werden, wird der Inhalt des Objekts in eine neue, vom Marshaller erstellte Variante kopiert, unter Verwendung der unter [Marshalling eines Objekts an eine Variante](#marshaling-object-to-variant) definierten Regeln.</span><span class="sxs-lookup"><span data-stu-id="5eac7-279">When passing objects from managed code to COM, the contents of the object are copied into a new variant created by the marshaler, using the rules defined in [Marshaling Object to Variant](#marshaling-object-to-variant).</span></span> <span data-ttu-id="5eac7-280">Die auf der nicht verwalteten Seite der Variante vorgenommenen Änderungen, werden bei Rückgabe aus dem Aufruf nicht auf das ursprüngliche Objekt zurückübertragen.</span><span class="sxs-lookup"><span data-stu-id="5eac7-280">Changes made to the variant on the unmanaged side are not propagated back to the original object on return from the call.</span></span>

- <span data-ttu-id="5eac7-281">Wenn Varianten von COM an verwalteten Code übergeben werden, wird der Inhalt der Variante in ein neu erstelltes Objekt kopiert, unter Verwendung der unter [Marshalling einer Variante an ein Objekt](#marshaling-variant-to-object) definierten Regeln.</span><span class="sxs-lookup"><span data-stu-id="5eac7-281">When passing variants from COM to managed code, the contents of the variant are copied to a newly created object, using the rules defined in [Marshaling Variant to Object](#marshaling-variant-to-object).</span></span> <span data-ttu-id="5eac7-282">Die auf der verwalteten Seite des Objekts vorgenommenen Änderungen, werden bei Rückgabe aus dem Aufruf nicht auf die ursprüngliche Variante zurückübertragen.</span><span class="sxs-lookup"><span data-stu-id="5eac7-282">Changes made to the object on the managed side are not propagated back to the original variant on return from the call.</span></span>

<span data-ttu-id="5eac7-283">**Standardverhalten für das Marshalling von Objekten und Varianten durch einen Verweis**</span><span class="sxs-lookup"><span data-stu-id="5eac7-283">**Default behavior for marshaling objects and variants by reference**</span></span>

<span data-ttu-id="5eac7-284">Um Änderungen an den Aufrufer weiterzugeben, müssen die Parameter durch einen Verweis übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="5eac7-284">To propagate changes back to the caller, the parameters must be passed by reference.</span></span> <span data-ttu-id="5eac7-285">Beispielsweise können Sie das **Ref**-Schlüsselwort in C# (oder **ByRef** in Visual Basic verwaltetem Code) zum Übergeben von Parametern durch einen Verweis verwenden.</span><span class="sxs-lookup"><span data-stu-id="5eac7-285">For example, you can use the **ref** keyword in C# (or **ByRef** in Visual Basic managed code) to pass parameters by reference.</span></span> <span data-ttu-id="5eac7-286">In COM werden Verweisparameter mithilfe eines Zeigers, z.B. als **Variante\*** übergeben.</span><span class="sxs-lookup"><span data-stu-id="5eac7-286">In COM, reference parameters are passed using a pointer such as a **variant \***.</span></span>

- <span data-ttu-id="5eac7-287">Wenn ein Objekt durch einen Verweis an COM übergeben wird, erstellt der Marshaller eine neue Variante und kopiert den Inhalt des Objektverweises in die Variante, bevor der Aufruf ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5eac7-287">When passing an object to COM by reference, the marshaler creates a new variant and copies the contents of the object reference into the variant before the call is made.</span></span> <span data-ttu-id="5eac7-288">Die Variante wird an die nicht verwaltete Funktion übergeben, in der der Benutzer den Inhalt der Variante nach Belieben ändern kann.</span><span class="sxs-lookup"><span data-stu-id="5eac7-288">The variant is passed to the unmanaged function where the user is free to change the contents of the variant.</span></span> <span data-ttu-id="5eac7-289">Die auf der nicht verwalteten Seite der Variante vorgenommenen Änderungen, werden bei Rückgabe aus dem Aufruf nicht auf das ursprüngliche Objekt zurückübertragen.</span><span class="sxs-lookup"><span data-stu-id="5eac7-289">On return from the call, any changes made to the variant on the unmanaged side are propagated back to the original object.</span></span> <span data-ttu-id="5eac7-290">Wenn der Typ der Variante vom Typ der an den Aufruf übergebenen Variante abweicht, werden die Änderungen auf ein Objekt eines anderen Typs zurückübertragen.</span><span class="sxs-lookup"><span data-stu-id="5eac7-290">If the type of the variant differs from the type of the variant passed to the call, then the changes are propagated back to an object of a different type.</span></span> <span data-ttu-id="5eac7-291">Das bedeutet, dass sich der Typ des an den Aufruf übergeben Objekts vom Typ des Objekts unterscheiden kann, der aus dem Aufruf zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="5eac7-291">That is, the type of the object passed into the call can differ from the type of the object returned from the call.</span></span>

- <span data-ttu-id="5eac7-292">Wenn eine Variante durch einen Verweis an verwalteten Code übergeben wird, erstellt der Marshaller ein neues Objekt, und kopiert den Inhalt der Variante in das Objekt, bevor der Aufruf ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5eac7-292">When passing a variant to managed code by reference, the marshaler creates a new object and copies the contents of the variant into the object before making the call.</span></span> <span data-ttu-id="5eac7-293">Ein Verweis auf das Objekt wird an die verwaltete Funktion übergeben, in der der Benutzer das Objekt nach Belieben ändern kann.</span><span class="sxs-lookup"><span data-stu-id="5eac7-293">A reference to the object is passed to the managed function, where the user is free to change the object.</span></span> <span data-ttu-id="5eac7-294">Die am referenzierten Objekt vorgenommenen Änderungen werden bei Rückgabe aus dem Aufruf auf die ursprüngliche Variante zurückübertragen.</span><span class="sxs-lookup"><span data-stu-id="5eac7-294">On return from the call, any changes made to the referenced object are propagated back to the original variant.</span></span> <span data-ttu-id="5eac7-295">Wenn sich der Typ des Objekts vom Typ des an den Aufruf übergebenen Objekts unterscheidet, wird der Typ der ursprünglichen Variante geändert, und der Wert wird wieder an die Variante zurückübertragen.</span><span class="sxs-lookup"><span data-stu-id="5eac7-295">If the type of the object differs from the type of the object passed in to the call, the type of the original variant is changed and the value is propagated back into the variant.</span></span> <span data-ttu-id="5eac7-296">Das bedeutet, dass sich der Typ der an den Aufruf übergebenen Variante vom Typ der durch den Aufruf zurückgegebenen Variante unterscheiden kann.</span><span class="sxs-lookup"><span data-stu-id="5eac7-296">Again, the type of the variant passed into the call can differ from the type of the variant returned from the call.</span></span>

 <span data-ttu-id="5eac7-297">**Standardverhalten für das Marshalling von Varianten mit eingerichtetem VT_BYREF-Flag**</span><span class="sxs-lookup"><span data-stu-id="5eac7-297">**Default behavior for marshaling a variant with the VT_BYREF flag set**</span></span>

- <span data-ttu-id="5eac7-298">Für eine durch einen Wert an verwalteten Code übergebene Variante, kann das **VT_BYREF**-Flag so festgelegt sein, dass angegeben wird, dass die Variante einen Verweis anstelle eines Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="5eac7-298">A variant being passed to managed code by value can have the **VT_BYREF** flag set to indicate that the variant contains a reference instead of a value.</span></span> <span data-ttu-id="5eac7-299">In diesem Fall wird die Variante noch auf ein Objekt gemarshallt, da die Variante als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5eac7-299">In this case, the variant is still marshaled to an object because the variant is being passed by value.</span></span> <span data-ttu-id="5eac7-300">Der Marshaller dereferenziert den Inhalt der Variante automatisch und kopiert sie vor der Ausführung des Aufrufs in ein neu erstelltes Objekt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-300">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="5eac7-301">Das Objekt wird dann in die verwaltete Funktion übergeben. Bei der Rückgabe aus dem Aufruf wird das Objekt jedoch nicht wieder in der ursprünglichen Variante zurückverteilt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-301">The object is then passed into the managed function; however, on return from the call, the object is not propagated back into the original variant.</span></span> <span data-ttu-id="5eac7-302">Am verwalteten Objekt vorgenommene Änderungen gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="5eac7-302">Changes made to the managed object are lost.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="5eac7-303">Es gibt keine Möglichkeit, den Wert einer Variante, die als Wert übergeben wurde zu ändern, selbst wenn für die Variante das **VT_BYREF**-Flag festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="5eac7-303">There is no way to change the value of a variant passed by value, even if the variant has the **VT_BYREF** flag set.</span></span>

- <span data-ttu-id="5eac7-304">Für eine durch einen Verweis an verwalteten Code übergebene Variante, kann das **VT_BYREF**-Flag so festgelegt sein, dass angegeben wird, dass die Variante einen weiteren Verweis enthält.</span><span class="sxs-lookup"><span data-stu-id="5eac7-304">A variant being passed to managed code by reference can also have the **VT_BYREF** flag set to indicate that the variant contains another reference.</span></span> <span data-ttu-id="5eac7-305">In diesem Fall wird die Variante noch auf ein **ref**-Objekt gemarshallt, da die Variante durch Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5eac7-305">If it does, the variant is marshaled to a **ref** object because the variant is being passed by reference.</span></span> <span data-ttu-id="5eac7-306">Der Marshaller dereferenziert den Inhalt der Variante automatisch und kopiert sie vor der Ausführung des Aufrufs in ein neu erstelltes Objekt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-306">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="5eac7-307">Bei der Rückgabe des Aufrufs wird der Wert des Objekts zurück an den Verweis in der ursprünglichen Variante nur weitergegeben, wenn das Objekt demselben Typ angehört wie das übergebene Objekt.</span><span class="sxs-lookup"><span data-stu-id="5eac7-307">On return from the call, the value of the object is propagated back to the reference within the original variant only if the object is the same type as the object passed in.</span></span> <span data-ttu-id="5eac7-308">Durch die Weitergabe wird also der Typ einer Variante mit dem eingerichteten **VT_BYREF**-Flag ändert.</span><span class="sxs-lookup"><span data-stu-id="5eac7-308">That is, propagation does not change the type of a variant with the **VT_BYREF** flag set.</span></span> <span data-ttu-id="5eac7-309">Wenn der Objekttyp während des Aufrufs geändert wird, wird bei Rückgabe aus dem Aufruf eine <xref:System.InvalidCastException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5eac7-309">If the type of the object is changed during the call, an <xref:System.InvalidCastException> occurs on return from the call.</span></span>

<span data-ttu-id="5eac7-310">In der folgenden Tabelle werden die Regeln zur Weitergabe für Varianten und Objekte zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="5eac7-310">The following table summarizes the propagation rules for variants and objects.</span></span>

|<span data-ttu-id="5eac7-311">Von</span><span class="sxs-lookup"><span data-stu-id="5eac7-311">From</span></span>|<span data-ttu-id="5eac7-312">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5eac7-312">To</span></span>|<span data-ttu-id="5eac7-313">Zurückübertragene Änderungen</span><span class="sxs-lookup"><span data-stu-id="5eac7-313">Changes propagated back</span></span>|
|----------|--------|-----------------------------|
|<span data-ttu-id="5eac7-314">**Variant** *v*</span><span class="sxs-lookup"><span data-stu-id="5eac7-314">**Variant**  *v*</span></span>|<span data-ttu-id="5eac7-315">**Object** *o*</span><span class="sxs-lookup"><span data-stu-id="5eac7-315">**Object**  *o*</span></span>|<span data-ttu-id="5eac7-316">Nie</span><span class="sxs-lookup"><span data-stu-id="5eac7-316">Never</span></span>|
|<span data-ttu-id="5eac7-317">**Object** *o*</span><span class="sxs-lookup"><span data-stu-id="5eac7-317">**Object**  *o*</span></span>|<span data-ttu-id="5eac7-318">**Variant** *v*</span><span class="sxs-lookup"><span data-stu-id="5eac7-318">**Variant**  *v*</span></span>|<span data-ttu-id="5eac7-319">Nie</span><span class="sxs-lookup"><span data-stu-id="5eac7-319">Never</span></span>|
|<span data-ttu-id="5eac7-320">**Variant** ***\**** *pv*</span><span class="sxs-lookup"><span data-stu-id="5eac7-320">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="5eac7-321">**Ref Object** *o*</span><span class="sxs-lookup"><span data-stu-id="5eac7-321">**Ref Object**  *o*</span></span>|<span data-ttu-id="5eac7-322">Always</span><span class="sxs-lookup"><span data-stu-id="5eac7-322">Always</span></span>|
|<span data-ttu-id="5eac7-323">**Ref object** *o*</span><span class="sxs-lookup"><span data-stu-id="5eac7-323">**Ref object**  *o*</span></span>|<span data-ttu-id="5eac7-324">**Variant** ***\**** *pv*</span><span class="sxs-lookup"><span data-stu-id="5eac7-324">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="5eac7-325">Always</span><span class="sxs-lookup"><span data-stu-id="5eac7-325">Always</span></span>|
|<span data-ttu-id="5eac7-326">**Variant** *v* **(VT_BYREF** *&#124;* **VT_\*)**</span><span class="sxs-lookup"><span data-stu-id="5eac7-326">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span></span>|<span data-ttu-id="5eac7-327">**Object** *o*</span><span class="sxs-lookup"><span data-stu-id="5eac7-327">**Object**  *o*</span></span>|<span data-ttu-id="5eac7-328">Nie</span><span class="sxs-lookup"><span data-stu-id="5eac7-328">Never</span></span>|
|<span data-ttu-id="5eac7-329">**Variant** *v* **(VT_BYREF** *&#124;* **VT_)**</span><span class="sxs-lookup"><span data-stu-id="5eac7-329">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span></span>|<span data-ttu-id="5eac7-330">**Ref Object** *o*</span><span class="sxs-lookup"><span data-stu-id="5eac7-330">**Ref Object**  *o*</span></span>|<span data-ttu-id="5eac7-331">Nur, wenn sich der Typ nicht geändert hat.</span><span class="sxs-lookup"><span data-stu-id="5eac7-331">Only if the type has not changed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="5eac7-332">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5eac7-332">See also</span></span>

- [<span data-ttu-id="5eac7-333">Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)</span><span class="sxs-lookup"><span data-stu-id="5eac7-333">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="5eac7-334">Blitfähige und nicht blitfähige Typen</span><span class="sxs-lookup"><span data-stu-id="5eac7-334">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="5eac7-335">[Direktionale Attribute](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5eac7-335">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="5eac7-336">Kopieren und Fixieren</span><span class="sxs-lookup"><span data-stu-id="5eac7-336">Copying and Pinning</span></span>](copying-and-pinning.md)
