---
title: Standardmäßiges Marshalling für Arrays
description: Machen Sie sich mit dem standardmäßigen Marshalling für Arrays vertraut. Erfahren Sie mehr über verwaltete Arrays, nicht verwaltete Arrays, das Übergeben von Arrayparametern an .NET-Code und das Übergeben von Arrays an COM.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, arrays
- arrays, interop marshaling
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
ms.openlocfilehash: 6bfe95576a6460efac75fd392e24acf42e36f2de
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555262"
---
# <a name="default-marshaling-for-arrays"></a><span data-ttu-id="a4582-104">Standardmäßiges Marshalling für Arrays</span><span class="sxs-lookup"><span data-stu-id="a4582-104">Default Marshaling for Arrays</span></span>
<span data-ttu-id="a4582-105">In einer Anwendung, die vollständig aus verwaltetem Code besteht, übergibt die Common Language Runtime Arraytypen als In-/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="a4582-105">In an application consisting entirely of managed code, the common language runtime passes array types as In/Out parameters.</span></span> <span data-ttu-id="a4582-106">Im Gegensatz dazu übergibt der Interopmarshaller außerdem ein Array als In-Parameter in der Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="a4582-106">In contrast, the interop marshaler passes an array as In parameters by default.</span></span>  
  
 <span data-ttu-id="a4582-107">Bei der [pinning optimization](copying-and-pinning.md) (Fixierungsoptimierung),kann ein blitfähiges Array den Anschein erwecken, dass es als In/Out-Parameter fungiert, wenn es mit Objekten in demselben Apartment interagiert.</span><span class="sxs-lookup"><span data-stu-id="a4582-107">With [pinning optimization](copying-and-pinning.md), a blittable array can appear to operate as an In/Out parameter when interacting with objects in the same apartment.</span></span> <span data-ttu-id="a4582-108">Wenn Sie allerdings den Code später in eine Typbibliothek exportieren, mit der der computerübergreifende Proxy generiert wird, und diese Bibliothek dazu verwendet wird, Ihre Aufrufe über Apartments hinweg zu marshallen, können sich die Aufrufe wieder wie TRUE-Parameter verhalten.</span><span class="sxs-lookup"><span data-stu-id="a4582-108">However, if you later export the code to a type library used to generate the cross-machine proxy, and that library is used to marshal your calls across apartments, the calls can revert to true In parameter behavior.</span></span>  
  
 <span data-ttu-id="a4582-109">Arrays sind naturgemäß komplex, und die Unterschiede zwischen verwalteten und nicht verwalteten Arrays bieten mehr Informationen als andere nicht blitfähige Typen.</span><span class="sxs-lookup"><span data-stu-id="a4582-109">Arrays are complex by nature, and the distinctions between managed and unmanaged arrays warrant more information than other non-blittable types.</span></span>  
  
## <a name="managed-arrays"></a><span data-ttu-id="a4582-110">Verwaltete Arrays</span><span class="sxs-lookup"><span data-stu-id="a4582-110">Managed Arrays</span></span>  
 <span data-ttu-id="a4582-111">Verwaltete Arraytypen können variieren. Allerdings ist die <xref:System.Array?displayProperty=nameWithType>-Klasse die Basisklasse für alle Arraytypen.</span><span class="sxs-lookup"><span data-stu-id="a4582-111">Managed array types can vary; however, the <xref:System.Array?displayProperty=nameWithType> class is the base class of all array types.</span></span> <span data-ttu-id="a4582-112">Die **System.Array**-Klasse enthält Eigenschaften, um den Rang, die Länge und die Unter- und Obergrenze eines Arrays zu bestimmen, als auch Methoden zum Zugreifen, Sortieren, Durchsuchen, Kopieren und Erstellen von Arrays.</span><span class="sxs-lookup"><span data-stu-id="a4582-112">The **System.Array** class has properties for determining the rank, length, and lower and upper bounds of an array, as well as methods for accessing, sorting, searching, copying, and creating arrays.</span></span>  
  
 <span data-ttu-id="a4582-113">Diese Arraytypen sind dynamisch und verfügen über keinen entsprechenden statischen, in der Basisklassenbibliothek definierten Typen.</span><span class="sxs-lookup"><span data-stu-id="a4582-113">These array types are dynamic and do not have a corresponding static type defined in the base class library.</span></span> <span data-ttu-id="a4582-114">Es ist sinnvoll, jede Kombination aus Elementtyp und Rang als gesonderten Arraytypen zu betrachten.</span><span class="sxs-lookup"><span data-stu-id="a4582-114">It is convenient to think of each combination of element type and rank as a distinct type of array.</span></span> <span data-ttu-id="a4582-115">Deshalb unterscheidet sich ein eindimensionales Array von ganzen Zahlen von einem eindimensionalen Array von Double-Typen.</span><span class="sxs-lookup"><span data-stu-id="a4582-115">Therefore, a one-dimensional array of integers is of a different type than a one-dimensional array of double types.</span></span> <span data-ttu-id="a4582-116">In ähnlicher Weise unterscheidet sich ein zweidimensionales Array von ganzen Zahlen von einem eindimensionalen Array von ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="a4582-116">Similarly a two-dimensional array of integers is different from a one-dimensional array of integers.</span></span> <span data-ttu-id="a4582-117">Die Grenzen des Arrays werden beim Vergleichen von Typen nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="a4582-117">The bounds of the array are not considered when comparing types.</span></span>  
  
 <span data-ttu-id="a4582-118">Wie die folgende Tabelle zeigt, muss jede Instanz eines verwalteten Arrays über einen bestimmter Elementtyp, Rang und eine bestimmte Untergrenze verfügen.</span><span class="sxs-lookup"><span data-stu-id="a4582-118">As the following table shows, any instance of a managed array must be of a specific element type, rank, and lower bound.</span></span>  
  
