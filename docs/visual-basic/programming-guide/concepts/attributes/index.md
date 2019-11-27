---
title: Übersicht über Attribute
ms.date: 07/20/2015
ms.assetid: 1449f69b-c063-41de-8d89-f0bbdcf96ac6
ms.openlocfilehash: 97a2a13102718b6ee8829fca678b2b49df21e5d1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349479"
---
# <a name="attributes-overview-visual-basic"></a><span data-ttu-id="9284e-102">Übersicht über Attribute (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9284e-102">Attributes overview (Visual Basic)</span></span>

<span data-ttu-id="9284e-103">Attribute stellen eine effiziente Methode dar, Metadaten oder deklarative Informationen Code (Assemblys, Typen, Methoden, Eigenschaften usw.) zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="9284e-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="9284e-104">Nach dem Zuordnen eines Attributs zu einer Programmentität kann das Attribut zur Laufzeit mit einer Technik namens *Reflektion* abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="9284e-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="9284e-105">Weitere Informationen finden Sie unter [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md).</span><span class="sxs-lookup"><span data-stu-id="9284e-105">For more information, see [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md).</span></span>

<span data-ttu-id="9284e-106">Attribute verfügen über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="9284e-106">Attributes have the following properties:</span></span>

- <span data-ttu-id="9284e-107">Attribute fügen Metadaten zu Ihrem Programm hinzu.</span><span class="sxs-lookup"><span data-stu-id="9284e-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="9284e-108">*Metadaten* sind Informationen zu den Typen, die in einem Programm definiert sind.</span><span class="sxs-lookup"><span data-stu-id="9284e-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="9284e-109">Alle .NET-Assemblys enthalten einen festgelegten Satz von Metadaten, der die Typen und Typmember beschreibt, die in der Assembly definiert sind.</span><span class="sxs-lookup"><span data-stu-id="9284e-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="9284e-110">Sie können benutzerdefinierte Attribute hinzufügen, um zusätzliche erforderliche Informationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9284e-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="9284e-111">Weitere Informationen finden Sie unter [Erstellen benutzerdefinierter Attribute (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="9284e-111">For more information, see, [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md).</span></span>

- <span data-ttu-id="9284e-112">Sie können eines oder mehrere Attribute auf ganze Assemblys, Module oder kleinere Programmelemente wie Klassen und Eigenschaften anwenden.</span><span class="sxs-lookup"><span data-stu-id="9284e-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>

- <span data-ttu-id="9284e-113">Attribute können Argumente auf die gleiche Art wie Methoden und Eigenschaften akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="9284e-113">Attributes can accept arguments in the same way as methods and properties.</span></span>

- <span data-ttu-id="9284e-114">Das Programm kann seine eigenen Metadaten oder die Metadaten in anderen Programmen mithilfe der Reflektion untersuchen.</span><span class="sxs-lookup"><span data-stu-id="9284e-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="9284e-115">Weitere Informationen finden Sie unter [Zugreifen auf Attribute mithilfe der Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="9284e-115">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>

## <a name="using-attributes"></a><span data-ttu-id="9284e-116">Verwenden von Attributen</span><span class="sxs-lookup"><span data-stu-id="9284e-116">Using Attributes</span></span>

<span data-ttu-id="9284e-117">Attribute können in nahezu jeder Deklaration platziert werden, auch wenn ein bestimmtes Attribut die Typen der Deklarationen einschränkt, für die es gültig ist.</span><span class="sxs-lookup"><span data-stu-id="9284e-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="9284e-118">In Visual Basic ist ein Attribut in spitzen Klammern eingeschlossen (\< >).</span><span class="sxs-lookup"><span data-stu-id="9284e-118">In Visual Basic, an attribute is enclosed in angle brackets (\< >).</span></span> <span data-ttu-id="9284e-119">Es muss in derselben Zeile direkt vor dem Element angezeigt werden, auf das es angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9284e-119">It must appear immediately before the element to which it is applied, on the same line.</span></span>

<span data-ttu-id="9284e-120">In diesem Beispiel wird das <xref:System.SerializableAttribute>-Attribut benutzt, um ein spezifisches Merkmal auf eine Klasse anzuwenden:</span><span class="sxs-lookup"><span data-stu-id="9284e-120">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>

```vb
<System.Serializable()> Public Class SampleClass
    ' Objects of this type can be serialized.
End Class
```

 <span data-ttu-id="9284e-121">Eine Methode mit dem Attribut <xref:System.Runtime.InteropServices.DllImportAttribute> wird wie folgt deklariert:</span><span class="sxs-lookup"><span data-stu-id="9284e-121">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like this:</span></span>

```vb
Imports System.Runtime.InteropServices
```

```vb
<System.Runtime.InteropServices.DllImport("user32.dll")>
Sub SampleMethod()
End Sub
```

<span data-ttu-id="9284e-122">Mehrere Attribute können in einer Deklaration platziert werden:</span><span class="sxs-lookup"><span data-stu-id="9284e-122">More than one attribute can be placed on a declaration:</span></span>

```vb
Imports System.Runtime.InteropServices
```

