---
title: Blitfähige und nicht blitfähige Typen
ms.date: 03/30/2017
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b4c1d213c2ed87126fc5eb9995050e14f9214bd
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155339"
---
# <a name="blittable-and-non-blittable-types"></a><span data-ttu-id="2f568-102">Blitfähige und nicht blitfähige Typen</span><span class="sxs-lookup"><span data-stu-id="2f568-102">Blittable and Non-Blittable Types</span></span>
<span data-ttu-id="2f568-103">Die meisten Datentypen verfügen über eine allgemeine Darstellung in verwaltetem und unverwaltetem Speicher und erfordern keine besondere Behandlung durch den Interop-Marshaller.</span><span class="sxs-lookup"><span data-stu-id="2f568-103">Most data types have a common representation in both managed and unmanaged memory and do not require special handling by the interop marshaler.</span></span> <span data-ttu-id="2f568-104">Diese Typen werden *blitfähige Typen* genannt, da keine Konvertierung erforderlich ist, wenn sie zwischen verwaltetem und nicht verwaltetem Code übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="2f568-104">These types are called *blittable types* because they do not require conversion when they are passed between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="2f568-105">Strukturen, die von Plattformaufrufen zurückgegeben werden, müssen blitfähige Typen sein.</span><span class="sxs-lookup"><span data-stu-id="2f568-105">Structures that are returned from platform invoke calls must be blittable types.</span></span> <span data-ttu-id="2f568-106">Der Plattformaufruf unterstützt keine nicht blitfähigen Strukturen als Rückgabetypen.</span><span class="sxs-lookup"><span data-stu-id="2f568-106">Platform invoke does not support non-blittable structures as return types.</span></span>  
  
 <span data-ttu-id="2f568-107">Die folgenden Typen aus dem <xref:System>-Namespace sind blitfähige Typen:</span><span class="sxs-lookup"><span data-stu-id="2f568-107">The following types from the <xref:System> namespace are blittable types:</span></span>  
  
-   <xref:System.Byte?displayProperty=nameWithType>  
  
-   <xref:System.SByte?displayProperty=nameWithType>  
  
-   <xref:System.Int16?displayProperty=nameWithType>  
  
-   <xref:System.UInt16?displayProperty=nameWithType>  
  
-   <xref:System.Int32?displayProperty=nameWithType>  
  
-   <xref:System.UInt32?displayProperty=nameWithType>  
  
-   <xref:System.Int64?displayProperty=nameWithType>  
  
-   <xref:System.UInt64?displayProperty=nameWithType>  
  
-   <xref:System.IntPtr?displayProperty=nameWithType>  
  
-   <xref:System.UIntPtr?displayProperty=nameWithType>  
  
-   <xref:System.Single?displayProperty=nameWithType>  
  
-   <xref:System.Double?displayProperty=nameWithType>  
  
 <span data-ttu-id="2f568-108">Die folgenden komplexen Typen sind ebenfalls blitfähige Typen:</span><span class="sxs-lookup"><span data-stu-id="2f568-108">The following complex types are also blittable types:</span></span>  
  
-   <span data-ttu-id="2f568-109">Eindimensionale Arrays von blitfähigen Typen, z.B. ein Array von Integern.</span><span class="sxs-lookup"><span data-stu-id="2f568-109">One-dimensional arrays of blittable types, such as an array of integers.</span></span> <span data-ttu-id="2f568-110">Ein Typ, der ein Variablenarray von blitfähigen Typen enthält, ist jedoch nicht selbst blitfähig.</span><span class="sxs-lookup"><span data-stu-id="2f568-110">However, a type that contains a variable array of blittable types is not itself blittable.</span></span>  
  