|<span data-ttu-id="a4582-119">Verwalteter Arraytyp</span><span class="sxs-lookup"><span data-stu-id="a4582-119">Managed array type</span></span>|<span data-ttu-id="a4582-120">Elementtyp</span><span class="sxs-lookup"><span data-stu-id="a4582-120">Element type</span></span>|<span data-ttu-id="a4582-121">Rang</span><span class="sxs-lookup"><span data-stu-id="a4582-121">Rank</span></span>|<span data-ttu-id="a4582-122">Unterer Grenzwert</span><span class="sxs-lookup"><span data-stu-id="a4582-122">Lower bound</span></span>|<span data-ttu-id="a4582-123">Signaturschreibweise</span><span class="sxs-lookup"><span data-stu-id="a4582-123">Signature notation</span></span>|  
|------------------------|------------------|----------|-----------------|------------------------|  
|<span data-ttu-id="a4582-124">**ELEMENT_TYPE_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="a4582-124">**ELEMENT_TYPE_ARRAY**</span></span>|<span data-ttu-id="a4582-125">Durch den Typ angegeben.</span><span class="sxs-lookup"><span data-stu-id="a4582-125">Specified by type.</span></span>|<span data-ttu-id="a4582-126">Durch den Rang angegeben.</span><span class="sxs-lookup"><span data-stu-id="a4582-126">Specified by rank.</span></span>|<span data-ttu-id="a4582-127">Optional durch Grenzen angegeben.</span><span class="sxs-lookup"><span data-stu-id="a4582-127">Optionally specified by bounds.</span></span>|<span data-ttu-id="a4582-128">*Typ* **[** *n*,*m* **]**</span><span class="sxs-lookup"><span data-stu-id="a4582-128">*type* **[** *n*,*m* **]**</span></span>|  
|<span data-ttu-id="a4582-129">**ELEMENT_TYPE_CLASS**</span><span class="sxs-lookup"><span data-stu-id="a4582-129">**ELEMENT_TYPE_CLASS**</span></span>|<span data-ttu-id="a4582-130">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="a4582-130">Unknown</span></span>|<span data-ttu-id="a4582-131">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="a4582-131">Unknown</span></span>|<span data-ttu-id="a4582-132">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="a4582-132">Unknown</span></span>|<span data-ttu-id="a4582-133">**System.Array**</span><span class="sxs-lookup"><span data-stu-id="a4582-133">**System.Array**</span></span>|  
|<span data-ttu-id="a4582-134">**ELEMENT_TYPE_SZARRAY**</span><span class="sxs-lookup"><span data-stu-id="a4582-134">**ELEMENT_TYPE_SZARRAY**</span></span>|<span data-ttu-id="a4582-135">Durch den Typ angegeben.</span><span class="sxs-lookup"><span data-stu-id="a4582-135">Specified by type.</span></span>|<span data-ttu-id="a4582-136">1</span><span class="sxs-lookup"><span data-stu-id="a4582-136">1</span></span>|<span data-ttu-id="a4582-137">0</span><span class="sxs-lookup"><span data-stu-id="a4582-137">0</span></span>|<span data-ttu-id="a4582-138">*Typ* **[** *n* **]**</span><span class="sxs-lookup"><span data-stu-id="a4582-138">*type* **[** *n* **]**</span></span>|  
  
## <a name="unmanaged-arrays"></a><span data-ttu-id="a4582-139">Nicht verwaltete Arrays</span><span class="sxs-lookup"><span data-stu-id="a4582-139">Unmanaged Arrays</span></span>  
 <span data-ttu-id="a4582-140">Nicht verwaltete Arrays sind entweder sichere Arrays im COM-Stil oder Arrays im C-Stil mit fester oder variabler Länge.</span><span class="sxs-lookup"><span data-stu-id="a4582-140">Unmanaged arrays are either COM-style safe arrays or C-style arrays with fixed or variable length.</span></span> <span data-ttu-id="a4582-141">Sichere Arrays sind selbstbeschreibende Arrays, die den Typ, den Rang und die Grenzen der verknüpften Arraydaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4582-141">Safe arrays are self-describing arrays that carry the type, rank, and bounds of the associated array data.</span></span> <span data-ttu-id="a4582-142">Arrays im C-Stil sind eindimensionale typisierte Arrays mit einer festen Untergrenze von 0.</span><span class="sxs-lookup"><span data-stu-id="a4582-142">C-style arrays are one-dimensional typed arrays with a fixed lower bound of 0.</span></span> <span data-ttu-id="a4582-143">Der Marshallingdienst bietet nur eingeschränkt Unterstützung für beide Typen von Arrays.</span><span class="sxs-lookup"><span data-stu-id="a4582-143">The marshaling service has limited support for both types of arrays.</span></span>  
  
