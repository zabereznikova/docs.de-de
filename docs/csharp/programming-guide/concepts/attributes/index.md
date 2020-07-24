---
title: Attribute (C#)
description: Erfahren Sie, wie Sie Attribute verwenden, um Metadaten oder deklarative Informationen mit Code in C# zu verknüpfen. Ein Attribut kann mithilfe der Reflexion zur Laufzeit abgefragt werden.
ms.date: 04/26/2018
ms.openlocfilehash: 5c57838b649531d8e8fe89919771adf8830e7f54
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924984"
---
# <a name="attributes-c"></a><span data-ttu-id="1db3f-104">Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="1db3f-104">Attributes (C#)</span></span>

<span data-ttu-id="1db3f-105">Attribute stellen eine effiziente Methode dar, Metadaten oder deklarative Informationen Code (Assemblys, Typen, Methoden, Eigenschaften usw.) zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="1db3f-105">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="1db3f-106">Nach dem Zuordnen eines Attributs zu einer Programmentität kann das Attribut zur Laufzeit mit einer Technik namens *Reflektion* abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="1db3f-106">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="1db3f-107">Weitere Informationen finden Sie unter [Reflektion (C#)](../reflection.md).</span><span class="sxs-lookup"><span data-stu-id="1db3f-107">For more information, see [Reflection (C#)](../reflection.md).</span></span>

<span data-ttu-id="1db3f-108">Attribute verfügen über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="1db3f-108">Attributes have the following properties:</span></span>

- <span data-ttu-id="1db3f-109">Attribute fügen Metadaten zu Ihrem Programm hinzu.</span><span class="sxs-lookup"><span data-stu-id="1db3f-109">Attributes add metadata to your program.</span></span> <span data-ttu-id="1db3f-110">*Metadaten* sind Informationen zu den Typen, die in einem Programm definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1db3f-110">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="1db3f-111">Alle .NET-Assemblys enthalten einen festgelegten Satz von Metadaten, der die Typen und Typmember beschreibt, die in der Assembly definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1db3f-111">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="1db3f-112">Sie können benutzerdefinierte Attribute hinzufügen, um zusätzliche erforderliche Informationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1db3f-112">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="1db3f-113">Weitere Informationen finden Sie unter [Erstellen benutzerdefinierter Attribute (C#)](creating-custom-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="1db3f-113">For more information, see, [Creating Custom Attributes (C#)](creating-custom-attributes.md).</span></span>
- <span data-ttu-id="1db3f-114">Sie können eines oder mehrere Attribute auf ganze Assemblys, Module oder kleinere Programmelemente wie Klassen und Eigenschaften anwenden.</span><span class="sxs-lookup"><span data-stu-id="1db3f-114">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>
- <span data-ttu-id="1db3f-115">Attribute können Argumente auf die gleiche Art wie Methoden und Eigenschaften akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="1db3f-115">Attributes can accept arguments in the same way as methods and properties.</span></span>
- <span data-ttu-id="1db3f-116">Das Programm kann seine eigenen Metadaten oder die Metadaten in anderen Programmen mithilfe der Reflektion untersuchen.</span><span class="sxs-lookup"><span data-stu-id="1db3f-116">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="1db3f-117">Weitere Informationen finden Sie unter [Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))](accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="1db3f-117">For more information, see [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="using-attributes"></a><span data-ttu-id="1db3f-118">Verwenden von Attributen</span><span class="sxs-lookup"><span data-stu-id="1db3f-118">Using attributes</span></span>

<span data-ttu-id="1db3f-119">Attribute können in nahezu jeder Deklaration platziert werden, auch wenn ein bestimmtes Attribut die Typen der Deklarationen einschränkt, für die es gültig ist.</span><span class="sxs-lookup"><span data-stu-id="1db3f-119">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="1db3f-120">In C# geben Sie ein Attribut durch Angabe des Namens des Attributs an, eingeschlossen in eckigen Klammern ([]), oberhalb der Deklaration der Entität, auf die es angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1db3f-120">In C#, you specify an attribute by placing the name of the attribute enclosed in square brackets ([]) above the declaration of the entity to which it applies.</span></span>

<span data-ttu-id="1db3f-121">In diesem Beispiel wird das Attribut <xref:System.SerializableAttribute> benutzt, um ein spezifisches Merkmal auf eine Klasse anzuwenden:</span><span class="sxs-lookup"><span data-stu-id="1db3f-121">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>

[!code-csharp[Using the serializable attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#1)]

<span data-ttu-id="1db3f-122">Eine Methode mit dem Attribut <xref:System.Runtime.InteropServices.DllImportAttribute> wird wie im folgenden Beispiel deklariert:</span><span class="sxs-lookup"><span data-stu-id="1db3f-122">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like the following example:</span></span>

[!code-csharp[Declaring a method to import from an external library](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#2)]

<span data-ttu-id="1db3f-123">Mehrere Attribute können in einer Deklaration platziert werden, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1db3f-123">More than one attribute can be placed on a declaration as the following example shows:</span></span>

[!code-csharp[Including the interop namespace](~/samples/snippets/csharp/attributes/AttributesOverview.cs#3)]
[!code-csharp[Declaring two way marshaling for arguments](~/samples/snippets/csharp/attributes/AttributesOverview.cs#4)]

<span data-ttu-id="1db3f-124">Einige Attribute können für eine bestimmte Entität mehrmals angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1db3f-124">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="1db3f-125">Ein Beispiel für ein solches mehrfach verwendbares Attribut ist <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="1db3f-125">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>

[!code-csharp[Using the conditional attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#5)]

> [!NOTE]
> <span data-ttu-id="1db3f-126">Alle Attributnamen enden laut Konvention mit dem Wort „Attribute“, um sie von anderen Elementen in .NET-Bibliotheken zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="1db3f-126">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET libraries.</span></span> <span data-ttu-id="1db3f-127">Sie müssen das Attributsuffix allerdings nicht angeben, wenn Sie Attribute im Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="1db3f-127">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="1db3f-128">Beispiel: `[DllImport]` entspricht `[DllImportAttribute]`, aber `DllImportAttribute` ist der tatsächliche Name des Attributs in der .NET-Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="1db3f-128">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Class Library.</span></span>

### <a name="attribute-parameters"></a><span data-ttu-id="1db3f-129">Attributparameter</span><span class="sxs-lookup"><span data-stu-id="1db3f-129">Attribute parameters</span></span>

<span data-ttu-id="1db3f-130">Viele Attribute weisen Parameter auf, die positional, unbenannt der benannt sein können.</span><span class="sxs-lookup"><span data-stu-id="1db3f-130">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="1db3f-131">Alle positionalen Parameter müssen in einer bestimmten Reihenfolge angegeben werden und können nicht weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="1db3f-131">Any positional parameters must be specified in a certain order and cannot be omitted.</span></span> <span data-ttu-id="1db3f-132">Benannte Parameter sind optional und können in beliebiger Reihenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1db3f-132">Named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="1db3f-133">Positionale Parameter werden zuerst angegeben.</span><span class="sxs-lookup"><span data-stu-id="1db3f-133">Positional parameters are specified first.</span></span> <span data-ttu-id="1db3f-134">Die folgenden drei Attribute sind beispielsweise äquivalent:</span><span class="sxs-lookup"><span data-stu-id="1db3f-134">For example, these three attributes are equivalent:</span></span>

```csharp
[DllImport("user32.dll")]
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]
```

<span data-ttu-id="1db3f-135">Der erste Parameter, der DLL-Name, ist positional und kommt immer an erster Stelle. Die anderen sind benannt.</span><span class="sxs-lookup"><span data-stu-id="1db3f-135">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="1db3f-136">In diesem Fall werden beide benannten Parameter standardmäßig auf „false“ festgelegt und können daher ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="1db3f-136">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="1db3f-137">Positionale Parameter entsprechen den Parametern des Attributkonstruktors.</span><span class="sxs-lookup"><span data-stu-id="1db3f-137">Positional parameters correspond to the parameters of the attribute constructor.</span></span> <span data-ttu-id="1db3f-138">Benannte oder optionale Parameter entsprechen den Eigenschaften oder Feldern des Attributs.</span><span class="sxs-lookup"><span data-stu-id="1db3f-138">Named or optional parameters correspond to either properties or fields of the attribute.</span></span> <span data-ttu-id="1db3f-139">In der Dokumentation des individuellen Attributs finden Sie Informationen zu Standardparameterwerten.</span><span class="sxs-lookup"><span data-stu-id="1db3f-139">Refer to the individual attribute's documentation for information on default parameter values.</span></span>

### <a name="attribute-targets"></a><span data-ttu-id="1db3f-140">Attributziele</span><span class="sxs-lookup"><span data-stu-id="1db3f-140">Attribute targets</span></span>

<span data-ttu-id="1db3f-141">Das *Ziel* eines Attributs ist die Entität, auf die das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1db3f-141">The *target* of an attribute is the entity which the attribute applies to.</span></span> <span data-ttu-id="1db3f-142">Ein Attribut kann beispielsweise auf eine Klasse, eine bestimmte Methode oder eine ganze Assembly angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1db3f-142">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="1db3f-143">Standardmäßig wird ein Attribut auf das darauffolgende Element angewendet.</span><span class="sxs-lookup"><span data-stu-id="1db3f-143">By default, an attribute applies to the element that follows it.</span></span> <span data-ttu-id="1db3f-144">Sie können allerdings auch explizit festlegen, dass ein Attribut beispielsweise auf eine Methode, ihren Parameter oder ihren Rückgabewert angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1db3f-144">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>

<span data-ttu-id="1db3f-145">Verwenden Sie die folgende Syntax, um ein Attributziel explizit zu kennzeichnen:</span><span class="sxs-lookup"><span data-stu-id="1db3f-145">To explicitly identify an attribute target, use the following syntax:</span></span>

```csharp
[target : attribute-list]
```

<span data-ttu-id="1db3f-146">Die Liste der möglichen `target`-Werte wird in der folgenden Tabelle gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1db3f-146">The list of possible `target` values is shown in the following table.</span></span>

|<span data-ttu-id="1db3f-147">Zielwert</span><span class="sxs-lookup"><span data-stu-id="1db3f-147">Target value</span></span>|<span data-ttu-id="1db3f-148">Betrifft</span><span class="sxs-lookup"><span data-stu-id="1db3f-148">Applies to</span></span>|
|------------------|----------------|
|`assembly`|<span data-ttu-id="1db3f-149">Gesamte Assembly</span><span class="sxs-lookup"><span data-stu-id="1db3f-149">Entire assembly</span></span>|
|`module`|<span data-ttu-id="1db3f-150">Aktuelle Assemblymodul</span><span class="sxs-lookup"><span data-stu-id="1db3f-150">Current assembly module</span></span>|
|`field`|<span data-ttu-id="1db3f-151">Feld in einer Klasse oder Struktur</span><span class="sxs-lookup"><span data-stu-id="1db3f-151">Field in a class or a struct</span></span>|
|`event`|<span data-ttu-id="1db3f-152">event</span><span class="sxs-lookup"><span data-stu-id="1db3f-152">Event</span></span>|
|`method`|<span data-ttu-id="1db3f-153">Methode oder `get`- und `set`-Eigenschaftenaccessors</span><span class="sxs-lookup"><span data-stu-id="1db3f-153">Method or `get` and `set` property accessors</span></span>|
|`param`|<span data-ttu-id="1db3f-154">Methodenparameter oder `set`-Parameter des Eigenschaftenaccessors</span><span class="sxs-lookup"><span data-stu-id="1db3f-154">Method parameters or `set` property accessor parameters</span></span>|
|`property`|<span data-ttu-id="1db3f-155">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1db3f-155">Property</span></span>|
|`return`|<span data-ttu-id="1db3f-156">Rückgabewert einer Methode, Eigenschaftenindexer oder `get`-Eigenschaftenaccessor</span><span class="sxs-lookup"><span data-stu-id="1db3f-156">Return value of a method, property indexer, or `get` property accessor</span></span>|
|`type`|<span data-ttu-id="1db3f-157">Struktur, Klasse, Schnittstelle, Enumeration oder Delegat</span><span class="sxs-lookup"><span data-stu-id="1db3f-157">Struct, class, interface, enum, or delegate</span></span>|

<span data-ttu-id="1db3f-158">Geben Sie den `field`-Zielwert an, um ein Attribut auf das für eine [automatisch implementierte Eigenschaft](../../../properties.md) erstellte Unterstützungsfeld anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="1db3f-158">You would specify the `field` target value to apply an attribute to the backing field created for an [auto-implemented property](../../../properties.md).</span></span>

<span data-ttu-id="1db3f-159">Im folgenden Beispiel wird veranschaulicht, wie Attribute auf Assemblys und Module angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1db3f-159">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="1db3f-160">Weitere Informationen finden Sie unter [Allgemeine Attribute (C#)](../../../language-reference/attributes/global.md).</span><span class="sxs-lookup"><span data-stu-id="1db3f-160">For more information, see [Common Attributes (C#)](../../../language-reference/attributes/global.md).</span></span>

```csharp
using System;
using System.Reflection;
[assembly: AssemblyTitleAttribute("Production assembly 4")]
[module: CLSCompliant(true)]
```

<span data-ttu-id="1db3f-161">Im folgenden Beispiel wird gezeigt, wie Attribute auf Methoden, Methodenparameter und Methodenrückgabewerte in C# angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1db3f-161">The following example shows how to apply attributes to methods, method parameters, and method return values in C#.</span></span>

[!code-csharp[Applying attributes to different code elements](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#6)]

> [!NOTE]
> <span data-ttu-id="1db3f-162">Unabhängig von den Zielen, auf denen `ValidatedContract` definiert wird, um gültig zu sein, muss das Ziel `return` angegeben werden, selbst wenn `ValidatedContract` nur für die Rückgabewerte definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1db3f-162">Regardless of the targets on which `ValidatedContract` is defined to be valid, the `return` target has to be specified, even if `ValidatedContract` were defined to apply only to return values.</span></span> <span data-ttu-id="1db3f-163">Das heißt, der Compiler verwendet keine `AttributeUsage`-Informationen zum Auflösen von mehrdeutigen Attributzielen.</span><span class="sxs-lookup"><span data-stu-id="1db3f-163">In other words, the compiler will not use `AttributeUsage` information to resolve ambiguous attribute targets.</span></span> <span data-ttu-id="1db3f-164">Weitere Informationen finden Sie unter [AttributeUsage (C#)](../../../language-reference/attributes/general.md).</span><span class="sxs-lookup"><span data-stu-id="1db3f-164">For more information, see [AttributeUsage (C#)](../../../language-reference/attributes/general.md).</span></span>

## <a name="common-uses-for-attributes"></a><span data-ttu-id="1db3f-165">Häufige Verwendungsmöglichkeiten für Attribute</span><span class="sxs-lookup"><span data-stu-id="1db3f-165">Common uses for attributes</span></span>

<span data-ttu-id="1db3f-166">Die folgende Liste enthält einige häufige Verwendungsmöglichkeiten von Attributen im Code:</span><span class="sxs-lookup"><span data-stu-id="1db3f-166">The following list includes a few of the common uses of attributes in code:</span></span>

- <span data-ttu-id="1db3f-167">Kennzeichnen von Methoden mit dem `WebMethod`-Attribut in Webdiensten, um anzugeben, dass die Methode über das SOAP-Protokoll aufrufbar sein sollte.</span><span class="sxs-lookup"><span data-stu-id="1db3f-167">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="1db3f-168">Weitere Informationen finden Sie unter <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1db3f-168">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>
- <span data-ttu-id="1db3f-169">Beschreiben, wie Methodenparameter bei der Interaktion mit systemeigenem Code gemarshallt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1db3f-169">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="1db3f-170">Weitere Informationen finden Sie unter <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1db3f-170">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>
- <span data-ttu-id="1db3f-171">Beschreiben der COM-Eigenschaften für Klassen, Methoden und Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="1db3f-171">Describing the COM properties for classes, methods, and interfaces.</span></span>
- <span data-ttu-id="1db3f-172">Aufrufen von nicht verwaltetem Code mithilfe der Klasse <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1db3f-172">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>
- <span data-ttu-id="1db3f-173">Beschreiben der Assembly im Hinblick auf Titel, Version, Beschreibung oder Marke.</span><span class="sxs-lookup"><span data-stu-id="1db3f-173">Describing your assembly in terms of title, version, description, or trademark.</span></span>
- <span data-ttu-id="1db3f-174">Beschreiben, welche Member einer Klasse zur Verbesserung der Dauerhaftigkeit serialisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1db3f-174">Describing which members of a class to serialize for persistence.</span></span>
- <span data-ttu-id="1db3f-175">Beschreiben der Zuordnung zwischen Klassenmembern und XML-Knoten für die XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="1db3f-175">Describing how to map between class members and XML nodes for XML serialization.</span></span>
- <span data-ttu-id="1db3f-176">Beschreiben der Sicherheitsanforderungen für Methoden.</span><span class="sxs-lookup"><span data-stu-id="1db3f-176">Describing the security requirements for methods.</span></span>
- <span data-ttu-id="1db3f-177">Angeben von Eigenschaften zum Erzwingen der Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="1db3f-177">Specifying characteristics used to enforce security.</span></span>
- <span data-ttu-id="1db3f-178">Steuern der vom JIT-Compiler (Just-In-Time-Compiler) ausgeführten Optimierungen, damit der Code weiterhin problemlos debuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1db3f-178">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>
- <span data-ttu-id="1db3f-179">Abrufen von Informationen zum Aufrufer einer Methode.</span><span class="sxs-lookup"><span data-stu-id="1db3f-179">Obtaining information about the caller to a method.</span></span>

## <a name="related-sections"></a><span data-ttu-id="1db3f-180">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1db3f-180">Related sections</span></span>

<span data-ttu-id="1db3f-181">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="1db3f-181">For more information, see:</span></span>

- [<span data-ttu-id="1db3f-182">Erstellen benutzerdefinierter Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="1db3f-182">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)  
- [<span data-ttu-id="1db3f-183">Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))</span><span class="sxs-lookup"><span data-stu-id="1db3f-183">Accessing Attributes by Using Reflection (C#)</span></span>](accessing-attributes-by-using-reflection.md)  
- [<span data-ttu-id="1db3f-184">Erstellen einer Union in C/C++ mit Attributen (C#)</span><span class="sxs-lookup"><span data-stu-id="1db3f-184">How to create a C/C++ union by using attributes (C#)</span></span>](how-to-create-a-c-cpp-union-by-using-attributes.md)  
- [<span data-ttu-id="1db3f-185">Allgemeine Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="1db3f-185">Common Attributes (C#)</span></span>](../../../language-reference/attributes/global.md)  
- [<span data-ttu-id="1db3f-186">Aufruferinformationen (C#)</span><span class="sxs-lookup"><span data-stu-id="1db3f-186">Caller Information (C#)</span></span>](../../../language-reference/attributes/caller-information.md)  

## <a name="see-also"></a><span data-ttu-id="1db3f-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1db3f-187">See also</span></span>

- [<span data-ttu-id="1db3f-188">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1db3f-188">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="1db3f-189">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="1db3f-189">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="1db3f-190">Attribute</span><span class="sxs-lookup"><span data-stu-id="1db3f-190">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="1db3f-191">Verwenden von Attributen in C#</span><span class="sxs-lookup"><span data-stu-id="1db3f-191">Using Attributes in C#</span></span>](../../../tutorials/attributes.md)
