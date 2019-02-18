---
title: Standardmäßiges Marshalling für Arrays
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, arrays
- arrays, interop marshaling
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae339b18032becffcaece1924a22b958ed86d364
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219684"
---
# <a name="default-marshaling-for-arrays"></a><span data-ttu-id="b7b0d-102">Standardmäßiges Marshalling für Arrays</span><span class="sxs-lookup"><span data-stu-id="b7b0d-102">Default Marshaling for Arrays</span></span>
<span data-ttu-id="b7b0d-103">In einer Anwendung, die vollständig aus verwaltetem Code besteht, übergibt die Common Language Runtime Arraytypen als In-/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-103">In an application consisting entirely of managed code, the common language runtime passes array types as In/Out parameters.</span></span> <span data-ttu-id="b7b0d-104">Im Gegensatz dazu übergibt der Interopmarshaller außerdem ein Array als In-Parameter in der Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-104">In contrast, the interop marshaler passes an array as In parameters by default.</span></span>  
  
 <span data-ttu-id="b7b0d-105">Bei der [pinning optimization](copying-and-pinning.md) (Fixierungsoptimierung),kann ein blitfähiges Array den Anschein erwecken, dass es als In/Out-Parameter fungiert, wenn es mit Objekten in demselben Apartment interagiert.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-105">With [pinning optimization](copying-and-pinning.md), a blittable array can appear to operate as an In/Out parameter when interacting with objects in the same apartment.</span></span> <span data-ttu-id="b7b0d-106">Wenn Sie allerdings den Code später in eine Typbibliothek exportieren, mit der der computerübergreifende Proxy generiert wird, und diese Bibliothek dazu verwendet wird, Ihre Aufrufe über Apartments hinweg zu marshallen, können sich die Aufrufe wieder wie TRUE-Parameter verhalten.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-106">However, if you later export the code to a type library used to generate the cross-machine proxy, and that library is used to marshal your calls across apartments, the calls can revert to true In parameter behavior.</span></span>  
  
 <span data-ttu-id="b7b0d-107">Arrays sind naturgemäß komplex, und die Unterschiede zwischen verwalteten und nicht verwalteten Arrays bieten mehr Informationen als andere nicht blitfähige Typen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-107">Arrays are complex by nature, and the distinctions between managed and unmanaged arrays warrant more information than other non-blittable types.</span></span> <span data-ttu-id="b7b0d-108">Dieses Thema enthält die folgenden Informationen zum Marshallen von Arrays:</span><span class="sxs-lookup"><span data-stu-id="b7b0d-108">This topic provides the following information on marshaling arrays:</span></span>  
  