## <a name="passing-array-parameters-to-net-code"></a><span data-ttu-id="a4582-144">Übergeben von Arrayparametern an .NET-Code</span><span class="sxs-lookup"><span data-stu-id="a4582-144">Passing Array Parameters to .NET Code</span></span>  
 <span data-ttu-id="a4582-145">Arrays im C-Stil und sichere Arrays, können aus nicht verwaltetem Code an .NET-Code, als ein sicheres Array oder ein Array im C-Stil übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-145">Both C-style arrays and safe arrays can be passed to .NET code from unmanaged code as either a safe array or a C-style array.</span></span> <span data-ttu-id="a4582-146">Die folgende Tabelle zeigt den nicht verwalteten Typwert und den importierten Typ.</span><span class="sxs-lookup"><span data-stu-id="a4582-146">The following table shows the unmanaged type value and the imported type.</span></span>  
  
|<span data-ttu-id="a4582-147">Nicht verwalteter Typ</span><span class="sxs-lookup"><span data-stu-id="a4582-147">Unmanaged type</span></span>|<span data-ttu-id="a4582-148">Importierter Typ</span><span class="sxs-lookup"><span data-stu-id="a4582-148">Imported type</span></span>|  
|--------------------|-------------------|  
|<span data-ttu-id="a4582-149">**SafeArray(** *Typ* **)**</span><span class="sxs-lookup"><span data-stu-id="a4582-149">**SafeArray(** *Type* **)**</span></span>|<span data-ttu-id="a4582-150">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span><span class="sxs-lookup"><span data-stu-id="a4582-150">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="a4582-151">Rang = 1, Untergrenze = 0.</span><span class="sxs-lookup"><span data-stu-id="a4582-151">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="a4582-152">Die Größe ist nur bekannt, wenn sie in der verwalteten Signatur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a4582-152">Size is known only if provided in the managed signature.</span></span> <span data-ttu-id="a4582-153">Sichere Arrays, bei denen Rang = 1 oder Untergrenze = 0 nicht gilt, können nicht als **SZARRAY** gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-153">Safe arrays that are not rank = 1 or lower bound = 0 cannot be marshaled as **SZARRAY**.</span></span>|  
|<span data-ttu-id="a4582-154">*Typ* **[]**</span><span class="sxs-lookup"><span data-stu-id="a4582-154">*Type*  **[]**</span></span>|<span data-ttu-id="a4582-155">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span><span class="sxs-lookup"><span data-stu-id="a4582-155">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="a4582-156">Rang = 1, Untergrenze = 0.</span><span class="sxs-lookup"><span data-stu-id="a4582-156">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="a4582-157">Die Größe ist nur bekannt, wenn sie in der verwalteten Signatur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a4582-157">Size is known only if provided in the managed signature.</span></span>|  
  
### <a name="safe-arrays"></a><span data-ttu-id="a4582-158">Sichere Arrays</span><span class="sxs-lookup"><span data-stu-id="a4582-158">Safe Arrays</span></span>  
 <span data-ttu-id="a4582-159">Wenn ein sicheres Array aus einer Typbibliothek in eine .NET-Assembly importiert wird, wird das Array in ein eindimensionales Array eines bekannten Typs konvertiert (z.B. **int**).</span><span class="sxs-lookup"><span data-stu-id="a4582-159">When a safe array is imported from a type library to a .NET assembly, the array is converted to a one-dimensional array of a known type (such as **int**).</span></span> <span data-ttu-id="a4582-160">Dieselben Typkonvertierungsregeln, die für Parameter gelten, gelten auch für Arrayelemente.</span><span class="sxs-lookup"><span data-stu-id="a4582-160">The same type conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="a4582-161">So wird beispielsweise ein sicheres Array von **BSTR**-Typen zu einem verwalteten Array von Zeichenfolgen, und ein sicheres Array von Varianten zu einem verwalteten Array von Objekten.</span><span class="sxs-lookup"><span data-stu-id="a4582-161">For example, a safe array of **BSTR** types becomes a managed array of strings and a safe array of variants becomes a managed array of objects.</span></span> <span data-ttu-id="a4582-162">Der **SAFEARRAY**-Elementtyp wird aus der Typbibliothek abgerufen, und im **SAFEARRAY**-Wert der <xref:System.Runtime.InteropServices.UnmanagedType>-Enumeration gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a4582-162">The **SAFEARRAY** element type is captured from the type library and saved in the **SAFEARRAY** value of the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration.</span></span>  
  
 <span data-ttu-id="a4582-163">Da Rang und Grenzen eines sicheren Arrays über die Typbibliothek nicht bestimmt werden können, wird für den Rang ein Wert von 1 und für die Untergrenze ein Wert von 0 angenommen.</span><span class="sxs-lookup"><span data-stu-id="a4582-163">Because the rank and bounds of the safe array cannot be determined from the type library, the rank is assumed to equal 1 and the lower bound is assumed to equal 0.</span></span> <span data-ttu-id="a4582-164">Rang und Grenzen müssen in der vom [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) (Typbibliothek Importer) erzeugten verwalteten Signatur definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-164">The rank and bounds must be defined in the managed signature produced by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="a4582-165">Wenn der zur Laufzeit an die Methode übergebene Rang unterschiedlich ist, wird eine <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a4582-165">If the rank passed to the method at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> is thrown.</span></span> <span data-ttu-id="a4582-166">Wenn der zur Laufzeit übergebene Arraytyp unterschiedlich ist, wird eine <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a4582-166">If the type of the array passed at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> is thrown.</span></span> <span data-ttu-id="a4582-167">Das folgende Beispiel zeigt sichere Arrays in verwaltetem und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="a4582-167">The following example shows safe arrays in managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="a4582-168">**Nicht verwaltete Signatur**</span><span class="sxs-lookup"><span data-stu-id="a4582-168">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 <span data-ttu-id="a4582-169">**Verwaltete Signatur**</span><span class="sxs-lookup"><span data-stu-id="a4582-169">**Managed signature**</span></span>  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_I4)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_DATE)> _
   ar() As DateTime)  