```vb
Sub MethodA(<[In](), Out()> ByVal x As Double)
End Sub
Sub MethodB(<Out(), [In]()> ByVal x As Double)
End Sub
```

<span data-ttu-id="9284e-123">Einige Attribute können für eine bestimmte Entität mehrmals angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9284e-123">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="9284e-124">Ein Beispiel für ein solches mehrfach verwendbares Attribut ist <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="9284e-124">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>

```vb
<Conditional("DEBUG"), Conditional("TEST1")>
Sub TraceMethod()
End Sub
```

> [!NOTE]
> <span data-ttu-id="9284e-125">Alle Attributnamen enden laut Konvention mit dem Wort „Attribute“, um sie von anderen Elementen in .NET Framework zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="9284e-125">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET Framework.</span></span> <span data-ttu-id="9284e-126">Sie müssen das Attributsuffix allerdings nicht angeben, wenn Sie Attribute im Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="9284e-126">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="9284e-127">Beispiel: `[DllImport]` entspricht `[DllImportAttribute]`, aber `DllImportAttribute` ist der tatsächliche Name des Attributs in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9284e-127">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework.</span></span>

### <a name="attribute-parameters"></a><span data-ttu-id="9284e-128">Attributparameter</span><span class="sxs-lookup"><span data-stu-id="9284e-128">Attribute Parameters</span></span>

<span data-ttu-id="9284e-129">Viele Attribute weisen Parameter auf, die positional, unbenannt der benannt sein können.</span><span class="sxs-lookup"><span data-stu-id="9284e-129">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="9284e-130">Alle positionalen Parameter müssen in einer bestimmten Reihenfolge angegeben und können nicht ausgelassen werden. Benannte Parameter sind optional und können in beliebiger Reihenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9284e-130">Any positional parameters must be specified in a certain order and cannot be omitted; named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="9284e-131">Positionale Parameter werden zuerst angegeben.</span><span class="sxs-lookup"><span data-stu-id="9284e-131">Positional parameters are specified first.</span></span> <span data-ttu-id="9284e-132">Die folgenden drei Attribute sind beispielsweise äquivalent:</span><span class="sxs-lookup"><span data-stu-id="9284e-132">For example, these three attributes are equivalent:</span></span>

```vb
<DllImport("user32.dll")>
<DllImport("user32.dll", SetLastError:=False, ExactSpelling:=False)>
<DllImport("user32.dll", ExactSpelling:=False, SetLastError:=False)>
```

<span data-ttu-id="9284e-133">Der erste Parameter, der DLL-Name, ist positional und kommt immer an erster Stelle. Die anderen sind benannt.</span><span class="sxs-lookup"><span data-stu-id="9284e-133">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="9284e-134">In diesem Fall werden beide benannten Parameter standardmäßig auf „false“ festgelegt und können daher ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="9284e-134">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="9284e-135">In der Dokumentation des individuellen Attributs finden Sie Informationen zu Standardparameterwerten.</span><span class="sxs-lookup"><span data-stu-id="9284e-135">Refer to the individual attribute's documentation for information on default parameter values.</span></span>

### <a name="attribute-targets"></a><span data-ttu-id="9284e-136">Attributziele</span><span class="sxs-lookup"><span data-stu-id="9284e-136">Attribute Targets</span></span>

<span data-ttu-id="9284e-137">Das *Ziel* eines Attributs ist die Entität, auf die das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9284e-137">The *target* of an attribute is the entity to which the attribute applies.</span></span> <span data-ttu-id="9284e-138">Ein Attribut kann beispielsweise auf eine Klasse, eine bestimmte Methode oder eine ganze Assembly angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9284e-138">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="9284e-139">Standardmäßig wird ein Attribut auf das voranstehende Element angewendet.</span><span class="sxs-lookup"><span data-stu-id="9284e-139">By default, an attribute applies to the element that it precedes.</span></span> <span data-ttu-id="9284e-140">Sie können allerdings auch explizit festlegen, dass ein Attribut beispielsweise auf eine Methode, ihren Parameter oder ihren Rückgabewert angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9284e-140">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>

<span data-ttu-id="9284e-141">Verwenden Sie die folgende Syntax, um ein Attributziel explizit zu kennzeichnen:</span><span class="sxs-lookup"><span data-stu-id="9284e-141">To explicitly identify an attribute target, use the following syntax:</span></span>

```vb
<target : attribute-list>
```

<span data-ttu-id="9284e-142">Die Liste der möglichen `target`-Werte wird in der folgenden Tabelle gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9284e-142">The list of possible `target` values is shown in the following table.</span></span>

