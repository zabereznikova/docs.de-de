---
title: Attribute (C#)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: f148f13f-a0d5-4f22-9c87-4b73d5dde270
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f9fc23cf7afbd28f0c9ae438cbce298cbf362fbd
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2017
---
# <a name="attributes-c"></a><span data-ttu-id="e0ea1-102">Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="e0ea1-102">Attributes (C#)</span></span>
<span data-ttu-id="e0ea1-103">Attribute stellen eine effiziente Methode dar, Metadaten oder deklarative Informationen Code (Assemblys, Typen, Methoden, Eigenschaften usw.) zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="e0ea1-104">Nach dem Zuordnen eines Attributs zu einer Programmentität kann das Attribut zur Laufzeit mit einer Technik namens *Reflektion* abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="e0ea1-105">Weitere Informationen finden Sie unter [Reflektion (C#)](../../../../csharp/programming-guide/concepts/reflection.md).</span><span class="sxs-lookup"><span data-stu-id="e0ea1-105">For more information, see [Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md).</span></span>  
  
 <span data-ttu-id="e0ea1-106">Attribute verfügen über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e0ea1-106">Attributes have the following properties:</span></span>  
  
-   <span data-ttu-id="e0ea1-107">Attribute fügen Metadaten zu Ihrem Programm hinzu.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="e0ea1-108">*Metadaten* sind Informationen zu den Typen, die in einem Programm definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="e0ea1-109">Alle .NET-Assemblys enthalten einen festgelegten Satz von Metadaten, der die Typen und Typmember beschreibt, die in der Assembly definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="e0ea1-110">Sie können benutzerdefinierte Attribute hinzufügen, um zusätzliche erforderliche Informationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="e0ea1-111">Weitere Informationen finden Sie unter [Erstellen benutzerdefinierter Attribute (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="e0ea1-111">For more information, see, [Creating Custom Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md).</span></span>  
  
-   <span data-ttu-id="e0ea1-112">Sie können eines oder mehrere Attribute auf ganze Assemblys, Module oder kleinere Programmelemente wie Klassen und Eigenschaften anwenden.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>  
  
-   <span data-ttu-id="e0ea1-113">Attribute können Argumente auf die gleiche Art wie Methoden und Eigenschaften akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-113">Attributes can accept arguments in the same way as methods and properties.</span></span>  
  
-   <span data-ttu-id="e0ea1-114">Das Programm kann seine eigenen Metadaten oder die Metadaten in anderen Programmen mithilfe der Reflektion untersuchen.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="e0ea1-115">Weitere Informationen finden Sie unter [Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="e0ea1-115">For more information, see [Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="using-attributes"></a><span data-ttu-id="e0ea1-116">Verwenden von Attributen</span><span class="sxs-lookup"><span data-stu-id="e0ea1-116">Using Attributes</span></span>  
 <span data-ttu-id="e0ea1-117">Attribute können in nahezu jeder Deklaration platziert werden, auch wenn ein bestimmtes Attribut die Typen der Deklarationen einschränkt, für die es gültig ist.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="e0ea1-118">In C# geben Sie ein Attribut durch Angabe des Namens des Attributs an, eingeschlossen in eckigen Klammern ([]), oberhalb der Deklaration der Entität, auf die es angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-118">In C#, you specify an attribute by placing the name of the attribute, enclosed in square brackets ([]), above the declaration of the entity to which it applies.</span></span>  
  
 <span data-ttu-id="e0ea1-119">In diesem Beispiel wird das Attribut <xref:System.SerializableAttribute> benutzt, um ein spezifisches Merkmal auf eine Klasse anzuwenden:</span><span class="sxs-lookup"><span data-stu-id="e0ea1-119">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>  
  
```csharp  
[System.Serializable]  
public class SampleClass  
{  
    // Objects of this type can be serialized.  
}  
```  
  
 <span data-ttu-id="e0ea1-120">Eine Methode mit dem Attribut <xref:System.Runtime.InteropServices.DllImportAttribute> wird wie folgt deklariert:</span><span class="sxs-lookup"><span data-stu-id="e0ea1-120">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like this:</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
[System.Runtime.InteropServices.DllImport("user32.dll")]  
extern static void SampleMethod();  
```  
  
 <span data-ttu-id="e0ea1-121">Mehrere Attribute können in einer Deklaration platziert werden:</span><span class="sxs-lookup"><span data-stu-id="e0ea1-121">More than one attribute can be placed on a declaration:</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
void MethodA([In][Out] ref double x) { }  
void MethodB([Out][In] ref double x) { }  
void MethodC([In, Out] ref double x) { }  
```  
  
 <span data-ttu-id="e0ea1-122">Einige Attribute können für eine bestimmte Entität mehrmals angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-122">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="e0ea1-123">Ein Beispiel für ein solches mehrfach verwendbares Attribut ist <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="e0ea1-123">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>  
  
```csharp  
[Conditional("DEBUG"), Conditional("TEST1")]  
void TraceMethod()  
{  
    // ...  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="e0ea1-124">Alle Attributnamen enden laut Konvention mit dem Wort „Attribute“, um sie von anderen Elementen in .NET Framework zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-124">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET Framework.</span></span> <span data-ttu-id="e0ea1-125">Sie müssen das Attributsuffix allerdings nicht angeben, wenn Sie Attribute im Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-125">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="e0ea1-126">Beispiel: `[DllImport]` entspricht `[DllImportAttribute]`, aber `DllImportAttribute` ist der tatsächliche Name des Attributs in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-126">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework.</span></span>  
  
### <a name="attribute-parameters"></a><span data-ttu-id="e0ea1-127">Attributparameter</span><span class="sxs-lookup"><span data-stu-id="e0ea1-127">Attribute Parameters</span></span>  
 <span data-ttu-id="e0ea1-128">Viele Attribute weisen Parameter auf, die positional, unbenannt der benannt sein können.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-128">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="e0ea1-129">Alle positionalen Parameter müssen in einer bestimmten Reihenfolge angegeben und können nicht ausgelassen werden. Benannte Parameter sind optional und können in beliebiger Reihenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-129">Any positional parameters must be specified in a certain order and cannot be omitted; named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="e0ea1-130">Positionale Parameter werden zuerst angegeben.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-130">Positional parameters are specified first.</span></span> <span data-ttu-id="e0ea1-131">Die folgenden drei Attribute sind beispielsweise äquivalent:</span><span class="sxs-lookup"><span data-stu-id="e0ea1-131">For example, these three attributes are equivalent:</span></span>  
  
```csharp  
[DllImport("user32.dll")]  
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]  
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]  
```  
  
 <span data-ttu-id="e0ea1-132">Der erste Parameter, der DLL-Name, ist positional und kommt immer an erster Stelle. Die anderen sind benannt.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-132">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="e0ea1-133">In diesem Fall werden beide benannten Parameter standardmäßig auf „false“ festgelegt und können daher ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-133">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="e0ea1-134">In der Dokumentation des individuellen Attributs finden Sie Informationen zu Standardparameterwerten.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-134">Refer to the individual attribute's documentation for information on default parameter values.</span></span>  
  
### <a name="attribute-targets"></a><span data-ttu-id="e0ea1-135">Attributziele</span><span class="sxs-lookup"><span data-stu-id="e0ea1-135">Attribute Targets</span></span>  
 <span data-ttu-id="e0ea1-136">Das *Ziel* eines Attributs ist die Entität, auf die das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-136">The *target* of an attribute is the entity to which the attribute applies.</span></span> <span data-ttu-id="e0ea1-137">Ein Attribut kann beispielsweise auf eine Klasse, eine bestimmte Methode oder eine ganze Assembly angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-137">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="e0ea1-138">Standardmäßig wird ein Attribut auf das voranstehende Element angewendet.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-138">By default, an attribute applies to the element that it precedes.</span></span> <span data-ttu-id="e0ea1-139">Sie können allerdings auch explizit festlegen, dass ein Attribut beispielsweise auf eine Methode, ihren Parameter oder ihren Rückgabewert angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-139">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>  
  
 <span data-ttu-id="e0ea1-140">Verwenden Sie die folgende Syntax, um ein Attributziel explizit zu kennzeichnen:</span><span class="sxs-lookup"><span data-stu-id="e0ea1-140">To explicitly identify an attribute target, use the following syntax:</span></span>  
  
```csharp  
[target : attribute-list]  
```  
  
 <span data-ttu-id="e0ea1-141">Die Liste der möglichen `target`-Werte wird in der folgenden Tabelle gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e0ea1-141">The list of possible `target` values is shown in the following table.</span></span>  
  
|<span data-ttu-id="e0ea1-142">Zielwert</span><span class="sxs-lookup"><span data-stu-id="e0ea1-142">Target value</span></span>|<span data-ttu-id="e0ea1-143">Betrifft</span><span class="sxs-lookup"><span data-stu-id="e0ea1-143">Applies to</span></span>|  
|------------------|----------------|  
|`assembly`|<span data-ttu-id="e0ea1-144">Gesamte Assembly</span><span class="sxs-lookup"><span data-stu-id="e0ea1-144">Entire assembly</span></span>|  
|`module`|<span data-ttu-id="e0ea1-145">Aktuelle Assemblymodul</span><span class="sxs-lookup"><span data-stu-id="e0ea1-145">Current assembly module</span></span>|  
|`field`|<span data-ttu-id="e0ea1-146">Feld in einer Klasse oder Struktur</span><span class="sxs-lookup"><span data-stu-id="e0ea1-146">Field in a class or a struct</span></span>|  
|`event`|<span data-ttu-id="e0ea1-147">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e0ea1-147">Event</span></span>|  
|`method`|<span data-ttu-id="e0ea1-148">Methode oder `get`- und `set`-Eigenschaftenaccessors</span><span class="sxs-lookup"><span data-stu-id="e0ea1-148">Method or `get` and `set` property accessors</span></span>|  
|`param`|<span data-ttu-id="e0ea1-149">Methodenparameter oder `set`-Parameter des Eigenschaftenaccessors</span><span class="sxs-lookup"><span data-stu-id="e0ea1-149">Method parameters or `set` property accessor parameters</span></span>|  
|`property`|<span data-ttu-id="e0ea1-150">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e0ea1-150">Property</span></span>|  
|`return`|<span data-ttu-id="e0ea1-151">Rückgabewert einer Methode, Eigenschaftenindexer oder `get`-Eigenschaftenaccessor</span><span class="sxs-lookup"><span data-stu-id="e0ea1-151">Return value of a method, property indexer, or `get` property accessor</span></span>|  
|`type`|<span data-ttu-id="e0ea1-152">Struktur, Klasse, Schnittstelle, Enumeration oder Delegat</span><span class="sxs-lookup"><span data-stu-id="e0ea1-152">Struct, class, interface, enum, or delegate</span></span>|  
  
 <span data-ttu-id="e0ea1-153">Im folgenden Beispiel wird veranschaulicht, wie Attribute auf Assemblys und Module angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-153">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="e0ea1-154">Weitere Informationen finden Sie unter [Allgemeine Attribute (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="e0ea1-154">For more information, see [Common Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
```csharp  
using System;  
using System.Reflection;  
[assembly: AssemblyTitleAttribute("Production assembly 4")]  
[module: CLSCompliant(true)]  
```  
  
 <span data-ttu-id="e0ea1-155">Im folgenden Beispiel wird gezeigt, wie Attribute auf Methoden, Methodenparameter und Methodenrückgabewerte in C# angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-155">The following example shows how to apply attributes to methods, method parameters, and method return values in C#.</span></span>  
  
```csharp  
// default: applies to method  
[SomeAttr]  
int Method1() { return 0; }  
  
// applies to method  
[method: SomeAttr]  
int Method2() { return 0; }  
  
// applies to return value  
[return: SomeAttr]  
int Method3() { return 0; }  
```  
  
> [!NOTE]
>  <span data-ttu-id="e0ea1-156">Unabhängig von den Zielen, auf denen `SomeAttr` definiert wird, um gültig zu sein, muss das Ziel `return` angegeben werden, selbst wenn `SomeAttr` nur für die Rückgabewerte definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-156">Regardless of the targets on which `SomeAttr` is defined to be valid, the `return` target has to be specified, even if `SomeAttr` were defined to apply only to return values.</span></span> <span data-ttu-id="e0ea1-157">Das heißt, der Compiler verwendet keine `AttributeUsage`-Informationen zum Auflösen von mehrdeutigen Attributzielen.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-157">In other words, the compiler will not use `AttributeUsage` information to resolve ambiguous attribute targets.</span></span> <span data-ttu-id="e0ea1-158">Weitere Informationen finden Sie unter [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md).</span><span class="sxs-lookup"><span data-stu-id="e0ea1-158">For more information, see [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md).</span></span>  
  
## <a name="common-uses-for-attributes"></a><span data-ttu-id="e0ea1-159">Häufige Verwendungsmöglichkeiten für Attribute</span><span class="sxs-lookup"><span data-stu-id="e0ea1-159">Common Uses for Attributes</span></span>  
 <span data-ttu-id="e0ea1-160">Die folgende Liste enthält einige häufige Verwendungsmöglichkeiten von Attributen im Code:</span><span class="sxs-lookup"><span data-stu-id="e0ea1-160">The following list includes a few of the common uses of attributes in code:</span></span>  
  
-   <span data-ttu-id="e0ea1-161">Kennzeichnen von Methoden mit dem `WebMethod`-Attribut in Webdiensten, um anzugeben, dass die Methode über das SOAP-Protokoll aufrufbar sein sollte.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-161">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="e0ea1-162">Weitere Informationen finden Sie unter <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-162">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
-   <span data-ttu-id="e0ea1-163">Beschreiben, wie Methodenparameter bei der Interaktion mit systemeigenem Code gemarshallt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-163">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="e0ea1-164">Weitere Informationen finden Sie unter <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-164">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>  
  
-   <span data-ttu-id="e0ea1-165">Beschreiben der COM-Eigenschaften für Klassen, Methoden und Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-165">Describing the COM properties for classes, methods, and interfaces.</span></span>  
  
-   <span data-ttu-id="e0ea1-166">Aufrufen von nicht verwaltetem Code mithilfe der Klasse <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-166">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>  
  
-   <span data-ttu-id="e0ea1-167">Beschreiben der Assembly im Hinblick auf Titel, Version, Beschreibung oder Marke.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-167">Describing your assembly in terms of title, version, description, or trademark.</span></span>  
  
-   <span data-ttu-id="e0ea1-168">Beschreiben, welche Member einer Klasse zur Verbesserung der Dauerhaftigkeit serialisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-168">Describing which members of a class to serialize for persistence.</span></span>  
  
-   <span data-ttu-id="e0ea1-169">Beschreiben der Zuordnung zwischen Klassenmembern und XML-Knoten für die XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-169">Describing how to map between class members and XML nodes for XML serialization.</span></span>  
  
-   <span data-ttu-id="e0ea1-170">Beschreiben der Sicherheitsanforderungen für Methoden.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-170">Describing the security requirements for methods.</span></span>  
  
-   <span data-ttu-id="e0ea1-171">Angeben von Eigenschaften zum Erzwingen der Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-171">Specifying characteristics used to enforce security.</span></span>  
  
-   <span data-ttu-id="e0ea1-172">Steuern der vom JIT-Compiler (Just-In-Time-Compiler) ausgeführten Optimierungen, damit der Code weiterhin problemlos debuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-172">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>  
  
-   <span data-ttu-id="e0ea1-173">Abrufen von Informationen zum Aufrufer einer Methode.</span><span class="sxs-lookup"><span data-stu-id="e0ea1-173">Obtaining information about the caller to a method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e0ea1-174">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e0ea1-174">Related Sections</span></span>  
 <span data-ttu-id="e0ea1-175">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="e0ea1-175">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e0ea1-176">Erstellen benutzerdefinierter Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="e0ea1-176">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
  
-   [<span data-ttu-id="e0ea1-177">Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))</span><span class="sxs-lookup"><span data-stu-id="e0ea1-177">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)  
  
-   [<span data-ttu-id="e0ea1-178">Vorgehensweise: Erstellen einer Union in C/C++ mit Attributen (C#)</span><span class="sxs-lookup"><span data-stu-id="e0ea1-178">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md)  
  
-   [<span data-ttu-id="e0ea1-179">Allgemeine Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="e0ea1-179">Common Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md)  
  
-   [<span data-ttu-id="e0ea1-180">Aufruferinformationen (C#)</span><span class="sxs-lookup"><span data-stu-id="e0ea1-180">Caller Information (C#)</span></span>](../../../../csharp/programming-guide/concepts/caller-information.md)  
  
## <a name="see-also"></a><span data-ttu-id="e0ea1-181">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0ea1-181">See Also</span></span>  
 [<span data-ttu-id="e0ea1-182">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e0ea1-182">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e0ea1-183">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="e0ea1-183">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="e0ea1-184">Attribute</span><span class="sxs-lookup"><span data-stu-id="e0ea1-184">Attributes</span></span>](../../../../../docs/standard/attributes/index.md)