Sub New3(ByRef <MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_BSTR)> _
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_I4)] int[] ar) ;  
void New2([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_DATE)]
   DateTime[] ar);  
void New3([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_BSTR)]
   ref String[] ar);  
```  
  
 <span data-ttu-id="a4582-170">Mehrdimensionale oder gebundene sichere Arrays mit einem Wert ungleich null, können in verwalteten Code gemarshallt werden, wenn die von Tlbimp.exe erzeugte Methodensignatur so geändert wird, dass sie einen Elementtyp von **ELEMENT_TYPE_ARRAY** anstelle von **ELEMENT_TYPE_SZARRAY** angibt.</span><span class="sxs-lookup"><span data-stu-id="a4582-170">Multidimensional, or nonzero-bound safe arrays, can be marshaled into managed code if the method signature produced by Tlbimp.exe is modified to indicate an element type of **ELEMENT_TYPE_ARRAY** instead of **ELEMENT_TYPE_SZARRAY**.</span></span> <span data-ttu-id="a4582-171">Alternativ können Sie den **/sysarray** -Schalter mit Tlbimp.exe verwenden, um alle Arrays als <xref:System.Array?displayProperty=nameWithType>-Objekte zu importieren.</span><span class="sxs-lookup"><span data-stu-id="a4582-171">Alternatively, you can use the **/sysarray** switch with Tlbimp.exe to import all arrays as <xref:System.Array?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="a4582-172">Wenn bekannt ist, dass das übergebene Array mehrdimensional ist, können Sie den durch Tlbimp.exeMicrosoft erzeugten Intermediate Language-Code (MSIL) bearbeiten, und diesen anschließend neu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="a4582-172">In cases where the array being passed is known to be multidimensional, you can edit the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompile it.</span></span> <span data-ttu-id="a4582-173">Ausführliche Informationen zum Ändern des MSIL-Codes finden Sie unter [Customizing Runtime Callable Wrappers (Anpassen von durch die Laufzeit aufrufbaren Wrappern)](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a4582-173">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span>  
  
### <a name="c-style-arrays"></a><span data-ttu-id="a4582-174">Arrays im C-Stil</span><span class="sxs-lookup"><span data-stu-id="a4582-174">C-Style Arrays</span></span>  
 <span data-ttu-id="a4582-175">Wenn ein Array im C-Stil aus einer Typbibliothek in eine .NET Framework-Assembly importiert wird, wird das Array in **ELEMENT_TYPE_SZARRAY** konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a4582-175">When a C-style array is imported from a type library to a .NET assembly, the array is converted to **ELEMENT_TYPE_SZARRAY**.</span></span>  
  
 <span data-ttu-id="a4582-176">Der Elementtyp des Arrays wird durch die Typbibliothek bestimmt und während des Imports beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a4582-176">The array element type is determined from the type library and preserved during the import.</span></span> <span data-ttu-id="a4582-177">Dieselben Konvertierungsregeln, die für Parameter gelten, gelten auch für Arrayelemente.</span><span class="sxs-lookup"><span data-stu-id="a4582-177">The same conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="a4582-178">Ein Array von **LPStr**-Typen wird z.B. zu einem Array von **Zeichenfolge**-Typen.</span><span class="sxs-lookup"><span data-stu-id="a4582-178">For example, an array of **LPStr** types becomes an array of **String** types.</span></span> <span data-ttu-id="a4582-179">Tlbimp.exe erfasst den Elementtyp des Arrays und wendet das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut auf den Parameter an.</span><span class="sxs-lookup"><span data-stu-id="a4582-179">Tlbimp.exe captures the array element type and applies the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to the parameter.</span></span>  
  
 <span data-ttu-id="a4582-180">Es wird angenommen, dass der Rang des Arrays gleich 1 ist.</span><span class="sxs-lookup"><span data-stu-id="a4582-180">The array rank is assumed to equal 1.</span></span> <span data-ttu-id="a4582-181">Wenn der Rang größer als 1 ist, wird das Array als eindimensionales Array nach Spaltengröße gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="a4582-181">If the rank is greater than 1, the array is marshaled as a one-dimensional array in column-major order.</span></span> <span data-ttu-id="a4582-182">Die Untergrenze ist immer gleich 0.</span><span class="sxs-lookup"><span data-stu-id="a4582-182">The lower bound always equals 0.</span></span>  
  
 <span data-ttu-id="a4582-183">Typbibliotheken können Arrays mit fester oder variabler Länge enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4582-183">Type libraries can contain arrays of fixed or variable length.</span></span> <span data-ttu-id="a4582-184">Tlbimp.exe kann nur Arrays mit fester Länge aus Typbibliotheken importieren, da Typbibliotheken nicht die benötigten Informationen zum Marshallen von Arrays mit variabler Länge enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4582-184">Tlbimp.exe can import only fixed-length arrays from type libraries because type libraries lack the information needed to marshal variable-length arrays.</span></span> <span data-ttu-id="a4582-185">Bei Arrays mit fester Länge, wird die Größe aus der Typbibliothek importiert und im **MarshalAsAttribute**, das auf den Parameter angewendet wird, erfasst.</span><span class="sxs-lookup"><span data-stu-id="a4582-185">With fixed-length arrays, the size is imported from the type library and captured in the **MarshalAsAttribute** that is applied to the parameter.</span></span>  
  
 <span data-ttu-id="a4582-186">Typbibliotheken, die Arrays mit variabler Länge beinhalten müssen, wie in folgendem Beispiel gezeigt, manuell definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-186">You must manually define type libraries containing variable-length arrays, as shown in the following example.</span></span>  
  
 <span data-ttu-id="a4582-187">**Nicht verwaltete Signatur**</span><span class="sxs-lookup"><span data-stu-id="a4582-187">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 <span data-ttu-id="a4582-188">**Verwaltete Signatur**</span><span class="sxs-lookup"><span data-stu-id="a4582-188">**Managed signature**</span></span>  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.LPArray, SizeConst=10)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, SizeConst=200)> _  
   ar() As Double)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)> _  
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.LPArray, SizeConst=10)] int[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray, SizeConst=200)] double[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray,
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)] String[] ar);  
```  
  
 <span data-ttu-id="a4582-189">Obwohl Sie das **Size_is**- oder **Length_is**-Attribut auf ein Array in der Interface Definition Language (IDL)-Quelle anwenden können, um einem Client die Größe mitzuteilen, übermittelt der Microsoft Interface Definition Language (MIDL)-Compiler diese Information nicht an die Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="a4582-189">Although you can apply the **size_is** or **length_is** attributes to an array in Interface Definition Language (IDL) source to convey the size to a client, the Microsoft Interface Definition Language (MIDL) compiler does not propagate that information to the type library.</span></span> <span data-ttu-id="a4582-190">Ohne die Größe zu kennen, kann der Interop-Marshallingdienst die Arrayelemente nicht marshallen.</span><span class="sxs-lookup"><span data-stu-id="a4582-190">Without knowing the size, the interop marshaling service cannot marshal the array elements.</span></span> <span data-ttu-id="a4582-191">Folglich werden Arrays mit variabler Länge als Verweisargumente importiert.</span><span class="sxs-lookup"><span data-stu-id="a4582-191">Consequently, variable-length arrays are imported as reference arguments.</span></span> <span data-ttu-id="a4582-192">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a4582-192">For example:</span></span>  
  
 <span data-ttu-id="a4582-193">**Nicht verwaltete Signatur**</span><span class="sxs-lookup"><span data-stu-id="a4582-193">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 <span data-ttu-id="a4582-194">**Verwaltete Signatur**</span><span class="sxs-lookup"><span data-stu-id="a4582-194">**Managed signature**</span></span>  
  
