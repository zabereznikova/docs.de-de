---
title: Attribute (C#)
ms.date: 04/26/2018
ms.openlocfilehash: 62424163303417746a67707d9ef34185954db316
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389539"
---
# <a name="attributes-c"></a><span data-ttu-id="6c1bd-102">Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="6c1bd-102">Attributes (C#)</span></span>

<span data-ttu-id="6c1bd-103">Attribute stellen eine effiziente Methode dar, Metadaten oder deklarative Informationen Code (Assemblys, Typen, Methoden, Eigenschaften usw.) zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="6c1bd-104">Nach dem Zuordnen eines Attributs zu einer Programmentität kann das Attribut zur Laufzeit mit einer Technik namens *Reflektion* abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="6c1bd-105">Weitere Informationen finden Sie unter [Reflektion (C#)](../reflection.md).</span><span class="sxs-lookup"><span data-stu-id="6c1bd-105">For more information, see [Reflection (C#)](../reflection.md).</span></span>

<span data-ttu-id="6c1bd-106">Attribute verfügen über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="6c1bd-106">Attributes have the following properties:</span></span>

- <span data-ttu-id="6c1bd-107">Attribute fügen Metadaten zu Ihrem Programm hinzu.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="6c1bd-108">*Metadaten* sind Informationen zu den Typen, die in einem Programm definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="6c1bd-109">Alle .NET-Assemblys enthalten einen festgelegten Satz von Metadaten, der die Typen und Typmember beschreibt, die in der Assembly definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="6c1bd-110">Sie können benutzerdefinierte Attribute hinzufügen, um zusätzliche erforderliche Informationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="6c1bd-111">Weitere Informationen finden Sie unter [Erstellen benutzerdefinierter Attribute (C#)](creating-custom-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="6c1bd-111">For more information, see, [Creating Custom Attributes (C#)](creating-custom-attributes.md).</span></span>
- <span data-ttu-id="6c1bd-112">Sie können eines oder mehrere Attribute auf ganze Assemblys, Module oder kleinere Programmelemente wie Klassen und Eigenschaften anwenden.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>
- <span data-ttu-id="6c1bd-113">Attribute können Argumente auf die gleiche Art wie Methoden und Eigenschaften akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-113">Attributes can accept arguments in the same way as methods and properties.</span></span>
- <span data-ttu-id="6c1bd-114">Das Programm kann seine eigenen Metadaten oder die Metadaten in anderen Programmen mithilfe der Reflektion untersuchen.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="6c1bd-115">Weitere Informationen finden Sie unter [Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))](accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="6c1bd-115">For more information, see [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="using-attributes"></a><span data-ttu-id="6c1bd-116">Verwenden von Attributen</span><span class="sxs-lookup"><span data-stu-id="6c1bd-116">Using attributes</span></span>

<span data-ttu-id="6c1bd-117">Attribute können in nahezu jeder Deklaration platziert werden, auch wenn ein bestimmtes Attribut die Typen der Deklarationen einschränkt, für die es gültig ist.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="6c1bd-118">In C# geben Sie ein Attribut durch Angabe des Namens des Attributs an, eingeschlossen in eckigen Klammern ([]), oberhalb der Deklaration der Entität, auf die es angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-118">In C#, you specify an attribute by placing the name of the attribute enclosed in square brackets ([]) above the declaration of the entity to which it applies.</span></span>

<span data-ttu-id="6c1bd-119">In diesem Beispiel wird das Attribut <xref:System.SerializableAttribute> benutzt, um ein spezifisches Merkmal auf eine Klasse anzuwenden:</span><span class="sxs-lookup"><span data-stu-id="6c1bd-119">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>

[!code-csharp[Using the serializable attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#1)]

<span data-ttu-id="6c1bd-120">Eine Methode mit dem Attribut <xref:System.Runtime.InteropServices.DllImportAttribute> wird wie im folgenden Beispiel deklariert:</span><span class="sxs-lookup"><span data-stu-id="6c1bd-120">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like the following example:</span></span>

[!code-csharp[Declaring a method to import from an external library](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#2)]

<span data-ttu-id="6c1bd-121">Mehrere Attribute können in einer Deklaration platziert werden, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="6c1bd-121">More than one attribute can be placed on a declaration as the following example shows:</span></span>

[!code-csharp[Including the interop namespace](~/samples/snippets/csharp/attributes/AttributesOverview.cs#3)]
[!code-csharp[Declaring two way marshaling for arguments](~/samples/snippets/csharp/attributes/AttributesOverview.cs#4)]

<span data-ttu-id="6c1bd-122">Einige Attribute können für eine bestimmte Entität mehrmals angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-122">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="6c1bd-123">Ein Beispiel für ein solches mehrfach verwendbares Attribut ist <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="6c1bd-123">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>

[!code-csharp[Using the conditional attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#5)]

> [!NOTE]
> <span data-ttu-id="6c1bd-124">Alle Attributnamen enden laut Konvention mit dem Wort „Attribute“, um sie von anderen Elementen in .NET-Bibliotheken zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-124">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET libraries.</span></span> <span data-ttu-id="6c1bd-125">Sie müssen das Attributsuffix allerdings nicht angeben, wenn Sie Attribute im Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-125">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="6c1bd-126">Beispiel: `[DllImport]` entspricht `[DllImportAttribute]`, aber `DllImportAttribute` ist der tatsächliche Name des Attributs in der .NET Framework-Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-126">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework Class Library.</span></span>

### <a name="attribute-parameters"></a><span data-ttu-id="6c1bd-127">Attributparameter</span><span class="sxs-lookup"><span data-stu-id="6c1bd-127">Attribute parameters</span></span>

<span data-ttu-id="6c1bd-128">Viele Attribute weisen Parameter auf, die positional, unbenannt der benannt sein können.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-128">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="6c1bd-129">Alle positionalen Parameter müssen in einer bestimmten Reihenfolge angegeben werden und können nicht weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-129">Any positional parameters must be specified in a certain order and cannot be omitted.</span></span> <span data-ttu-id="6c1bd-130">Benannte Parameter sind optional und können in beliebiger Reihenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-130">Named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="6c1bd-131">Positionale Parameter werden zuerst angegeben.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-131">Positional parameters are specified first.</span></span> <span data-ttu-id="6c1bd-132">Die folgenden drei Attribute sind beispielsweise äquivalent:</span><span class="sxs-lookup"><span data-stu-id="6c1bd-132">For example, these three attributes are equivalent:</span></span>

```csharp
[DllImport("user32.dll")]
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]
```

<span data-ttu-id="6c1bd-133">Der erste Parameter, der DLL-Name, ist positional und kommt immer an erster Stelle. Die anderen sind benannt.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-133">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="6c1bd-134">In diesem Fall werden beide benannten Parameter standardmäßig auf „false“ festgelegt und können daher ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-134">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="6c1bd-135">Positionale Parameter entsprechen den Parametern des Attributkonstruktors.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-135">Positional parameters correspond to the parameters of the attribute constructor.</span></span> <span data-ttu-id="6c1bd-136">Benannte oder optionale Parameter entsprechen den Eigenschaften oder Feldern des Attributs.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-136">Named or optional parameters correspond to either properties or fields of the attribute.</span></span> <span data-ttu-id="6c1bd-137">In der Dokumentation des individuellen Attributs finden Sie Informationen zu Standardparameterwerten.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-137">Refer to the individual attribute's documentation for information on default parameter values.</span></span>

### <a name="attribute-targets"></a><span data-ttu-id="6c1bd-138">Attributziele</span><span class="sxs-lookup"><span data-stu-id="6c1bd-138">Attribute targets</span></span>

<span data-ttu-id="6c1bd-139">Das *Ziel* eines Attributs ist die Entität, auf die das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-139">The *target* of an attribute is the entity which the attribute applies to.</span></span> <span data-ttu-id="6c1bd-140">Ein Attribut kann beispielsweise auf eine Klasse, eine bestimmte Methode oder eine ganze Assembly angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-140">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="6c1bd-141">Standardmäßig wird ein Attribut auf das darauffolgende Element angewendet.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-141">By default, an attribute applies to the element that follows it.</span></span> <span data-ttu-id="6c1bd-142">Sie können allerdings auch explizit festlegen, dass ein Attribut beispielsweise auf eine Methode, ihren Parameter oder ihren Rückgabewert angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-142">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>

<span data-ttu-id="6c1bd-143">Verwenden Sie die folgende Syntax, um ein Attributziel explizit zu kennzeichnen:</span><span class="sxs-lookup"><span data-stu-id="6c1bd-143">To explicitly identify an attribute target, use the following syntax:</span></span>

```csharp
[target : attribute-list]
```

<span data-ttu-id="6c1bd-144">Die Liste der möglichen `target`-Werte wird in der folgenden Tabelle gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6c1bd-144">The list of possible `target` values is shown in the following table.</span></span>

|<span data-ttu-id="6c1bd-145">Zielwert</span><span class="sxs-lookup"><span data-stu-id="6c1bd-145">Target value</span></span>|<span data-ttu-id="6c1bd-146">Betrifft</span><span class="sxs-lookup"><span data-stu-id="6c1bd-146">Applies to</span></span>|
|------------------|----------------|
|`assembly`|<span data-ttu-id="6c1bd-147">Gesamte Assembly</span><span class="sxs-lookup"><span data-stu-id="6c1bd-147">Entire assembly</span></span>|
|`module`|<span data-ttu-id="6c1bd-148">Aktuelle Assemblymodul</span><span class="sxs-lookup"><span data-stu-id="6c1bd-148">Current assembly module</span></span>|
|`field`|<span data-ttu-id="6c1bd-149">Feld in einer Klasse oder Struktur</span><span class="sxs-lookup"><span data-stu-id="6c1bd-149">Field in a class or a struct</span></span>|
|`event`|<span data-ttu-id="6c1bd-150">event</span><span class="sxs-lookup"><span data-stu-id="6c1bd-150">Event</span></span>|
|`method`|<span data-ttu-id="6c1bd-151">Methode oder `get`- und `set`-Eigenschaftenaccessors</span><span class="sxs-lookup"><span data-stu-id="6c1bd-151">Method or `get` and `set` property accessors</span></span>|
|`param`|<span data-ttu-id="6c1bd-152">Methodenparameter oder `set`-Parameter des Eigenschaftenaccessors</span><span class="sxs-lookup"><span data-stu-id="6c1bd-152">Method parameters or `set` property accessor parameters</span></span>|
|`property`|<span data-ttu-id="6c1bd-153">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6c1bd-153">Property</span></span>|
|`return`|<span data-ttu-id="6c1bd-154">Rückgabewert einer Methode, Eigenschaftenindexer oder `get`-Eigenschaftenaccessor</span><span class="sxs-lookup"><span data-stu-id="6c1bd-154">Return value of a method, property indexer, or `get` property accessor</span></span>|
|`type`|<span data-ttu-id="6c1bd-155">Struktur, Klasse, Schnittstelle, Enumeration oder Delegat</span><span class="sxs-lookup"><span data-stu-id="6c1bd-155">Struct, class, interface, enum, or delegate</span></span>|

<span data-ttu-id="6c1bd-156">Geben Sie den `field`-Zielwert an, um ein Attribut auf das für eine [automatisch implementierte Eigenschaft](../../../properties.md) erstellte Unterstützungsfeld anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-156">You would specify the `field` target value to apply an attribute to the backing field created for an [auto-implemented property](../../../properties.md).</span></span>

<span data-ttu-id="6c1bd-157">Im folgenden Beispiel wird veranschaulicht, wie Attribute auf Assemblys und Module angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-157">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="6c1bd-158">Weitere Informationen finden Sie unter [Allgemeine Attribute (C#)](common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="6c1bd-158">For more information, see [Common Attributes (C#)](common-attributes.md).</span></span>

```csharp
using System;
using System.Reflection;
[assembly: AssemblyTitleAttribute("Production assembly 4")]
[module: CLSCompliant(true)]
```

<span data-ttu-id="6c1bd-159">Im folgenden Beispiel wird gezeigt, wie Attribute auf Methoden, Methodenparameter und Methodenrückgabewerte in C# angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-159">The following example shows how to apply attributes to methods, method parameters, and method return values in C#.</span></span>

[!code-csharp[Applying attributes to different code elements](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#6)]

> [!NOTE]
> <span data-ttu-id="6c1bd-160">Unabhängig von den Zielen, auf denen `ValidatedContract` definiert wird, um gültig zu sein, muss das Ziel `return` angegeben werden, selbst wenn `ValidatedContract` nur für die Rückgabewerte definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-160">Regardless of the targets on which `ValidatedContract` is defined to be valid, the `return` target has to be specified, even if `ValidatedContract` were defined to apply only to return values.</span></span> <span data-ttu-id="6c1bd-161">Das heißt, der Compiler verwendet keine `AttributeUsage`-Informationen zum Auflösen von mehrdeutigen Attributzielen.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-161">In other words, the compiler will not use `AttributeUsage` information to resolve ambiguous attribute targets.</span></span> <span data-ttu-id="6c1bd-162">Weitere Informationen finden Sie unter [AttributeUsage (C#)](../../../language-reference/attributes/general.md).</span><span class="sxs-lookup"><span data-stu-id="6c1bd-162">For more information, see [AttributeUsage (C#)](../../../language-reference/attributes/general.md).</span></span>

## <a name="common-uses-for-attributes"></a><span data-ttu-id="6c1bd-163">Häufige Verwendungsmöglichkeiten für Attribute</span><span class="sxs-lookup"><span data-stu-id="6c1bd-163">Common uses for attributes</span></span>

<span data-ttu-id="6c1bd-164">Die folgende Liste enthält einige häufige Verwendungsmöglichkeiten von Attributen im Code:</span><span class="sxs-lookup"><span data-stu-id="6c1bd-164">The following list includes a few of the common uses of attributes in code:</span></span>

- <span data-ttu-id="6c1bd-165">Kennzeichnen von Methoden mit dem `WebMethod`-Attribut in Webdiensten, um anzugeben, dass die Methode über das SOAP-Protokoll aufrufbar sein sollte.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-165">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="6c1bd-166">Weitere Informationen finden Sie unter <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-166">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>
- <span data-ttu-id="6c1bd-167">Beschreiben, wie Methodenparameter bei der Interaktion mit systemeigenem Code gemarshallt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-167">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="6c1bd-168">Weitere Informationen finden Sie unter <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-168">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>
- <span data-ttu-id="6c1bd-169">Beschreiben der COM-Eigenschaften für Klassen, Methoden und Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-169">Describing the COM properties for classes, methods, and interfaces.</span></span>
- <span data-ttu-id="6c1bd-170">Aufrufen von nicht verwaltetem Code mithilfe der Klasse <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-170">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>
- <span data-ttu-id="6c1bd-171">Beschreiben der Assembly im Hinblick auf Titel, Version, Beschreibung oder Marke.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-171">Describing your assembly in terms of title, version, description, or trademark.</span></span>
- <span data-ttu-id="6c1bd-172">Beschreiben, welche Member einer Klasse zur Verbesserung der Dauerhaftigkeit serialisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-172">Describing which members of a class to serialize for persistence.</span></span>
- <span data-ttu-id="6c1bd-173">Beschreiben der Zuordnung zwischen Klassenmembern und XML-Knoten für die XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-173">Describing how to map between class members and XML nodes for XML serialization.</span></span>
- <span data-ttu-id="6c1bd-174">Beschreiben der Sicherheitsanforderungen für Methoden.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-174">Describing the security requirements for methods.</span></span>
- <span data-ttu-id="6c1bd-175">Angeben von Eigenschaften zum Erzwingen der Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-175">Specifying characteristics used to enforce security.</span></span>
- <span data-ttu-id="6c1bd-176">Steuern der vom JIT-Compiler (Just-In-Time-Compiler) ausgeführten Optimierungen, damit der Code weiterhin problemlos debuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-176">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>
- <span data-ttu-id="6c1bd-177">Abrufen von Informationen zum Aufrufer einer Methode.</span><span class="sxs-lookup"><span data-stu-id="6c1bd-177">Obtaining information about the caller to a method.</span></span>

## <a name="related-sections"></a><span data-ttu-id="6c1bd-178">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="6c1bd-178">Related sections</span></span>

<span data-ttu-id="6c1bd-179">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="6c1bd-179">For more information, see:</span></span>

- [<span data-ttu-id="6c1bd-180">Erstellen benutzerdefinierter Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="6c1bd-180">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)  
- [<span data-ttu-id="6c1bd-181">Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))</span><span class="sxs-lookup"><span data-stu-id="6c1bd-181">Accessing Attributes by Using Reflection (C#)</span></span>](accessing-attributes-by-using-reflection.md)  
- [<span data-ttu-id="6c1bd-182">Erstellen einer Union in C/C++ mit Attributen (C#)</span><span class="sxs-lookup"><span data-stu-id="6c1bd-182">How to create a C/C++ union by using attributes (C#)</span></span>](how-to-create-a-c-cpp-union-by-using-attributes.md)  
- [<span data-ttu-id="6c1bd-183">Allgemeine Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="6c1bd-183">Common Attributes (C#)</span></span>](common-attributes.md)  
- [<span data-ttu-id="6c1bd-184">Aufruferinformationen (C#)</span><span class="sxs-lookup"><span data-stu-id="6c1bd-184">Caller Information (C#)</span></span>](../../../language-reference/attributes/caller-information.md)  

## <a name="see-also"></a><span data-ttu-id="6c1bd-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c1bd-185">See also</span></span>

- [<span data-ttu-id="6c1bd-186">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6c1bd-186">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="6c1bd-187">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="6c1bd-187">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="6c1bd-188">Attribute</span><span class="sxs-lookup"><span data-stu-id="6c1bd-188">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="6c1bd-189">Verwenden von Attributen in C#</span><span class="sxs-lookup"><span data-stu-id="6c1bd-189">Using Attributes in C#</span></span>](../../../tutorials/attributes.md)
