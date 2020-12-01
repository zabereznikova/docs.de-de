---
title: Für Blitting geeignete und nicht geeignete Typen
description: Erfahren Sie mehr zu für Blitting geeignete und nicht geeignete Typen. Für Blitting geeignete Datentypen werden üblicherweise in verwaltetem und nicht verwaltetem Speicher dargestellt und benötigen keine besondere Behandlung.
ms.date: 03/30/2017
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
ms.openlocfilehash: 5f0f6b2f35c184b4df8c93af1c85e7169cb0cc95
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283145"
---
# <a name="blittable-and-non-blittable-types"></a><span data-ttu-id="f828f-104">Für Blitting geeignete und nicht geeignete Typen</span><span class="sxs-lookup"><span data-stu-id="f828f-104">Blittable and Non-Blittable Types</span></span>

<span data-ttu-id="f828f-105">Die meisten Datentypen verfügen über eine allgemeine Darstellung in verwaltetem und unverwaltetem Speicher und erfordern keine besondere Behandlung durch den Interop-Marshaller.</span><span class="sxs-lookup"><span data-stu-id="f828f-105">Most data types have a common representation in both managed and unmanaged memory and do not require special handling by the interop marshaler.</span></span> <span data-ttu-id="f828f-106">Diese Typen werden *blitfähige Typen* genannt, da keine Konvertierung erforderlich ist, wenn sie zwischen verwaltetem und nicht verwaltetem Code übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="f828f-106">These types are called *blittable types* because they do not require conversion when they are passed between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="f828f-107">Strukturen, die von Plattformaufrufen zurückgegeben werden, müssen blitfähige Typen sein.</span><span class="sxs-lookup"><span data-stu-id="f828f-107">Structures that are returned from platform invoke calls must be blittable types.</span></span> <span data-ttu-id="f828f-108">Der Plattformaufruf unterstützt keine nicht blitfähigen Strukturen als Rückgabetypen.</span><span class="sxs-lookup"><span data-stu-id="f828f-108">Platform invoke does not support non-blittable structures as return types.</span></span>  
  
 <span data-ttu-id="f828f-109">Die folgenden Typen aus dem <xref:System>-Namespace sind blitfähige Typen:</span><span class="sxs-lookup"><span data-stu-id="f828f-109">The following types from the <xref:System> namespace are blittable types:</span></span>  
  
- <xref:System.Byte?displayProperty=nameWithType>  
  
- <xref:System.SByte?displayProperty=nameWithType>  
  
- <xref:System.Int16?displayProperty=nameWithType>  
  
- <xref:System.UInt16?displayProperty=nameWithType>  
  
- <xref:System.Int32?displayProperty=nameWithType>  
  
- <xref:System.UInt32?displayProperty=nameWithType>  
  
- <xref:System.Int64?displayProperty=nameWithType>  
  
- <xref:System.UInt64?displayProperty=nameWithType>  
  
- <xref:System.IntPtr?displayProperty=nameWithType>  
  
- <xref:System.UIntPtr?displayProperty=nameWithType>  
  
- <xref:System.Single?displayProperty=nameWithType>  
  
- <xref:System.Double?displayProperty=nameWithType>  
  
 <span data-ttu-id="f828f-110">Die folgenden komplexen Typen sind ebenfalls blitfähige Typen:</span><span class="sxs-lookup"><span data-stu-id="f828f-110">The following complex types are also blittable types:</span></span>  
  
- <span data-ttu-id="f828f-111">Eindimensionale Arrays von blitfähigen Typen, z.B. ein Array von Integern.</span><span class="sxs-lookup"><span data-stu-id="f828f-111">One-dimensional arrays of blittable types, such as an array of integers.</span></span> <span data-ttu-id="f828f-112">Ein Typ, der ein Variablenarray von blitfähigen Typen enthält, ist jedoch nicht selbst blitfähig.</span><span class="sxs-lookup"><span data-stu-id="f828f-112">However, a type that contains a variable array of blittable types is not itself blittable.</span></span>  
  