```vb  
Sub New1(ByRef ar As Integer)  
Sub New2(ByRef ar As Double)  
Sub New3(ByRef ar As String)  
```  
  
```csharp  
void New1(ref int ar);
void New2(ref double ar);
void New3(ref String ar);
```  
  
 <span data-ttu-id="a4582-195">Sie können die Arraygröße für den Marshaller bereitstellen, indem Sie den durch Tlbimp.exe erzeugten Microsoft intermediate Language-Code (MSIL) bearbeiten und anschließend neu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="a4582-195">You can provide the marshaler with the array size by editing the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompiling it.</span></span> <span data-ttu-id="a4582-196">Ausführliche Informationen zum Ändern des MSIL-Codes finden Sie unter [Customizing Runtime Callable Wrappers (Anpassen von durch die Laufzeit aufrufbaren Wrappern)](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a4582-196">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span> <span data-ttu-id="a4582-197">Um die Anzahl der Elemente im Array anzuzeigen, wenden Sie den <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Typ auf den Arrayparameter der verwalteten Methodendefinition durch eine der folgenden Vorgehensweisen an:</span><span class="sxs-lookup"><span data-stu-id="a4582-197">To indicate the number of elements in the array, apply the <xref:System.Runtime.InteropServices.MarshalAsAttribute> type to the array parameter of the managed method definition in one of the following ways:</span></span>  
  
- <span data-ttu-id="a4582-198">Geben Sie einen weiteren Parameter an, der die Anzahl der Elemente im Array enthält.</span><span class="sxs-lookup"><span data-stu-id="a4582-198">Identify another parameter that contains the number of elements in the array.</span></span> <span data-ttu-id="a4582-199">Die Parameter werden anhand der Position bestimmt, beginnend mit dem ersten Parameter als Nummer 0.</span><span class="sxs-lookup"><span data-stu-id="a4582-199">The parameters are identified by position, starting with the first parameter as number 0.</span></span>
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       \<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
- <span data-ttu-id="a4582-200">Definieren Sie die Größe des Arrays als Konstante.</span><span class="sxs-lookup"><span data-stu-id="a4582-200">Define the size of the array as a constant.</span></span> <span data-ttu-id="a4582-201">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a4582-201">For example:</span></span>  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 <span data-ttu-id="a4582-202">Beim Marshallen von Arrays aus nicht verwaltetem Code an verwalteten Code überprüft der Marshaller das dem Parameter zugeordnete **MarshalAsAttribute**, um die Arraygröße zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="a4582-202">When marshaling arrays from unmanaged code to managed code, the marshaler checks the **MarshalAsAttribute** associated with the parameter to determine the array size.</span></span> <span data-ttu-id="a4582-203">Wenn die Größe des Arrays nicht angegeben ist, wird nur ein Element gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="a4582-203">If the array size is not specified, only one element is marshaled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4582-204">Das Attribut **MarshalAsAttribute** wirkt sich nicht auf das Marshallen verwalteter Arrays an nicht verwalteten Code aus.</span><span class="sxs-lookup"><span data-stu-id="a4582-204">The **MarshalAsAttribute** has no effect on marshaling managed arrays to unmanaged code.</span></span> <span data-ttu-id="a4582-205">In dieser Richtung wird die Arraygröße durch Prüfung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="a4582-205">In that direction, the array size is determined by examination.</span></span> <span data-ttu-id="a4582-206">Es besteht keine Möglichkeit, einen Teil eines verwalteten Arrays zu marshallen.</span><span class="sxs-lookup"><span data-stu-id="a4582-206">There is no way to marshal a subset of a managed array.</span></span>  
  
 <span data-ttu-id="a4582-207">Der Interop-Marshaller verwendet die **CoTaskMemAlloc**- und **CoTaskMemFree**-Methoden, um Speicherplatz zu belegen und abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a4582-207">The interop marshaler uses the **CoTaskMemAlloc** and **CoTaskMemFree** methods to allocate and retrieve memory.</span></span> <span data-ttu-id="a4582-208">Diese Methoden müssen auch bei der Speicherbelegung durch nicht verwalteten Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-208">Memory allocation performed by unmanaged code must also use these methods.</span></span>  
  
## <a name="passing-arrays-to-com"></a><span data-ttu-id="a4582-209">Übergeben von Arrays an COM</span><span class="sxs-lookup"><span data-stu-id="a4582-209">Passing Arrays to COM</span></span>  
 <span data-ttu-id="a4582-210">Alle verwalteten Arraytypen können von verwaltetem Code an nicht verwalteten Code übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-210">All managed array types can be passed to unmanaged code from managed code.</span></span> <span data-ttu-id="a4582-211">Abhängig vom verwalteten Typ und den auf diesen Typ angewendeten Attributen, kann, wie in der folgenden Tabelle gezeigt, das Array als sicheres Array oder als Array im C-Stil abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-211">Depending on the managed type and the attributes applied to it, the array can be accessed as a safe array or a C-style array, as shown in the following table.</span></span>  
  
|<span data-ttu-id="a4582-212">Verwalteter Arraytyp</span><span class="sxs-lookup"><span data-stu-id="a4582-212">Managed array type</span></span>|<span data-ttu-id="a4582-213">Exportiert als</span><span class="sxs-lookup"><span data-stu-id="a4582-213">Exported as</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="a4582-214">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span><span class="sxs-lookup"><span data-stu-id="a4582-214">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span></span>|<span data-ttu-id="a4582-215"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *Typ* **)**</span><span class="sxs-lookup"><span data-stu-id="a4582-215"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="a4582-216">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="a4582-216">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="a4582-217">Typ wird in der Signatur angegeben.</span><span class="sxs-lookup"><span data-stu-id="a4582-217">Type is provided in the signature.</span></span> <span data-ttu-id="a4582-218">Rang ist immer 1, Untergrenze ist immer 0.</span><span class="sxs-lookup"><span data-stu-id="a4582-218">Rank is always 1, lower bound is always 0.</span></span> <span data-ttu-id="a4582-219">Die Größe ist immer zur Laufzeit bekannt.</span><span class="sxs-lookup"><span data-stu-id="a4582-219">Size is always known at run time.</span></span>|  
|<span data-ttu-id="a4582-220">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>** [ **\<** *bounds* **>** ]</span><span class="sxs-lookup"><span data-stu-id="a4582-220">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]</span></span>|<span data-ttu-id="a4582-221">**UnmanagedType.SafeArray(** *Typ* **)**</span><span class="sxs-lookup"><span data-stu-id="a4582-221">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="a4582-222">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="a4582-222">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="a4582-223">Typ, Rang und Grenzen sind in der Signatur angegeben.</span><span class="sxs-lookup"><span data-stu-id="a4582-223">Type, rank, bounds are provided in the signature.</span></span> <span data-ttu-id="a4582-224">Die Größe ist immer zur Laufzeit bekannt.</span><span class="sxs-lookup"><span data-stu-id="a4582-224">Size is always known at run time.</span></span>|  
|<span data-ttu-id="a4582-225">**ELEMENT_TYPE_CLASS** \*\*\<**<xref:System.Array?displayProperty=nameWithType>>\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a4582-225">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>\*\*</span></span>|<span data-ttu-id="a4582-226">**UT_Interface**</span><span class="sxs-lookup"><span data-stu-id="a4582-226">**UT_Interface**</span></span><br /><br /> <span data-ttu-id="a4582-227">**UnmanagedType.SafeArray(** *Typ* **)**</span><span class="sxs-lookup"><span data-stu-id="a4582-227">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="a4582-228">Typ, Rang, Grenzen und Größe sind immer zur Laufzeit bekannt.</span><span class="sxs-lookup"><span data-stu-id="a4582-228">Type, rank, bounds, and size are always known at run time.</span></span>|  
  
 <span data-ttu-id="a4582-229">In der OLE-Automatisierung, gibt es im Zusammenhang mit Arrays von Strukturen, die LPSTR oder LPWSTR enthalten eine Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="a4582-229">There is a limitation in OLE Automation relating to arrays of structures that contain LPSTR or LPWSTR.</span></span>  <span data-ttu-id="a4582-230">Aus diesem Grund müssen **Zeichenfolge**-Felder als **UnmanagedType.BSTR** gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-230">Therefore, **String** fields have to be marshaled as **UnmanagedType.BSTR**.</span></span> <span data-ttu-id="a4582-231">Andernfalls wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a4582-231">Otherwise, an exception will be thrown.</span></span>  
  
