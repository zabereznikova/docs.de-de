---
title: "Verarbeiten der XML-Datei (C# Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML processing [C#]
- XML [C#], processing
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 610f3ac5c88fb41a4b55f2990fecdc4c13074e19
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="processing-the-xml-file-c-programming-guide"></a><span data-ttu-id="80028-102">Verarbeiten der XML-Datei (C# Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="80028-102">Processing the XML File (C# Programming Guide)</span></span>
<span data-ttu-id="80028-103">Für jedes Konstrukt, das zum Generieren von Dokumentation gekennzeichnet ist, wird vom Compiler eine ID-Zeichenfolge generiert.</span><span class="sxs-lookup"><span data-stu-id="80028-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="80028-104">(Weitere Informationen darüber, wie Code mit Tags versehen werden kann, finden Sie unter [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).) Das Konstrukt wird über die ID-Zeichenfolge eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="80028-104">(For information about how to tag your code, see [Recommended Tags for Documentation Comments](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="80028-105">Programme, die die XML-Datei verarbeiten, können mithilfe der ID-Zeichenfolge das entsprechende .NET Framework-Metadaten-/Reflektionselement identifizieren, für das die Dokumentation gilt.</span><span class="sxs-lookup"><span data-stu-id="80028-105">Programs that process the XML file can use the ID string to identify the corresponding .NET Framework metadata/reflection item that the documentation applies to.</span></span>  
  
 <span data-ttu-id="80028-106">Die XML-Datei enthält keine hierarchische Darstellung des Codes. Es handelt sich um eine flache Liste mit einer generierten ID für jedes Element.</span><span class="sxs-lookup"><span data-stu-id="80028-106">The XML file is not a hierarchical representation of your code; it is a flat list that has a generated ID for each element.</span></span>  
  
 <span data-ttu-id="80028-107">Der Compiler beachtet beim Generieren der ID-Zeichenfolgen die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="80028-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
-   <span data-ttu-id="80028-108">Die Zeichenfolge darf keinen Leerraum enthalten.</span><span class="sxs-lookup"><span data-stu-id="80028-108">No whitespace is in the string.</span></span>  
  
-   <span data-ttu-id="80028-109">Der erste Teil der ID-Zeichenfolge kennzeichnet die Art des zu identifizierenden Members durch ein einzelnes Zeichen, gefolgt von einem Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="80028-109">The first part of the ID string identifies the kind of member being identified, by way of a single character followed by a colon.</span></span> <span data-ttu-id="80028-110">Die folgenden Membertypen werden verwendet:</span><span class="sxs-lookup"><span data-stu-id="80028-110">The following member types are used:</span></span>  
  
    |<span data-ttu-id="80028-111">Zeichen</span><span class="sxs-lookup"><span data-stu-id="80028-111">Character</span></span>|<span data-ttu-id="80028-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80028-112">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="80028-113">N</span><span class="sxs-lookup"><span data-stu-id="80028-113">N</span></span>|<span data-ttu-id="80028-114">namespace</span><span class="sxs-lookup"><span data-stu-id="80028-114">namespace</span></span><br /><br /> <span data-ttu-id="80028-115">Einem Namespace können keine Dokumentationskommentare hinzugefügt werden. Falls unterstützt, können jedoch cref-Verweise hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="80028-115">You cannot add documentation comments to a namespace, but you can make cref references to them, where supported.</span></span>|  
    |<span data-ttu-id="80028-116">T</span><span class="sxs-lookup"><span data-stu-id="80028-116">T</span></span>|<span data-ttu-id="80028-117">Typ: Klasse, Schnittstelle, Struktur, Enumeration, Delegat</span><span class="sxs-lookup"><span data-stu-id="80028-117">type: class, interface, struct, enum, delegate</span></span>|  
    |<span data-ttu-id="80028-118">F</span><span class="sxs-lookup"><span data-stu-id="80028-118">F</span></span>|<span data-ttu-id="80028-119">Feld</span><span class="sxs-lookup"><span data-stu-id="80028-119">field</span></span>|  
    |<span data-ttu-id="80028-120">P</span><span class="sxs-lookup"><span data-stu-id="80028-120">P</span></span>|<span data-ttu-id="80028-121">Eigenschaft (einschließlich von Indexern oder anderen indizierten Eigenschaften)</span><span class="sxs-lookup"><span data-stu-id="80028-121">property (including indexers or other indexed properties)</span></span>|  
    |<span data-ttu-id="80028-122">M</span><span class="sxs-lookup"><span data-stu-id="80028-122">M</span></span>|<span data-ttu-id="80028-123">Methode (einschließlich spezieller Methoden wie Konstruktoren, Operatoren usw.)</span><span class="sxs-lookup"><span data-stu-id="80028-123">method (including such special methods as constructors, operators, and so forth)</span></span>|  
    |<span data-ttu-id="80028-124">E</span><span class="sxs-lookup"><span data-stu-id="80028-124">E</span></span>|<span data-ttu-id="80028-125">event</span><span class="sxs-lookup"><span data-stu-id="80028-125">event</span></span>|  
    |<span data-ttu-id="80028-126">!</span><span class="sxs-lookup"><span data-stu-id="80028-126">!</span></span>|<span data-ttu-id="80028-127">Fehlerzeichenfolge</span><span class="sxs-lookup"><span data-stu-id="80028-127">error string</span></span><br /><br /> <span data-ttu-id="80028-128">Der verbleibende Teil der Zeichenfolge enthält Fehlerinformationen.</span><span class="sxs-lookup"><span data-stu-id="80028-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="80028-129">Vom C#-Compiler werden Fehlerinformationen für Links erstellt, die nicht aufgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="80028-129">The C# compiler generates error information for links that cannot be resolved.</span></span>|  
  
-   <span data-ttu-id="80028-130">Beim zweiten Teil der Zeichenfolge handelt es sich um den vollqualifizierten Namen eines Elements, beginnend mit dem Namespace-Stammverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="80028-130">The second part of the string is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="80028-131">Der Name des Elements, der oder die einschließenden Typen und der Namespace sind durch Punkte getrennt.</span><span class="sxs-lookup"><span data-stu-id="80028-131">The name of the item, its enclosing type(s), and namespace are separated by periods.</span></span> <span data-ttu-id="80028-132">Wenn der Name des Elements selbst Punkte enthält, werden sie durch ein Rautezeichen (#) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="80028-132">If the name of the item itself has periods, they are replaced by the hash-sign ('#').</span></span> <span data-ttu-id="80028-133">Es wird vorausgesetzt, dass kein Element direkt im Namen ein Rautezeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="80028-133">It is assumed that no item has a hash-sign directly in its name.</span></span> <span data-ttu-id="80028-134">Der vollqualifizierte Name des String-Konstruktors würde beispielsweise „System.String.#ctor“ lauten.</span><span class="sxs-lookup"><span data-stu-id="80028-134">For example, the fully qualified name of the String constructor would be "System.String.#ctor".</span></span>  
  
-   <span data-ttu-id="80028-135">Wenn es sich bei Eigenschaften und Methoden um Argumente der Methode handelt, folgt die in Klammern eingeschlossene Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="80028-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="80028-136">Wenn keine Argumente vorhanden sind, werden keine Klammern verwendet.</span><span class="sxs-lookup"><span data-stu-id="80028-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="80028-137">Die Argumente werden durch Kommas voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="80028-137">The arguments are separated by commas.</span></span> <span data-ttu-id="80028-138">Die Codierung jedes Arguments erfolgt genauso wie die Codierung in einer .NET Framework-Signatur:</span><span class="sxs-lookup"><span data-stu-id="80028-138">The encoding of each argument follows directly how it is encoded in a .NET Framework signature:</span></span>  
  
    -   <span data-ttu-id="80028-139">Basistypen.</span><span class="sxs-lookup"><span data-stu-id="80028-139">Base types.</span></span> <span data-ttu-id="80028-140">Reguläre Typen (ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE) werden als vollqualifizierter Name des Typs dargestellt.</span><span class="sxs-lookup"><span data-stu-id="80028-140">Regular types (ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE) are represented as the fully qualified name of the type.</span></span>  
  
    -   <span data-ttu-id="80028-141">Systeminterne Typen (z.B. ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF</span><span class="sxs-lookup"><span data-stu-id="80028-141">Intrinsic types (for example, ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF.</span></span> <span data-ttu-id="80028-142">und ELEMENT_TYPE_VOID) werden als vollqualifizierter Name des entsprechenden vollständigen Typs dargestellt.</span><span class="sxs-lookup"><span data-stu-id="80028-142">and ELEMENT_TYPE_VOID) are represented as the fully qualified name of the corresponding full type.</span></span> <span data-ttu-id="80028-143">Als Beispiel sei hier System.Int32 oder System.TypedReference genannt.</span><span class="sxs-lookup"><span data-stu-id="80028-143">For example, System.Int32 or System.TypedReference.</span></span>  
  
    -   <span data-ttu-id="80028-144">ELEMENT_TYPE_PTR wird als * dargestellt, das auf den geänderten Typ folgt.</span><span class="sxs-lookup"><span data-stu-id="80028-144">ELEMENT_TYPE_PTR is represented as a '*' following the modified type.</span></span>  
  
    -   <span data-ttu-id="80028-145">ELEMENT_TYPE_BYREF wird als @ dargestellt, das auf den geänderten Typ folgt.</span><span class="sxs-lookup"><span data-stu-id="80028-145">ELEMENT_TYPE_BYREF is represented as a '@' following the modified type.</span></span>  
  
    -   <span data-ttu-id="80028-146">ELEMENT_TYPE_PINNED wird als ^ dargestellt, das auf den geänderten Typ folgt.</span><span class="sxs-lookup"><span data-stu-id="80028-146">ELEMENT_TYPE_PINNED is represented as a '^' following the modified type.</span></span> <span data-ttu-id="80028-147">Dies wird nie vom C#-Compiler generiert.</span><span class="sxs-lookup"><span data-stu-id="80028-147">The C# compiler never generates this.</span></span>  
  
    -   <span data-ttu-id="80028-148">ELEMENT_TYPE_CMOD_REQ wird als &#124; und vollqualifizierter Name der Modifiziererklasse dargestellt, das bzw. der auf den geänderten Typ folgt.</span><span class="sxs-lookup"><span data-stu-id="80028-148">ELEMENT_TYPE_CMOD_REQ is represented as a '&#124;' and the fully qualified name of the modifier class, following the modified type.</span></span> <span data-ttu-id="80028-149">Dies wird nie vom C#-Compiler generiert.</span><span class="sxs-lookup"><span data-stu-id="80028-149">The C# compiler never generates this.</span></span>  
  
    -   <span data-ttu-id="80028-150">ELEMENT_TYPE_CMOD_OPT wird als ! mit nachstehendem vollqualifizierten Namen der Modifiziererklasse dargestellt, das auf den geänderten Typ folgt.</span><span class="sxs-lookup"><span data-stu-id="80028-150">ELEMENT_TYPE_CMOD_OPT is represented as a '!' and the fully qualified name of the modifier class, following the modified type.</span></span>  
  
    -   <span data-ttu-id="80028-151">ELEMENT_TYPE_SZARRAY wird als [] dargestellt, das auf den Elementtyp des Arrays folgt.</span><span class="sxs-lookup"><span data-stu-id="80028-151">ELEMENT_TYPE_SZARRAY is represented as "[]" following the element type of the array.</span></span>  
  
    -   <span data-ttu-id="80028-152">ELEMENT_TYPE_GENERICARRAY wird als [?] dargestellt, das auf den Elementtyp des Arrays folgt.</span><span class="sxs-lookup"><span data-stu-id="80028-152">ELEMENT_TYPE_GENERICARRAY is represented as "[?]" following the element type of the array.</span></span> <span data-ttu-id="80028-153">Dies wird nie vom C#-Compiler generiert.</span><span class="sxs-lookup"><span data-stu-id="80028-153">The C# compiler never generates this.</span></span>  
  
    -   <span data-ttu-id="80028-154">ELEMENT_TYPE_ARRAY wird als [*lowerbound*:`size`,*lowerbound*:`size`] dargestellt, wobei die Anzahl von Kommas als Rang minus 1 berechnet wird und die untere Grenze sowie die Größe jeder Dimension – sofern bekannt – dezimal dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="80028-154">ELEMENT_TYPE_ARRAY is represented as [*lowerbound*:`size`,*lowerbound*:`size`] where the number of commas is the rank - 1, and the lower bounds and size of each dimension, if known, are represented in decimal.</span></span> <span data-ttu-id="80028-155">Wenn die untere Grenze oder die Größe nicht angegeben ist, wird sie einfach ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="80028-155">If a lower bound or size is not specified, it is simply omitted.</span></span> <span data-ttu-id="80028-156">Wenn die untere Grenze und die Größe für eine bestimmte Dimension ausgelassen werden, kann der Doppelpunkt (:) ebenfalls ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="80028-156">If the lower bound and size for a particular dimension are omitted, the ':' is omitted as well.</span></span> <span data-ttu-id="80028-157">[1:,1:] ist beispielsweise ein zweidimensionales Array mit 1 als unterer Grenze und nicht angegebenen Größen.</span><span class="sxs-lookup"><span data-stu-id="80028-157">For example, a 2-dimensional array with 1 as the lower bounds and unspecified sizes is [1:,1:].</span></span>  
  
    -   <span data-ttu-id="80028-158">ELEMENT_TYPE_FNPTR wird als „=FUNC:`type`(*signature*)“ dargestellt, wobei `type` den Rückgabetyp angibt und es sich bei *signature* um die Argumente der Methode handelt.</span><span class="sxs-lookup"><span data-stu-id="80028-158">ELEMENT_TYPE_FNPTR is represented as "=FUNC:`type`(*signature*)", where `type` is the return type, and *signature* is the arguments of the method.</span></span> <span data-ttu-id="80028-159">Sind keine Argumente vorhanden, werden keine Klammern verwendet.</span><span class="sxs-lookup"><span data-stu-id="80028-159">If there are no arguments, the parentheses are omitted.</span></span> <span data-ttu-id="80028-160">Dies wird nie vom C#-Compiler generiert.</span><span class="sxs-lookup"><span data-stu-id="80028-160">The C# compiler never generates this.</span></span>  
  
     <span data-ttu-id="80028-161">Die folgenden Signaturkomponenten werden nicht dargestellt, weil sie nicht zur Unterscheidung überladener Methoden verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="80028-161">The following signature components are not represented because they are never used for differentiating overloaded methods:</span></span>  
  
    -   <span data-ttu-id="80028-162">Aufrufkonvention</span><span class="sxs-lookup"><span data-stu-id="80028-162">calling convention</span></span>  
  
    -   <span data-ttu-id="80028-163">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="80028-163">return type</span></span>  
  
    -   <span data-ttu-id="80028-164">ELEMENT_TYPE_SENTINEL</span><span class="sxs-lookup"><span data-stu-id="80028-164">ELEMENT_TYPE_SENTINEL</span></span>  
  
-   <span data-ttu-id="80028-165">Nur für Konvertierungsoperatoren („op_Implicit“ und „op_Explicit“) wird der Rückgabewert der Methode als ~ gefolgt vom Rückgabewert codiert, wie weiter oben gezeigt.</span><span class="sxs-lookup"><span data-stu-id="80028-165">For conversion operators only (op_Implicit and op_Explicit), the return value of the method is encoded as a '~' followed by the return type, as encoded above.</span></span>  
  
-   <span data-ttu-id="80028-166">Bei generischen Typen folgt auf den Namen des Typs ein Graviszeichen und dann eine Zahl, mit der die Anzahl generischer Typparameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="80028-166">For generic types, the name of the type will be followed by a back tick and then a number that indicates the number of generic type parameters.</span></span>  <span data-ttu-id="80028-167">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80028-167">For example,</span></span>  
  
     <span data-ttu-id="80028-168">`<member name="T:SampleClass`2">` is the tag for a type that is defined as `public class SampleClass\<T, U>\`.</span><span class="sxs-lookup"><span data-stu-id="80028-168">`<member name="T:SampleClass`2">` is the tag for a type that is defined as `public class SampleClass\<T, U>\`.</span></span>  
  
     <span data-ttu-id="80028-169">Bei Methoden, die generische Typen als Parameter verwenden, werden die generischen Parameter des Typs als Zahlen mit vorangestelltem Graviszeichen angegeben (z.B. \`0,`1).</span><span class="sxs-lookup"><span data-stu-id="80028-169">For methods taking generic types as parameters, the generic type parameters are specified as numbers prefaced with back ticks (for example \`0,`1).</span></span>  <span data-ttu-id="80028-170">Jede Zahl stellt eine bei 0 beginnende Arraynotation für die generischen Parameter des Typs dar.</span><span class="sxs-lookup"><span data-stu-id="80028-170">Each number representing a zero-based array notation for the type's generic parameters.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="80028-171">Beispiele</span><span class="sxs-lookup"><span data-stu-id="80028-171">Examples</span></span>  
 <span data-ttu-id="80028-172">Die folgenden Beispiele zeigen, wie die ID-Zeichenfolgen für eine Klasse und ihre Member generiert werden würden:</span><span class="sxs-lookup"><span data-stu-id="80028-172">The following examples show how the ID strings for a class and its members would be generated:</span></span>  
  
 <span data-ttu-id="80028-173">[!code-cs[csProgGuidePointers#21](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/processing-the-xml-file_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="80028-173">[!code-cs[csProgGuidePointers#21](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/processing-the-xml-file_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80028-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80028-174">See Also</span></span>  
 <span data-ttu-id="80028-175">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="80028-175">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="80028-176">[/doc (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="80028-176">[/doc (C# Compiler Options)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span></span>  
 [<span data-ttu-id="80028-177">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="80028-177">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