- <span data-ttu-id="f828f-113">Formatierte Werttypen, die ausschließlich blitfähige Typen (oder Klassen, wenn sie als formatierte Typen gemarshallt werden) enthalten.</span><span class="sxs-lookup"><span data-stu-id="f828f-113">Formatted value types that contain only blittable types (and classes if they are marshaled as formatted types).</span></span> <span data-ttu-id="f828f-114">Weitere Informationen zu formatierten Werttypen finden Sie unter [Standardmäßiges Marshalling für Werttypen](default-marshaling-behavior.md#default-marshaling-for-value-types).</span><span class="sxs-lookup"><span data-stu-id="f828f-114">For more information about formatted value types, see [Default marshaling for value types](default-marshaling-behavior.md#default-marshaling-for-value-types).</span></span>  
  
 <span data-ttu-id="f828f-115">Objektverweise sind nicht für Blitvorgänge geeignet.</span><span class="sxs-lookup"><span data-stu-id="f828f-115">Object references are not blittable.</span></span> <span data-ttu-id="f828f-116">Dies schließt ein Array von Verweisen auf Objekte ein, die selbst für Blitting geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="f828f-116">This includes an array of references to objects that are blittable by themselves.</span></span> <span data-ttu-id="f828f-117">Beispielsweise können Sie eine Struktur definieren, die für Blitting geeignet ist, jedoch keine blitfähigen Typen, die ein Array von Verweisen auf diese Strukturen enthält.</span><span class="sxs-lookup"><span data-stu-id="f828f-117">For example, you can define a structure that is blittable, but you cannot define a blittable type that contains an array of references to those structures.</span></span>  
  
 <span data-ttu-id="f828f-118">Zur Optimierung werden Arrays von blitfähigen Typen und Klassen, die nur für Blitting geeignete Member enthalten, während des Marshalling [angeheftet](copying-and-pinning.md) und nicht kopiert.</span><span class="sxs-lookup"><span data-stu-id="f828f-118">As an optimization, arrays of blittable types and classes that contain only blittable members are [pinned](copying-and-pinning.md) instead of copied during marshaling.</span></span> <span data-ttu-id="f828f-119">Es kann so wirken, als ob diese Typen als In/Out-Parameter gemarshallt werden, wenn der Aufrufer und der Aufgerufene im selben Apartment sind.</span><span class="sxs-lookup"><span data-stu-id="f828f-119">These types can appear to be marshaled as In/Out parameters when the caller and callee are in the same apartment.</span></span> <span data-ttu-id="f828f-120">Allerdings werden diese Typen tatsächlich als In-Parameter gemarshallt, und Sie müssen die <xref:System.Runtime.InteropServices.InAttribute>- und <xref:System.Runtime.InteropServices.OutAttribute>-Attribute anwenden, wenn Sie das Argument als In/Out-Parameter gemarshallt haben möchten.</span><span class="sxs-lookup"><span data-stu-id="f828f-120">However, these types are actually marshaled as In parameters, and you must apply the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes if you want to marshal the argument as an In/Out parameter.</span></span>  
  
 <span data-ttu-id="f828f-121">Einige verwaltete Datentypen erfordern eine andere Darstellung in einer nicht verwalteten Umgebung.</span><span class="sxs-lookup"><span data-stu-id="f828f-121">Some managed data types require a different representation in an unmanaged environment.</span></span> <span data-ttu-id="f828f-122">Diese nicht blitfähigen Datentypen müssen in ein Format konvertiert werden, das gemarshallt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f828f-122">These non-blittable data types must be converted into a form that can be marshaled.</span></span> <span data-ttu-id="f828f-123">Beispielsweise sind verwaltete Zeichenfolgen nicht blitfähige Typen, da sie in Zeichenfolgenobjekte konvertiert werden müssen, bevor sie gemarshallt werden können.</span><span class="sxs-lookup"><span data-stu-id="f828f-123">For example, managed strings are non-blittable types because they must be converted into string objects before they can be marshaled.</span></span>  
  
 <span data-ttu-id="f828f-124">Die folgende Tabelle listet nicht blitfähige Typen aus dem <xref:System>-Namespace auf.</span><span class="sxs-lookup"><span data-stu-id="f828f-124">The following table lists non-blittable types from the <xref:System> namespace.</span></span> <span data-ttu-id="f828f-125">[Delegaten](default-marshaling-behavior.md#default-marshaling-for-delegates) sind Datenstrukturen, die auf eine statische Methode oder auf eine Klasseninstanz verweisen, und sind nicht blitfähig.</span><span class="sxs-lookup"><span data-stu-id="f828f-125">[Delegates](default-marshaling-behavior.md#default-marshaling-for-delegates), which are data structures that refer to a static method or to a class instance, are also non-blittable.</span></span>  
  
|<span data-ttu-id="f828f-126">Nicht blitfähiger Typ</span><span class="sxs-lookup"><span data-stu-id="f828f-126">Non-blittable type</span></span>|<span data-ttu-id="f828f-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f828f-127">Description</span></span>|  
|-------------------------|-----------------|  
|[<span data-ttu-id="f828f-128">System.Array</span><span class="sxs-lookup"><span data-stu-id="f828f-128">System.Array</span></span>](default-marshaling-for-arrays.md)|<span data-ttu-id="f828f-129">Konvertiert in ein Array im C-Format oder ein `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="f828f-129">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|<span data-ttu-id="f828f-130">[System.Boolean](/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f828f-130">[System.Boolean](/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))</span></span>|<span data-ttu-id="f828f-131">Konvertiert in einen 1-, 2- oder 4-Byte-Wert mit `true` als 1 oder -1.</span><span class="sxs-lookup"><span data-stu-id="f828f-131">Converts to a 1, 2, or 4-byte value with `true` as 1 or -1.</span></span>|  
|<span data-ttu-id="f828f-132">[System.Char](/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f828f-132">[System.Char](/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))</span></span>|<span data-ttu-id="f828f-133">Konvertiert in ein Unicode- oder ANSI-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f828f-133">Converts to a Unicode or ANSI character.</span></span>|  
|<span data-ttu-id="f828f-134">[System.Class](/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f828f-134">[System.Class](/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))</span></span>|<span data-ttu-id="f828f-135">Konvertiert in eine Klassenschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f828f-135">Converts to a class interface.</span></span>|  
|[<span data-ttu-id="f828f-136">System.Object</span><span class="sxs-lookup"><span data-stu-id="f828f-136">System.Object</span></span>](default-marshaling-for-objects.md)|<span data-ttu-id="f828f-137">Konvertiert in eine Variante oder eine Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f828f-137">Converts to a variant or an interface.</span></span>|  
|[<span data-ttu-id="f828f-138">System.Mdarray</span><span class="sxs-lookup"><span data-stu-id="f828f-138">System.Mdarray</span></span>](default-marshaling-for-arrays.md)|<span data-ttu-id="f828f-139">Konvertiert in ein Array im C-Format oder ein `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="f828f-139">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|[<span data-ttu-id="f828f-140">System.String</span><span class="sxs-lookup"><span data-stu-id="f828f-140">System.String</span></span>](default-marshaling-for-strings.md)|<span data-ttu-id="f828f-141">Konvertiert in eine Zeichenfolge, die in einem NULL-Verweis oder in einem BSTR endet.</span><span class="sxs-lookup"><span data-stu-id="f828f-141">Converts to a string terminating in a null reference or to a BSTR.</span></span>|  
|<span data-ttu-id="f828f-142">[System.Valuetype](/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f828f-142">[System.Valuetype](/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))</span></span>|<span data-ttu-id="f828f-143">Konvertiert in eine Struktur mit einem festen Speicherlayout.</span><span class="sxs-lookup"><span data-stu-id="f828f-143">Converts to a structure with a fixed memory layout.</span></span>|  
|[<span data-ttu-id="f828f-144">System.Szarray</span><span class="sxs-lookup"><span data-stu-id="f828f-144">System.Szarray</span></span>](default-marshaling-for-arrays.md)|<span data-ttu-id="f828f-145">Konvertiert in ein Array im C-Format oder ein `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="f828f-145">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
  
 <span data-ttu-id="f828f-146">Klassen und Objekttypen werden nur von COM-Interop unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f828f-146">Class and object types are supported only by COM interop.</span></span> <span data-ttu-id="f828f-147">Informationen zu den entsprechenden Typen in Visual Basic, C# und C++ finden Sie unter [Übersicht über die Klassenbibliothek](../../standard/class-library-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f828f-147">For corresponding types in Visual Basic, C#, and C++, see the [Class Library Overview](../../standard/class-library-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f828f-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f828f-148">See also</span></span>

- [<span data-ttu-id="f828f-149">Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)</span><span class="sxs-lookup"><span data-stu-id="f828f-149">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