### <a name="element_type_szarray"></a><span data-ttu-id="a4582-232">ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="a4582-232">ELEMENT_TYPE_SZARRAY</span></span>  
 <span data-ttu-id="a4582-233">Wenn eine Methode mit einem **ELEMENT_TYPE_SZARRAY**-Parameter (eindimensionales Array) aus einer .NET-Assembly in eine Typbibliothek exportiert wird, wird der Arrayparameter in ein **SAFEARRAY** eines gegebenen Typs konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a4582-233">When a method containing an **ELEMENT_TYPE_SZARRAY** parameter (one-dimensional array) is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="a4582-234">Dieselben Konvertierungsregeln gelten für die Arrayelementtypen.</span><span class="sxs-lookup"><span data-stu-id="a4582-234">The same conversion rules apply to the array element types.</span></span> <span data-ttu-id="a4582-235">Der Inhalt des verwalteten Arrays wird automatisch aus dem verwalteten Speicher in das **SAFEARRAY** kopiert.</span><span class="sxs-lookup"><span data-stu-id="a4582-235">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="a4582-236">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a4582-236">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="a4582-237">Verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="a4582-237">Managed signature</span></span>  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="a4582-238">Nicht verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="a4582-238">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="a4582-239">Der Rang eines sicheren Arrays ist immer 1, und die Untergrenze ist immer 0.</span><span class="sxs-lookup"><span data-stu-id="a4582-239">The rank of the safe arrays is always 1 and the lower bound is always 0.</span></span> <span data-ttu-id="a4582-240">Die Größe wird zur Laufzeit durch die Größe des übergebenen verwalteten Arrays bestimmt.</span><span class="sxs-lookup"><span data-stu-id="a4582-240">The size is determined at run time by the size of the managed array being passed.</span></span>  
  
 <span data-ttu-id="a4582-241">Das Array kann auch als Array im C-Stil, mithilfe des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributs gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-241">The array can also be marshaled as a C-style array by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="a4582-242">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a4582-242">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="a4582-243">Verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="a4582-243">Managed signature</span></span>  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As Long, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]
   long [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]
   String [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, ArraySubType=
   UnmanagedType.LPStr, SizeParamIndex=1)]
   String [] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="a4582-244">Nicht verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="a4582-244">Unmanaged signature</span></span>  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(BSTR ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="a4582-245">Obwohl der Marshaller die erforderlichen Längeninformationen zum Marshallen von Arrays hat, wird die Länge des Arrays in der Regel als separates Argument übergeben, um dem Aufgerufenen die Länge mitzuteilen.</span><span class="sxs-lookup"><span data-stu-id="a4582-245">Although the marshaler has the length information needed to marshal the array, the array length is usually passed as a separate argument to convey the length to the callee.</span></span>  
  
### <a name="element_type_array"></a><span data-ttu-id="a4582-246">ELEMENT_TYPE_ARRAY</span><span class="sxs-lookup"><span data-stu-id="a4582-246">ELEMENT_TYPE_ARRAY</span></span>  
 <span data-ttu-id="a4582-247">Wenn eine Methode mit einem **ELEMENT_TYPE_ARRAY**-Parameter aus einer .NET-Assembly in eine Typbibliothek exportiert wird, wird der Arrayparameter in ein **SAFEARRAY** eines gegebenen Typs konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a4582-247">When a method containing an **ELEMENT_TYPE_ARRAY** parameter is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="a4582-248">Der Inhalt des verwalteten Arrays wird automatisch aus dem verwalteten Speicher in das **SAFEARRAY** kopiert.</span><span class="sxs-lookup"><span data-stu-id="a4582-248">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="a4582-249">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a4582-249">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="a4582-250">Verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="a4582-250">Managed signature</span></span>  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="a4582-251">Nicht verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="a4582-251">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="a4582-252">Der Rang, die Größe und die Grenzen eines sicheren Arrays werden zur Laufzeit durch die Merkmale des verwalteten Arrays bestimmt.</span><span class="sxs-lookup"><span data-stu-id="a4582-252">The rank, size, and bounds of the safe arrays are determined at run time by the characteristics of the managed array.</span></span>  
  
 <span data-ttu-id="a4582-253">Das Array kann auch als Array im C-Stil, mithilfe des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributs gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-253">The array can also be marshaled as a C-style array by applying the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="a4582-254">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a4582-254">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="a4582-255">Verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="a4582-255">Managed signature</span></span>  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex:=1)> _  
   ar(,) As Long, size As Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, _  
   ArraySubType:=UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar(,) As String, size As Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex=1)]
   long [,] ar, int size );  