|<span data-ttu-id="9284e-143">Zielwert</span><span class="sxs-lookup"><span data-stu-id="9284e-143">Target value</span></span>|<span data-ttu-id="9284e-144">Betrifft</span><span class="sxs-lookup"><span data-stu-id="9284e-144">Applies to</span></span>|
|------------------|----------------|
|`assembly`|<span data-ttu-id="9284e-145">Gesamte Assembly</span><span class="sxs-lookup"><span data-stu-id="9284e-145">Entire assembly</span></span>|
|`module`|<span data-ttu-id="9284e-146">Aktuelles Assemblymodul (unterscheidet sich von einem Visual Basic-Modul)</span><span class="sxs-lookup"><span data-stu-id="9284e-146">Current assembly module (which is different from a Visual Basic Module)</span></span>|

 <span data-ttu-id="9284e-147">Im folgenden Beispiel wird veranschaulicht, wie Attribute auf Assemblys und Module angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9284e-147">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="9284e-148">Weitere Informationen finden Sie unter [Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) (Gemeinsame Attribute (Visual Basic)).</span><span class="sxs-lookup"><span data-stu-id="9284e-148">For more information, see [Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md).</span></span>

```vb
Imports System.Reflection
<Assembly: AssemblyTitleAttribute("Production assembly 4"),
Module: CLSCompliant(True)>
```

## <a name="common-uses-for-attributes"></a><span data-ttu-id="9284e-149">Häufige Verwendungsmöglichkeiten für Attribute</span><span class="sxs-lookup"><span data-stu-id="9284e-149">Common Uses for Attributes</span></span>

<span data-ttu-id="9284e-150">Die folgende Liste enthält einige häufige Verwendungsmöglichkeiten von Attributen im Code:</span><span class="sxs-lookup"><span data-stu-id="9284e-150">The following list includes a few of the common uses of attributes in code:</span></span>

- <span data-ttu-id="9284e-151">Kennzeichnen von Methoden mit dem `WebMethod`-Attribut in Webdiensten, um anzugeben, dass die Methode über das SOAP-Protokoll aufrufbar sein sollte.</span><span class="sxs-lookup"><span data-stu-id="9284e-151">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="9284e-152">Weitere Informationen finden Sie unter <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9284e-152">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>

- <span data-ttu-id="9284e-153">Beschreiben, wie Methodenparameter bei der Interaktion mit systemeigenem Code gemarshallt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9284e-153">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="9284e-154">Weitere Informationen finden Sie unter <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9284e-154">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>

- <span data-ttu-id="9284e-155">Beschreiben der COM-Eigenschaften für Klassen, Methoden und Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="9284e-155">Describing the COM properties for classes, methods, and interfaces.</span></span>

- <span data-ttu-id="9284e-156">Aufrufen von nicht verwaltetem Code mithilfe der Klasse <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9284e-156">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>

- <span data-ttu-id="9284e-157">Beschreiben der Assembly im Hinblick auf Titel, Version, Beschreibung oder Marke.</span><span class="sxs-lookup"><span data-stu-id="9284e-157">Describing your assembly in terms of title, version, description, or trademark.</span></span>

- <span data-ttu-id="9284e-158">Beschreiben, welche Member einer Klasse zur Verbesserung der Dauerhaftigkeit serialisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9284e-158">Describing which members of a class to serialize for persistence.</span></span>

- <span data-ttu-id="9284e-159">Beschreiben der Zuordnung zwischen Klassenmembern und XML-Knoten für die XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="9284e-159">Describing how to map between class members and XML nodes for XML serialization.</span></span>

- <span data-ttu-id="9284e-160">Beschreiben der Sicherheitsanforderungen für Methoden.</span><span class="sxs-lookup"><span data-stu-id="9284e-160">Describing the security requirements for methods.</span></span>

- <span data-ttu-id="9284e-161">Angeben von Eigenschaften zum Erzwingen der Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="9284e-161">Specifying characteristics used to enforce security.</span></span>

- <span data-ttu-id="9284e-162">Steuern der vom JIT-Compiler (Just-In-Time-Compiler) ausgeführten Optimierungen, damit der Code weiterhin problemlos debuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9284e-162">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>

- <span data-ttu-id="9284e-163">Abrufen von Informationen zum Aufrufer einer Methode.</span><span class="sxs-lookup"><span data-stu-id="9284e-163">Obtaining information about the caller to a method.</span></span>

## <a name="related-sections"></a><span data-ttu-id="9284e-164">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="9284e-164">Related Sections</span></span>

<span data-ttu-id="9284e-165">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="9284e-165">For more information, see:</span></span>

- <span data-ttu-id="9284e-166">[Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Erstellen benutzerdefinierter Attribute (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9284e-166">[Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)</span></span>

- <span data-ttu-id="9284e-167">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Zugreifen auf Attribute mithilfe der Reflektion (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9284e-167">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>

- <span data-ttu-id="9284e-168">[How to: Create a C/C++ Union by Using Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md) (Gewusst wie: Erstellen einer Union in C/C++ mit Attributen (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9284e-168">[How to: Create a C/C++ Union by Using Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md)</span></span>

- <span data-ttu-id="9284e-169">[Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) (Gemeinsame Attribute (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9284e-169">[Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md)</span></span>

- <span data-ttu-id="9284e-170">[Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md) (Aufruferinformationen (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9284e-170">[Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="9284e-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9284e-171">See also</span></span>

- [<span data-ttu-id="9284e-172">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9284e-172">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="9284e-173">Reflektion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9284e-173">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [<span data-ttu-id="9284e-174">Attribute</span><span class="sxs-lookup"><span data-stu-id="9284e-174">Attributes</span></span>](../../../../standard/attributes/index.md)