-   [<span data-ttu-id="b7b0d-109">Verwaltete Arrays</span><span class="sxs-lookup"><span data-stu-id="b7b0d-109">Managed Arrays</span></span>](#cpcondefaultmarshalingforarraysanchor1)  
  
-   [<span data-ttu-id="b7b0d-110">Nicht verwaltete Arrays</span><span class="sxs-lookup"><span data-stu-id="b7b0d-110">Unmanaged Arrays</span></span>](#cpcondefaultmarshalingforarraysanchor2)  
  
-   [<span data-ttu-id="b7b0d-111">Übergeben von Arrayparametern an .NET-Code</span><span class="sxs-lookup"><span data-stu-id="b7b0d-111">Passing Array Parameters to .NET Code</span></span>](#cpcondefaultmarshalingforarraysanchor3)  
  
-   [<span data-ttu-id="b7b0d-112">Übergeben von Arrays an COM</span><span class="sxs-lookup"><span data-stu-id="b7b0d-112">Passing Arrays to COM</span></span>](#cpcondefaultmarshalingforarraysanchor4)  
  
<a name="cpcondefaultmarshalingforarraysanchor1"></a>   
## <a name="managed-arrays"></a><span data-ttu-id="b7b0d-113">Verwaltete Arrays</span><span class="sxs-lookup"><span data-stu-id="b7b0d-113">Managed Arrays</span></span>  
 <span data-ttu-id="b7b0d-114">Verwaltete Arraytypen können variieren. Allerdings ist die <xref:System.Array?displayProperty=nameWithType>-Klasse die Basisklasse für alle Arraytypen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-114">Managed array types can vary; however, the <xref:System.Array?displayProperty=nameWithType> class is the base class of all array types.</span></span> <span data-ttu-id="b7b0d-115">Die **System.Array**-Klasse enthält Eigenschaften, um den Rang, die Länge und die Unter- und Obergrenze eines Arrays zu bestimmen, als auch Methoden zum Zugreifen, Sortieren, Durchsuchen, Kopieren und Erstellen von Arrays.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-115">The **System.Array** class has properties for determining the rank, length, and lower and upper bounds of an array, as well as methods for accessing, sorting, searching, copying, and creating arrays.</span></span>  
  
 <span data-ttu-id="b7b0d-116">Diese Arraytypen sind dynamisch und verfügen über keinen entsprechenden statischen, in der Basisklassenbibliothek definierten Typen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-116">These array types are dynamic and do not have a corresponding static type defined in the base class library.</span></span> <span data-ttu-id="b7b0d-117">Es ist sinnvoll, jede Kombination aus Elementtyp und Rang als gesonderten Arraytypen zu betrachten.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-117">It is convenient to think of each combination of element type and rank as a distinct type of array.</span></span> <span data-ttu-id="b7b0d-118">Deshalb unterscheidet sich ein eindimensionales Array von ganzen Zahlen von einem eindimensionalen Array von Double-Typen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-118">Therefore, a one-dimensional array of integers is of a different type than a one-dimensional array of double types.</span></span> <span data-ttu-id="b7b0d-119">In ähnlicher Weise unterscheidet sich ein zweidimensionales Array von ganzen Zahlen von einem eindimensionalen Array von ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-119">Similarly a two-dimensional array of integers is different from a one-dimensional array of integers.</span></span> <span data-ttu-id="b7b0d-120">Die Grenzen des Arrays werden beim Vergleichen von Typen nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-120">The bounds of the array are not considered when comparing types.</span></span>  
  
 <span data-ttu-id="b7b0d-121">Wie die folgende Tabelle zeigt, muss jede Instanz eines verwalteten Arrays über einen bestimmter Elementtyp, Rang und eine bestimmte Untergrenze verfügen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-121">As the following table shows, any instance of a managed array must be of a specific element type, rank, and lower bound.</span></span>  
  
|<span data-ttu-id="b7b0d-122">Verwalteter Arraytyp</span><span class="sxs-lookup"><span data-stu-id="b7b0d-122">Managed array type</span></span>|<span data-ttu-id="b7b0d-123">Elementtyp</span><span class="sxs-lookup"><span data-stu-id="b7b0d-123">Element type</span></span>|<span data-ttu-id="b7b0d-124">Rang</span><span class="sxs-lookup"><span data-stu-id="b7b0d-124">Rank</span></span>|<span data-ttu-id="b7b0d-125">Unterer Grenzwert</span><span class="sxs-lookup"><span data-stu-id="b7b0d-125">Lower bound</span></span>|<span data-ttu-id="b7b0d-126">Signaturschreibweise</span><span class="sxs-lookup"><span data-stu-id="b7b0d-126">Signature notation</span></span>|  
|------------------------|------------------|----------|-----------------|------------------------|  
|<span data-ttu-id="b7b0d-127">**ELEMENT_TYPE_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-127">**ELEMENT_TYPE_ARRAY**</span></span>|<span data-ttu-id="b7b0d-128">Durch den Typ angegeben.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-128">Specified by type.</span></span>|<span data-ttu-id="b7b0d-129">Durch den Rang angegeben.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-129">Specified by rank.</span></span>|<span data-ttu-id="b7b0d-130">Optional durch Grenzen angegeben.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-130">Optionally specified by bounds.</span></span>|<span data-ttu-id="b7b0d-131">*Typ* **[** *n*,*m* **]**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-131">*type* **[** *n*,*m* **]**</span></span>|  
|<span data-ttu-id="b7b0d-132">**ELEMENT_TYPE_CLASS**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-132">**ELEMENT_TYPE_CLASS**</span></span>|<span data-ttu-id="b7b0d-133">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="b7b0d-133">Unknown</span></span>|<span data-ttu-id="b7b0d-134">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="b7b0d-134">Unknown</span></span>|<span data-ttu-id="b7b0d-135">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="b7b0d-135">Unknown</span></span>|<span data-ttu-id="b7b0d-136">**System.Array**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-136">**System.Array**</span></span>|  
|<span data-ttu-id="b7b0d-137">**ELEMENT_TYPE_SZARRAY**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-137">**ELEMENT_TYPE_SZARRAY**</span></span>|<span data-ttu-id="b7b0d-138">Durch den Typ angegeben.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-138">Specified by type.</span></span>|<span data-ttu-id="b7b0d-139">1</span><span class="sxs-lookup"><span data-stu-id="b7b0d-139">1</span></span>|<span data-ttu-id="b7b0d-140">0</span><span class="sxs-lookup"><span data-stu-id="b7b0d-140">0</span></span>|<span data-ttu-id="b7b0d-141">*Typ* **[** *n* **]**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-141">*type* **[** *n* **]**</span></span>|  
  
<a name="cpcondefaultmarshalingforarraysanchor2"></a>   
## <a name="unmanaged-arrays"></a><span data-ttu-id="b7b0d-142">Nicht verwaltete Arrays</span><span class="sxs-lookup"><span data-stu-id="b7b0d-142">Unmanaged Arrays</span></span>  
 <span data-ttu-id="b7b0d-143">Nicht verwaltete Arrays sind entweder sichere Arrays im COM-Stil oder Arrays im C-Stil mit fester oder variabler Länge.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-143">Unmanaged arrays are either COM-style safe arrays or C-style arrays with fixed or variable length.</span></span> <span data-ttu-id="b7b0d-144">Sichere Arrays sind selbstbeschreibende Arrays, die den Typ, den Rang und die Grenzen der verknüpften Arraydaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-144">Safe arrays are self-describing arrays that carry the type, rank, and bounds of the associated array data.</span></span> <span data-ttu-id="b7b0d-145">Arrays im C-Stil sind eindimensionale typisierte Arrays mit einer festen Untergrenze von 0.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-145">C-style arrays are one-dimensional typed arrays with a fixed lower bound of 0.</span></span> <span data-ttu-id="b7b0d-146">Der Marshallingdienst bietet nur eingeschränkt Unterstützung für beide Typen von Arrays.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-146">The marshaling service has limited support for both types of arrays.</span></span>  
  
<a name="cpcondefaultmarshalingforarraysanchor3"></a>   
## <a name="passing-array-parameters-to-net-code"></a><span data-ttu-id="b7b0d-147">Übergeben von Arrayparametern an .NET-Code</span><span class="sxs-lookup"><span data-stu-id="b7b0d-147">Passing Array Parameters to .NET Code</span></span>  
 <span data-ttu-id="b7b0d-148">Arrays im C-Stil und sichere Arrays, können aus nicht verwaltetem Code an .NET-Code, als ein sicheres Array oder ein Array im C-Stil übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-148">Both C-style arrays and safe arrays can be passed to .NET code from unmanaged code as either a safe array or a C-style array.</span></span> <span data-ttu-id="b7b0d-149">Die folgende Tabelle zeigt den nicht verwalteten Typwert und den importierten Typ.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-149">The following table shows the unmanaged type value and the imported type.</span></span>  
  
|<span data-ttu-id="b7b0d-150">Nicht verwalteter Typ</span><span class="sxs-lookup"><span data-stu-id="b7b0d-150">Unmanaged type</span></span>|<span data-ttu-id="b7b0d-151">Importierter Typ</span><span class="sxs-lookup"><span data-stu-id="b7b0d-151">Imported type</span></span>|  
|--------------------|-------------------|  
|<span data-ttu-id="b7b0d-152">**SafeArray(** *Typ* **)**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-152">**SafeArray(** *Type* **)**</span></span>|<span data-ttu-id="b7b0d-153">**ELEMENT_TYPE_SZARRAY** **\<** *KonvertierterTyp* **>**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-153">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="b7b0d-154">Rang = 1, Untergrenze = 0.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-154">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="b7b0d-155">Die Größe ist nur bekannt, wenn sie in der verwalteten Signatur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-155">Size is known only if provided in the managed signature.</span></span> <span data-ttu-id="b7b0d-156">Sichere Arrays, bei denen Rang = 1 oder Untergrenze = 0 nicht gilt, können nicht als **SZARRAY** gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-156">Safe arrays that are not rank = 1 or lower bound = 0 cannot be marshaled as **SZARRAY**.</span></span>|  
|<span data-ttu-id="b7b0d-157">*Typ*  **[]**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-157">*Type*  **[]**</span></span>|<span data-ttu-id="b7b0d-158">**ELEMENT_TYPE_SZARRAY** **\<** *KonvertierterTyp* **>**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-158">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="b7b0d-159">Rang = 1, Untergrenze = 0.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-159">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="b7b0d-160">Die Größe ist nur bekannt, wenn sie in der verwalteten Signatur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-160">Size is known only if provided in the managed signature.</span></span>|  
  
### <a name="safe-arrays"></a><span data-ttu-id="b7b0d-161">Sichere Arrays</span><span class="sxs-lookup"><span data-stu-id="b7b0d-161">Safe Arrays</span></span>  
 <span data-ttu-id="b7b0d-162">Wenn ein sicheres Array aus einer Typbibliothek in eine .NET-Assembly importiert wird, wird das Array in ein eindimensionales Array eines bekannten Typs konvertiert (z.B. **int**).</span><span class="sxs-lookup"><span data-stu-id="b7b0d-162">When a safe array is imported from a type library to a .NET assembly, the array is converted to a one-dimensional array of a known type (such as **int**).</span></span> <span data-ttu-id="b7b0d-163">Dieselben Typkonvertierungsregeln, die für Parameter gelten, gelten auch für Arrayelemente.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-163">The same type conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="b7b0d-164">So wird beispielsweise ein sicheres Array von **BSTR**-Typen zu einem verwalteten Array von Zeichenfolgen, und ein sicheres Array von Varianten zu einem verwalteten Array von Objekten.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-164">For example, a safe array of **BSTR** types becomes a managed array of strings and a safe array of variants becomes a managed array of objects.</span></span> <span data-ttu-id="b7b0d-165">Der **SAFEARRAY**-Elementtyp wird aus der Typbibliothek abgerufen, und im **SAFEARRAY**-Wert der <xref:System.Runtime.InteropServices.UnmanagedType>-Enumeration gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-165">The **SAFEARRAY** element type is captured from the type library and saved in the **SAFEARRAY** value of the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration.</span></span>  
  
 <span data-ttu-id="b7b0d-166">Da Rang und Grenzen eines sicheren Arrays über die Typbibliothek nicht bestimmt werden können, wird für den Rang ein Wert von 1 und für die Untergrenze ein Wert von 0 angenommen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-166">Because the rank and bounds of the safe array cannot be determined from the type library, the rank is assumed to equal 1 and the lower bound is assumed to equal 0.</span></span> <span data-ttu-id="b7b0d-167">Rang und Grenzen müssen in der vom [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) (Typbibliothek Importer) erzeugten verwalteten Signatur definiert werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-167">The rank and bounds must be defined in the managed signature produced by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="b7b0d-168">Wenn der zur Laufzeit an die Methode übergebene Rang unterschiedlich ist, wird eine <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-168">If the rank passed to the method at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> is thrown.</span></span> <span data-ttu-id="b7b0d-169">Wenn der zur Laufzeit übergebene Arraytyp unterschiedlich ist, wird eine <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-169">If the type of the array passed at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> is thrown.</span></span> <span data-ttu-id="b7b0d-170">Das folgende Beispiel zeigt sichere Arrays in verwaltetem und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-170">The following example shows safe arrays in managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="b7b0d-171">**Nicht verwaltete Signatur**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-171">**Unmanaged signature**</span></span>  
  
```  
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 <span data-ttu-id="b7b0d-172">**Verwaltete Signatur**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-172">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="b7b0d-173">Mehrdimensionale oder gebundene sichere Arrays mit einem Wert ungleich null, können in verwalteten Code gemarshallt werden, wenn die von Tlbimp.exe erzeugte Methodensignatur so geändert wird, dass sie einen Elementtyp von **ELEMENT_TYPE_ARRAY** anstelle von **ELEMENT_TYPE_SZARRAY** angibt.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-173">Multidimensional, or nonzero-bound safe arrays, can be marshaled into managed code if the method signature produced by Tlbimp.exe is modified to indicate an element type of **ELEMENT_TYPE_ARRAY** instead of **ELEMENT_TYPE_SZARRAY**.</span></span> <span data-ttu-id="b7b0d-174">Alternativ können Sie den **/sysarray** -Schalter mit Tlbimp.exe verwenden, um alle Arrays als <xref:System.Array?displayProperty=nameWithType>-Objekte zu importieren.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-174">Alternatively, you can use the **/sysarray** switch with Tlbimp.exe to import all arrays as <xref:System.Array?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="b7b0d-175">Wenn bekannt ist, dass das übergebene Array mehrdimensional ist, können Sie den durch Tlbimp.exeMicrosoft erzeugten Intermediate Language-Code (MSIL) bearbeiten, und diesen anschließend neu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-175">In cases where the array being passed is known to be multidimensional, you can edit the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompile it.</span></span> <span data-ttu-id="b7b0d-176">Ausführliche Informationen zum Ändern des MSIL-Codes finden Sie unter [Customizing Runtime Callable Wrappers (Anpassen von durch die Laufzeit aufrufbaren Wrappern)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b7b0d-176">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span>  
  
### <a name="c-style-arrays"></a><span data-ttu-id="b7b0d-177">Arrays im C-Stil</span><span class="sxs-lookup"><span data-stu-id="b7b0d-177">C-Style Arrays</span></span>  
 <span data-ttu-id="b7b0d-178">Wenn ein Array im C-Stil aus einer Typbibliothek in eine .NET Framework-Assembly importiert wird, wird das Array in **ELEMENT_TYPE_SZARRAY** konvertiert.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-178">When a C-style array is imported from a type library to a .NET assembly, the array is converted to **ELEMENT_TYPE_SZARRAY**.</span></span>  
  
 <span data-ttu-id="b7b0d-179">Der Elementtyp des Arrays wird durch die Typbibliothek bestimmt und während des Imports beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-179">The array element type is determined from the type library and preserved during the import.</span></span> <span data-ttu-id="b7b0d-180">Dieselben Konvertierungsregeln, die für Parameter gelten, gelten auch für Arrayelemente.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-180">The same conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="b7b0d-181">Ein Array von **LPStr**-Typen wird z.B. zu einem Array von **Zeichenfolge**-Typen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-181">For example, an array of **LPStr** types becomes an array of **String** types.</span></span> <span data-ttu-id="b7b0d-182">Tlbimp.exe erfasst den Elementtyp des Arrays und wendet das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut auf den Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-182">Tlbimp.exe captures the array element type and applies the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to the parameter.</span></span>  
  
 <span data-ttu-id="b7b0d-183">Es wird angenommen, dass der Rang des Arrays gleich 1 ist.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-183">The array rank is assumed to equal 1.</span></span> <span data-ttu-id="b7b0d-184">Wenn der Rang größer als 1 ist, wird das Array als eindimensionales Array nach Spaltengröße gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-184">If the rank is greater than 1, the array is marshaled as a one-dimensional array in column-major order.</span></span> <span data-ttu-id="b7b0d-185">Die Untergrenze ist immer gleich 0.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-185">The lower bound always equals 0.</span></span>  
  
 <span data-ttu-id="b7b0d-186">Typbibliotheken können Arrays mit fester oder variabler Länge enthalten.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-186">Type libraries can contain arrays of fixed or variable length.</span></span> <span data-ttu-id="b7b0d-187">Tlbimp.exe kann nur Arrays mit fester Länge aus Typbibliotheken importieren, da Typbibliotheken nicht die benötigten Informationen zum Marshallen von Arrays mit variabler Länge enthalten.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-187">Tlbimp.exe can import only fixed-length arrays from type libraries because type libraries lack the information needed to marshal variable-length arrays.</span></span> <span data-ttu-id="b7b0d-188">Bei Arrays mit fester Länge, wird die Größe aus der Typbibliothek importiert und im **MarshalAsAttribute**, das auf den Parameter angewendet wird, erfasst.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-188">With fixed-length arrays, the size is imported from the type library and captured in the **MarshalAsAttribute** that is applied to the parameter.</span></span>  
  
 <span data-ttu-id="b7b0d-189">Typbibliotheken, die Arrays mit variabler Länge beinhalten müssen, wie in folgendem Beispiel gezeigt, manuell definiert werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-189">You must manually define type libraries containing variable-length arrays, as shown in the following example.</span></span>  
  
 <span data-ttu-id="b7b0d-190">**Nicht verwaltete Signatur**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-190">**Unmanaged signature**</span></span>  
  
```  
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 <span data-ttu-id="b7b0d-191">**Verwaltete Signatur**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-191">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="b7b0d-192">Obwohl Sie das **Size_is**- oder **Length_is**-Attribut auf ein Array in der Interface Definition Language (IDL)-Quelle anwenden können, um einem Client die Größe mitzuteilen, übermittelt der Microsoft Interface Definition Language (MIDL)-Compiler diese Information nicht an die Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-192">Although you can apply the **size_is** or **length_is** attributes to an array in Interface Definition Language (IDL) source to convey the size to a client, the Microsoft Interface Definition Language (MIDL) compiler does not propagate that information to the type library.</span></span> <span data-ttu-id="b7b0d-193">Ohne die Größe zu kennen, kann der Interop-Marshallingdienst die Arrayelemente nicht marshallen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-193">Without knowing the size, the interop marshaling service cannot marshal the array elements.</span></span> <span data-ttu-id="b7b0d-194">Folglich werden Arrays mit variabler Länge als Verweisargumente importiert.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-194">Consequently, variable-length arrays are imported as reference arguments.</span></span> <span data-ttu-id="b7b0d-195">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b7b0d-195">For example:</span></span>  
  
 <span data-ttu-id="b7b0d-196">**Nicht verwaltete Signatur**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-196">**Unmanaged signature**</span></span>  
  
```  
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 <span data-ttu-id="b7b0d-197">**Verwaltete Signatur**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-197">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="b7b0d-198">Sie können die Arraygröße für den Marshaller bereitstellen, indem Sie den durch Tlbimp.exe erzeugten Microsoft intermediate Language-Code (MSIL) bearbeiten und anschließend neu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-198">You can provide the marshaler with the array size by editing the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompiling it.</span></span> <span data-ttu-id="b7b0d-199">Ausführliche Informationen zum Ändern des MSIL-Codes finden Sie unter [Customizing Runtime Callable Wrappers (Anpassen von durch die Laufzeit aufrufbaren Wrappern)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b7b0d-199">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span> <span data-ttu-id="b7b0d-200">Um die Anzahl der Elemente im Array anzuzeigen, wenden Sie den <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Typ auf den Arrayparameter der verwalteten Methodendefinition durch eine der folgenden Vorgehensweisen an:</span><span class="sxs-lookup"><span data-stu-id="b7b0d-200">To indicate the number of elements in the array, apply the <xref:System.Runtime.InteropServices.MarshalAsAttribute> type to the array parameter of the managed method definition in one of the following ways:</span></span>  
  
-   <span data-ttu-id="b7b0d-201">Geben Sie einen weiteren Parameter an, der die Anzahl der Elemente im Array enthält.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-201">Identify another parameter that contains the number of elements in the array.</span></span> <span data-ttu-id="b7b0d-202">Die Parameter werden anhand der Position bestimmt, beginnend mit dem ersten Parameter als Nummer 0.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-202">The parameters are identified by position, starting with the first parameter as number 0.</span></span>     
  
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
  
-   <span data-ttu-id="b7b0d-203">Definieren Sie die Größe des Arrays als Konstante.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-203">Define the size of the array as a constant.</span></span> <span data-ttu-id="b7b0d-204">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b7b0d-204">For example:</span></span>  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 <span data-ttu-id="b7b0d-205">Beim Marshallen von Arrays aus nicht verwaltetem Code an verwalteten Code überprüft der Marshaller das dem Parameter zugeordnete **MarshalAsAttribute**, um die Arraygröße zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-205">When marshaling arrays from unmanaged code to managed code, the marshaler checks the **MarshalAsAttribute** associated with the parameter to determine the array size.</span></span> <span data-ttu-id="b7b0d-206">Wenn die Größe des Arrays nicht angegeben ist, wird nur ein Element gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-206">If the array size is not specified, only one element is marshaled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7b0d-207">Das Attribut **MarshalAsAttribute** wirkt sich nicht auf das Marshallen verwalteter Arrays an nicht verwalteten Code aus.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-207">The **MarshalAsAttribute** has no effect on marshaling managed arrays to unmanaged code.</span></span> <span data-ttu-id="b7b0d-208">In dieser Richtung wird die Arraygröße durch Prüfung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-208">In that direction, the array size is determined by examination.</span></span> <span data-ttu-id="b7b0d-209">Es besteht keine Möglichkeit, einen Teil eines verwalteten Arrays zu marshallen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-209">There is no way to marshal a subset of a managed array.</span></span>  
  
 <span data-ttu-id="b7b0d-210">Der Interop-Marshaller verwendet die **CoTaskMemAlloc**- und **CoTaskMemFree**-Methoden, um Speicherplatz zu belegen und abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-210">The interop marshaler uses the **CoTaskMemAlloc** and **CoTaskMemFree** methods to allocate and retrieve memory.</span></span> <span data-ttu-id="b7b0d-211">Diese Methoden müssen auch bei der Speicherbelegung durch nicht verwalteten Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-211">Memory allocation performed by unmanaged code must also use these methods.</span></span>  
  
<a name="cpcondefaultmarshalingforarraysanchor4"></a>   
## <a name="passing-arrays-to-com"></a><span data-ttu-id="b7b0d-212">Übergeben von Arrays an COM</span><span class="sxs-lookup"><span data-stu-id="b7b0d-212">Passing Arrays to COM</span></span>  
 <span data-ttu-id="b7b0d-213">Alle verwalteten Arraytypen können von verwaltetem Code an nicht verwalteten Code übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-213">All managed array types can be passed to unmanaged code from managed code.</span></span> <span data-ttu-id="b7b0d-214">Abhängig vom verwalteten Typ und den auf diesen Typ angewendeten Attributen, kann, wie in der folgenden Tabelle gezeigt, das Array als sicheres Array oder als Array im C-Stil abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-214">Depending on the managed type and the attributes applied to it, the array can be accessed as a safe array or a C-style array, as shown in the following table.</span></span>  
  
|<span data-ttu-id="b7b0d-215">Verwalteter Arraytyp</span><span class="sxs-lookup"><span data-stu-id="b7b0d-215">Managed array type</span></span>|<span data-ttu-id="b7b0d-216">Exportiert als</span><span class="sxs-lookup"><span data-stu-id="b7b0d-216">Exported as</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="b7b0d-217">**ELEMENT_TYPE_SZARRAY** **\<** *Typ* **>**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-217">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span></span>|<span data-ttu-id="b7b0d-218"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *Typ* **)**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-218"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="b7b0d-219">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-219">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="b7b0d-220">Typ wird in der Signatur angegeben.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-220">Type is provided in the signature.</span></span> <span data-ttu-id="b7b0d-221">Rang ist immer 1, Untergrenze ist immer 0.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-221">Rank is always 1, lower bound is always 0.</span></span> <span data-ttu-id="b7b0d-222">Größe ist immer zur Laufzeit bekannt.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-222">Size is always known at run time.</span></span>|  
|<span data-ttu-id="b7b0d-223">**ELEMENT_TYPE_ARRAY** **\<** *Typ* **>** **\<** *Rang* **>**[**\<** *Grenzen* **>**]</span><span class="sxs-lookup"><span data-stu-id="b7b0d-223">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]</span></span>|<span data-ttu-id="b7b0d-224">**UnmanagedType.SafeArray(** *Typ* **)**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-224">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="b7b0d-225">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-225">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="b7b0d-226">Typ, Rang und Grenzen sind in der Signatur angegeben.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-226">Type, rank, bounds are provided in the signature.</span></span> <span data-ttu-id="b7b0d-227">Die Größe ist immer zur Laufzeit bekannt.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-227">Size is always known at run time.</span></span>|  
|<span data-ttu-id="b7b0d-228">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-228">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>**</span></span>|<span data-ttu-id="b7b0d-229">**UT_Interface**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-229">**UT_Interface**</span></span><br /><br /> <span data-ttu-id="b7b0d-230">**UnmanagedType.SafeArray(** *Typ* **)**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-230">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="b7b0d-231">Typ, Rang, Grenzen und Größe sind immer zur Laufzeit bekannt.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-231">Type, rank, bounds, and size are always known at run time.</span></span>|  
  
 <span data-ttu-id="b7b0d-232">In der OLE-Automatisierung, gibt es im Zusammenhang mit Arrays von Strukturen, die LPSTR oder LPWSTR enthalten eine Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-232">There is a limitation in OLE Automation relating to arrays of structures that contain LPSTR or LPWSTR.</span></span>  <span data-ttu-id="b7b0d-233">Aus diesem Grund müssen **Zeichenfolge**-Felder als **UnmanagedType.BSTR** gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-233">Therefore, **String** fields have to be marshaled as **UnmanagedType.BSTR**.</span></span> <span data-ttu-id="b7b0d-234">Andernfalls wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-234">Otherwise, an exception will be thrown.</span></span>  
  
### <a name="elementtypeszarray"></a><span data-ttu-id="b7b0d-235">ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="b7b0d-235">ELEMENT_TYPE_SZARRAY</span></span>  
 <span data-ttu-id="b7b0d-236">Wenn eine Methode mit einem **ELEMENT_TYPE_SZARRAY**-Parameter (eindimensionales Array) aus einer .NET-Assembly in eine Typbibliothek exportiert wird, wird der Arrayparameter in ein **SAFEARRAY** eines gegebenen Typs konvertiert.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-236">When a method containing an **ELEMENT_TYPE_SZARRAY** parameter (one-dimensional array) is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="b7b0d-237">Dieselben Konvertierungsregeln gelten für die Arrayelementtypen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-237">The same conversion rules apply to the array element types.</span></span> <span data-ttu-id="b7b0d-238">Der Inhalt des verwalteten Arrays wird automatisch aus dem verwalteten Speicher in das **SAFEARRAY** kopiert.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-238">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="b7b0d-239">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b7b0d-239">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="b7b0d-240">Verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="b7b0d-240">Managed signature</span></span>  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="b7b0d-241">Nicht verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="b7b0d-241">Unmanaged signature</span></span>  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="b7b0d-242">Der Rang eines sicheren Arrays ist immer 1, und die Untergrenze ist immer 0.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-242">The rank of the safe arrays is always 1 and the lower bound is always 0.</span></span> <span data-ttu-id="b7b0d-243">Die Größe wird zur Laufzeit durch die Größe des übergebenen verwalteten Arrays bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-243">The size is determined at run time by the size of the managed array being passed.</span></span>  
  
 <span data-ttu-id="b7b0d-244">Das Array kann auch als Array im C-Stil, mithilfe des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributs gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-244">The array can also be marshaled as a C-style array by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="b7b0d-245">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b7b0d-245">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="b7b0d-246">Verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="b7b0d-246">Managed signature</span></span>  
  
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
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="b7b0d-247">Nicht verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="b7b0d-247">Unmanaged signature</span></span>  
  
```  
HRESULT New(long ar[]);   
HRESULT New(BSTR ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="b7b0d-248">Obwohl der Marshaller die erforderlichen Längeninformationen zum Marshallen von Arrays hat, wird die Länge des Arrays in der Regel als separates Argument übergeben, um dem Aufgerufenen die Länge mitzuteilen.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-248">Although the marshaler has the length information needed to marshal the array, the array length is usually passed as a separate argument to convey the length to the callee.</span></span>  
  
### <a name="elementtypearray"></a><span data-ttu-id="b7b0d-249">ELEMENT_TYPE_ARRAY</span><span class="sxs-lookup"><span data-stu-id="b7b0d-249">ELEMENT_TYPE_ARRAY</span></span>  
 <span data-ttu-id="b7b0d-250">Wenn eine Methode mit einem **ELEMENT_TYPE_ARRAY**-Parameter aus einer .NET-Assembly in eine Typbibliothek exportiert wird, wird der Arrayparameter in ein **SAFEARRAY** eines gegebenen Typs konvertiert.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-250">When a method containing an **ELEMENT_TYPE_ARRAY** parameter is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="b7b0d-251">Der Inhalt des verwalteten Arrays wird automatisch aus dem verwalteten Speicher in das **SAFEARRAY** kopiert.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-251">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="b7b0d-252">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b7b0d-252">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="b7b0d-253">Verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="b7b0d-253">Managed signature</span></span>  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="b7b0d-254">Nicht verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="b7b0d-254">Unmanaged signature</span></span>  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="b7b0d-255">Der Rang, die Größe und die Grenzen eines sicheren Arrays werden zur Laufzeit durch die Merkmale des verwalteten Arrays bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-255">The rank, size, and bounds of the safe arrays are determined at run time by the characteristics of the managed array.</span></span>  
  
 <span data-ttu-id="b7b0d-256">Das Array kann auch als Array im C-Stil, mithilfe des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributs gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-256">The array can also be marshaled as a C-style array by applying the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="b7b0d-257">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b7b0d-257">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="b7b0d-258">Verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="b7b0d-258">Managed signature</span></span>  
  
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
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="b7b0d-259">Nicht verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="b7b0d-259">Unmanaged signature</span></span>  
  
```  
HRESULT New(long ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="b7b0d-260">Geschachtelte Arrays können nicht gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-260">Nested arrays cannot be marshaled.</span></span> <span data-ttu-id="b7b0d-261">Die folgende Signatur generiert beispielsweise einen Fehler, wenn sie mit dem [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-261">For example, the following signature generates an error when exported with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="b7b0d-262">Verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="b7b0d-262">Managed signature</span></span>  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="elementtypeclass-systemarray"></a><span data-ttu-id="b7b0d-263">ELEMENT_TYPE_CLASS \<System.Array></span><span class="sxs-lookup"><span data-stu-id="b7b0d-263">ELEMENT_TYPE_CLASS \<System.Array></span></span>  
 <span data-ttu-id="b7b0d-264">Wenn eine Methode, die einen <xref:System.Array?displayProperty=nameWithType>-Parameter enthält aus einer .NET-Assembly in eine Typbibliothek exportiert wird, wird der Arrayparameter in eine **_Array**-Schnittstelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-264">When a method containing a <xref:System.Array?displayProperty=nameWithType> parameter is exported from a .NET assembly to a type library, the array parameter is converted to an **_Array** interface.</span></span> <span data-ttu-id="b7b0d-265">Auf den Inhalt des verwalteten Arrays kann nur über die Methoden und Eigenschaften der **_Array**-Schnittstelle zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-265">The contents of the managed array are accessible only through the methods and properties of the **_Array** interface.</span></span> <span data-ttu-id="b7b0d-266">**System.Array** kann auch als **SAFEARRAY**, mithilfe von <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributen gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-266">**System.Array** can also be marshaled as a **SAFEARRAY** by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="b7b0d-267">Wenn die Arrayelemente als sicheres Array gemarshallt werden, werden sie als Varianten gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-267">When marshaled as a safe array, the array elements are marshaled as variants.</span></span> <span data-ttu-id="b7b0d-268">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b7b0d-268">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="b7b0d-269">Verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="b7b0d-269">Managed signature</span></span>  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="b7b0d-270">Nicht verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="b7b0d-270">Unmanaged signature</span></span>  
  
```  
HRESULT New([in] _Array *ar);   
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a><span data-ttu-id="b7b0d-271">Arrays in Strukturen</span><span class="sxs-lookup"><span data-stu-id="b7b0d-271">Arrays within Structures</span></span>  
 <span data-ttu-id="b7b0d-272">Nicht verwaltete Strukturen können eingebettete Arrays enthalten.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-272">Unmanaged structures can contain embedded arrays.</span></span> <span data-ttu-id="b7b0d-273">Standardmäßig werden diese eingebetteten Arrayfelder als SAFEARRAY gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-273">By default, these embedded array fields are marshaled as a SAFEARRAY.</span></span> <span data-ttu-id="b7b0d-274">Im folgenden Beispiel ist `s1` ein eingebettetes Array, das direkt innerhalb der Struktur selbst zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-274">In the following example, `s1` is an embedded array that is allocated directly within the structure itself.</span></span>  
  
#### <a name="unmanaged-representation"></a><span data-ttu-id="b7b0d-275">Nicht verwalteten Darstellung</span><span class="sxs-lookup"><span data-stu-id="b7b0d-275">Unmanaged representation</span></span>  
  
```  
struct MyStruct {  
    short s1[128];  
}  
```  
  
 <span data-ttu-id="b7b0d-276">Arrays können als <xref:System.Runtime.InteropServices.UnmanagedType> gemarshallt sein, was das Einrichten des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Felds voraussetzt.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-276">Arrays can be marshaled as <xref:System.Runtime.InteropServices.UnmanagedType>, which requires you to set the <xref:System.Runtime.InteropServices.MarshalAsAttribute> field.</span></span> <span data-ttu-id="b7b0d-277">Die Größe kann nur als eine Konstante festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-277">The size can be set only as a constant.</span></span> <span data-ttu-id="b7b0d-278">Der folgende Code zeigt die entsprechende verwaltete Definition von `MyStruct`.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-278">The following code shows the corresponding managed definition of `MyStruct`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b7b0d-279">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7b0d-279">See also</span></span>
- [<span data-ttu-id="b7b0d-280">Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)</span><span class="sxs-lookup"><span data-stu-id="b7b0d-280">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="b7b0d-281">Blitfähige und nicht blitfähige Typen</span><span class="sxs-lookup"><span data-stu-id="b7b0d-281">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="b7b0d-282">[Direktionale Attribute](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b7b0d-282">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="b7b0d-283">Kopieren und Fixieren</span><span class="sxs-lookup"><span data-stu-id="b7b0d-283">Copying and Pinning</span></span>](copying-and-pinning.md)