void New([MarshalAs(UnmanagedType.LPARRAY,
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex=1)]
   String [,] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="a4582-256">Nicht verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="a4582-256">Unmanaged signature</span></span>  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="a4582-257">Geschachtelte Arrays können nicht gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-257">Nested arrays cannot be marshaled.</span></span> <span data-ttu-id="a4582-258">Die folgende Signatur generiert beispielsweise einen Fehler, wenn sie mit dem [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="a4582-258">For example, the following signature generates an error when exported with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="a4582-259">Verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="a4582-259">Managed signature</span></span>  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="element_type_class-systemarray"></a><span data-ttu-id="a4582-260">ELEMENT_TYPE_CLASS \<System.Array></span><span class="sxs-lookup"><span data-stu-id="a4582-260">ELEMENT_TYPE_CLASS \<System.Array></span></span>  
 <span data-ttu-id="a4582-261">Wenn eine Methode, die einen <xref:System.Array?displayProperty=nameWithType>-Parameter enthält aus einer .NET-Assembly in eine Typbibliothek exportiert wird, wird der Arrayparameter in eine **_Array**-Schnittstelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a4582-261">When a method containing a <xref:System.Array?displayProperty=nameWithType> parameter is exported from a .NET assembly to a type library, the array parameter is converted to an **_Array** interface.</span></span> <span data-ttu-id="a4582-262">Auf den Inhalt des verwalteten Arrays kann nur über die Methoden und Eigenschaften der **_Array**-Schnittstelle zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-262">The contents of the managed array are accessible only through the methods and properties of the **_Array** interface.</span></span> <span data-ttu-id="a4582-263">**System.Array** kann auch als **SAFEARRAY**, mithilfe von <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributen gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-263">**System.Array** can also be marshaled as a **SAFEARRAY** by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="a4582-264">Wenn die Arrayelemente als sicheres Array gemarshallt werden, werden sie als Varianten gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="a4582-264">When marshaled as a safe array, the array elements are marshaled as variants.</span></span> <span data-ttu-id="a4582-265">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a4582-265">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="a4582-266">Verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="a4582-266">Managed signature</span></span>  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="a4582-267">Nicht verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="a4582-267">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] _Array *ar);
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a><span data-ttu-id="a4582-268">Arrays in Strukturen</span><span class="sxs-lookup"><span data-stu-id="a4582-268">Arrays within Structures</span></span>  
 <span data-ttu-id="a4582-269">Nicht verwaltete Strukturen können eingebettete Arrays enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4582-269">Unmanaged structures can contain embedded arrays.</span></span> <span data-ttu-id="a4582-270">Standardmäßig werden diese eingebetteten Arrayfelder als SAFEARRAY gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="a4582-270">By default, these embedded array fields are marshaled as a SAFEARRAY.</span></span> <span data-ttu-id="a4582-271">Im folgenden Beispiel ist `s1` ein eingebettetes Array, das direkt innerhalb der Struktur selbst zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a4582-271">In the following example, `s1` is an embedded array that is allocated directly within the structure itself.</span></span>  
  