-   <span data-ttu-id="2f568-111">Formatierte Werttypen, die ausschließlich blitfähige Typen (oder Klassen, wenn sie als formatierte Typen gemarshallt werden) enthalten.</span><span class="sxs-lookup"><span data-stu-id="2f568-111">Formatted value types that contain only blittable types (and classes if they are marshaled as formatted types).</span></span> <span data-ttu-id="2f568-112">Weitere Informationen zu formatierten Werttypen finden Sie unter [Standardmäßiges Marshalling für Werttypen](https://msdn.microsoft.com/library/4d9a876c-e05a-40ba-bd85-bd22877f984a(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="2f568-112">For more information about formatted value types, see [Default Marshaling for Value Types](https://msdn.microsoft.com/library/4d9a876c-e05a-40ba-bd85-bd22877f984a(v=vs.100)).</span></span>  
  
 <span data-ttu-id="2f568-113">Objektverweise sind nicht für Blitvorgänge geeignet.</span><span class="sxs-lookup"><span data-stu-id="2f568-113">Object references are not blittable.</span></span> <span data-ttu-id="2f568-114">Dies schließt ein Array von Verweisen auf Objekte ein, die selbst für Blitting geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="2f568-114">This includes an array of references to objects that are blittable by themselves.</span></span> <span data-ttu-id="2f568-115">Beispielsweise können Sie eine Struktur definieren, die für Blitting geeignet ist, jedoch keine blitfähigen Typen, die ein Array von Verweisen auf diese Strukturen enthält.</span><span class="sxs-lookup"><span data-stu-id="2f568-115">For example, you can define a structure that is blittable, but you cannot define a blittable type that contains an array of references to those structures.</span></span>  
  
 <span data-ttu-id="2f568-116">Zur Optimierung werden Arrays von blitfähigen Typen und Klassen, die nur für Blitting geeignete Member enthalten, während des Marshalling [angeheftet](../../../docs/framework/interop/copying-and-pinning.md) und nicht kopiert.</span><span class="sxs-lookup"><span data-stu-id="2f568-116">As an optimization, arrays of blittable types and classes that contain only blittable members are [pinned](../../../docs/framework/interop/copying-and-pinning.md) instead of copied during marshaling.</span></span> <span data-ttu-id="2f568-117">Es kann so wirken, als ob diese Typen als In/Out-Parameter gemarshallt werden, wenn der Aufrufer und der Aufgerufene im selben Apartment sind.</span><span class="sxs-lookup"><span data-stu-id="2f568-117">These types can appear to be marshaled as In/Out parameters when the caller and callee are in the same apartment.</span></span> <span data-ttu-id="2f568-118">Allerdings werden diese Typen tatsächlich als In-Parameter gemarshallt, und Sie müssen die <xref:System.Runtime.InteropServices.InAttribute>- und <xref:System.Runtime.InteropServices.OutAttribute>-Attribute anwenden, wenn Sie das Argument als In/Out-Parameter gemarshallt haben möchten.</span><span class="sxs-lookup"><span data-stu-id="2f568-118">However, these types are actually marshaled as In parameters, and you must apply the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes if you want to marshal the argument as an In/Out parameter.</span></span>  
  
 <span data-ttu-id="2f568-119">Einige verwaltete Datentypen erfordern eine andere Darstellung in einer nicht verwalteten Umgebung.</span><span class="sxs-lookup"><span data-stu-id="2f568-119">Some managed data types require a different representation in an unmanaged environment.</span></span> <span data-ttu-id="2f568-120">Diese nicht blitfähigen Datentypen müssen in ein Format konvertiert werden, das gemarshallt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2f568-120">These non-blittable data types must be converted into a form that can be marshaled.</span></span> <span data-ttu-id="2f568-121">Beispielsweise sind verwaltete Zeichenfolgen nicht blitfähige Typen, da sie in Zeichenfolgenobjekte konvertiert werden müssen, bevor sie gemarshallt werden können.</span><span class="sxs-lookup"><span data-stu-id="2f568-121">For example, managed strings are non-blittable types because they must be converted into string objects before they can be marshaled.</span></span>  
  
 <span data-ttu-id="2f568-122">Die folgende Tabelle listet nicht blitfähige Typen aus dem <xref:System>-Namespace auf.</span><span class="sxs-lookup"><span data-stu-id="2f568-122">The following table lists non-blittable types from the <xref:System> namespace.</span></span> <span data-ttu-id="2f568-123">[Delegaten](https://msdn.microsoft.com/library/d176ee76-f982-494b-b03d-92e4118896e2(v=vs.100)) sind Datenstrukturen, die auf eine statische Methode oder auf eine Klasseninstanz verweisen, und sind nicht blitfähig.</span><span class="sxs-lookup"><span data-stu-id="2f568-123">[Delegates](https://msdn.microsoft.com/library/d176ee76-f982-494b-b03d-92e4118896e2(v=vs.100)), which are data structures that refer to a static method or to a class instance, are also non-blittable.</span></span>  
  
|<span data-ttu-id="2f568-124">Nicht blitfähiger Typ</span><span class="sxs-lookup"><span data-stu-id="2f568-124">Non-blittable type</span></span>|<span data-ttu-id="2f568-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f568-125">Description</span></span>|  
|-------------------------|-----------------|  
|[<span data-ttu-id="2f568-126">System.Array</span><span class="sxs-lookup"><span data-stu-id="2f568-126">System.Array</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="2f568-127">Konvertiert in ein Array im C-Format oder ein `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="2f568-127">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|<span data-ttu-id="2f568-128">[System.Boolean](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2f568-128">[System.Boolean](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))</span></span>|<span data-ttu-id="2f568-129">Konvertiert in einen 1-, 2- oder 4-Byte-Wert mit `true` als 1 oder -1.</span><span class="sxs-lookup"><span data-stu-id="2f568-129">Converts to a 1, 2, or 4-byte value with `true` as 1 or -1.</span></span>|  
|<span data-ttu-id="2f568-130">[System.Char](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2f568-130">[System.Char](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))</span></span>|<span data-ttu-id="2f568-131">Konvertiert in ein Unicode- oder ANSI-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2f568-131">Converts to a Unicode or ANSI character.</span></span>|  
|<span data-ttu-id="2f568-132">[System.Class](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2f568-132">[System.Class](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))</span></span>|<span data-ttu-id="2f568-133">Konvertiert in eine Klassenschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2f568-133">Converts to a class interface.</span></span>|  
|[<span data-ttu-id="2f568-134">System.Object</span><span class="sxs-lookup"><span data-stu-id="2f568-134">System.Object</span></span>](../../../docs/framework/interop/default-marshaling-for-objects.md)|<span data-ttu-id="2f568-135">Konvertiert in eine Variante oder eine Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2f568-135">Converts to a variant or an interface.</span></span>|  
|[<span data-ttu-id="2f568-136">System.Mdarray</span><span class="sxs-lookup"><span data-stu-id="2f568-136">System.Mdarray</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="2f568-137">Konvertiert in ein Array im C-Format oder ein `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="2f568-137">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|[<span data-ttu-id="2f568-138">System.String</span><span class="sxs-lookup"><span data-stu-id="2f568-138">System.String</span></span>](../../../docs/framework/interop/default-marshaling-for-strings.md)|<span data-ttu-id="2f568-139">Konvertiert in eine Zeichenfolge, die in einem NULL-Verweis oder in einem BSTR endet.</span><span class="sxs-lookup"><span data-stu-id="2f568-139">Converts to a string terminating in a null reference or to a BSTR.</span></span>|  
|<span data-ttu-id="2f568-140">[System.Valuetype](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2f568-140">[System.Valuetype](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))</span></span>|<span data-ttu-id="2f568-141">Konvertiert in eine Struktur mit einem festen Speicherlayout.</span><span class="sxs-lookup"><span data-stu-id="2f568-141">Converts to a structure with a fixed memory layout.</span></span>|  
|[<span data-ttu-id="2f568-142">System.Szarray</span><span class="sxs-lookup"><span data-stu-id="2f568-142">System.Szarray</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="2f568-143">Konvertiert in ein Array im C-Format oder ein `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="2f568-143">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
  
 <span data-ttu-id="2f568-144">Klassen und Objekttypen werden nur von COM-Interop unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2f568-144">Class and object types are supported only by COM interop.</span></span> <span data-ttu-id="2f568-145">Informationen zu den entsprechenden Typen in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# und C++ finden Sie unter [Übersicht über die Klassenbibliothek](../../../docs/standard/class-library-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2f568-145">For corresponding types in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++, see the [Class Library Overview](../../../docs/standard/class-library-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f568-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f568-146">See Also</span></span>  
 [<span data-ttu-id="2f568-147">Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)</span><span class="sxs-lookup"><span data-stu-id="2f568-147">Default Marshaling Behavior</span></span>](../../../docs/framework/interop/default-marshaling-behavior.md)