#### <a name="unmanaged-representation"></a><span data-ttu-id="a4582-272">Nicht verwalteten Darstellung</span><span class="sxs-lookup"><span data-stu-id="a4582-272">Unmanaged representation</span></span>  
  
```cpp
struct MyStruct {  
    short s1[128];  
}  
```  
  
 <span data-ttu-id="a4582-273">Arrays können als <xref:System.Runtime.InteropServices.UnmanagedType> gemarshallt sein, was das Einrichten des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Felds voraussetzt.</span><span class="sxs-lookup"><span data-stu-id="a4582-273">Arrays can be marshaled as <xref:System.Runtime.InteropServices.UnmanagedType>, which requires you to set the <xref:System.Runtime.InteropServices.MarshalAsAttribute> field.</span></span> <span data-ttu-id="a4582-274">Die Größe kann nur als eine Konstante festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="a4582-274">The size can be set only as a constant.</span></span> <span data-ttu-id="a4582-275">Der folgende Code zeigt die entsprechende verwaltete Definition von `MyStruct`.</span><span class="sxs-lookup"><span data-stu-id="a4582-275">The following code shows the corresponding managed definition of `MyStruct`.</span></span>  
  
```vb  
Public Structure <StructLayout(LayoutKind.Sequential)> MyStruct  
   Public <MarshalAs(UnmanagedType.ByValArray, SizeConst := 128)> _  
     s1() As Short  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MyStruct {  
   [MarshalAs(UnmanagedType.ByValArray, SizeConst=128)] public short[] s1;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4582-276">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4582-276">See also</span></span>

- [<span data-ttu-id="a4582-277">Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)</span><span class="sxs-lookup"><span data-stu-id="a4582-277">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="a4582-278">Blitfähige und nicht blitfähige Typen</span><span class="sxs-lookup"><span data-stu-id="a4582-278">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="a4582-279">[Direktionale Attribute](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a4582-279">[Directional Attributes](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="a4582-280">Kopieren und Fixieren</span><span class="sxs-lookup"><span data-stu-id="a4582-280">Copying and Pinning</span></span>](copying-and-pinning.md)
