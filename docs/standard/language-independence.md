---
title: Sprachunabhängigkeit und sprachunabhängige Komponenten
description: 'Erfahren Sie, wie Sie in einer der vielen in .NET unterstützten Sprachen entwickeln können: u.a. C#, C++/CLI, F#, IronPython, VB, Visual COBOL und PowerShell.'
ms.date: 07/22/2016
dev_langs:
- csharp
- vb
ms.technology: dotnet-standard
ms.assetid: 2dbed1bc-86f5-43cd-9a57-adbb1c5efba4
ms.openlocfilehash: 524f8dc9838d7c438e8155da683c4fa5b01f36a3
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162985"
---
# <a name="language-independence-and-language-independent-components"></a><span data-ttu-id="7d228-103">Sprachunabhängigkeit und sprachunabhängige Komponenten</span><span class="sxs-lookup"><span data-stu-id="7d228-103">Language independence and language-independent components</span></span>

<span data-ttu-id="7d228-104">.NET ist sprachunabhängig.</span><span class="sxs-lookup"><span data-stu-id="7d228-104">.NET is language independent.</span></span> <span data-ttu-id="7d228-105">Dies bedeutet, dass Sie als Entwickler in einer von vielen Sprachen für die .NET-Implementierung entwickeln können, beispielsweise C#, F# und Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7d228-105">This means that, as a developer, you can develop in one of the many languages that target .NET implementations, such as C#, F#, and Visual Basic.</span></span> <span data-ttu-id="7d228-106">Sie können auf die Typen und Member von Klassenbibliotheken zugreifen, die für die .NET-Implementierung entwickelt wurden, ohne die Sprache, in der sie ursprünglich geschrieben wurden, kennen und ohne den Konventionen der Originalsprache folgen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="7d228-106">You can access the types and members of class libraries developed for .NET implementations without having to know the language in which they were originally written and without having to follow any of the original language's conventions.</span></span> <span data-ttu-id="7d228-107">Wenn Sie Komponentenentwickler sind, kann von allen .NET-Apps sprachunabhängig auf die Komponente zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-107">If you're a component developer, your component can be accessed by any .NET app, regardless of its language.</span></span>

> [!NOTE]
> <span data-ttu-id="7d228-108">In diesem Artikel wird das Erstellen sprachunabhängiger Komponenten erläutert. Diese Komponenten können von Apps verwendet werden, die in einer beliebigen Sprache geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="7d228-108">This first part of this article discusses creating language-independent components, that is, components that can be consumed by apps that are written in any language.</span></span> <span data-ttu-id="7d228-109">Sie können auch eine einzelne Komponente oder App aus Quellcode erstellen, der in mehreren Sprachen geschrieben wurde. Weitere Informationen finden Sie im zweiten Teil dieses Artikels unter [Sprachübergreifende Interoperabilität](#cross-language-interoperability).</span><span class="sxs-lookup"><span data-stu-id="7d228-109">You can also create a single component or app from source code written in multiple languages; see [Cross-Language Interoperability](#cross-language-interoperability) in the second part of this article.</span></span>

<span data-ttu-id="7d228-110">Um vollständig mit anderen Objekten zu interagieren, die in irgendeiner Programmiersprache geschrieben wurden, müssen die Objekte den Aufrufern nur die Funktionen verfügbar machen, die allen Sprachen gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="7d228-110">To fully interact with other objects written in any language, objects must expose to callers only those features that are common to all languages.</span></span> <span data-ttu-id="7d228-111">Dieser gemeinsame Satz von Funktionen wird von der CLS (Common Language Specification) definiert. Das ist ein Satz von Regeln, die für generierte Assemblys gelten.</span><span class="sxs-lookup"><span data-stu-id="7d228-111">This common set of features is defined by the Common Language Specification (CLS), which is a set of rules that apply to generated assemblies.</span></span> <span data-ttu-id="7d228-112">Die Common Language Specification wird in der Partition I, in den Klauseln 7 bis 11 im [ECMA 335-Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm) definiert.</span><span class="sxs-lookup"><span data-stu-id="7d228-112">The Common Language Specification is defined in Partition I, Clauses 7 through 11 of the [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>

<span data-ttu-id="7d228-113">Wenn die Komponente der Common Language Specification entspricht, ist sichergestellt, dass sie CLS-kompatibel ist, und dass vom Code in Assemblys, die in irgendeiner CLS unterstützenden Programmiersprache geschrieben wurden, aus auf sie zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7d228-113">If your component conforms to the Common Language Specification, it is guaranteed to be CLS-compliant and can be accessed from code in assemblies written in any programming language that supports the CLS.</span></span> <span data-ttu-id="7d228-114">Sie können bestimmen, ob die Komponente zur Kompilierzeit der Common Language Specification entspricht, indem Sie das [CLSCompliantAttribute](xref:System.CLSCompliantAttribute)-Attribut auf den Quellcode anwenden.</span><span class="sxs-lookup"><span data-stu-id="7d228-114">You can determine whether your component conforms to the Common Language Specification at compile time by applying the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute to your source code.</span></span> <span data-ttu-id="7d228-115">Weitere Informationen finden Sie im Abschnitt zum [CLSCompliantAttribute-Attribut](#the-clscompliantattribute-attribute).</span><span class="sxs-lookup"><span data-stu-id="7d228-115">For more information, see [The CLSCompliantAttribute attribute](#the-clscompliantattribute-attribute).</span></span>

## <a name="cls-compliance-rules"></a><span data-ttu-id="7d228-116">CLS-Kompatibilitätsregeln</span><span class="sxs-lookup"><span data-stu-id="7d228-116">CLS compliance rules</span></span>

<span data-ttu-id="7d228-117">In diesem Abschnitt werden die Regeln zum Erstellen einer CLS-kompatiblen Komponente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7d228-117">This section discusses the rules for creating a CLS-compliant component.</span></span> <span data-ttu-id="7d228-118">Eine vollständige Liste der Regeln finden Sie unter Partition I, Klausel 11 im [ECMA 335-Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="7d228-118">For a complete list of rules, see Partition I, Clause 11 of the [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="7d228-119">In der Common Language Specification wird für jede Regel der CLS-Kompatibilität erläutert, wie sie auf Consumer (Entwickler, die programmgesteuert auf eine CLS-kompatible Komponente zugreifen), Frameworks (Entwickler, die einen Sprachcompiler zum Erstellen von CLS-kompatiblen Bibliotheken verwenden) und Extender (Entwickler, die zum Erstellen CLS-kompatibler Komponenten ein Tool, wie einen Sprachcompiler oder einen Codeparser, erstellen) anzuwenden ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-119">The Common Language Specification discusses each rule for CLS compliance as it applies to consumers (developers who are programmatically accessing a component that is CLS-compliant), frameworks (developers who are using a language compiler to create CLS-compliant libraries), and extenders (developers who are creating a tool such as a language compiler or a code parser that creates CLS-compliant components).</span></span> <span data-ttu-id="7d228-120">In diesem Artikel wird auf die Anwendbarkeit der Regeln für Frameworks eingegangen.</span><span class="sxs-lookup"><span data-stu-id="7d228-120">This article focuses on the rules as they apply to frameworks.</span></span> <span data-ttu-id="7d228-121">Beachten Sie allerdings, dass möglicherweise einige der Regeln für Extender auch auf Assemblys anwendbar sind, die mithilfe von [Reflection.Emit](xref:System.Reflection.Emit) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-121">Note, though, that some of the rules that apply to extenders may also apply to assemblies that are created using [Reflection.Emit](xref:System.Reflection.Emit).</span></span>

<span data-ttu-id="7d228-122">Um eine sprachenneutrale Komponente zu entwerfen, müssen Sie nur die CLS-Kompatibilitätregeln auf die öffentliche Schnittstelle der Komponente anwenden.</span><span class="sxs-lookup"><span data-stu-id="7d228-122">To design a component that is language independent, you only need to apply the rules for CLS compliance to your component's public interface.</span></span> <span data-ttu-id="7d228-123">Die private Implementierung muss nicht mit der Spezifikation konform sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-123">Your private implementation does not have to conform to the specification.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d228-124">Die Regeln für CLS-Kompatibilität gelten nur für die öffentlichen Schnittstelle einer Komponente, nicht für die private Implementierung.</span><span class="sxs-lookup"><span data-stu-id="7d228-124">The rules for CLS compliance apply only to a component's public interface, not to its private implementation.</span></span>

<span data-ttu-id="7d228-125">Zum Beispiel sind ganze Zahlen ohne Vorzeichen, außer [Byte](xref:System.Byte), nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-125">For example, unsigned integers other than [Byte](xref:System.Byte) are not CLS-compliant.</span></span> <span data-ttu-id="7d228-126">Da die `Person`-Klasse im folgenden Beispiel eine `Age`-Eigenschaft des Typs [UInt16](xref:System.UInt16) verfügbar macht, zeigt der folgende Code eine Compilerwarnung an.</span><span class="sxs-lookup"><span data-stu-id="7d228-126">Because the `Person` class in the following example exposes an `Age` property of type [UInt16](xref:System.UInt16), the following code displays a compiler warning.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private UInt16 personAge = 0;

   public UInt16 Age
   { get { return personAge; } }
}
// The attempt to compile the example displays the following compiler warning:
//    Public1.cs(10,18): warning CS3003: Type of 'Person.Age' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As UInt16
      Get
         Return personAge
      End Get
   End Property
End Class
' The attempt to compile the example displays the following compiler warning:
'    Public1.vb(9) : warning BC40027: Return type of function 'Age' is not CLS-compliant.
'
'       Public ReadOnly Property Age As UInt16
'                                ~~~
```

<span data-ttu-id="7d228-127">Sie können CLS-Kompatibilität für die Person-Klasse erreichen, indem Sie den Typ der `Age`-Eigenschaft von `UInt16` in [Int16](xref:System.Int16) ändern. Dies ist eine CLS-kompatible ganze Zahl mit Vorzeichen und einer Länge von 16 Bit.</span><span class="sxs-lookup"><span data-stu-id="7d228-127">You can make the Person class CLS-compliant by changing the type of `Age` property from `UInt16` to [Int16](xref:System.Int16), which is a CLS-compliant, 16-bit signed integer.</span></span> <span data-ttu-id="7d228-128">Sie müssen den Typ des privaten `personAge`-Felds nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="7d228-128">You do not have to change the type of the private `personAge` field.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private Int16 personAge = 0;

   public Int16 Age
   { get { return personAge; } }
}
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As Int16
      Get
         Return CType(personAge, Int16)
      End Get
   End Property
End Class
```

<span data-ttu-id="7d228-129">Die öffentliche Schnittstelle einer Bibliothek besteht aus folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="7d228-129">A library's public interface consists of the following:</span></span>

* <span data-ttu-id="7d228-130">Definitionen öffentlicher Klassen</span><span class="sxs-lookup"><span data-stu-id="7d228-130">Definitions of public classes.</span></span>

* <span data-ttu-id="7d228-131">Definitionen öffentlicher Member von öffentlichen Klassen sowie in Definitionen von Membern, auf die abgeleitete Klassen zugreifen können (d. h. geschützte Member).</span><span class="sxs-lookup"><span data-stu-id="7d228-131">Definitions of the public members of public classes, and definitions of members accessible to derived classes (that is, protected members).</span></span>

* <span data-ttu-id="7d228-132">Parameter und Rückgabetypen öffentlicher Methoden von öffentlichen Klassen sowie Parameter und Rückgabetypen von Methoden, auf die abgeleitete Klassen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="7d228-132">Parameters and return types of public methods of public classes, and parameters and return types of methods accessible to derived classes.</span></span>

<span data-ttu-id="7d228-133">Die Regeln für CLS-Kompatibilität werden in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7d228-133">The rules for CLS compliance are listed in the following table.</span></span> <span data-ttu-id="7d228-134">Der Text der Regeln wird in vollem Wortlaut dem [ECMA 335-Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm) entnommen. Copyright 2012 durch Ecma-International.</span><span class="sxs-lookup"><span data-stu-id="7d228-134">The text of the rules is taken verbatim from the [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm), which is Copyright 2012 by Ecma International.</span></span> <span data-ttu-id="7d228-135">Ausführlichere Informationen zu diesen Regeln finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="7d228-135">More detailed information about these rules is found in the following sections.</span></span>

<span data-ttu-id="7d228-136">Kategorie</span><span class="sxs-lookup"><span data-stu-id="7d228-136">Category</span></span> | <span data-ttu-id="7d228-137">Siehe</span><span class="sxs-lookup"><span data-stu-id="7d228-137">See</span></span> | <span data-ttu-id="7d228-138">Regel</span><span class="sxs-lookup"><span data-stu-id="7d228-138">Rule</span></span> | <span data-ttu-id="7d228-139">Regelzahl</span><span class="sxs-lookup"><span data-stu-id="7d228-139">Rule Number</span></span>
-------- | --- | ---- | -----------
<span data-ttu-id="7d228-140">Zugriff</span><span class="sxs-lookup"><span data-stu-id="7d228-140">Accessibility</span></span> | [<span data-ttu-id="7d228-141">Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="7d228-141">Member accessibility</span></span>](#member-accessibility) | <span data-ttu-id="7d228-142">Beim Überschreiben von geerbten Methoden darf der Zugriff nicht geändert werden, außer wenn eine Methode überschrieben wird, die von einer anderen Assembly mit `family-or-assembly`-Zugriff vererbt wurde.</span><span class="sxs-lookup"><span data-stu-id="7d228-142">Accessibility shall not be changed when overriding inherited methods, except when overriding a method inherited from a different assembly with accessibility `family-or-assembly`.</span></span> <span data-ttu-id="7d228-143">In diesem Fall muss für die Überschreibung `family`-Zugriff festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-143">In this case, the override shall have accessibility `family`.</span></span> | <span data-ttu-id="7d228-144">10</span><span class="sxs-lookup"><span data-stu-id="7d228-144">10</span></span>
<span data-ttu-id="7d228-145">Zugriff</span><span class="sxs-lookup"><span data-stu-id="7d228-145">Accessibility</span></span> | [<span data-ttu-id="7d228-146">Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="7d228-146">Member accessibility</span></span>](#member-accessibility) | <span data-ttu-id="7d228-147">Die Sichtbarkeit und der Zugriff von Typen und Membern soll so beschaffen sein, dass Typen in der Signatur eines Members sichtbar und zugreifbar sind, wann immer der Member selbst sichtbar und zugreifbar ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-147">The visibility and accessibility of types and members shall be such that types in the signature of any member shall be visible and accessible whenever the member itself is visible and accessible.</span></span> <span data-ttu-id="7d228-148">Zum Beispiel soll eine öffentliche Methode, die außerhalb der Assembly sichtbar ist, über kein Argument verfügen, dessen Typ nur innerhalb der Assembly sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-148">For example, a public method that is visible outside its assembly shall not have an argument whose type is visible only within the assembly.</span></span> <span data-ttu-id="7d228-149">Die Sichtbarkeit und der Zugriff von Typen, die einen instanziierten generischen Typ zusammensetzen, der in der Signatur eines beliebigen Members verwendet wird, soll sichtbar und zugreifbar sein, wenn der Member selbst sichtbar und zugreifbar ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-149">The visibility and accessibility of types composing an instantiated generic type used in the signature of any member shall be visible and accessible whenever the member itself is visible and accessible.</span></span> <span data-ttu-id="7d228-150">Zum Beispiel soll ein instanziierter generischer Typ, der in der Signatur eines außerhalb der Assembly sichtbaren Members vorhanden ist, über kein generisches Argument verfügen, dessen Typ nur innerhalb der Assembly sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-150">For example, an instantiated generic type present in the signature of a member that is visible outside its assembly shall not have a generic argument whose type is visible only within the assembly.</span></span> | <span data-ttu-id="7d228-151">12</span><span class="sxs-lookup"><span data-stu-id="7d228-151">12</span></span>
<span data-ttu-id="7d228-152">Arrays</span><span class="sxs-lookup"><span data-stu-id="7d228-152">Arrays</span></span> | [<span data-ttu-id="7d228-153">Arrays</span><span class="sxs-lookup"><span data-stu-id="7d228-153">Arrays</span></span>](#arrays) | <span data-ttu-id="7d228-154">Arrays müssen über Elemente mit einem CLS-kompatiblen Typ verfügen, und die Untergrenze aller Dimensionen des Arrays muss Null sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-154">Arrays shall have elements with a CLS-compliant type, and all dimensions of the array shall have lower bounds of zero.</span></span> <span data-ttu-id="7d228-155">Nur der Tatsache, dass es sich bei einem Element um ein Array handelt sowie der Elementtyp des Arrays muss zur Unterscheidung zwischen Überladungen ausreichen.</span><span class="sxs-lookup"><span data-stu-id="7d228-155">Only the fact that an item is an array and the element type of the array shall be required to distinguish between overloads.</span></span> <span data-ttu-id="7d228-156">Wenn das Überladen auf Grundlage mindestens zweier Arraytypen erfolgt, muss es sich bei den Elementtypen um benannte Typen handeln.</span><span class="sxs-lookup"><span data-stu-id="7d228-156">When overloading is based on two or more array types, the element types shall be named types.</span></span> | <span data-ttu-id="7d228-157">16</span><span class="sxs-lookup"><span data-stu-id="7d228-157">16</span></span>
<span data-ttu-id="7d228-158">Attribute</span><span class="sxs-lookup"><span data-stu-id="7d228-158">Attributes</span></span> | [<span data-ttu-id="7d228-159">Attribute</span><span class="sxs-lookup"><span data-stu-id="7d228-159">Attributes</span></span>](#attributes) | <span data-ttu-id="7d228-160">Attribute müssen vom Typ [System.Attribute](xref:System.Attribute) sein oder von diesem erben.</span><span class="sxs-lookup"><span data-stu-id="7d228-160">Attributes shall be of type [System.Attribute](xref:System.Attribute), or a type inheriting from it.</span></span> | <span data-ttu-id="7d228-161">41</span><span class="sxs-lookup"><span data-stu-id="7d228-161">41</span></span>
<span data-ttu-id="7d228-162">Attribute</span><span class="sxs-lookup"><span data-stu-id="7d228-162">Attributes</span></span> | [<span data-ttu-id="7d228-163">Attribute</span><span class="sxs-lookup"><span data-stu-id="7d228-163">Attributes</span></span>](#attributes) | <span data-ttu-id="7d228-164">CLS gestattet nur eine Teilmenge der Codierungen benutzerdefinierter Attribute.</span><span class="sxs-lookup"><span data-stu-id="7d228-164">The CLS only allows a subset of the encodings of custom attributes.</span></span> <span data-ttu-id="7d228-165">Die einzigen Typen, die in diesen Codierungen angezeigt werden sollen, sind (gemäß Partition IV): [System.Type](xref:System.Type), [System.String](xref:System.String), [System.Char](xref:System.Char), [System.Boolean](xref:System.Boolean), [System.Byte](xref:System.Byte), [System.Int16](xref:System.Int16), [System.Int32](xref:System.Int32), [System.Int64](xref:System.Int64), [System.Single](xref:System.Single), [System.Double](xref:System.Double) und jeder Enumerationstyp basierend auf einem CLS-kompatiblen ganzzahligen Basistyp.</span><span class="sxs-lookup"><span data-stu-id="7d228-165">The only types that shall appear in these encodings are (see Partition IV): [System.Type](xref:System.Type), [System.String](xref:System.String), [System.Char](xref:System.Char), [System.Boolean](xref:System.Boolean), [System.Byte](xref:System.Byte), [System.Int16](xref:System.Int16), [System.Int32](xref:System.Int32), [System.Int64](xref:System.Int64), [System.Single](xref:System.Single), [System.Double](xref:System.Double), and any enumeration type based on a CLS-compliant base integer type.</span></span> | <span data-ttu-id="7d228-166">34</span><span class="sxs-lookup"><span data-stu-id="7d228-166">34</span></span>
<span data-ttu-id="7d228-167">Attribute</span><span class="sxs-lookup"><span data-stu-id="7d228-167">Attributes</span></span> | [<span data-ttu-id="7d228-168">Attribute</span><span class="sxs-lookup"><span data-stu-id="7d228-168">Attributes</span></span>](#attributes) | <span data-ttu-id="7d228-169">Nach der CLS sind nicht öffentlich sichtbare erforderliche Modifizierer (`modreq`, siehe Partition II) zulässig, allerdings sind optionale Modifizierer (`modopt`, siehe Partition II), die sie nicht versteht, zulässig.</span><span class="sxs-lookup"><span data-stu-id="7d228-169">The CLS does not allow publicly visible required modifiers (`modreq`, see Partition II), but does allow optional modifiers (`modopt`, see Partition II) it does not understand.</span></span> | <span data-ttu-id="7d228-170">35</span><span class="sxs-lookup"><span data-stu-id="7d228-170">35</span></span>
<span data-ttu-id="7d228-171">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="7d228-171">Constructors</span></span> | [<span data-ttu-id="7d228-172">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="7d228-172">Constructors</span></span>](#constructors) | <span data-ttu-id="7d228-173">Ein Objektkonstruktor muss einen Instanzenkonstruktor seiner Basisklasse aufrufen, bevor ein Zugriff auf geerbte Instanzdaten erfolgt.</span><span class="sxs-lookup"><span data-stu-id="7d228-173">An object constructor shall call some instance constructor of its base class before any access occurs to inherited instance data.</span></span> <span data-ttu-id="7d228-174">(Dies gilt nicht für Werttypen, die über keine Konstruktoren verfügen müssen.)</span><span class="sxs-lookup"><span data-stu-id="7d228-174">(This does not apply to value types, which need not have constructors.)</span></span>  | <span data-ttu-id="7d228-175">21</span><span class="sxs-lookup"><span data-stu-id="7d228-175">21</span></span>
<span data-ttu-id="7d228-176">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="7d228-176">Constructors</span></span> | [<span data-ttu-id="7d228-177">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="7d228-177">Constructors</span></span>](#constructors) | <span data-ttu-id="7d228-178">Ein Objektkonstruktor darf nicht aufgerufen werden, außer als Teil bei der Erstellung eines Objekts und ein Objekt darf nicht zweimal initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-178">An object constructor shall not be called except as part of the creation of an object, and an object shall not be initialized twice.</span></span> | <span data-ttu-id="7d228-179">22</span><span class="sxs-lookup"><span data-stu-id="7d228-179">22</span></span>
<span data-ttu-id="7d228-180">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7d228-180">Enumerations</span></span> | [<span data-ttu-id="7d228-181">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7d228-181">Enumerations</span></span>](#enumerations) | <span data-ttu-id="7d228-182">Der zugrunde liegende Typ einer Enumeration muss ein integrierter CLS-Ganzzahltyp sein, der Name des Felds muss "value__" lauten, und das Feld muss als `RTSpecialName` gekennzeichnet sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-182">The underlying type of an enum shall be a built-in CLS integer type, the name of the field shall be "value__", and that field shall be marked `RTSpecialName`.</span></span> |  <span data-ttu-id="7d228-183">7</span><span class="sxs-lookup"><span data-stu-id="7d228-183">7</span></span>
<span data-ttu-id="7d228-184">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7d228-184">Enumerations</span></span> | [<span data-ttu-id="7d228-185">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7d228-185">Enumerations</span></span>](#enumerations) | <span data-ttu-id="7d228-186">Es gibt zwei verschiedene Arten von Enumerationen, die aufgrund des Vorhandenseins oder Fehlens des benutzerdefinierten Attributs [System.FlagsAttribute](xref:System.FlagsAttribute) (gemäß Partition IV Library) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-186">There are two distinct kinds of enums, indicated by the presence or absence of the [System.FlagsAttribute](xref:System.FlagsAttribute) (see Partition IV Library) custom attribute.</span></span> <span data-ttu-id="7d228-187">Eine stellt benannte ganzzahlige Werte dar, die Andere stellt benannte Bitflags dar, die zum Generieren eines unbenannten Werts kombiniert werden können.</span><span class="sxs-lookup"><span data-stu-id="7d228-187">One represents named integer values; the other represents named bit flags that can be combined to generate an unnamed value.</span></span> <span data-ttu-id="7d228-188">Der Wert einer `enum` ist nicht auf die angegebenen Werte beschränkt.</span><span class="sxs-lookup"><span data-stu-id="7d228-188">The value of an `enum` is not limited to the specified values.</span></span> |  <span data-ttu-id="7d228-189">8</span><span class="sxs-lookup"><span data-stu-id="7d228-189">8</span></span>
<span data-ttu-id="7d228-190">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7d228-190">Enumerations</span></span> | [<span data-ttu-id="7d228-191">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7d228-191">Enumerations</span></span>](#enumerations) | <span data-ttu-id="7d228-192">Literale statische Felder einer Enumeration müssen vom Typ der Enumeration selbst sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-192">Literal static fields of an enum shall have the type of the enum itself.</span></span> |  <span data-ttu-id="7d228-193">9</span><span class="sxs-lookup"><span data-stu-id="7d228-193">9</span></span>
<span data-ttu-id="7d228-194">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7d228-194">Events</span></span> | [<span data-ttu-id="7d228-195">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7d228-195">Events</span></span>](#events) | <span data-ttu-id="7d228-196">Die Methoden, die ein Ereignis implementieren, müssen in den Metadaten als `SpecialName` gekennzeichnet sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-196">The methods that implement an event shall be marked `SpecialName` in the metadata.</span></span> |<span data-ttu-id="7d228-197">29</span><span class="sxs-lookup"><span data-stu-id="7d228-197">29</span></span>
<span data-ttu-id="7d228-198">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7d228-198">Events</span></span> | [<span data-ttu-id="7d228-199">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7d228-199">Events</span></span>](#events) | <span data-ttu-id="7d228-200">Der Zugriff eines Ereignisses und seiner Zugriffsmethoden muss identisch sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-200">The accessibility of an event and of its accessors shall be identical.</span></span> |<span data-ttu-id="7d228-201">30</span><span class="sxs-lookup"><span data-stu-id="7d228-201">30</span></span>
<span data-ttu-id="7d228-202">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7d228-202">Events</span></span> | [<span data-ttu-id="7d228-203">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7d228-203">Events</span></span>](#events) | <span data-ttu-id="7d228-204">Die `add` und `remove`-Methoden eines Ereignisses müssen entweder beide vorhanden oder beide nicht vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-204">The `add` and `remove` methods for an event shall both either be present or absent.</span></span> |<span data-ttu-id="7d228-205">31</span><span class="sxs-lookup"><span data-stu-id="7d228-205">31</span></span>
<span data-ttu-id="7d228-206">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7d228-206">Events</span></span> | [<span data-ttu-id="7d228-207">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7d228-207">Events</span></span>](#events) | <span data-ttu-id="7d228-208">Die `add`- und `remove`-Methoden eines Ereignisses müssen jeweils einen Parameter akzeptieren, dessen Typ den Ereignistyp definiert. Dieser Typ muss von [System.Delegate](xref:System.Delegate) abgeleitet sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-208">The `add` and `remove` methods for an event shall each take one parameter whose type defines the type of the event and that shall be derived from [System.Delegate](xref:System.Delegate).</span></span> |<span data-ttu-id="7d228-209">32</span><span class="sxs-lookup"><span data-stu-id="7d228-209">32</span></span>
<span data-ttu-id="7d228-210">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7d228-210">Events</span></span> | [<span data-ttu-id="7d228-211">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7d228-211">Events</span></span>](#events) | <span data-ttu-id="7d228-212">Ereignisse müssen einem bestimmten Benennungsschema folgen.</span><span class="sxs-lookup"><span data-stu-id="7d228-212">Events shall adhere to a specific naming pattern.</span></span> <span data-ttu-id="7d228-213">Das SpecialName-Attribut, auf das in CLS-Regel 29 verwiesen wird, muss in den entsprechenden Namensvergleichen ignoriert werden und Bezeichnerregeln einhalten.</span><span class="sxs-lookup"><span data-stu-id="7d228-213">The SpecialName attribute referred to in CLS rule 29 shall be ignored in appropriate name comparisons and shall adhere to identifier rules.</span></span>  |<span data-ttu-id="7d228-214">33</span><span class="sxs-lookup"><span data-stu-id="7d228-214">33</span></span>
<span data-ttu-id="7d228-215">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="7d228-215">Exceptions</span></span> | [<span data-ttu-id="7d228-216">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="7d228-216">Exceptions</span></span>](#exceptions) | <span data-ttu-id="7d228-217">Ausgelöste Objekte müssen vom Typ [System.Exception](xref:System.Exception) oder einem davon geerbten Typ sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-217">Objects that are thrown shall be of type [System.Exception](xref:System.Exception) or a type inheriting from it.</span></span> <span data-ttu-id="7d228-218">Dennoch müssen CLS-kompatible Methoden die Weitergabe anderer Ausnahmetypen nicht blockieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-218">Nonetheless, CLS-compliant methods are not required to block the propagation of other types of exceptions.</span></span> | <span data-ttu-id="7d228-219">40</span><span class="sxs-lookup"><span data-stu-id="7d228-219">40</span></span>
<span data-ttu-id="7d228-220">Allgemein</span><span class="sxs-lookup"><span data-stu-id="7d228-220">General</span></span> | [<span data-ttu-id="7d228-221">CLS-Kompatibilitätsregeln</span><span class="sxs-lookup"><span data-stu-id="7d228-221">CLS compliance rules</span></span>](#cls-compliance-rules) | <span data-ttu-id="7d228-222">CLS-Regeln gelten nur für die Teile eines Typs, die außerhalb der definierenden Assembly sichtbar sind und auf die außerhalb der definierenden Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7d228-222">CLS rules apply only to those parts of a type that are accessible or visible outside of the defining assembly.</span></span> | <span data-ttu-id="7d228-223">1</span><span class="sxs-lookup"><span data-stu-id="7d228-223">1</span></span>
<span data-ttu-id="7d228-224">Allgemein</span><span class="sxs-lookup"><span data-stu-id="7d228-224">General</span></span> | [<span data-ttu-id="7d228-225">CLS-Kompatibilitätsregeln</span><span class="sxs-lookup"><span data-stu-id="7d228-225">CLS compliance rules</span></span>](#cls-compliance-rules) | <span data-ttu-id="7d228-226">Member von Typen, die nicht CLS-kompatibel sind, dürfen nicht als CLS-kompatibel gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-226">Members of non-CLS compliant types shall not be marked CLS-compliant.</span></span> | <span data-ttu-id="7d228-227">2</span><span class="sxs-lookup"><span data-stu-id="7d228-227">2</span></span>
<span data-ttu-id="7d228-228">Generics</span><span class="sxs-lookup"><span data-stu-id="7d228-228">Generics</span></span> | [<span data-ttu-id="7d228-229">Generische Typen und Member</span><span class="sxs-lookup"><span data-stu-id="7d228-229">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="7d228-230">Geschachtelte Typen müssen mindestens so viele generische Parameter aufweisen wie der einschließende Typ.</span><span class="sxs-lookup"><span data-stu-id="7d228-230">Nested types shall have at least as many generic parameters as the enclosing type.</span></span> <span data-ttu-id="7d228-231">Die Position von generischen Parametern in einem geschachtelten Typ entspricht der Position der generischen Parameter im einschließenden Typ.</span><span class="sxs-lookup"><span data-stu-id="7d228-231">Generic parameters in a nested type correspond by position to the generic parameters in its enclosing type.</span></span>  | <span data-ttu-id="7d228-232">42</span><span class="sxs-lookup"><span data-stu-id="7d228-232">42</span></span>
<span data-ttu-id="7d228-233">Generics</span><span class="sxs-lookup"><span data-stu-id="7d228-233">Generics</span></span> | [<span data-ttu-id="7d228-234">Generische Typen und Member</span><span class="sxs-lookup"><span data-stu-id="7d228-234">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="7d228-235">Der Name eines generischen Typs muss die Anzahl von Typparametern, die auf dem nicht geschachtelten Typ deklariert oder neu in den Typ eingeführt werden, kodieren, wenn er entsprechend der oben definierten Regeln geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-235">The name of a generic type shall encode the number of type parameters declared on the non-nested type, or newly introduced to the type if nested, according to the rules defined above.</span></span> | <span data-ttu-id="7d228-236">43</span><span class="sxs-lookup"><span data-stu-id="7d228-236">43</span></span>
<span data-ttu-id="7d228-237">Generics</span><span class="sxs-lookup"><span data-stu-id="7d228-237">Generics</span></span> | [<span data-ttu-id="7d228-238">Generische Typen und Member</span><span class="sxs-lookup"><span data-stu-id="7d228-238">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="7d228-239">Ein generischer Typ muss genügend Einschränkungen neu deklarieren, um zu gewährleisten, dass alle Einschränkungen des Basistyps oder der Schnittstellen durch die Einschränkungen des generischen Typs erfüllt sein würden.</span><span class="sxs-lookup"><span data-stu-id="7d228-239">A generic type shall redeclare sufficient constraints to guarantee that any constraints on the base type, or interfaces would be satisfied by the generic type constraints.</span></span> | <span data-ttu-id="7d228-240">44</span><span class="sxs-lookup"><span data-stu-id="7d228-240">44</span></span>
<span data-ttu-id="7d228-241">Generics</span><span class="sxs-lookup"><span data-stu-id="7d228-241">Generics</span></span> | [<span data-ttu-id="7d228-242">Generische Typen und Member</span><span class="sxs-lookup"><span data-stu-id="7d228-242">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="7d228-243">Als Einschränkungen für generische Parameter verwendete Typen müssen selbst CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-243">Types used as constraints on generic parameters shall themselves be CLS-compliant.</span></span> | <span data-ttu-id="7d228-244">45</span><span class="sxs-lookup"><span data-stu-id="7d228-244">45</span></span>
<span data-ttu-id="7d228-245">Generics</span><span class="sxs-lookup"><span data-stu-id="7d228-245">Generics</span></span> | [<span data-ttu-id="7d228-246">Generische Typen und Member</span><span class="sxs-lookup"><span data-stu-id="7d228-246">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="7d228-247">Es muss davon ausgegangen werden, dass die Sichtbarkeit und der Zugriff auf Member (einschließlich geschachtelter Typen) in einem instanziierten generischen Typ sich nicht auf die gesamte Deklaration des generischen Typs bezieht, sondern auf die spezifische Instanziierung.</span><span class="sxs-lookup"><span data-stu-id="7d228-247">The visibility and accessibility of members (including nested types) in an instantiated generic type shall be considered to be scoped to the specific instantiation rather than the generic type declaration as a whole.</span></span> <span data-ttu-id="7d228-248">Davon ausgehend gelten die Sichtbarkeits- und Zugriffsregeln der CLS-Regel 12 weiterhin.</span><span class="sxs-lookup"><span data-stu-id="7d228-248">Assuming this, the visibility and accessibility rules of CLS rule 12 still apply.</span></span> | <span data-ttu-id="7d228-249">46</span><span class="sxs-lookup"><span data-stu-id="7d228-249">46</span></span>
<span data-ttu-id="7d228-250">Generics</span><span class="sxs-lookup"><span data-stu-id="7d228-250">Generics</span></span> | [<span data-ttu-id="7d228-251">Generische Typen und Member</span><span class="sxs-lookup"><span data-stu-id="7d228-251">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="7d228-252">Für jede abstrakte oder virtuell generische Methode muss es eine konkrete (nicht abstrakte) Standardimplementierung geben.</span><span class="sxs-lookup"><span data-stu-id="7d228-252">For each abstract or virtual generic method, there shall be a default concrete (nonabstract) implementation</span></span> | <span data-ttu-id="7d228-253">47</span><span class="sxs-lookup"><span data-stu-id="7d228-253">47</span></span>
<span data-ttu-id="7d228-254">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7d228-254">Interfaces</span></span> | [<span data-ttu-id="7d228-255">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7d228-255">Interfaces</span></span>](#interfaces) | <span data-ttu-id="7d228-256">Zum Implementieren von CLS-kompatiblen Schnittstellen darf keine Definition von nicht CLS-kompatiblen Methoden erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-256">CLS-compliant interfaces shall not require the definition of non-CLS compliant methods in order to implement them.</span></span> | <span data-ttu-id="7d228-257">18</span><span class="sxs-lookup"><span data-stu-id="7d228-257">18</span></span>
<span data-ttu-id="7d228-258">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7d228-258">Interfaces</span></span> | [<span data-ttu-id="7d228-259">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7d228-259">Interfaces</span></span>](#interfaces) | <span data-ttu-id="7d228-260">CLS-kompatible Schnittstellen dürfen weder statische Methoden noch Felder definieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-260">CLS-compliant interfaces shall not define static methods, nor shall they define fields.</span></span> | <span data-ttu-id="7d228-261">19</span><span class="sxs-lookup"><span data-stu-id="7d228-261">19</span></span>
<span data-ttu-id="7d228-262">Member</span><span class="sxs-lookup"><span data-stu-id="7d228-262">Members</span></span> | [<span data-ttu-id="7d228-263">Typmember im Allgemeinen</span><span class="sxs-lookup"><span data-stu-id="7d228-263">Type members in general</span></span>](#type-members-in-general) | <span data-ttu-id="7d228-264">Globale static-Felder und Methoden sind nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-264">Global static fields and methods are not CLS-compliant.</span></span> | <span data-ttu-id="7d228-265">36</span><span class="sxs-lookup"><span data-stu-id="7d228-265">36</span></span>
<span data-ttu-id="7d228-266">Member</span><span class="sxs-lookup"><span data-stu-id="7d228-266">Members</span></span> | -- | <span data-ttu-id="7d228-267">Der Wert eines literalen statischen Elements wird von der Verwendung von Feldinitialisierungsmetadaten angegeben.</span><span class="sxs-lookup"><span data-stu-id="7d228-267">The value of a literal static is specified through the use of field initialization metadata.</span></span> <span data-ttu-id="7d228-268">Ein CLS-kompatibles Literal muss über einen Wert verfügen, der in den Feldinitialisierungsmetadaten angegeben wird, der genau vom gleichen Typ wie das Literal ist (oder des zugrunde liegenden Typs, wenn dieses Literal `enum` ist).</span><span class="sxs-lookup"><span data-stu-id="7d228-268">A CLS-compliant literal must have a value specified in field initialization metadata that is of exactly the same type as the literal (or of the underlying type, if that literal is an `enum`).</span></span> | <span data-ttu-id="7d228-269">13</span><span class="sxs-lookup"><span data-stu-id="7d228-269">13</span></span>
<span data-ttu-id="7d228-270">Member</span><span class="sxs-lookup"><span data-stu-id="7d228-270">Members</span></span> | [<span data-ttu-id="7d228-271">Typmember im Allgemeinen</span><span class="sxs-lookup"><span data-stu-id="7d228-271">Type members in general</span></span>](#type-members-in-general) | <span data-ttu-id="7d228-272">Die vararg-Einschränkung ist nicht Teil der CLS, und die einzige Aufrufkonvention, die von der CLS unterstützt wird, ist die verwaltete Standardaufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="7d228-272">The vararg constraint is not part of the CLS, and the only calling convention supported by the CLS is the standard managed calling convention.</span></span> | <span data-ttu-id="7d228-273">15</span><span class="sxs-lookup"><span data-stu-id="7d228-273">15</span></span>
<span data-ttu-id="7d228-274">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="7d228-274">Naming conventions</span></span> | [<span data-ttu-id="7d228-275">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="7d228-275">Naming conventions</span></span>](#naming-conventions) | <span data-ttu-id="7d228-276">Assemblys müssen Anhang 7 von Fachbericht 15 des Unicode Standard3.0 folgen, in dem der Satz von Zeichen geregelt wird, die am Anfang oder innerhalb von Bezeichnern enthalten sein dürfen. Er ist online unter [Unicode Normalization Forms](https://unicode.org/reports/tr15/) (Unicode-Normalisierungsformen) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7d228-276">Assemblies shall follow Annex 7 of Technical Report 15 of the Unicode Standard3.0 governing the set of characters permitted to start and be included in identifiers, available online at [Unicode Normalization Forms](https://unicode.org/reports/tr15/).</span></span> <span data-ttu-id="7d228-277">Bezeichner müssen im kanonischen Format vorliegen, das durch die Unicode-Normalisierungsform C definiert wird. Im Sinne der CLS sind zwei Bezeichner gleich, wenn ihre kleingeschriebenen Zuordnungen (wie von den Gebietsschema-unabhängigen, klein geschriebenen 1:1-Unicodezuordnungen angegeben) gleich sind.</span><span class="sxs-lookup"><span data-stu-id="7d228-277">Identifiers shall be in the canonical format defined by Unicode Normalization Form C. For CLS purposes, two identifiers are the same if their lowercase mappings (as specified by the Unicode locale-insensitive, one-to-one lowercase mappings) are the same.</span></span> <span data-ttu-id="7d228-278">Demnach müssen sich zwei Bezeichner in mehr als nur der Großschreibung unterscheiden, damit sie gemäß der CLS als unterschiedlich angesehen werden können.</span><span class="sxs-lookup"><span data-stu-id="7d228-278">That is, for two identifiers to be considered different under the CLS they shall differ in more than simply their case.</span></span> <span data-ttu-id="7d228-279">Um jedoch eine geerbte Definition überschreiben zu können, erfordert die CLI die genaue Codierung der ursprünglichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="7d228-279">However, in order to override an inherited definition the CLI requires the precise encoding of the original declaration be used.</span></span> | <span data-ttu-id="7d228-280">4</span><span class="sxs-lookup"><span data-stu-id="7d228-280">4</span></span>
<span data-ttu-id="7d228-281">Überladen</span><span class="sxs-lookup"><span data-stu-id="7d228-281">Overloading</span></span> | [<span data-ttu-id="7d228-282">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="7d228-282">Naming conventions</span></span>](#naming-conventions) | <span data-ttu-id="7d228-283">Alle Namen, die in einem CLS-kompatiblen Bereich eingeführt werden, müssen in ihrer Art eindeutig unabhängig sein, außer bei identischen Namen, die durch Überladen aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-283">All names introduced in a CLS-compliant scope shall be distinct independent of kind, except where the names are identical and resolved via overloading.</span></span> <span data-ttu-id="7d228-284">Während es bei CTS möglich ist, dass ein einzelner Typ denselben Namen für eine Methode und ein Feld verwendet, ist dies bei CLS demnach unmöglich.</span><span class="sxs-lookup"><span data-stu-id="7d228-284">That is, while the CTS allows a single type to use the same name for a method and a field, the CLS does not.</span></span> | <span data-ttu-id="7d228-285">5</span><span class="sxs-lookup"><span data-stu-id="7d228-285">5</span></span>
<span data-ttu-id="7d228-286">Überladen</span><span class="sxs-lookup"><span data-stu-id="7d228-286">Overloading</span></span> | [<span data-ttu-id="7d228-287">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="7d228-287">Naming conventions</span></span>](#naming-conventions) | <span data-ttu-id="7d228-288">Felder und geschachtelte Typen müssen allein durch Vergleich des Bezeichners zu unterscheiden sein, auch wenn bei CTS verschiedene Signaturen unterschieden werden können.</span><span class="sxs-lookup"><span data-stu-id="7d228-288">Fields and nested types shall be distinct by identifier comparison alone, even though the CTS allows distinct signatures to be distinguished.</span></span> <span data-ttu-id="7d228-289">Methoden, Eigenschaften und Ereignisse mit demselben Namen (gemäß Bezeichnervergleich) müssen sich durch mehr als nur den Rückgabetyp unterscheiden (außer wie in CLS-Regel 39 angegeben).</span><span class="sxs-lookup"><span data-stu-id="7d228-289">Methods, properties, and events that have the same name (by identifier comparison) shall differ by more than just the return type, except as specified in CLS Rule 39</span></span> | <span data-ttu-id="7d228-290">6</span><span class="sxs-lookup"><span data-stu-id="7d228-290">6</span></span>
<span data-ttu-id="7d228-291">Überladen</span><span class="sxs-lookup"><span data-stu-id="7d228-291">Overloading</span></span> | [<span data-ttu-id="7d228-292">Overloads</span><span class="sxs-lookup"><span data-stu-id="7d228-292">Overloads</span></span>](#overloads) | <span data-ttu-id="7d228-293">Nur Eigenschaften und Methoden können überladen werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-293">Only properties and methods can be overloaded.</span></span> | <span data-ttu-id="7d228-294">37</span><span class="sxs-lookup"><span data-stu-id="7d228-294">37</span></span>
<span data-ttu-id="7d228-295">Überladen</span><span class="sxs-lookup"><span data-stu-id="7d228-295">Overloading</span></span> | [<span data-ttu-id="7d228-296">Overloads</span><span class="sxs-lookup"><span data-stu-id="7d228-296">Overloads</span></span>](#overloads) |<span data-ttu-id="7d228-297">Eigenschaften und Methoden können allein basierend auf der Anzahl und den Typen ihrer Parameter überladen werden, außer den Konvertierungsoperatoren `op_Implicit` und `op_Explicit`, die auch auf Grundlage des Rückgabetyps überladen werden können.</span><span class="sxs-lookup"><span data-stu-id="7d228-297">Properties and methods can be overloaded based only on the number and types of their parameters, except the conversion operators named `op_Implicit` and `op_Explicit`, which can also be overloaded based on their return type.</span></span> | <span data-ttu-id="7d228-298">38</span><span class="sxs-lookup"><span data-stu-id="7d228-298">38</span></span>
<span data-ttu-id="7d228-299">Überladen</span><span class="sxs-lookup"><span data-stu-id="7d228-299">Overloading</span></span> | -- | <span data-ttu-id="7d228-300">Wenn mindestens zwei CLS-kompatible Methoden, die in einem Typ deklariert werden, den gleichen Namen und für einen bestimmten Satz von Typinstanziierungen die gleichen Parameter und Rückgabetypen nutzen, dann müssen alle diese Methoden bei diesen Typinstanziierungen semantisch gleichwertig sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-300">If two or more CLS-compliant methods declared in a type have the same name and, for a specific set of type instantiations, they have the same parameter and return types, then all these methods shall be semantically equivalent at those type instantiations.</span></span> | <span data-ttu-id="7d228-301">48</span><span class="sxs-lookup"><span data-stu-id="7d228-301">48</span></span>
<span data-ttu-id="7d228-302">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d228-302">Properties</span></span> | [<span data-ttu-id="7d228-303">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d228-303">Properties</span></span>](#properties) | <span data-ttu-id="7d228-304">Die Methoden, mit denen die Getter- und die Setter-Methode einer Eigenschaft implementiert werden, müssen in den Metadaten mit `SpecialName` markiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-304">The methods that implement the getter and setter methods of a property shall be marked `SpecialName` in the metadata.</span></span> | <span data-ttu-id="7d228-305">24</span><span class="sxs-lookup"><span data-stu-id="7d228-305">24</span></span>
<span data-ttu-id="7d228-306">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d228-306">Properties</span></span> | [<span data-ttu-id="7d228-307">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d228-307">Properties</span></span>](#properties) | <span data-ttu-id="7d228-308">Die Zugriffsmethoden einer Eigenschaft müssen alle „static“, alle „virtual“ oder alle „instance“ sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-308">A property's accessors shall all be static, all be virtual, or all be instance.</span></span> | <span data-ttu-id="7d228-309">26</span><span class="sxs-lookup"><span data-stu-id="7d228-309">26</span></span>
<span data-ttu-id="7d228-310">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d228-310">Properties</span></span> | [<span data-ttu-id="7d228-311">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d228-311">Properties</span></span>](#properties) | <span data-ttu-id="7d228-312">Der Typ einer Eigenschaft muss dem Rückgabetyp der Getter-Methode und dem Typ des letzten Arguments der Setter-Methode entsprechen.</span><span class="sxs-lookup"><span data-stu-id="7d228-312">The type of a property shall be the return type of the getter and the type of the last argument of the setter.</span></span> <span data-ttu-id="7d228-313">Die Parametertypen der Eigenschaft müssen den Parametertypen der Getter-Methode und, ausgenommen dem Letzten, allen Parametertypen der Setter-Methode entsprechen.</span><span class="sxs-lookup"><span data-stu-id="7d228-313">The types of the parameters of the property shall be the types of the parameters to the getter and the types of all but the final parameter of the setter.</span></span> <span data-ttu-id="7d228-314">Diese Typen müssen CLS-kompatibel sein und dürfen keine verwalteten Zeiger sein (d.h., sie dürfen nicht als Verweise übergeben werden).</span><span class="sxs-lookup"><span data-stu-id="7d228-314">All of these types shall be CLS-compliant, and shall not be managed pointers (that is, shall not be passed by reference).</span></span> | <span data-ttu-id="7d228-315">27</span><span class="sxs-lookup"><span data-stu-id="7d228-315">27</span></span>
<span data-ttu-id="7d228-316">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d228-316">Properties</span></span> | [<span data-ttu-id="7d228-317">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d228-317">Properties</span></span>](#properties) | <span data-ttu-id="7d228-318">Eigenschaften müssen einem bestimmten Benennungsschema folgen.</span><span class="sxs-lookup"><span data-stu-id="7d228-318">Properties shall adhere to a specific naming pattern.</span></span> <span data-ttu-id="7d228-319">Das `SpecialName`-Attribut, auf das in CLS-Regel 24 verwiesen wird, muss in den entsprechenden Namensvergleichen ignoriert werden und Bezeichnerregeln einhalten.</span><span class="sxs-lookup"><span data-stu-id="7d228-319">The `SpecialName` attribute referred to in CLS rule 24 shall be ignored in appropriate name comparisons and shall adhere to identifier rules.</span></span> <span data-ttu-id="7d228-320">Eine Eigenschaft verfügt über eine Getter-Methode, eine Setter-Methode oder beide.</span><span class="sxs-lookup"><span data-stu-id="7d228-320">A property shall have a getter method, a setter method, or both.</span></span> | <span data-ttu-id="7d228-321">28</span><span class="sxs-lookup"><span data-stu-id="7d228-321">28</span></span>
<span data-ttu-id="7d228-322">Typkonvertierung</span><span class="sxs-lookup"><span data-stu-id="7d228-322">Type conversion</span></span> | [<span data-ttu-id="7d228-323">Typkonvertierung</span><span class="sxs-lookup"><span data-stu-id="7d228-323">Type conversion</span></span>](#type-conversion) | <span data-ttu-id="7d228-324">Wenn entweder op_Implicit oder op_Explicit bereitgestellt wird, muss eine alternative Möglichkeit für die Umwandlung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-324">If either op_Implicit or op_Explicit is provided, an alternate means of providing the coercion shall be provided.</span></span> | <span data-ttu-id="7d228-325">39</span><span class="sxs-lookup"><span data-stu-id="7d228-325">39</span></span>
<span data-ttu-id="7d228-326">Typen</span><span class="sxs-lookup"><span data-stu-id="7d228-326">Types</span></span> | [<span data-ttu-id="7d228-327">Typen und Typmembersignaturen</span><span class="sxs-lookup"><span data-stu-id="7d228-327">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="7d228-328">Geschachtelte Werttypen sind nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-328">Boxed value types are not CLS-compliant.</span></span> | <span data-ttu-id="7d228-329">3</span><span class="sxs-lookup"><span data-stu-id="7d228-329">3</span></span>
<span data-ttu-id="7d228-330">Typen</span><span class="sxs-lookup"><span data-stu-id="7d228-330">Types</span></span> | [<span data-ttu-id="7d228-331">Typen und Typmembersignaturen</span><span class="sxs-lookup"><span data-stu-id="7d228-331">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="7d228-332">Alle Typen, die in einer Signatur erscheinen, müssen CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-332">All types appearing in a signature shall be CLS-compliant.</span></span> <span data-ttu-id="7d228-333">Alle Typen, die einen instanziierten generischen Typ erstellen, müssen CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-333">All types composing an instantiated generic type shall be CLS-compliant.</span></span> | <span data-ttu-id="7d228-334">11</span><span class="sxs-lookup"><span data-stu-id="7d228-334">11</span></span>
<span data-ttu-id="7d228-335">Typen</span><span class="sxs-lookup"><span data-stu-id="7d228-335">Types</span></span> | [<span data-ttu-id="7d228-336">Typen und Typmembersignaturen</span><span class="sxs-lookup"><span data-stu-id="7d228-336">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="7d228-337">Typisierte Verweise sind nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-337">Typed references are not CLS-compliant.</span></span> | <span data-ttu-id="7d228-338">14</span><span class="sxs-lookup"><span data-stu-id="7d228-338">14</span></span>
<span data-ttu-id="7d228-339">Typen</span><span class="sxs-lookup"><span data-stu-id="7d228-339">Types</span></span> | [<span data-ttu-id="7d228-340">Typen und Typmembersignaturen</span><span class="sxs-lookup"><span data-stu-id="7d228-340">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="7d228-341">Nicht verwaltete Zeigertypen sind nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-341">Unmanaged pointer types are not CLS-compliant.</span></span> | <span data-ttu-id="7d228-342">17</span><span class="sxs-lookup"><span data-stu-id="7d228-342">17</span></span>
<span data-ttu-id="7d228-343">Typen</span><span class="sxs-lookup"><span data-stu-id="7d228-343">Types</span></span> | [<span data-ttu-id="7d228-344">Typen und Typmembersignaturen</span><span class="sxs-lookup"><span data-stu-id="7d228-344">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="7d228-345">CLS-kompatible Klassen, Werttypen und Schnittstellen dürfen nicht die Implementierung nicht CLS-kompatibler Member erfordern.</span><span class="sxs-lookup"><span data-stu-id="7d228-345">CLS-compliant classes, value types, and interfaces shall not require the implementation of non-CLS-compliant members</span></span> | <span data-ttu-id="7d228-346">20</span><span class="sxs-lookup"><span data-stu-id="7d228-346">20</span></span>
<span data-ttu-id="7d228-347">Typen</span><span class="sxs-lookup"><span data-stu-id="7d228-347">Types</span></span> | [<span data-ttu-id="7d228-348">Typen und Typmembersignaturen</span><span class="sxs-lookup"><span data-stu-id="7d228-348">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="7d228-349">[System.Object](xref:System.Object) ist CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-349">[System.Object](xref:System.Object) is CLS-compliant.</span></span> <span data-ttu-id="7d228-350">Jede andere CLS-kompatible Klasse muss von einer CLS-kompatiblen Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="7d228-350">Any other CLS-compliant class shall inherit from a CLS-compliant class.</span></span> | <span data-ttu-id="7d228-351">23</span><span class="sxs-lookup"><span data-stu-id="7d228-351">23</span></span>

<span data-ttu-id="7d228-352">Index für Unterabschnitte:</span><span class="sxs-lookup"><span data-stu-id="7d228-352">Index to subsections:</span></span>

* [<span data-ttu-id="7d228-353">Typen und Typmembersignaturen</span><span class="sxs-lookup"><span data-stu-id="7d228-353">Types and type member signatures</span></span>](#types-and-type-member-signatures)
* [<span data-ttu-id="7d228-354">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="7d228-354">Naming conventions</span></span>](#naming-conventions)
* [<span data-ttu-id="7d228-355">Typkonvertierung</span><span class="sxs-lookup"><span data-stu-id="7d228-355">Type conversion</span></span>](#type-conversion)
* [<span data-ttu-id="7d228-356">Arrays</span><span class="sxs-lookup"><span data-stu-id="7d228-356">Arrays</span></span>](#arrays)
* [<span data-ttu-id="7d228-357">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7d228-357">Interfaces</span></span>](#interfaces)
* [<span data-ttu-id="7d228-358">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7d228-358">Enumerations</span></span>](#enumerations)
* [<span data-ttu-id="7d228-359">Typmember im Allgemeinen</span><span class="sxs-lookup"><span data-stu-id="7d228-359">Type members in general</span></span>](#type-members-in-general)
* [<span data-ttu-id="7d228-360">Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="7d228-360">Member accessibility</span></span>](#member-accessibility)
* [<span data-ttu-id="7d228-361">Generische Typen und Member</span><span class="sxs-lookup"><span data-stu-id="7d228-361">Generic types and members</span></span>](#generic-types-and-members)
* [<span data-ttu-id="7d228-362">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="7d228-362">Constructors</span></span>](#constructors)
* [<span data-ttu-id="7d228-363">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d228-363">Properties</span></span>](#properties)
* [<span data-ttu-id="7d228-364">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7d228-364">Events</span></span>](#events)
* [<span data-ttu-id="7d228-365">Überladungen</span><span class="sxs-lookup"><span data-stu-id="7d228-365">Overloads</span></span>](#overloads)
* [<span data-ttu-id="7d228-366">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="7d228-366">Exceptions</span></span>](#exceptions)
* [<span data-ttu-id="7d228-367">Attribute</span><span class="sxs-lookup"><span data-stu-id="7d228-367">Attributes</span></span>](#attributes)

### <a name="types-and-type-member-signatures"></a><span data-ttu-id="7d228-368">Typen und Typmembersignaturen</span><span class="sxs-lookup"><span data-stu-id="7d228-368">Types and type member signatures</span></span>

<span data-ttu-id="7d228-369">Der [System.Object](xref:System.Object)-Typ ist CLS-kompatibel, und er ist der Basistyp aller Objekttypen im .NET-Typsystem.</span><span class="sxs-lookup"><span data-stu-id="7d228-369">The [System.Object](xref:System.Object) type is CLS-compliant and is the base type of all object types in the .NET type system.</span></span> <span data-ttu-id="7d228-370">Vererbung erfolgt in .NET entweder implizit (zum Beispiel erbt die [String](xref:System.String)-Klasse implizit von der `Object`-Klasse) oder explizit (zum Beispiel erbt die [CultureNotFoundException](xref:System.Globalization.CultureNotFoundException)-Klasse explizit von der [ArgumentException](xref:System.ArgumentException)-Klasse, die explizit von der [Exception](xref:System.Exception)-Klasse erbt).</span><span class="sxs-lookup"><span data-stu-id="7d228-370">Inheritance in .NET is either implicit (for example, the [String](xref:System.String) class implicitly inherits from the `Object` class) or explicit (for example, the [CultureNotFoundException](xref:System.Globalization.CultureNotFoundException) class explicitly inherits from the [ArgumentException](xref:System.ArgumentException) class, which explicitly inherits from the [Exception](xref:System.Exception) class.</span></span> <span data-ttu-id="7d228-371">Damit ein abgeleiteter Typ CLS-kompatibel ist, muss auch der Basistyp CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-371">For a derived type to be CLS compliant, its base type must also be CLS-compliant.</span></span>

<span data-ttu-id="7d228-372">Im folgenden Beispiel wird ein abgeleiteter Typ veranschaulicht, dessen Basistyp nicht CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-372">The following example shows a derived type whose base type is not CLS-compliant.</span></span> <span data-ttu-id="7d228-373">Es wird eine `Counter`-Basisklasse definiert, die eine ganze Zahl ohne Vorzeichen mit einer Länge von 32 Bit als Indikator verwendet.</span><span class="sxs-lookup"><span data-stu-id="7d228-373">It defines a base `Counter` class that uses an unsigned 32-bit integer as a counter.</span></span> <span data-ttu-id="7d228-374">Da die Klasse Gegenfunktionalität bereitstellt, indem eine ganze Zahl ohne Vorzeichen umgebrochen wird, wird die Klasse als nicht CLS-kompatibel gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="7d228-374">Because the class provides counter functionality by wrapping an unsigned integer, the class is marked as non-CLS-compliant.</span></span> <span data-ttu-id="7d228-375">Daher ist eine abgeleitete Klasse, `NonZeroCounter`, auch nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-375">As a result, a derived class, `NonZeroCounter`, is also not CLS-compliant.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

[CLSCompliant(false)]
public class Counter
{
   UInt32 ctr;

   public Counter()
   {
      ctr = 0;
   }

   protected Counter(UInt32 ctr)
   {
      this.ctr = ctr;
   }

   public override string ToString()
   {
      return $"{ctr}). ";
   }

   public UInt32 Value
   {
      get { return ctr; }
   }

   public void Increment()
   {
      ctr += (uint) 1;
   }
}

public class NonZeroCounter : Counter
{
   public NonZeroCounter(int startIndex) : this((uint) startIndex)
   {
   }

   private NonZeroCounter(UInt32 startIndex) : base(startIndex)
   {
   }
}
// Compilation produces a compiler warning like the following:
//    Type3.cs(37,14): warning CS3009: 'NonZeroCounter': base type 'Counter' is not
//            CLS-compliant
//    Type3.cs(7,14): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>

<CLSCompliant(False)> _
Public Class Counter
   Dim ctr As UInt32

   Public Sub New
      ctr = 0
   End Sub

   Protected Sub New(ctr As UInt32)
      ctr = ctr
   End Sub

   Public Overrides Function ToString() As String
      Return $"{ctr}). "
   End Function

   Public ReadOnly Property Value As UInt32
      Get
         Return ctr
      End Get
   End Property

   Public Sub Increment()
      ctr += CType(1, UInt32)
   End Sub
End Class

Public Class NonZeroCounter : Inherits Counter
   Public Sub New(startIndex As Integer)
      MyClass.New(CType(startIndex, UInt32))
   End Sub

   Private Sub New(startIndex As UInt32)
      MyBase.New(CType(startIndex, UInt32))
   End Sub
End Class
' Compilation produces a compiler warning like the following:
'    Type3.vb(34) : warning BC40026: 'NonZeroCounter' is not CLS-compliant
'    because it derives from 'Counter', which is not CLS-compliant.
'
'    Public Class NonZeroCounter : Inherits Counter
'                 ~~~~~~~~~~~~~~
```

<span data-ttu-id="7d228-376">Alle in den Membersignaturen angezeigten Typen, einschließlich des Rückgabetyps oder des Eigenschaftentyps einer Methode, müssen CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-376">All types that appear in member signatures, including a method's return type or a property type, must be CLS-compliant.</span></span> <span data-ttu-id="7d228-377">Außerdem ist für generische Typen Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="7d228-377">In addition, for generic types:</span></span>

* <span data-ttu-id="7d228-378">Alle Typen, die einen instanziierten generischen Typ zusammensetzen, müssen CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-378">All types that compose an instantiated generic type must be CLS-compliant.</span></span>

* <span data-ttu-id="7d228-379">Alle als Einschränkungen für generische Parameter verwendeten Typen müssen CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-379">All types used as constraints on generic parameters must be CLS-compliant.</span></span>

<span data-ttu-id="7d228-380">Das [allgemeine Typsystem](common-type-system.md) von .NET enthält verschiedene integrierte Datentypen, die direkt von der Common Language Runtime unterstützt werden und insbesondere in den Metadaten einer Assembly codiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-380">The .NET [common type system](common-type-system.md) includes a number of built-in types that are supported directly by the common language runtime and are specially encoded in an assembly's metadata.</span></span> <span data-ttu-id="7d228-381">Von diesen systeminternen Typen sind die in der folgenden Tabelle aufgeführten Typen CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-381">Of these intrinsic types, the types listed in the following table are CLS-compliant.</span></span>

<span data-ttu-id="7d228-382">CLS-kompatibler Typ</span><span class="sxs-lookup"><span data-stu-id="7d228-382">CLS-compliant type</span></span> | <span data-ttu-id="7d228-383">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d228-383">Description</span></span>
------------------ | -----------
[<span data-ttu-id="7d228-384">Byte</span><span class="sxs-lookup"><span data-stu-id="7d228-384">Byte</span></span>](xref:System.Byte) | <span data-ttu-id="7d228-385">Ganze 8-Bit-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="7d228-385">8-bit unsigned integer</span></span>
[<span data-ttu-id="7d228-386">Int16</span><span class="sxs-lookup"><span data-stu-id="7d228-386">Int16</span></span>](xref:System.Int16) | <span data-ttu-id="7d228-387">Ganze 16-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="7d228-387">16-bit signed integer</span></span>
[<span data-ttu-id="7d228-388">Int32</span><span class="sxs-lookup"><span data-stu-id="7d228-388">Int32</span></span>](xref:System.Int32) | <span data-ttu-id="7d228-389">32-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="7d228-389">32-bit signed integer</span></span>
[<span data-ttu-id="7d228-390">Int64</span><span class="sxs-lookup"><span data-stu-id="7d228-390">Int64</span></span>](xref:System.Int64) | <span data-ttu-id="7d228-391">64-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="7d228-391">64-bit signed integer</span></span>
[<span data-ttu-id="7d228-392">Single</span><span class="sxs-lookup"><span data-stu-id="7d228-392">Single</span></span>](xref:System.Single) | <span data-ttu-id="7d228-393">Gleitkommawert mit einfacher Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="7d228-393">Single-precision floating-point value</span></span>
[<span data-ttu-id="7d228-394">Double</span><span class="sxs-lookup"><span data-stu-id="7d228-394">Double</span></span>](xref:System.Double) | <span data-ttu-id="7d228-395">Gleitkommawert mit doppelter Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="7d228-395">Double-precision floating-point value</span></span>
[<span data-ttu-id="7d228-396">Boolean</span><span class="sxs-lookup"><span data-stu-id="7d228-396">Boolean</span></span>](xref:System.Boolean) | <span data-ttu-id="7d228-397">TRUE- oder FALSE-Werttyp</span><span class="sxs-lookup"><span data-stu-id="7d228-397">true or false value type</span></span>
[<span data-ttu-id="7d228-398">Char</span><span class="sxs-lookup"><span data-stu-id="7d228-398">Char</span></span>](xref:System.Char) | <span data-ttu-id="7d228-399">UTF-16-codierte Codeeinheit</span><span class="sxs-lookup"><span data-stu-id="7d228-399">UTF-16 encoded code unit</span></span>
[<span data-ttu-id="7d228-400">Decimal</span><span class="sxs-lookup"><span data-stu-id="7d228-400">Decimal</span></span>](xref:System.Decimal) | <span data-ttu-id="7d228-401">Dezimalzahl ohne Gleitkomma</span><span class="sxs-lookup"><span data-stu-id="7d228-401">Non-floating-point decimal number</span></span>
[<span data-ttu-id="7d228-402">IntPtr</span><span class="sxs-lookup"><span data-stu-id="7d228-402">IntPtr</span></span>](xref:System.IntPtr) | <span data-ttu-id="7d228-403">Zeiger oder Handle einer Plattform-definierten Größe</span><span class="sxs-lookup"><span data-stu-id="7d228-403">Pointer or handle of a platform-defined size</span></span>
[<span data-ttu-id="7d228-404">String</span><span class="sxs-lookup"><span data-stu-id="7d228-404">String</span></span>](xref:System.String) | <span data-ttu-id="7d228-405">Sammlung von null, einem oder mehreren Char-Objekten</span><span class="sxs-lookup"><span data-stu-id="7d228-405">Collection of zero, one, or more Char objects</span></span>

<span data-ttu-id="7d228-406">Die in der folgenden Tabelle aufgeführten systeminternen Typen sind nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-406">The intrinsic types listed in the following table are not CLS-Compliant.</span></span>

<span data-ttu-id="7d228-407">Nicht kompatibler Typ</span><span class="sxs-lookup"><span data-stu-id="7d228-407">Non-compliant type</span></span> | <span data-ttu-id="7d228-408">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d228-408">Description</span></span> | <span data-ttu-id="7d228-409">CLS-kompatible Alternative</span><span class="sxs-lookup"><span data-stu-id="7d228-409">CLS-compliant alternative</span></span>
------------------ | ----------- | -------------------------
[<span data-ttu-id="7d228-410">SByte</span><span class="sxs-lookup"><span data-stu-id="7d228-410">SByte</span></span>](xref:System.SByte) | <span data-ttu-id="7d228-411">Ganzzahliger 8-Bit-Datentyp mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="7d228-411">8-bit signed integer data type</span></span> | [<span data-ttu-id="7d228-412">Int16</span><span class="sxs-lookup"><span data-stu-id="7d228-412">Int16</span></span>](xref:System.Int16)
[<span data-ttu-id="7d228-413">UInt16</span><span class="sxs-lookup"><span data-stu-id="7d228-413">UInt16</span></span>](xref:System.UInt16) | <span data-ttu-id="7d228-414">16-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="7d228-414">16-bit unsigned integer</span></span> | [<span data-ttu-id="7d228-415">Int32</span><span class="sxs-lookup"><span data-stu-id="7d228-415">Int32</span></span>](xref:System.Int32)
[<span data-ttu-id="7d228-416">UInt32</span><span class="sxs-lookup"><span data-stu-id="7d228-416">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="7d228-417">32-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="7d228-417">32-bit unsigned integer</span></span> | [<span data-ttu-id="7d228-418">Int64</span><span class="sxs-lookup"><span data-stu-id="7d228-418">Int64</span></span>](xref:System.Int64)
[<span data-ttu-id="7d228-419">UInt64</span><span class="sxs-lookup"><span data-stu-id="7d228-419">UInt64</span></span>](xref:System.UInt64) | <span data-ttu-id="7d228-420">64-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="7d228-420">64-bit unsigned integer</span></span> | <span data-ttu-id="7d228-421">[Int64](xref:System.Int64) (kann überlaufen), [BigInteger](xref:System.Numerics.BigInteger) oder [Double](xref:System.Double)</span><span class="sxs-lookup"><span data-stu-id="7d228-421">[Int64](xref:System.Int64) (may overflow), [BigInteger](xref:System.Numerics.BigInteger), or [Double](xref:System.Double)</span></span>
[<span data-ttu-id="7d228-422">UIntPtr</span><span class="sxs-lookup"><span data-stu-id="7d228-422">UIntPtr</span></span>](xref:System.UIntPtr) | <span data-ttu-id="7d228-423">Zeiger ohne Vorzeichen oder Handle</span><span class="sxs-lookup"><span data-stu-id="7d228-423">Unsigned pointer or handle</span></span> | [<span data-ttu-id="7d228-424">IntPtr</span><span class="sxs-lookup"><span data-stu-id="7d228-424">IntPtr</span></span>](xref:System.IntPtr)

<span data-ttu-id="7d228-425">Die .NET-Klassenbibliothek oder jede andere Klassenbibliothek schließen möglicherweise andere nicht CLS-kompatible Typen ein, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7d228-425">The .NET Class Library or any other class library may include other types that aren't CLS-compliant; for example:</span></span>

* <span data-ttu-id="7d228-426">Geschachtelte Werttypen</span><span class="sxs-lookup"><span data-stu-id="7d228-426">Boxed value types.</span></span> <span data-ttu-id="7d228-427">Im folgenden C#-Beispiel wird eine Klasse erstellt, die über eine öffentliche Eigenschaft des Typs `int*` namens `Value` verfügt.</span><span class="sxs-lookup"><span data-stu-id="7d228-427">The following C# example creates a class that has a public property of type `int*` named `Value`.</span></span> <span data-ttu-id="7d228-428">Da `int*` ein geschachtelter Werttyp ist, markiert der Compiler ihn als nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-428">Because an `int*` is a boxed value type, the compiler flags it as non-CLS-compliant.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public unsafe class TestClass
{
   private int* val;

   public TestClass(int number)
   {
      val = (int*) number;
   }

   public int* Value {
      get { return val; }
   }
}
// The compiler generates the following output when compiling this example:
//        warning CS3003: Type of 'TestClass.Value' is not CLS-compliant
```

* <span data-ttu-id="7d228-429">Typisierte Verweise, die spezielle Konstrukte sind, in denen ein Verweis auf ein Objekt und ein Verweis auf einen Typ enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="7d228-429">Typed references, which are special constructs that contain a reference to an object and a reference to a type.</span></span>

<span data-ttu-id="7d228-430">Wenn ein Typ nicht CLS-kompatibel ist, sollten Sie das Attribut [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) mit einem *isCompliant*-Parameter mit einem Wert von `false` anwenden.</span><span class="sxs-lookup"><span data-stu-id="7d228-430">If a type is not CLS-compliant, you should apply the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute with an *isCompliant* parameter with a value of `false` to it.</span></span> <span data-ttu-id="7d228-431">Weitere Informationen finden Sie im Abschnitt zum [CLSCompliantAttribute-Attribut](#the-clscompliantattribute-attribute).</span><span class="sxs-lookup"><span data-stu-id="7d228-431">For more information, see the [CLSCompliantAttribute attribute](#the-clscompliantattribute-attribute) section.</span></span>

<span data-ttu-id="7d228-432">Im folgenden Beispiel wird das Problem der CLS-Kompatibilität in einer Methodensignatur und in der Instanziierung des generischen Typs veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7d228-432">The following example illustrates the problem of CLS compliance in a method signature and in generic type instantiation.</span></span> <span data-ttu-id="7d228-433">Dabei wird eine `InvoiceItem`-Klasse mit einer Eigenschaft vom Typ [UInt32](xref:System.UInt32), einer Eigenschaft vom Typ [Nullable(Of UInt32)](xref:System.Nullable%601) und einem Konstruktor mit Parametern vom Typ `UInt32` und `Nullable(Of UInt32)` definiert.</span><span class="sxs-lookup"><span data-stu-id="7d228-433">It defines an `InvoiceItem` class with a property of type [UInt32](xref:System.UInt32), a property of type [Nullable(Of UInt32)](xref:System.Nullable%601), and a constructor with parameters of type `UInt32` and `Nullable(Of UInt32)`.</span></span> <span data-ttu-id="7d228-434">Sie erhalten vier Compilerwarnungen, wenn Sie versuchen, das Beispiel zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-434">You get four compiler warnings when you try to compile this example.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<uint> qty;

   public InvoiceItem(uint sku, Nullable<uint> quantity)
   {
      itemId = sku;
      qty = quantity;
   }

   public Nullable<uint> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public uint InvoiceId
   {
      get { return invId; }
      set { invId = value; }
   }
}
// The attempt to compile the example displays the following output:
//    Type1.cs(13,23): warning CS3001: Argument type 'uint' is not CLS-compliant
//    Type1.cs(13,33): warning CS3001: Argument type 'uint?' is not CLS-compliant
//    Type1.cs(19,26): warning CS3003: Type of 'InvoiceItem.Quantity' is not CLS-compliant
//    Type1.cs(25,16): warning CS3003: Type of 'InvoiceItem.InvoiceId' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of UInteger)

   Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
      itemId = sku
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of UInteger)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As UInteger
      Get
         Return invId
      End Get
      Set
         invId = value
      End Set
   End Property
End Class
' The attempt to compile the example displays output similar to the following:
'    Type1.vb(13) : warning BC40028: Type of parameter 'sku' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                      ~~~
'    Type1.vb(13) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                                                               ~~~~~~~~
'    Type1.vb(18) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Property Quantity As Nullable(Of UInteger)
'                                               ~~~~~~~~
'    Type1.vb(27) : warning BC40027: Return type of function 'InvoiceId' is not CLS-compliant.
'
'       Public Property InvoiceId As UInteger
```

<span data-ttu-id="7d228-435">Um die Compilerwarnungen auszuschließen, ersetzen Sie die nicht CLS-kompatiblen Typen in der öffentlichen `InvoiceItem`-Schnittstelle durch kompatible Typen:</span><span class="sxs-lookup"><span data-stu-id="7d228-435">To eliminate the compiler warnings, replace the non-CLS-compliant types in the `InvoiceItem` public interface with compliant types:</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<int> qty;

   public InvoiceItem(int sku, Nullable<int> quantity)
   {
      if (sku <= 0)
         throw new ArgumentOutOfRangeException("The item number is zero or negative.");
      itemId = (uint) sku;

      qty = quantity;
   }

   public Nullable<int> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public int InvoiceId
   {
      get { return (int) invId; }
      set {
         if (value <= 0)
            throw new ArgumentOutOfRangeException("The invoice number is zero or negative.");
         invId = (uint) value; }
   }
}
```

```vb
Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of Integer)

   Public Sub New(sku As Integer, quantity As Nullable(Of Integer))
      If sku <= 0 Then
         Throw New ArgumentOutOfRangeException("The item number is zero or negative.")
      End If
      itemId = CUInt(sku)
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of Integer)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As Integer
      Get
         Return CInt(invId)
      End Get
      Set
         invId = CUInt(value)
      End Set
   End Property
End Class
```

<span data-ttu-id="7d228-436">Zusätzlich zu bestimmten aufgeführten Typen sind einige Typenkategorien ebenfalls nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-436">In addition to the specific types listed, some categories of types are not CLS compliant.</span></span> <span data-ttu-id="7d228-437">Diese schließen nicht verwaltete Zeigertypen und Funktionszeigertypen ein.</span><span class="sxs-lookup"><span data-stu-id="7d228-437">These include unmanaged pointer types and function pointer types.</span></span> <span data-ttu-id="7d228-438">Im folgenden Beispiel wird eine Compilerwarnung erzeugt, da ein Zeiger auf eine ganze Zahl verwendet wird, um ein Array ganzer Zahlen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d228-438">The following example generates a compiler warning because it uses a pointer to an integer to create an array of integers.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

<span data-ttu-id="7d228-439">Für CLS-kompatible abstrakte Klassen (also Klassen, die in C# als `abstract` markiert sind), müssen alle Member der Klasse auch CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-439">For CLS-compliant abstract classes (that is, classes marked as `abstract` in C#), all members of the class must also be CLS-compliant.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="7d228-440">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="7d228-440">Naming conventions</span></span>

<span data-ttu-id="7d228-441">Da bei einigen Programmiersprachen die Groß- und Kleinschreibung nicht beachtet werden muss, müssen Bezeichner (wie die Namen von Namespaces, Typen und Membern) durch mehr als die Groß-/Kleinschreibung unterschieden werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-441">Because some programming languages are case-insensitive, identifiers (such as the names of namespaces, types, and members) must differ by more than case.</span></span> <span data-ttu-id="7d228-442">Zwei Bezeichner gelten als äquivalent, wenn ihre kleingeschriebenen Zuordnungen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="7d228-442">Two identifiers are considered equivalent if their lowercase mappings are the same.</span></span> <span data-ttu-id="7d228-443">Im folgenden C#-Beispiel werden zwei öffentliche Klassen definiert: `Person` und `person`.</span><span class="sxs-lookup"><span data-stu-id="7d228-443">The following C# example defines two public classes, `Person` and `person`.</span></span> <span data-ttu-id="7d228-444">Da sie sich nur durch die Groß-/Kleinschreibung unterscheiden, markiert der C#-Compiler sie als nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-444">Because they differ only by case, the C# compiler flags them as not CLS-compliant.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person : person
{

}

public class person
{

}
// Compilation produces a compiler warning like the following:
//    Naming1.cs(11,14): warning CS3005: Identifier 'person' differing
//                       only in case is not CLS-compliant
//    Naming1.cs(6,14): (Location of symbol related to previous warning)
```

<span data-ttu-id="7d228-445">Programmiersprachenbezeichner wie die Namen von Namespaces, Typen und Membern müssen dem [Unicode-Standard](https://unicode.org/reports/tr15/) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="7d228-445">Programming language identifiers, such as the names of namespaces, types, and members, must conform to the [Unicode Standard](https://unicode.org/reports/tr15/).</span></span> <span data-ttu-id="7d228-446">Dies bedeutet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7d228-446">This means that:</span></span>

* <span data-ttu-id="7d228-447">Das erste Zeichen eines Bezeichners kann jeder Unicode-Großbuchstabe, Kleinbuchstabe, großer Anfangsbuchstabe, Modifiziererbuchstabe, anderer Buchstabe oder jede Buchstabenzahl sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-447">The first character of an identifier can be any Unicode uppercase letter, lowercase letter, title case letter, modifier letter, other letter, or letter number.</span></span> <span data-ttu-id="7d228-448">Informationen zu Unicode-Zeichenkategorien finden Sie unter der [System.Globalization.UnicodeCategory](xref:System.Globalization.UnicodeCategory)-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="7d228-448">For information on Unicode character categories, see the [System.Globalization.UnicodeCategory](xref:System.Globalization.UnicodeCategory) enumeration.</span></span>

* <span data-ttu-id="7d228-449">Nachfolgende Zeichen können aus einer der Kategorien wie das erste Zeichen stammen, und sie können auch Markierungen ohne Zwischenraum, Sperrmarkierungen, Dezimalwerte, Connectorinterpunktionen und Formatierungscodes umfassen.</span><span class="sxs-lookup"><span data-stu-id="7d228-449">Subsequent characters can be from any of the categories as the first character, and can also include non-spacing marks, spacing combining marks, decimal numbers, connector punctuation, and formatting codes.</span></span>

<span data-ttu-id="7d228-450">Bevor Sie Bezeichner vergleichen, sollten Sie Formatierungscodes herausfiltern und die Bezeichner in die Unicode-Normalisierungsform C konvertieren, da ein einzelnes Zeichen durch mehrere UTF-16-codierte Codeeinheiten dargestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7d228-450">Before you compare identifiers, you should filter out formatting codes and convert the identifiers to Unicode Normalization Form C, because a single character can be represented by multiple UTF-16-encoded code units.</span></span> <span data-ttu-id="7d228-451">Zeichensequenzen, die die gleichen Codeeinheiten in der Unicode-Normalisierungsform C erzeugen, sind nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-451">Character sequences that produce the same code units in Unicode Normalization Form C are not CLS-compliant.</span></span> <span data-ttu-id="7d228-452">Im folgenden Beispiel werden zwei Eigenschaften definiert: eine namens `Å`, die aus dem Zeichen ÅNGSTRÖM-ZEICHEN (U+212B) besteht, und eine zweite namens `Å`, die aus dem Zeichen LATEINISCHER GROSSBUCHSTABE A MIT RING OBEN (U+00C5) besteht.</span><span class="sxs-lookup"><span data-stu-id="7d228-452">The following example defines a property named `Å`, which consists of the character ANGSTROM SIGN (U+212B), and a second property named `Å`, which consists of the character LATIN CAPITAL LETTER A WITH RING ABOVE (U+00C5).</span></span> <span data-ttu-id="7d228-453">Der C#-Compiler kennzeichnet den Quellcode als nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-453">The C# compiler flags the source code as non-CLS-compliant.</span></span>

```csharp
public class Size
{
   private double a1;
   private double a2;

   public double Å
   {
       get { return a1; }
       set { a1 = value; }
   }

   public double Å
   {
       get { return a2; }
       set { a2 = value; }
   }
}
// Compilation produces a compiler warning like the following:
//    Naming2a.cs(16,18): warning CS3005: Identifier 'Size.Å' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(10,18): (Location of symbol related to previous warning)
//    Naming2a.cs(18,8): warning CS3005: Identifier 'Size.Å.get' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(12,8): (Location of symbol related to previous warning)
//    Naming2a.cs(19,8): warning CS3005: Identifier 'Size.Å.set' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(13,8): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>
Public Class Size
   Private a1 As Double
   Private a2 As Double

   Public Property Å As Double
       Get
          Return a1
       End Get
       Set
          a1 = value
       End Set
   End Property

   Public Property Å As Double
       Get
          Return a2
       End Get
       Set
          a2 = value
       End Set
   End Property
End Class
' Compilation produces a compiler warning like the following:
'    Naming1.vb(9) : error BC30269: 'Public Property Å As Double' has multiple definitions
'     with identical signatures.
'
'       Public Property Å As Double
'                       ~
```

<span data-ttu-id="7d228-454">Membernamen innerhalb eines bestimmten Bereichs (wie den Namespaces innerhalb einer Assembly, den Typen in einem Namespace oder den Membern innerhalb eines Typs) müssen eindeutig sein, abgesehen von Namen, die durch Überladen aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-454">Member names within a particular scope (such as the namespaces within an assembly, the types within a namespace, or the members within a type) must be unique except for names that are resolved through overloading.</span></span> <span data-ttu-id="7d228-455">Diese Anforderung ist zwingender als die des allgemeinen Typsystems, bei dem mehrere Member innerhalb eines Bereichs über identische Namen verfügen dürfen, solange es unterschiedliche Arten von Membern sind (zum Beispiel eine Methode und ein Feld).</span><span class="sxs-lookup"><span data-stu-id="7d228-455">This requirement is more stringent than that of the common type system, which allows multiple members within a scope to have identical names as long as they are different kinds of members (for example, one is a method and one is a field).</span></span> <span data-ttu-id="7d228-456">Insbesondere für Typmember:</span><span class="sxs-lookup"><span data-stu-id="7d228-456">In particular, for type members:</span></span>

* <span data-ttu-id="7d228-457">Felder und geschachtelte Typen werden allein nach Namen unterschieden.</span><span class="sxs-lookup"><span data-stu-id="7d228-457">Fields and nested types are distinguished by name alone.</span></span>

* <span data-ttu-id="7d228-458">Methoden, Eigenschaften und Ereignisse mit demselben Namen müssen sich durch mehr als nur den Rückgabetyp unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="7d228-458">Methods, properties, and events that have the same name must differ by more than just return type.</span></span>

<span data-ttu-id="7d228-459">Im folgenden Beispiel wird die Anforderung veranschaulicht, dass Membernamen innerhalb des Bereichs eindeutig sein müssen.</span><span class="sxs-lookup"><span data-stu-id="7d228-459">The following example illustrates the requirement that member names must be unique within their scope.</span></span> <span data-ttu-id="7d228-460">Es wird eine Klasse namens `Converter` definiert, die vier Member namens `Conversion` umfasst.</span><span class="sxs-lookup"><span data-stu-id="7d228-460">It defines a class named `Converter` that includes four members named `Conversion`.</span></span> <span data-ttu-id="7d228-461">Drei Methoden und eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7d228-461">Three are methods, and one is a property.</span></span> <span data-ttu-id="7d228-462">Die Methode, die einen Parameter `Int64` umfasst, hat einen eindeutigen Namen, doch die beiden Methoden mit einem `Int32`-Parameter sind nicht eindeutig, da der Rückgabewert nicht als ein Teil der Signatur eines Members gültig ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-462">The method that includes an `Int64` parameter is uniquely named, but the two methods with an `Int32` parameter are not, because return value is not considered a part of a member's signature.</span></span> <span data-ttu-id="7d228-463">Die `Conversion`- Eigenschaft verstößt auch gegen diese Anforderung, da Eigenschaften nicht den gleichen Namen wie überladene Methoden besitzen dürfen.</span><span class="sxs-lookup"><span data-stu-id="7d228-463">The `Conversion` property also violates this requirement, because properties cannot have the same name as overloaded methods.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Converter
{
   public double Conversion(int number)
   {
      return (double) number;
   }

   public float Conversion(int number)
   {
      return (float) number;
   }

   public double Conversion(long number)
   {
      return (double) number;
   }

   public bool Conversion
   {
      get { return true; }
   }
}
// Compilation produces a compiler error like the following:
//    Naming3.cs(13,17): error CS0111: Type 'Converter' already defines a member called
//            'Conversion' with the same parameter types
//    Naming3.cs(8,18): (Location of symbol related to previous error)
//    Naming3.cs(23,16): error CS0102: The type 'Converter' already contains a definition for
//            'Conversion'
//    Naming3.cs(8,18): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Converter
   Public Function Conversion(number As Integer) As Double
      Return CDbl(number)
   End Function

   Public Function Conversion(number As Integer) As Single
      Return CSng(number)
   End Function

   Public Function Conversion(number As Long) As Double
      Return CDbl(number)
   End Function

   Public ReadOnly Property Conversion As Boolean
      Get
         Return True
      End Get
   End Property
End Class
' Compilation produces a compiler error like the following:
'    Naming3.vb(8) : error BC30301: 'Public Function Conversion(number As Integer) As Double'
'                    and 'Public Function Conversion(number As Integer) As Single' cannot
'                    overload each other because they differ only by return types.
'
'       Public Function Conversion(number As Integer) As Double
'                       ~~~~~~~~~~
'    Naming3.vb(20) : error BC30260: 'Conversion' is already declared as 'Public Function
'                     Conversion(number As Integer) As Single' in this class.
'
'       Public ReadOnly Property Conversion As Boolean
'                                ~~~~~~~~~~
```

<span data-ttu-id="7d228-464">Einzelne Sprachen enthalten eindeutige Schlüsselwörter, sodass Sprachen für die Common Language Runtime einen Mechanismus zum Verweisen auf Bezeichner (z. B. Typnamen) bereitstellen müssen, die mit den Schlüsselwörtern übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="7d228-464">Individual languages include unique keywords, so languages that target the common language runtime must also provide some mechanism for referencing identifiers (such as type names) that coincide with keywords.</span></span> <span data-ttu-id="7d228-465">Beispielsweise ist `case` ein Schlüsselwort in C# und Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7d228-465">For example, `case` is a keyword in both C# and Visual Basic.</span></span> <span data-ttu-id="7d228-466">Im folgenden Visual Basic-Beispiel wird eine Klasse namens `case` eindeutig vom `case`-Schlüsselwort unterschieden, indem öffnende und schließende geschweifte Klammern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-466">However, the following Visual Basic example is able to disambiguate a class named `case` from the `case` keyword by using opening and closing braces.</span></span> <span data-ttu-id="7d228-467">Andernfalls würde in dem Beispiel die folgende Fehlermeldung erzeugt: "Das Schlüsselwort ist kein gültiger Bezeichner", und der Code könnte nicht kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-467">Otherwise, the example would produce the error message, "Keyword is not valid as an identifier," and fail to compile.</span></span>

```vb
Public Class [case]
   Private _id As Guid
   Private name As String

   Public Sub New(name As String)
      _id = Guid.NewGuid()
      Me.name = name
   End Sub

   Public ReadOnly Property ClientName As String
      Get
         Return name
      End Get
   End Property
End Class
```

<span data-ttu-id="7d228-468">Im folgenden C#-Beispiel kann die `case`-Klasse instanziiert werden, indem das @-Symbol verwendet wird, um den Bezeichner eindeutig vom Schlüsselwort zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="7d228-468">The following C# example is able to instantiate the `case` class by using the @ symbol to disambiguate the identifier from the language keyword.</span></span> <span data-ttu-id="7d228-469">Ohne dieses Zeichen würde der C#-Compiler zwei Fehlermeldungen anzeigen:"Typ erwartet" und "Ungültiger Ausdruck 'case'".</span><span class="sxs-lookup"><span data-stu-id="7d228-469">Without it, the C# compiler would display two error messages, "Type expected" and "Invalid expression term 'case'."</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      @case c = new @case("John");
      Console.WriteLine(c.ClientName);
   }
}
```

### <a name="type-conversion"></a><span data-ttu-id="7d228-470">Typkonvertierung</span><span class="sxs-lookup"><span data-stu-id="7d228-470">Type conversion</span></span>

<span data-ttu-id="7d228-471">In der Common Language Specification werden zwei Konvertierungsoperatoren definiert:</span><span class="sxs-lookup"><span data-stu-id="7d228-471">The Common Language Specification defines two conversion operators:</span></span>

* <span data-ttu-id="7d228-472">`op_Implicit`, das für Erweiterungskonvertierungen verwendet wird, die zu keinem Datenverlust oder Genauigkeitsverlust führen.</span><span class="sxs-lookup"><span data-stu-id="7d228-472">`op_Implicit`, which is used for widening conversions that do not result in loss of data or precision.</span></span> <span data-ttu-id="7d228-473">Zum Beispiel umfasst die [Decimal](xref:System.Decimal)-Struktur einen überladenen `op_Implicit`-Operator, um Werte integraler Typen und [Char](xref:System.Char)-Werte in `Decimal`-Werte zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-473">For example, the [Decimal](xref:System.Decimal) structure includes an overloaded `op_Implicit` operator to convert values of integral types and [Char](xref:System.Char) values to `Decimal` values.</span></span>

* <span data-ttu-id="7d228-474">`op_Explicit`, der für einschränkende Konvertierungen verwendet wird, die zu Größenverlusten (ein Wert wird in einen Wert konvertiert, der über einen kleineren Bereich verfügt) bzw. zu Verlusten der Genauigkeit führen können.</span><span class="sxs-lookup"><span data-stu-id="7d228-474">`op_Explicit`, which is used for narrowing conversions that can result in loss of magnitude (a value is converted to a value that has a smaller range) or precision.</span></span> <span data-ttu-id="7d228-475">Zum Beispiel umfasst die `Decimal`-Struktur einen überladenen `op_Explicit`-Operator, um den [Double](xref:System.Double)-Wert und den [Single](xref:System.Single)-Wert in `Decimal` zu konvertieren und die `Decimal`-Werte in integrale Werte, `Double`, `Single` und `Char` zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-475">For example, the `Decimal` structure includes an overloaded `op_Explicit` operator to convert [Double](xref:System.Double) and [Single](xref:System.Single) values to `Decimal` and to convert `Decimal` values to integral values, `Double`, `Single`, and `Char`.</span></span>

<span data-ttu-id="7d228-476">Allerdings wird Operatorüberladung oder die Definition benutzerdefinierter Operatoren nicht von allen Sprachen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d228-476">However, not all languages support operator overloading or the definition of custom operators.</span></span> <span data-ttu-id="7d228-477">Wenn Sie diese Konvertierungsoperatoren implementieren, sollten Sie eine alternative Methode zum Ausführen der Konvertierung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7d228-477">If you choose to implement these conversion operators, you should also provide an alternate way to perform the conversion.</span></span> <span data-ttu-id="7d228-478">Es wird empfohlen, `From`Xxx- und `To`Xxx-Methoden bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7d228-478">We recommend that you provide `From`Xxx and `To`Xxx methods.</span></span>

<span data-ttu-id="7d228-479">Im folgenden Beispiel werden CLS-kompatible implizite und explizite Konvertierungen definiert.</span><span class="sxs-lookup"><span data-stu-id="7d228-479">The following example defines CLS-compliant implicit and explicit conversions.</span></span> <span data-ttu-id="7d228-480">Es wird eine `UDouble`-Klasse erstellt, die eine Gleitkommazahl mit doppelter Genauigkeit und Vorzeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="7d228-480">It creates a `UDouble` class that represents a signed double-precision, floating-point number.</span></span> <span data-ttu-id="7d228-481">Implizite Konvertierungen aus `UDouble` in `Double` und explizite Konvertierungen aus `UDouble` in `Single`, aus `Double` in `UDouble` und aus `Single` in `UDouble` werden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7d228-481">It provides for implicit conversions from `UDouble` to `Double` and for explicit conversions from `UDouble` to `Single`, `Double` to `UDouble`, and `Single` to `UDouble`.</span></span> <span data-ttu-id="7d228-482">Es wird auch eine `ToDouble`-Methode als Alternative zum Operator für implizite Konvertierung definiert, und die `ToSingle`, `FromDouble`-Methode sowie die `FromSingle`-Methode werden als Alternativen zu den Operatoren der expliziten Konvertierung definiert.</span><span class="sxs-lookup"><span data-stu-id="7d228-482">It also defines a `ToDouble` method as an alternative to the implicit conversion operator and the `ToSingle`, `FromDouble`, and `FromSingle` methods as alternatives to the explicit conversion operators.</span></span>

```csharp
using System;

public struct UDouble
{
   private double number;

   public UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public static readonly UDouble MinValue = (UDouble) 0.0;
   public static readonly UDouble MaxValue = (UDouble) Double.MaxValue;

   public static explicit operator Double(UDouble value)
   {
      return value.number;
   }

   public static implicit operator Single(UDouble value)
   {
      if (value.number > (double) Single.MaxValue)
         throw new InvalidCastException("A UDouble value is out of range of the Single type.");

      return (float) value.number;
   }

   public static explicit operator UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static implicit operator UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static Double ToDouble(UDouble value)
   {
      return (Double) value;
   }

   public static float ToSingle(UDouble value)
   {
      return (float) value;
   }

   public static UDouble FromDouble(double value)
   {
      return new UDouble(value);
   }

   public static UDouble FromSingle(float value)
   {
      return new UDouble(value);
   }
}
```

```vb
Public Structure UDouble
   Private number As Double

   Public Sub New(value As Double)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Sub New(value As Single)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Shared ReadOnly MinValue As UDouble = CType(0.0, UDouble)
   Public Shared ReadOnly MaxValue As UDouble = Double.MaxValue

   Public Shared Widening Operator CType(value As UDouble) As Double
      Return value.number
   End Operator

   Public Shared Narrowing Operator CType(value As UDouble) As Single
      If value.number > CDbl(Single.MaxValue) Then
         Throw New InvalidCastException("A UDouble value is out of range of the Single type.")
      End If
      Return CSng(value.number)
   End Operator

   Public Shared Narrowing Operator CType(value As Double) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Narrowing Operator CType(value As Single) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Function ToDouble(value As UDouble) As Double
      Return CType(value, Double)
   End Function

   Public Shared Function ToSingle(value As UDouble) As Single
      Return CType(value, Single)
   End Function

   Public Shared Function FromDouble(value As Double) As UDouble
      Return New UDouble(value)
   End Function

   Public Shared Function FromSingle(value As Single) As UDouble
      Return New UDouble(value)
   End Function
End Structure
```

### <a name="arrays"></a><span data-ttu-id="7d228-483">Arrays</span><span class="sxs-lookup"><span data-stu-id="7d228-483">Arrays</span></span>

<span data-ttu-id="7d228-484">CLS-kompatible Arrays sind mit den folgenden Regeln kompatibel:</span><span class="sxs-lookup"><span data-stu-id="7d228-484">CLS-compliant arrays conform to the following rules:</span></span>

* <span data-ttu-id="7d228-485">Die unteren Begrenzungen aller Dimensionen eines Arrays müssen gleich 0 sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-485">All dimensions of an array must have a lower bound of zero.</span></span> <span data-ttu-id="7d228-486">Im folgenden Beispiel wird ein Array mit einer nicht CLS-kompatiblen Untergrenze von eins erstellt.</span><span class="sxs-lookup"><span data-stu-id="7d228-486">The following example creates a non-CLS-compliant array with a lower bound of one.</span></span> <span data-ttu-id="7d228-487">Beachten Sie, dass der Compiler ungeachtet des Vorhandenseins des Attributs [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) nicht erkennt, dass das von der `Numbers.GetTenPrimes`-Methode zurückgegebene Array nicht CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-487">Despite the presence of the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute, the compiler does not detect that the array returned by the `Numbers.GetTenPrimes` method is not CLS-compliant.</span></span>

  ```csharp
  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static Array GetTenPrimes()
    {
        Array arr = Array.CreateInstance(typeof(Int32), new int[] {10}, new int[] {1});
        arr.SetValue(1, 1);
        arr.SetValue(2, 2);
        arr.SetValue(3, 3);
        arr.SetValue(5, 4);
        arr.SetValue(7, 5);
        arr.SetValue(11, 6);
        arr.SetValue(13, 7);
        arr.SetValue(17, 8);
        arr.SetValue(19, 9);
        arr.SetValue(23, 10);

        return arr;
    }
  }
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As Array
        Dim arr As Array = Array.CreateInstance(GetType(Int32), {10}, {1})
        arr.SetValue(1, 1)
        arr.SetValue(2, 2)
        arr.SetValue(3, 3)
        arr.SetValue(5, 4)
        arr.SetValue(7, 5)
        arr.SetValue(11, 6)
        arr.SetValue(13, 7)
        arr.SetValue(17, 8)
        arr.SetValue(19, 9)
        arr.SetValue(23, 10)
        Return arr
     End Function
  End Class
  ```

* <span data-ttu-id="7d228-488">Alle Arrayelemente müssen aus CLS-kompatiblen Typen bestehen.</span><span class="sxs-lookup"><span data-stu-id="7d228-488">All array elements must consist of CLS-compliant types.</span></span> <span data-ttu-id="7d228-489">Im folgenden Beispiel werden zwei Methoden, die nicht CLS-kompatible Arrays zurückgeben, definiert.</span><span class="sxs-lookup"><span data-stu-id="7d228-489">The following example defines two methods that return non-CLS-compliant arrays.</span></span> <span data-ttu-id="7d228-490">Die erste Methode gibt ein Array von [UInt32](xref:System.UInt32)-Werten zurück.</span><span class="sxs-lookup"><span data-stu-id="7d228-490">The first returns an array of [UInt32](xref:System.UInt32) values.</span></span> <span data-ttu-id="7d228-491">Die zweite Methode gibt ein [Object](xref:System.Object)-Array zurück, das [Int32](xref:System.Int32)- und `UInt32`-Werte umfasst.</span><span class="sxs-lookup"><span data-stu-id="7d228-491">The second returns an [Object](xref:System.Object) array that includes [Int32](xref:System.Int32) and `UInt32` values.</span></span> <span data-ttu-id="7d228-492">Obwohl der Compiler das erste Array aufgrund des `UInt32`-Typs als nicht kompatibel identifiziert, wird nicht erkannt, dass das zweite Array nicht CLS-kompatible Elemente umfasst.</span><span class="sxs-lookup"><span data-stu-id="7d228-492">Although the compiler identifies the first array as non-compliant because of its `UInt32` type, it fails to recognize that the second array includes non-CLS-compliant elements.</span></span>

  ```csharp
  using System;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static UInt32[] GetTenPrimes()
    {
        uint[] arr = { 1u, 2u, 3u, 5u, 7u, 11u, 13u, 17u, 19u };
        return arr;
    }

    public static Object[] GetFivePrimes()
    {
        Object[] arr = { 1, 2, 3, 5u, 7u };
        return arr;
    }
  }
  // Compilation produces a compiler warning like the following:
  //    Array2.cs(8,27): warning CS3002: Return type of 'Numbers.GetTenPrimes()' is not
  //            CLS-compliant
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As UInt32()
        Return { 1ui, 2ui, 3ui, 5ui, 7ui, 11ui, 13ui, 17ui, 19ui }
     End Function
     Public Shared Function GetFivePrimes() As Object()
        Dim arr() As Object = { 1, 2, 3, 5ui, 7ui }
        Return arr
     End Function
  End Class
  ' Compilation produces a compiler warning like the following:
  '    warning BC40027: Return type of function 'GetTenPrimes' is not CLS-compliant.
  ```

* <span data-ttu-id="7d228-493">Die Überladungsauflösung für Methoden mit Arrayparametern basiert sowohl auf der Tatsache, dass es Arrays sind, als auch auf dem Elementtyp.</span><span class="sxs-lookup"><span data-stu-id="7d228-493">Overload resolution for methods that have array parameters is based on the fact that they are arrays and on their element type.</span></span> <span data-ttu-id="7d228-494">Aus diesem Grund ist die folgende Definition einer überladenen `GetSquares`-Methode CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-494">For this reason, the following definition of an overloaded `GetSquares` method is CLS-compliant.</span></span>

  ```csharp
  using System;
  using System.Numerics;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static byte[] GetSquares(byte[] numbers)
    {
        byte[] numbersOut = new byte[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++) {
            int square = ((int) numbers[ctr]) * ((int) numbers[ctr]);
            if (square <= Byte.MaxValue)
                numbersOut[ctr] = (byte) square;
            // If there's an overflow, assign MaxValue to the corresponding
            // element.
            else
                numbersOut[ctr] = Byte.MaxValue;

        }
        return numbersOut;
    }

    public static BigInteger[] GetSquares(BigInteger[] numbers)
  {
        BigInteger[] numbersOut = new BigInteger[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++)
            numbersOut[ctr] = numbers[ctr] * numbers[ctr];

       return numbersOut;
    }
  }
  ```

  ```vb
  Imports System.Numerics

  <Assembly: CLSCompliant(True)>

  Public Module Numbers
     Public Function GetSquares(numbers As Byte()) As Byte()
        Dim numbersOut(numbers.Length - 1) As Byte
        For ctr As Integer = 0 To numbers.Length - 1
           Dim square As Integer = (CInt(numbers(ctr)) * CInt(numbers(ctr)))
           If square <= Byte.MaxValue Then
              numbersOut(ctr) = CByte(square)
           ' If there's an overflow, assign MaxValue to the corresponding
           ' element.
           Else
              numbersOut(ctr) = Byte.MaxValue
           End If
        Next
        Return numbersOut
     End Function

     Public Function GetSquares(numbers As BigInteger()) As BigInteger()
         Dim numbersOut(numbers.Length - 1) As BigInteger
         For ctr As Integer = 0 To numbers.Length - 1
            numbersOut(ctr) = numbers(ctr) * numbers(ctr)
         Next
         Return numbersOut
     End Function
  End Module
  ```

### <a name="interfaces"></a><span data-ttu-id="7d228-495">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7d228-495">Interfaces</span></span>

<span data-ttu-id="7d228-496">CLS-kompatible Schnittstellen können Eigenschaften, Ereignisse und virtuelle Methoden (Methoden ohne Implementierung) definieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-496">CLS-compliant interfaces can define properties, events, and virtual methods (methods with no implementation).</span></span> <span data-ttu-id="7d228-497">Eine CLS-kompatible Schnittstelle kann keine der folgenden Aspekte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="7d228-497">A CLS-compliant interface cannot have any of the following:</span></span>

* <span data-ttu-id="7d228-498">Statische Methoden oder statische Felder</span><span class="sxs-lookup"><span data-stu-id="7d228-498">Static methods or static fields.</span></span> <span data-ttu-id="7d228-499">Der C#-Compiler generiert Compilerfehler, wenn Sie einen statischen Member in einer Schnittstelle definieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-499">The C# compiler generates compiler errors if you define a static member in an interface.</span></span>

* <span data-ttu-id="7d228-500">Felder</span><span class="sxs-lookup"><span data-stu-id="7d228-500">Fields.</span></span> <span data-ttu-id="7d228-501">Die C#-Compiler generiert Compilerfehler, wenn Sie ein Feld in einer Schnittstelle definieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-501">The C# a compiler generates compiler errors if you define a field in an interface.</span></span>

* <span data-ttu-id="7d228-502">Methoden, die nicht CLS-kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="7d228-502">Methods that are not CLS-compliant.</span></span> <span data-ttu-id="7d228-503">Zum Beispiel umfasst die folgende Schnittstellendefinition eine Methode, `INumber.GetUnsigned`, die als nicht CLS-kompatibel gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="7d228-503">For example, the following interface definition includes a method, `INumber.GetUnsigned`, that is marked as non-CLS-compliant.</span></span> <span data-ttu-id="7d228-504">In diesem Beispiel wird eine Compilerwarnung generiert.</span><span class="sxs-lookup"><span data-stu-id="7d228-504">This example generates a compiler warning.</span></span>

  ```csharp
  using System;

  [assembly:CLSCompliant(true)]

  public interface INumber
  {
      int Length();
      [CLSCompliant(false)] ulong GetUnsigned();
  }
  // Attempting to compile the example displays output like the following:
  //    Interface2.cs(8,32): warning CS3010: 'INumber.GetUnsigned()': CLS-compliant interfaces
  //            must have only CLS-compliant members
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Interface INumber
    Function Length As Integer
      <CLSCompliant(False)> Function GetUnsigned As ULong
    End Interface
    ' Attempting to compile the example displays output like the following:
    '    Interface2.vb(9) : warning BC40033: Non CLS-compliant 'function' is not allowed in a
    '    CLS-compliant interface.
    '
    '       <CLSCompliant(False)> Function GetUnsigned As ULong
    '                                      ~~~~~~~~~~~
  ```

  <span data-ttu-id="7d228-505">Aufgrund dieser Regel, ist es nicht erforderlich, dass CLS-kompatible Typen nicht CLS-kompatible Member implementieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-505">Because of this rule, CLS-compliant types are not required to implement non-CLS-compliant members.</span></span> <span data-ttu-id="7d228-506">Wenn ein CLS-kompatibles Framework eine Klasse verfügbar macht, die eine nicht CLS- kompatible Schnittstelle implementiert, sollte sie konkrete Implementierungen aller nicht-CLS-kompatiblen Member angeben.</span><span class="sxs-lookup"><span data-stu-id="7d228-506">If a CLS-compliant framework does expose a class that implements a non-CLS compliant interface, it should also provide concrete implementations of all non-CLS-compliant members.</span></span>

<span data-ttu-id="7d228-507">CLS-kompatible Sprachcompiler müssen einer Klasse auch ermöglichen, separate Implementierungen von Membern bereitzustellen, die in mehreren Schnittstellen über den gleichen Namen und dieselbe Signatur verfügen.</span><span class="sxs-lookup"><span data-stu-id="7d228-507">CLS-compliant language compilers must also allow a class to provide separate implementations of members that have the same name and signature in multiple interfaces.</span></span> <span data-ttu-id="7d228-508">C# unterstützt explizite Schnittstellenimplementierungen, um unterschiedliche Implementierungen identisch benannter Methoden bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7d228-508">C# supports explicit interface implementations to provide different implementations of identically named methods.</span></span> <span data-ttu-id="7d228-509">Im folgenden Beispiel wird dieses Szenario veranschaulicht, indem eine `Temperature`-Klasse definiert wird, die die `ICelsius`-Schnittstelle und die `IFahrenheit`-Schnittstelle als explizite Schnittstellenimplementierungen implementiert.</span><span class="sxs-lookup"><span data-stu-id="7d228-509">The following example illustrates this scenario by defining a `Temperature` class that implements the `ICelsius` and `IFahrenheit` interfaces as explicit interface implementations.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public interface IFahrenheit
{
   decimal GetTemperature();
}

public interface ICelsius
{
   decimal GetTemperature();
}

public class Temperature : ICelsius, IFahrenheit
{
   private decimal _value;

   public Temperature(decimal value)
   {
      // We assume that this is the Celsius value.
      _value = value;
   }

   decimal IFahrenheit.GetTemperature()
   {
      return _value * 9 / 5 + 32;
   }

   decimal ICelsius.GetTemperature()
   {
      return _value;
   }
}
public class Example
{
   public static void Main()
   {
      Temperature temp = new Temperature(100.0m);
      ICelsius cTemp = temp;
      IFahrenheit fTemp = temp;
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        cTemp.GetTemperature());
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        fTemp.GetTemperature());
   }
}
// The example displays the following output:
//       Temperature in Celsius: 100.0 degrees
//       Temperature in Fahrenheit: 212.0 degrees
```

```vb
Assembly: CLSCompliant(True)>

Public Interface IFahrenheit
   Function GetTemperature() As Decimal
End Interface

Public Interface ICelsius
   Function GetTemperature() As Decimal
End Interface

Public Class Temperature : Implements ICelsius, IFahrenheit
   Private _value As Decimal

   Public Sub New(value As Decimal)
      ' We assume that this is the Celsius value.
      _value = value
   End Sub

   Public Function GetFahrenheit() As Decimal _
          Implements IFahrenheit.GetTemperature
      Return _value * 9 / 5 + 32
   End Function

   Public Function GetCelsius() As Decimal _
          Implements ICelsius.GetTemperature
      Return _value
   End Function
End Class

Module Example
   Public Sub Main()
      Dim temp As New Temperature(100.0d)
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        temp.GetCelsius())
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        temp.GetFahrenheit())
   End Sub
End Module
' The example displays the following output:
'       Temperature in Celsius: 100.0 degrees
'       Temperature in Fahrenheit: 212.0 degrees
```

### <a name="enumerations"></a><span data-ttu-id="7d228-510">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7d228-510">Enumerations</span></span>

<span data-ttu-id="7d228-511">Bei CLS-kompatiblen Enumerationen müssen die folgenden Regeln beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="7d228-511">CLS-compliant enumerations must follow these rules:</span></span>

* <span data-ttu-id="7d228-512">Der zugrunde liegende Typ der Enumeration muss ein systeminterner CLS-kompatibler Ganzzahltyp sein ([Byte](xref:System.Byte), [Int16](xref:System.Int16), [Int32](xref:System.Int32) oder [Int64](xref:System.Int64)).</span><span class="sxs-lookup"><span data-stu-id="7d228-512">The underlying type of the enumeration must be an intrinsic CLS-compliant integer ([Byte](xref:System.Byte), [Int16](xref:System.Int16), [Int32](xref:System.Int32), or [Int64](xref:System.Int64)).</span></span> <span data-ttu-id="7d228-513">Im folgenden Code wird beispielsweise versucht, eine Enumeration zu definieren, deren zugrunde liegender Typ [UInt32](xref:System.UInt32) ist. Eine Compilerwarnung wird generiert.</span><span class="sxs-lookup"><span data-stu-id="7d228-513">For example, the following code tries to define an enumeration whose underlying type is [UInt32](xref:System.UInt32) and generates a compiler warning.</span></span>

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public enum Size : uint {
        Unspecified = 0,
        XSmall = 1,
        Small = 2,
        Medium = 3,
        Large = 4,
        XLarge = 5
    };

    public class Clothing
    {
        public string Name;
        public string Type;
        public string Size;
    }
    // The attempt to compile the example displays a compiler warning like the following:
    //    Enum3.cs(6,13): warning CS3009: 'Size': base type 'uint' is not CLS-compliant
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Enum Size As UInt32
       Unspecified = 0
       XSmall = 1
       Small = 2
       Medium = 3
       Large = 4
       XLarge = 5
    End Enum

    Public Class Clothing
       Public Name As String
       Public Type As String
       Public Size As Size
    End Class
    ' The attempt to compile the example displays a compiler warning like the following:
    '    Enum3.vb(6) : warning BC40032: Underlying type 'UInt32' of Enum is not CLS-compliant.
    '
    '    Public Enum Size As UInt32
    '                ~~~~
    ```

* <span data-ttu-id="7d228-514">Ein Enumerationstyp muss über ein Feld namens `Value__` mit einer einzelnen Instanz verfügen, das mit dem `FieldAttributes.RTSpecialName`-Attribut markiert ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-514">An enumeration type must have a single instance field named `Value__` that is marked with the `FieldAttributes.RTSpecialName` attribute.</span></span> <span data-ttu-id="7d228-515">Damit können Sie den Feldwert implizit verweisen.</span><span class="sxs-lookup"><span data-stu-id="7d228-515">This enables you to reference the field value implicitly.</span></span>

* <span data-ttu-id="7d228-516">Eine Enumeration umfasst literale statische Felder, deren Typen vom gleichen Typ wie die Enumeration selbst sein müssen.</span><span class="sxs-lookup"><span data-stu-id="7d228-516">An enumeration includes literal static fields whose types match the type of the enumeration itself.</span></span> <span data-ttu-id="7d228-517">Wenn Sie zum Beispiel eine `State`-Enumeration mit den Werten aus `State.On` und `State.Off` definieren, sind `State.On` und `State.Off` literale statische Felder, deren Typ `State` ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-517">For example, if you define a `State` enumeration with values of `State.On` and `State.Off`, `State.On` and `State.Off` are both literal static fields whose type is `State`.</span></span>

* <span data-ttu-id="7d228-518">Es gibt zwei Arten von Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="7d228-518">There are two kinds of enumerations:</span></span>

  * <span data-ttu-id="7d228-519">Eine Enumeration, die einen Satz wechselseitig exklusiver, benannter ganzzahliger Werte darstellt.</span><span class="sxs-lookup"><span data-stu-id="7d228-519">An enumeration that represents a set of mutually exclusive, named integer values.</span></span> <span data-ttu-id="7d228-520">Dieser Typ der Enumeration wird durch das Fehlen des benutzerdefinierten [System.FlagsAttribute](xref:System.FlagsAttribute)-Attributs angegeben.</span><span class="sxs-lookup"><span data-stu-id="7d228-520">This type of enumeration is indicated by the absence of the [System.FlagsAttribute](xref:System.FlagsAttribute) custom attribute.</span></span>

  * <span data-ttu-id="7d228-521">Eine Enumeration, die einen Satz von Bitflags darstellt, die zum Generieren eines unbenannten Werts kombiniert werden können.</span><span class="sxs-lookup"><span data-stu-id="7d228-521">An enumeration that represents a set of bit flags that can combine to generate an unnamed value.</span></span> <span data-ttu-id="7d228-522">Dieser Typ der Enumeration wird durch das Vorhandensein des benutzerdefinierten [System.FlagsAttribute](xref:System.FlagsAttribute)-Attributs angegeben.</span><span class="sxs-lookup"><span data-stu-id="7d228-522">This type of enumeration is indicated by the presence of the [System.FlagsAttribute](xref:System.FlagsAttribute) custom attribute.</span></span>

<span data-ttu-id="7d228-523">Weitere Informationen finden Sie in der Dokumentation zur [Enum](xref:System.Enum)-Struktur.</span><span class="sxs-lookup"><span data-stu-id="7d228-523">For more information, see the documentation for the [Enum](xref:System.Enum) structure.</span></span>

* <span data-ttu-id="7d228-524">Der Wert einer Enumeration wird nicht auf den Bereich der angegebenen Werte beschränkt.</span><span class="sxs-lookup"><span data-stu-id="7d228-524">The value of an enumeration is not limited to the range of its specified values.</span></span> <span data-ttu-id="7d228-525">Das heißt, der Wertebereich einer Enumeration ist der Bereich des zugrunde liegenden Werts.</span><span class="sxs-lookup"><span data-stu-id="7d228-525">In other words, the range of values in an enumeration is the range of its underlying value.</span></span> <span data-ttu-id="7d228-526">Sie können die `Enum.IsDefined`-Methode verwenden, um zu bestimmen, ob ein angegebener Wert ein Member einer Enumeration ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-526">You can use the `Enum.IsDefined` method to determine whether a specified value is a member of an enumeration.</span></span>

### <a name="type-members-in-general"></a><span data-ttu-id="7d228-527">Typmember im Allgemeinen</span><span class="sxs-lookup"><span data-stu-id="7d228-527">Type members in general</span></span>

<span data-ttu-id="7d228-528">Die Common Language Specification erfordert, dass auf alle Felder und Methoden als Member einer bestimmten Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-528">The Common Language Specification requires all fields and methods to be accessed as members of a particular class.</span></span> <span data-ttu-id="7d228-529">Daher sind globale statische Felder und Methoden (das heißt, statische Felder oder Methoden, die unabhängig von einem Typ definiert werden), nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-529">Therefore, global static fields and methods (that is, static fields or methods that are defined apart from a type) are not CLS-compliant.</span></span> <span data-ttu-id="7d228-530">Wenn Sie versuchen, ein globales Feld oder eine Methode im Quellcode einzuschließen, wird vom C#-Compiler ein Compilerfehler generiert.</span><span class="sxs-lookup"><span data-stu-id="7d228-530">If you try to include a global field or method in your source code, the C# compiler generates a compiler error.</span></span>

<span data-ttu-id="7d228-531">Die Common Language Specification unterstützt nur die verwaltete Standardaufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="7d228-531">The Common Language Specification supports only the standard managed calling convention.</span></span> <span data-ttu-id="7d228-532">Sie unterstützt keine nicht verwalteten Aufrufkonventionen und keine Methoden mit variablen Argumentlisten, die mit dem `varargs`-Schlüsselwort gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-532">It doesn't support unmanaged calling conventions and methods with variable argument lists marked with the `varargs` keyword.</span></span> <span data-ttu-id="7d228-533">Verwenden Sie für Variablenargumentlisten, die mit der verwalteten Standardaufrufkonvention kompatibel sind, das [ParamArrayAttribute](xref:System.ParamArrayAttribute)-Attribut oder die Implementierung der jeweiligen Sprache, wie z.B. das `params`-Schlüsselwort in C# und das `ParamArray`-Schlüsselwort in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7d228-533">For variable argument lists that are compatible with the standard managed calling convention, use the [ParamArrayAttribute](xref:System.ParamArrayAttribute) attribute or the individual language's implementation, such as the `params` keyword in C# and the `ParamArray` keyword in Visual Basic.</span></span>

### <a name="member-accessibility"></a><span data-ttu-id="7d228-534">Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="7d228-534">Member accessibility</span></span>

<span data-ttu-id="7d228-535">Das Überschreiben eines geerbten Members kann den Zugriff auf diesen Member nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="7d228-535">Overriding an inherited member cannot change the accessibility of that member.</span></span> <span data-ttu-id="7d228-536">Beispielsweise kann eine öffentliche Methode in einer Basisklasse nicht von einer privaten Methode in einer abgeleiteten Klasse überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-536">For example, a public method in a base class cannot be overridden by a private method in a derived class.</span></span> <span data-ttu-id="7d228-537">Es gibt allerdings eine Ausnahme: einen `protected internal`-Member (in C#) oder einen `Protected Friend`-Member (in Visual Basic) in einer Assembly, die von einem Typ in einer anderen Assembly überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="7d228-537">There is one exception: a `protected internal` (in C#) or `Protected Friend` (in Visual Basic) member in one assembly that is overridden by a type in a different assembly.</span></span>  <span data-ttu-id="7d228-538">In diesem Fall ist der Zugriff auf die Überschreibung `Protected`.</span><span class="sxs-lookup"><span data-stu-id="7d228-538">In that case, the accessibility of the override is `Protected`.</span></span>

<span data-ttu-id="7d228-539">Im folgenden Beispiel wird der Fehler veranschaulicht, der generiert wird, wenn das [CLSCompliantAttribute](xref:System.CLSCompliantAttribute)-Attribut auf `true` festgelegt wird und `Person`, eine von `Animal` abgeleitete Klasse, versucht, den Zugriff auf die `Species`-Eigenschaft von öffentlich in privat zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7d228-539">The following example illustrates the error that is generated when the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute is set to `true`, and `Person`, which is a class derived from `Animal`, tries to change the accessibility of the `Species` property from public to private.</span></span> <span data-ttu-id="7d228-540">Das Beispiel wird erfolgreich kompiliert, wenn der Zugriff auf öffentlich geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7d228-540">The example compiles successfully if its accessibility is changed to public.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Animal
{
   private string _species;

   public Animal(string species)
   {
      _species = species;
   }

   public virtual string Species
   {
      get { return _species; }
   }

   public override string ToString()
   {
      return _species;
   }
}

public class Human : Animal
{
   private string _name;

   public Human(string name) : base("Homo Sapiens")
   {
      _name = name;
   }

   public string Name
   {
      get { return _name; }
   }

   private override string Species
   {
      get { return base.Species; }
   }

   public override string ToString()
   {
      return _name;
   }
}

public class Example
{
   public static void Main()
   {
      Human p = new Human("John");
      Console.WriteLine(p.Species);
      Console.WriteLine(p.ToString());
   }
}
// The example displays the following output:
//    error CS0621: 'Human.Species': virtual or abstract members cannot be private
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Animal
   Private _species As String

   Public Sub New(species As String)
      _species = species
   End Sub

   Public Overridable ReadOnly Property Species As String
      Get
         Return _species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _species
   End Function
End Class

Public Class Human : Inherits Animal
   Private _name As String

   Public Sub New(name As String)
      MyBase.New("Homo Sapiens")
      _name = name
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return _name
      End Get
   End Property

   Private Overrides ReadOnly Property Species As String
      Get
         Return MyBase.Species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _name
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim p As New Human("John")
      Console.WriteLine(p.Species)
      Console.WriteLine(p.ToString())
   End Sub
End Module
' The example displays the following output:
'     'Private Overrides ReadOnly Property Species As String' cannot override
'     'Public Overridable ReadOnly Property Species As String' because
'      they have different access levels.
'
'         Private Overrides ReadOnly Property Species As String
```

<span data-ttu-id="7d228-541">Der Zugriff auf Typen in der Signatur eines Members muss möglich sein, wenn auf den Member zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7d228-541">Types in the signature of a member must be accessible whenever that member is accessible.</span></span> <span data-ttu-id="7d228-542">Das bedeutet zum Beispiel, dass ein öffentlicher Member keinen Parameter enthalten kann, dessen Typ privat, geschützt oder intern ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-542">For example, this means that a public member cannot include a parameter whose type is private, protected, or internal.</span></span> <span data-ttu-id="7d228-543">Im folgenden Beispiel wird der Compilerfehler veranschaulicht, der entsteht, wenn ein `StringWrapper`-Klassenkonstruktor einen internen `StringOperationType`-Enumerationswert verfügbar macht, der bestimmt, wie ein Zeichenfolgenwert umschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="7d228-543">The following example illustrates the compiler error that results when a `StringWrapper` class constructor exposes an internal `StringOperationType` enumeration value that determines how a string value should be wrapped.</span></span>

```csharp
using System;
using System.Text;

public class StringWrapper
{
   string internalString;
   StringBuilder internalSB = null;
   bool useSB = false;

   public StringWrapper(StringOperationType type)
   {
      if (type == StringOperationType.Normal) {
         useSB = false;
      }
      else {
         useSB = true;
         internalSB = new StringBuilder();
      }
   }

   // The remaining source code...
}

internal enum StringOperationType { Normal, Dynamic }
// The attempt to compile the example displays the following output:
//    error CS0051: Inconsistent accessibility: parameter type
//            'StringOperationType' is less accessible than method
//            'StringWrapper.StringWrapper(StringOperationType)'
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class StringWrapper

   Dim internalString As String
   Dim internalSB As StringBuilder = Nothing
   Dim useSB As Boolean = False

   Public Sub New(type As StringOperationType)
      If type = StringOperationType.Normal Then
         useSB = False
      Else
         internalSB = New StringBuilder()
         useSB = True
      End If
   End Sub

   ' The remaining source code...
End Class

Friend Enum StringOperationType As Integer
   Normal = 0
   Dynamic = 1
End Enum
' The attempt to compile the example displays the following output:
'    error BC30909: 'type' cannot expose type 'StringOperationType'
'     outside the project through class 'StringWrapper'.
'
'       Public Sub New(type As StringOperationType)
'                              ~~~~~~~~~~~~~~~~~~~
```

### <a name="generic-types-and-members"></a><span data-ttu-id="7d228-544">Generische Typen und Member</span><span class="sxs-lookup"><span data-stu-id="7d228-544">Generic types and members</span></span>

<span data-ttu-id="7d228-545">Geschachtelte Typen weisen immer mindestens so viele generische Parameter auf wie der einschließende Typ.</span><span class="sxs-lookup"><span data-stu-id="7d228-545">Nested types always have at least as many generic parameters as their enclosing type.</span></span> <span data-ttu-id="7d228-546">Diese entsprechen der Position nach den generischen Parametern im einschließenden Typ.</span><span class="sxs-lookup"><span data-stu-id="7d228-546">These correspond by position to the generic parameters in the enclosing type.</span></span> <span data-ttu-id="7d228-547">Der generische Typ kann auch neue generische Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="7d228-547">The generic type can also include new generic parameters.</span></span>

<span data-ttu-id="7d228-548">Die Beziehung zwischen generischen Typparametern eines enthaltenden Typs und den geschachtelten Typen wird möglicherweise von der Syntax der einzelnen Sprachen verdeckt.</span><span class="sxs-lookup"><span data-stu-id="7d228-548">The relationship between the generic type parameters of a containing type and its nested types may be hidden by the syntax of individual languages.</span></span> <span data-ttu-id="7d228-549">Im folgenden Beispiel enthält ein generischer Typ `Outer<T>` zwei geschachtelte Klassen: `Inner1A` und `Inner1B<U>`.</span><span class="sxs-lookup"><span data-stu-id="7d228-549">In the following example, a generic type `Outer<T>` contains two nested classes, `Inner1A` and `Inner1B<U>`.</span></span> <span data-ttu-id="7d228-550">Die Aufrufe der `ToString`-Methode, die jede Klasse von `Object.ToString` erbt, zeigen, dass jede geschachtelte Klasse die Typparameter der enthaltenden Klasse umfasst.</span><span class="sxs-lookup"><span data-stu-id="7d228-550">The calls to the `ToString` method, which each class inherits from `Object.ToString`, show that each nested class includes the type parameters of its containing class.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Outer<T>
{
   T value;

   public Outer(T value)
   {
      this.value = value;
   }

   public class Inner1A : Outer<T>
   {
      public Inner1A(T value) : base(value)
      {  }
   }

   public class Inner1B<U> : Outer<T>
   {
      U value2;

      public Inner1B(T value1, U value2) : base(value1)
      {
         this.value2 = value2;
      }
   }
}

public class Example
{
   public static void Main()
   {
      var inst1 = new Outer<String>("This");
      Console.WriteLine(inst1);

      var inst2 = new Outer<String>.Inner1A("Another");
      Console.WriteLine(inst2);

      var inst3 = new Outer<String>.Inner1B<int>("That", 2);
      Console.WriteLine(inst3);
   }
}
// The example displays the following output:
//       Outer`1[System.String]
//       Outer`1+Inner1A[System.String]
//       Outer`1+Inner1B`1[System.String,System.Int32]
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Outer(Of T)
   Dim value As T

   Public Sub New(value As T)
      Me.value = value
   End Sub

   Public Class Inner1A : Inherits Outer(Of T)
      Public Sub New(value As T)
         MyBase.New(value)
      End Sub
   End Class

   Public Class Inner1B(Of U) : Inherits Outer(Of T)
      Dim value2 As U

      Public Sub New(value1 As T, value2 As U)
         MyBase.New(value1)
         Me.value2 = value2
      End Sub
   End Class
End Class

Public Module Example
   Public Sub Main()
      Dim inst1 As New Outer(Of String)("This")
      Console.WriteLine(inst1)

      Dim inst2 As New Outer(Of String).Inner1A("Another")
      Console.WriteLine(inst2)

      Dim inst3 As New Outer(Of String).Inner1B(Of Integer)("That", 2)
      Console.WriteLine(inst3)
   End Sub
End Module
' The example displays the following output:
'       Outer`1[System.String]
'       Outer`1+Inner1A[System.String]
'       Outer`1+Inner1B`1[System.String,System.Int32]
```

<span data-ttu-id="7d228-551">Der Name eines generischen Typs wird in der Form *name*'*n* codiert, wobei *name* der Typname, *\`* ein Zeichenliteral und *n* die Anzahl von Parametern ist, die für den Typ deklariert sind, oder, bei geschachtelten generischen Typen, die Anzahl neu eingeführter Typparameter.</span><span class="sxs-lookup"><span data-stu-id="7d228-551">Generic type names are encoded in the form *name*'*n*, where *name* is the type name, *\`* is a character literal, and *n* is the number of parameters declared on the type, or, for nested generic types, the number of newly introduced type parameters.</span></span> <span data-ttu-id="7d228-552">Diese Codierung von Namen des generischen Typs ist hauptsächlich für Entwickler relevant, die Reflexion verwenden, um auf CLS-kompatible generische Typen in einer Bibliothek zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="7d228-552">This encoding of generic type names is primarily of interest to developers who use reflection to access CLS-complaint generic types in a library.</span></span>

<span data-ttu-id="7d228-553">Wenn Einschränkungen auf einen generischen Typ angewendet werden, müssen alle als Einschränkungen verwendeten Typen auch CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-553">If constraints are applied to a generic type, any types used as constraints must also be CLS-compliant.</span></span> <span data-ttu-id="7d228-554">Im folgenden Beispiel wird eine Klasse namens `BaseClass` definiert, die nicht CLS-kompatibel ist sowie eine generische Klasse namens `BaseCollection` deren Typparameter von `BaseClass` abgeleitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="7d228-554">The following example defines a class named `BaseClass` that is not CLS-compliant and a generic class named `BaseCollection` whose type parameter must derive from `BaseClass`.</span></span> <span data-ttu-id="7d228-555">Aber, da `BaseClass` nicht CLS-kompatibel ist, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="7d228-555">But because `BaseClass` is not CLS-compliant, the compiler emits a warning.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

[CLSCompliant(false)] public class BaseClass
{}

public class BaseCollection<T> where T : BaseClass
{}
// Attempting to compile the example displays the following output:
//    warning CS3024: Constraint type 'BaseClass' is not CLS-compliant
```

```vb
Assembly: CLSCompliant(True)>

<CLSCompliant(False)> Public Class BaseClass
End Class

Public Class BaseCollection(Of T As BaseClass)
End Class
' Attempting to compile the example displays the following output:
'    warning BC40040: Generic parameter constraint type 'BaseClass' is not
'    CLS-compliant.
'
'    Public Class BaseCollection(Of T As BaseClass)
'                                        ~~~~~~~~~
```

<span data-ttu-id="7d228-556">Wenn ein generischer Typ von einem generischen Basistyp abgeleitet ist, muss er alle Einschränkungen erneut deklarieren, damit sichergestellt ist, dass auch die Einschränkungen des Basistyps erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-556">If a generic type is derived from a generic base type, it must redeclare any constraints so that it can guarantee that constraints on the base type are also satisfied.</span></span> <span data-ttu-id="7d228-557">Im folgenden Beispiel wird `Number<T>` definiert, das einen numerischen Typ darstellen kann.</span><span class="sxs-lookup"><span data-stu-id="7d228-557">The following example defines a `Number<T>` that can represent any numeric type.</span></span> <span data-ttu-id="7d228-558">Es definiert auch eine `FloatingPoint<T>`-Klasse, die einen Gleitkommawert darstellt.</span><span class="sxs-lookup"><span data-stu-id="7d228-558">It also defines a `FloatingPoint<T>` class that represents a floating point value.</span></span> <span data-ttu-id="7d228-559">Allerdings kann der Quellcode nicht kompiliert werden, da die Einschränkung auf `Number<T>` (dieses T muss ein Werttyp sein) nicht auf `FloatingPoint<T>` angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-559">However, the source code fails to compile, because it does not apply the constraint on `Number<T>` (that T must be a value type) to `FloatingPoint<T>`.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T>
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
// The attempt to compile the example displays the following output:
//       error CS0453: The type 'T' must be a non-nullable value type in
//               order to use it as parameter 'T' in the generic type or method 'Number<T>'
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
' The attempt to compile the example displays the following output:
'    error BC32105: Type argument 'T' does not satisfy the 'Structure'
'    constraint for type parameter 'T'.
'
'    Public Class FloatingPoint(Of T) : Inherits Number(Of T)
'                                                          ~
```

<span data-ttu-id="7d228-560">Das Beispiel wird erfolgreich kompiliert, wenn die Einschränkung der `FloatingPoint<T>`-Klasse hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="7d228-560">The example compiles successfully if the constraint is added to the `FloatingPoint<T>` class.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T> where T : struct
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T As Structure) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
```

<span data-ttu-id="7d228-561">Die Common Language Specification erzwingt ein konservatives Pro-Instanziierungsmodell für geschachtelte Typen und geschützte Member.</span><span class="sxs-lookup"><span data-stu-id="7d228-561">The Common Language Specification imposes a conservative per-instantiation model for nested types and protected members.</span></span> <span data-ttu-id="7d228-562">Offene generische Typen können Felder oder Member mit Signaturen nicht verfügbar machen, die eine bestimmte Instanziierung eines geschachtelten, geschützten generischen Typs enthalten.</span><span class="sxs-lookup"><span data-stu-id="7d228-562">Open generic types cannot expose fields or members with signatures that contain a specific instantiation of a nested, protected generic type.</span></span> <span data-ttu-id="7d228-563">Nicht generische Typen, die eine bestimmte Instanziierung einer generischen Basisklasse oder Schnittstelle erweitern, können Felder oder Member mit Signaturen nicht verfügbar machen, die eine andere Instanziierung eines geschachtelten, geschützten generischen Typs enthalten.</span><span class="sxs-lookup"><span data-stu-id="7d228-563">Non-generic types that extend a specific instantiation of a generic base class or interface cannot expose fields or members with signatures that contain a different instantiation of a nested, protected generic type.</span></span>

<span data-ttu-id="7d228-564">Das folgende Beispiel definiert einen generischen Typ „`C1<T>`“ und eine geschützte Klasse „`C1<T>.N`“.</span><span class="sxs-lookup"><span data-stu-id="7d228-564">The following example defines a generic type, `C1<T>`, and a protected class, `C1<T>.N`.</span></span> <span data-ttu-id="7d228-565">`C1<T>` verfügt über zwei Methoden, `M1` und `M2`.</span><span class="sxs-lookup"><span data-stu-id="7d228-565">`C1<T>` has two methods, `M1` and `M2`.</span></span> <span data-ttu-id="7d228-566">Allerdings ist `M1` nicht CLS-kompatibel, da versucht wird, ein `C1<int>.N`-Objekt von `C1<T>` zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="7d228-566">However, `M1` is not CLS-compliant because it tries to return a `C1<int>.N` object from `C1<T>`.</span></span> <span data-ttu-id="7d228-567">Eine zweite Klasse, `C2`, wird von `C1<long>` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="7d228-567">A second class, `C2`, is derived from `C1<long>`.</span></span> <span data-ttu-id="7d228-568">Sie verfügt über zwei Methoden, `M3` und `M4`.</span><span class="sxs-lookup"><span data-stu-id="7d228-568">It has two methods, `M3` and `M4`.</span></span> <span data-ttu-id="7d228-569">`M3` ist nicht CLS-kompatibel, da versucht wird, ein `C1<int>.N`-Objekt von einer Unterklasse von `C1<long>` zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="7d228-569">`M3` is not CLS-compliant because it tries to return a `C1<int>.N` object from a subclass of `C1<long>`.</span></span> <span data-ttu-id="7d228-570">Sprachcompiler können sogar noch restriktiver sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-570">Language compilers can be even more restrictive.</span></span> <span data-ttu-id="7d228-571">In diesem Beispiel zeigt Visual Basic einen Fehler an, wenn versucht wird, `M4` zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-571">In this example, Visual Basic displays an error when it tries to compile `M4`.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class C1<T>
{
   protected class N { }

   protected void M1(C1<int>.N n) { } // Not CLS-compliant - C1<int>.N not
                                      // accessible from within C1<T> in all
                                      // languages
   protected void M2(C1<T>.N n) { }   // CLS-compliant – C1<T>.N accessible
                                      // inside C1<T>
}

public class C2 : C1<long>
{
   protected void M3(C1<int>.N n) { }  // Not CLS-compliant – C1<int>.N is not
                                       // accessible in C2 (extends C1<long>)

   protected void M4(C1<long>.N n) { } // CLS-compliant, C1<long>.N is
                                       // accessible in C2 (extends C1<long>)
}
// Attempting to compile the example displays output like the following:
//       Generics4.cs(9,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
//       Generics4.cs(18,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
```

```vb
<Assembly:CLSCompliant(True)>

Public Class C1(Of T)
   Protected Class N
   End Class

   Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
                                             ' accessible from within C1(Of T) in all
   End Sub                                   ' languages

   Protected Sub M2(n As C1(Of T).N)     ' CLS-compliant – C1(Of T).N accessible
   End Sub                               ' inside C1(Of T)
End Class

Public Class C2 : Inherits C1(Of Long)
   Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant – C1(Of Integer).N is not
   End Sub                                   ' accessible in C2 (extends C1(Of Long))

   Protected Sub M4(n As C1(Of Long).N)
   End Sub
End Class
' Attempting to compile the example displays output like the following:
'    error BC30508: 'n' cannot expose type 'C1(Of Integer).N' in namespace
'    '<Default>' through class 'C1'.
'
'       Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
'                             ~~~~~~~~~~~~~~~~
'    error BC30389: 'C1(Of T).N' is not accessible in this context because
'    it is 'Protected'.
'
'       Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant - C1(Of Integer).N is not
'
'                             ~~~~~~~~~~~~~~~~
'
'    error BC30389: 'C1(Of T).N' is not accessible in this context because it is 'Protected'.
'
'       Protected Sub M4(n As C1(Of Long).N)
'                             ~~~~~~~~~~~~~
```

### <a name="constructors"></a><span data-ttu-id="7d228-572">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="7d228-572">Constructors</span></span>

<span data-ttu-id="7d228-573">Bei Konstruktoren in den CLS-kompatiblen Klassen und Strukturen müssen die folgenden Regeln beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="7d228-573">Constructors in CLS-compliant classes and structures must follow these rules:</span></span>

* <span data-ttu-id="7d228-574">Der Konstruktor einer abgeleiteten Klasse muss den Instanzkonstruktor der Basisklasse aufrufen, bevor er auf geerbte Instanzdaten zugreift.</span><span class="sxs-lookup"><span data-stu-id="7d228-574">A constructor of a derived class must call the instance constructor of its base class before it accesses inherited instance data.</span></span> <span data-ttu-id="7d228-575">Diese Anforderung basiert auf der Tatsache, dass Konstruktoren nicht nach ihren abgeleiteten Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-575">This requirement is due to the fact that base class constructors are not inherited by their derived classes.</span></span> <span data-ttu-id="7d228-576">Diese Regel gilt nicht für Strukturen, die keine direkte Vererbung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7d228-576">This rule does not apply to structures, which do not support direct inheritance.</span></span>

  <span data-ttu-id="7d228-577">In der Regel erzwingen Compiler diese Regel unabhängig von der CLS-Kompatibilität, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d228-577">Typically, compilers enforce this rule independently of CLS compliance, as the following example shows.</span></span> <span data-ttu-id="7d228-578">Es wird eine `Doctor`-Klasse erstellt, die von einer `Person`-Klasse abgeleitet ist. Doch die `Doctor`-Klasse kann den `Person`-Klassenkonstruktor nicht zum Initialisieren geerbter Instanzfelder aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7d228-578">It creates a `Doctor` class that is derived from a `Person` class, but the `Doctor` class fails to call the `Person` class constructor to initialize inherited instance fields.</span></span>

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public class Person
    {
    private string fName, lName, _id;

    public Person(string firstName, string lastName, string id)
    {
        if (String.IsNullOrEmpty(firstName + lastName))
            throw new ArgumentNullException("Either a first name or a last name must be provided.");

        fName = firstName;
        lName = lastName;
        _id = id;
    }

    public string FirstName
    {
        get { return fName; }
    }

    public string LastName
    {
        get { return lName; }
    }

    public string Id
    {
        get { return _id; }
    }

    public override string ToString()
    {
        return String.Format("{0}{1}{2}", fName,
                            String.IsNullOrEmpty(fName) ?  "" : " ",
                            lName);
    }
    }

    public class Doctor : Person
    {
    public Doctor(string firstName, string lastName, string id)
    {
    }

    public override string ToString()
    {
        return "Dr. " + base.ToString();
    }
    }
    // Attempting to compile the example displays output like the following:
    //    ctor1.cs(45,11): error CS1729: 'Person' does not contain a constructor that takes 0
    //            arguments
    //    ctor1.cs(10,11): (Location of symbol related to previous error)
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Class Person
       Private fName, lName, _id As String

       Public Sub New(firstName As String, lastName As String, id As String)
          If String.IsNullOrEmpty(firstName + lastName) Then
             Throw New ArgumentNullException("Either a first name or a last name must be provided.")
          End If

          fName = firstName
          lName = lastName
          _id = id
       End Sub

       Public ReadOnly Property FirstName As String
          Get
             Return fName
          End Get
       End Property

       Public ReadOnly Property LastName As String
          Get
             Return lName
          End Get
       End Property

       Public ReadOnly Property Id As String
          Get
             Return _id
          End Get
       End Property

       Public Overrides Function ToString() As String
          Return String.Format("{0}{1}{2}", fName,
                               If(String.IsNullOrEmpty(fName), "", " "),
                               lName)
       End Function
    End Class

    Public Class Doctor : Inherits Person
       Public Sub New(firstName As String, lastName As String, id As String)
       End Sub

       Public Overrides Function ToString() As String
          Return "Dr. " + MyBase.ToString()
       End Function
    End Class
    ' Attempting to compile the example displays output like the following:
    '    Ctor1.vb(46) : error BC30148: First statement of this 'Sub New' must be a call
    '    to 'MyBase.New' or 'MyClass.New' because base class 'Person' of 'Doctor' does
    '    not have an accessible 'Sub New' that can be called with no arguments.
    '
    '       Public Sub New()
    '                  ~~~
    ````

* <span data-ttu-id="7d228-579">Ein Objektkonstruktor kann nur aufgerufen werden, um ein Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d228-579">An object constructor cannot be called except to create an object.</span></span> <span data-ttu-id="7d228-580">Außerdem kann ein Objekt nicht zweimal initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-580">In addition, an object cannot be initialized twice.</span></span> <span data-ttu-id="7d228-581">Beispielsweise bedeutet dies, dass mit `Object.MemberwiseClone` keine Konstruktoren aufgerufen werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="7d228-581">For example, this means that `Object.MemberwiseClone` must not call constructors.</span></span>

### <a name="properties"></a><span data-ttu-id="7d228-582">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d228-582">Properties</span></span>

<span data-ttu-id="7d228-583">Eigenschaften in den CLS-kompatiblen Typen müssen die folgenden Regeln beachten:</span><span class="sxs-lookup"><span data-stu-id="7d228-583">Properties in CLS-compliant types must follow these rules:</span></span>

* <span data-ttu-id="7d228-584">Eine Eigenschaft muss über einen Setter, einen Getter oder beides verfügen.</span><span class="sxs-lookup"><span data-stu-id="7d228-584">A property must have a setter, a getter, or both.</span></span> <span data-ttu-id="7d228-585">In einer Assembly werden diese als spezielle Methoden implementiert, das bedeutet, dass sie als separate Methoden (der Getter hat den Namen `get`\_*propertyname* und der Setter den Namen `set`\_*propertyname*) erscheinen, die als `SpecialName` gekennzeichnet in den Metadaten der Assembly angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-585">In an assembly, these are implemented as special methods, which means that they will appear as separate methods (the getter is named `get`\_*propertyname* and the setter is `set`\_*propertyname*) marked as `SpecialName` in the assembly's metadata.</span></span> <span data-ttu-id="7d228-586">Die C#-Compiler erzwingt diese Regel automatisch, ohne das <xref:System.CLSCompliantAttribute>-Attribut anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="7d228-586">The C# compiler enforces this rule automatically without the need to apply the <xref:System.CLSCompliantAttribute> attribute.</span></span>

* <span data-ttu-id="7d228-587">Ein Typ der Eigenschaft entspricht dem Rückgabetyp der Getter-Methode der Eigenschaft und dem letzten Argument der Setter-Methode.</span><span class="sxs-lookup"><span data-stu-id="7d228-587">A property's type is the return type of the property getter and the last argument of the setter.</span></span> <span data-ttu-id="7d228-588">Diese Typen müssen CLS-kompatibel sein, und Argumente können der Eigenschaft nicht mithilfe eines Verweises zugewiesen werden (das heißt, es können keine verwalteten Zeiger sein).</span><span class="sxs-lookup"><span data-stu-id="7d228-588">These types must be CLS compliant, and arguments cannot be assigned to the property by reference (that is, they cannot be managed pointers).</span></span>

* <span data-ttu-id="7d228-589">Wenn eine Eigenschaft einen Getter und einen Setter aufweist, müssen beide "virtual", "static" oder "instance" sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-589">If a property has both a getter and a setter, they must both be virtual, both static, or both instance.</span></span> <span data-ttu-id="7d228-590">Der C#-Compiler erzwingt diese Regel automatisch über die Eigenschaftendefinitionssyntax.</span><span class="sxs-lookup"><span data-stu-id="7d228-590">The C# compiler automatically enforces this rule through property definition syntax.</span></span>

### <a name="events"></a><span data-ttu-id="7d228-591">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7d228-591">Events</span></span>

<span data-ttu-id="7d228-592">Ein Ereignis wird vom Namen und dem Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="7d228-592">An event is defined by its name and its type.</span></span> <span data-ttu-id="7d228-593">Der Ereignistyp ist ein Delegat, der zum Angeben des Ereignisses verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d228-593">The event type is a delegate that is used to indicate the event.</span></span> <span data-ttu-id="7d228-594">Zum Beispiel hat das `DbConnection.StateChange`-Ereignis den Typ `StateChangeEventHandler`.</span><span class="sxs-lookup"><span data-stu-id="7d228-594">For example, the `DbConnection.StateChange` event is of type `StateChangeEventHandler`.</span></span> <span data-ttu-id="7d228-595">Neben dem Ereignis selbst, stellen drei Methoden mit Namen basierend auf dem Ereignisnamen die Implementierung des Ereignisses bereit und werden in den Metadaten der Assembly als `SpecialName` gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="7d228-595">In addition to the event itself, three methods with names based on the event name provide the event's implementation and are marked as `SpecialName` in the assembly's metadata:</span></span>

* <span data-ttu-id="7d228-596">Eine Methode zum Hinzufügen eines Ereignishandlers namens `add`_*Ereignisname*.</span><span class="sxs-lookup"><span data-stu-id="7d228-596">A method for adding an event handler, named `add`_*EventName*.</span></span> <span data-ttu-id="7d228-597">Die Ereignisabonnementmethode für das `DbConnection.StateChange`-Ereignis hat zum Beispiel den Namen `add_StateChange`.</span><span class="sxs-lookup"><span data-stu-id="7d228-597">For example, the event subscription method for the `DbConnection.StateChange` event is named `add_StateChange`.</span></span>

* <span data-ttu-id="7d228-598">Eine Methode zum Enternen eines Ereignishandlers namens `remove`_*Ereignisname*.</span><span class="sxs-lookup"><span data-stu-id="7d228-598">A method for removing an event handler, named `remove`_*EventName*.</span></span> <span data-ttu-id="7d228-599">Die Entfernenmethode für das `DbConnection.StateChange`-Ereignis hat zum Beispiel den Namen `remove_StateChange`.</span><span class="sxs-lookup"><span data-stu-id="7d228-599">For example, the removal method for the `DbConnection.StateChange` event is named `remove_StateChange`.</span></span>

* <span data-ttu-id="7d228-600">Eine Methode für den Hinweis, dass das Ereignis namens `raise`\_*EventName* aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-600">A method for indicating that the event has occurred, named `raise`\_*EventName*.</span></span>

> [!NOTE]
> <span data-ttu-id="7d228-601">Die meisten Regeln der Common Language Specification zu Ereignissen werden von den Sprachcompilern implementiert und sind für Komponentenentwickler transparent.</span><span class="sxs-lookup"><span data-stu-id="7d228-601">Most of the Common Language Specification's rules regarding events are implemented by language compilers and are transparent to component developers.</span></span>

<span data-ttu-id="7d228-602">Die Methoden für das Hinzufügen, Entfernen und Auslösen des Ereignisses verfügen über den gleichen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="7d228-602">The methods for adding, removing, and raising the event must have the same accessibility.</span></span> <span data-ttu-id="7d228-603">Sie müssen zudem "static", "instance" oder "virtual" sein.</span><span class="sxs-lookup"><span data-stu-id="7d228-603">They must also all be static, instance, or virtual.</span></span> <span data-ttu-id="7d228-604">Die Methoden zum Hinzufügen und Entfernen eines Ereignisses verfügen über einen Parameter, dessen Typ der Ereignisdelegattyp ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-604">The methods for adding and removing an event have one parameter whose type is the event delegate type.</span></span> <span data-ttu-id="7d228-605">Die Methoden zum Hinzufügen und Entfernen müssen beide vorhanden sein oder beide fehlen.</span><span class="sxs-lookup"><span data-stu-id="7d228-605">The add and remove methods must both be present or both be absent.</span></span>

<span data-ttu-id="7d228-606">Im folgenden Beispiel wird eine CLS-kompatible Klasse namens `Temperature` definiert, die ein `TemperatureChanged`-Ereignis auslöst, wenn die Temperaturänderung zwischen zwei Messungen einem Schwellenwert entspricht oder diesen überschreitet.</span><span class="sxs-lookup"><span data-stu-id="7d228-606">The following example defines a CLS-compliant class named `Temperature` that raises a `TemperatureChanged` event if the change in temperature between two readings equals or exceeds a threshold value.</span></span> <span data-ttu-id="7d228-607">Die `Temperature`-Klasse definiert eine `raise_TemperatureChanged`-Methode explizit, sodass sie selektiv Ereignishandler ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="7d228-607">The `Temperature` class explicitly defines a `raise_TemperatureChanged` method so that it can selectively execute event handlers.</span></span>

```csharp
using System;
using System.Collections;
using System.Collections.Generic;

[assembly: CLSCompliant(true)]

public class TemperatureChangedEventArgs : EventArgs
{
   private Decimal originalTemp;
   private Decimal newTemp;
   private DateTimeOffset when;

   public TemperatureChangedEventArgs(Decimal original, Decimal @new, DateTimeOffset time)
   {
      originalTemp = original;
      newTemp = @new;
      when = time;
   }

   public Decimal OldTemperature
   {
      get { return originalTemp; }
   }

   public Decimal CurrentTemperature
   {
      get { return newTemp; }
   }

   public DateTimeOffset Time
   {
      get { return when; }
   }
}

public delegate void TemperatureChanged(Object sender, TemperatureChangedEventArgs e);

public class Temperature
{
   private struct TemperatureInfo
   {
      public Decimal Temperature;
      public DateTimeOffset Recorded;
   }

   public event TemperatureChanged TemperatureChanged;

   private Decimal previous;
   private Decimal current;
   private Decimal tolerance;
   private List<TemperatureInfo> tis = new List<TemperatureInfo>();

   public Temperature(Decimal temperature, Decimal tolerance)
   {
      current = temperature;
      TemperatureInfo ti = new TemperatureInfo();
      ti.Temperature = temperature;
      tis.Add(ti);
      ti.Recorded = DateTimeOffset.UtcNow;
      this.tolerance = tolerance;
   }

   public Decimal CurrentTemperature
   {
      get { return current; }
      set {
         TemperatureInfo ti = new TemperatureInfo();
         ti.Temperature = value;
         ti.Recorded = DateTimeOffset.UtcNow;
         previous = current;
         current = value;
         if (Math.Abs(current - previous) >= tolerance)
            raise_TemperatureChanged(new TemperatureChangedEventArgs(previous, current, ti.Recorded));
      }
   }

   public void raise_TemperatureChanged(TemperatureChangedEventArgs eventArgs)
   {
      if (TemperatureChanged == null)
         return;

      foreach (TemperatureChanged d in TemperatureChanged.GetInvocationList()) {
         if (d.Method.Name.Contains("Duplicate"))
            Console.WriteLine("Duplicate event handler; event handler not executed.");
         else
            d.Invoke(this, eventArgs);
      }
   }
}

public class Example
{
   public Temperature temp;

   public static void Main()
   {
      Example ex = new Example();
   }

   public Example()
   {
      temp = new Temperature(65, 3);
      temp.TemperatureChanged += this.TemperatureNotification;
      RecordTemperatures();
      Example ex = new Example(temp);
      ex.RecordTemperatures();
   }

   public Example(Temperature t)
   {
      temp = t;
      RecordTemperatures();
   }

   public void RecordTemperatures()
   {
      temp.TemperatureChanged += this.DuplicateTemperatureNotification;
      temp.CurrentTemperature = 66;
      temp.CurrentTemperature = 63;
   }

   internal void TemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }

   public void DuplicateTemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }
}
```

```vb
Imports System.Collections
Imports System.Collections.Generic

<Assembly: CLSCompliant(True)>

Public Class TemperatureChangedEventArgs   : Inherits EventArgs
   Private originalTemp As Decimal
   Private newTemp As Decimal
   Private [when] As DateTimeOffset

   Public Sub New(original As Decimal, [new] As Decimal, [time] As DateTimeOffset)
      originalTemp = original
      newTemp = [new]
      [when] = [time]
   End Sub

   Public ReadOnly Property OldTemperature As Decimal
      Get
         Return originalTemp
      End Get
   End Property

   Public ReadOnly Property CurrentTemperature As Decimal
      Get
         Return newTemp
      End Get
   End Property

   Public ReadOnly Property [Time] As DateTimeOffset
      Get
         Return [when]
      End Get
   End Property
End Class

Public Delegate Sub TemperatureChanged(sender As Object, e As TemperatureChangedEventArgs)

Public Class Temperature
   Private Structure TemperatureInfo
      Dim Temperature As Decimal
      Dim Recorded As DateTimeOffset
   End Structure

   Public Event TemperatureChanged As TemperatureChanged

   Private previous As Decimal
   Private current As Decimal
   Private tolerance As Decimal
   Private tis As New List(Of TemperatureInfo)

   Public Sub New(temperature As Decimal, tolerance As Decimal)
      current = temperature
      Dim ti As New TemperatureInfo()
      ti.Temperature = temperature
      ti.Recorded = DateTimeOffset.UtcNow
      tis.Add(ti)
      Me.tolerance = tolerance
   End Sub

   Public Property CurrentTemperature As Decimal
      Get
         Return current
      End Get
      Set
         Dim ti As New TemperatureInfo
         ti.Temperature = value
         ti.Recorded = DateTimeOffset.UtcNow
         previous = current
         current = value
         If Math.Abs(current - previous) >= tolerance Then
            raise_TemperatureChanged(New TemperatureChangedEventArgs(previous, current, ti.Recorded))
         End If
      End Set
   End Property

   Public Sub raise_TemperatureChanged(eventArgs As TemperatureChangedEventArgs)
      If TemperatureChangedEvent Is Nothing Then Exit Sub

      Dim ListenerList() As System.Delegate = TemperatureChangedEvent.GetInvocationList()
      For Each d As TemperatureChanged In TemperatureChangedEvent.GetInvocationList()
         If d.Method.Name.Contains("Duplicate") Then
            Console.WriteLine("Duplicate event handler; event handler not executed.")
         Else
            d.Invoke(Me, eventArgs)
         End If
      Next
   End Sub
End Class

Public Class Example
   Public WithEvents temp As Temperature

   Public Shared Sub Main()
      Dim ex As New Example()
   End Sub

   Public Sub New()
      temp = New Temperature(65, 3)
      RecordTemperatures()
      Dim ex As New Example(temp)
      ex.RecordTemperatures()
   End Sub

   Public Sub New(t As Temperature)
      temp = t
      RecordTemperatures()
   End Sub

   Public Sub RecordTemperatures()
      temp.CurrentTemperature = 66
      temp.CurrentTemperature = 63

   End Sub

   Friend Shared Sub TemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub

   Friend Shared Sub DuplicateTemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub
End Class
```

### <a name="overloads"></a><span data-ttu-id="7d228-608">Overloads</span><span class="sxs-lookup"><span data-stu-id="7d228-608">Overloads</span></span>

<span data-ttu-id="7d228-609">Die Common Language Specification erzwingt die folgenden Anforderungen für überladene Member:</span><span class="sxs-lookup"><span data-stu-id="7d228-609">The Common Language Specification imposes the following requirements on overloaded members:</span></span>

* <span data-ttu-id="7d228-610">Member können auf Grundlage der Anzahl und des Typs eines Parameters überladen werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-610">Members can be overloaded based on the number of parameters and the type of any parameter.</span></span> <span data-ttu-id="7d228-611">Aufrufkonvention, Rückgabetyp, die benutzerdefinierten Modifizierer, die auf die Methode oder deren Parameter angewendet werden und, ob Parameter nach Wert oder nach Verweis übergeben werden, werden bei der Unterscheidung zwischen Überladungen nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="7d228-611">Calling convention, return type, custom modifiers applied to the method or its parameter, and whether parameters are passed by value or by reference are not considered when differentiating between overloads.</span></span> <span data-ttu-id="7d228-612">Ein Beispiel finden Sie im Abschnitt [Namenskonventionen](#naming-conventions) im Code für die Anforderung, dass Namen innerhalb eines Bereichs eindeutig sein müssen.</span><span class="sxs-lookup"><span data-stu-id="7d228-612">For an example, see the code for the requirement that names must be unique within a scope in the [Naming conventions](#naming-conventions) section.</span></span>

* <span data-ttu-id="7d228-613">Nur Eigenschaften und Methoden können überladen werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-613">Only properties and methods can be overloaded.</span></span> <span data-ttu-id="7d228-614">Felder und Ereignisse können nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-614">Fields and events cannot be overloaded.</span></span>

* <span data-ttu-id="7d228-615">Generische Methoden können auf Grundlage der Anzahl ihrer generischen Parameter überladen werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-615">Generic methods can be overloaded based on the number of their generic parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="7d228-616">Der `op_Explicit`-Operator und der `op_Implicit`-Operator sind Ausnahmen von der Regel, dass Rückgabewerte nicht als Teil einer Methodensignatur für Überladungsauflösung gelten.</span><span class="sxs-lookup"><span data-stu-id="7d228-616">The `op_Explicit` and `op_Implicit` operators are exceptions to the rule that return value is not considered part of a method signature for overload resolution.</span></span> <span data-ttu-id="7d228-617">Diese beiden Operatoren können auf Grundlage ihrer Parameter und ihrer Rückgabewerte überladen werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-617">These two operators can be overloaded based on both their parameters and their return value.</span></span>

### <a name="exceptions"></a><span data-ttu-id="7d228-618">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="7d228-618">Exceptions</span></span>

<span data-ttu-id="7d228-619">Ausnahmeobjekte müssen von [System.Exception](xref:System.Exception) oder von einem anderen Typ abgeleitet werden, der von `System.Exception` abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="7d228-619">Exception objects must derive from [System.Exception](xref:System.Exception) or from another type derived from `System.Exception`.</span></span> <span data-ttu-id="7d228-620">Im folgenden Beispiel wird der Compilerfehler veranschaulicht, der entsteht, wenn eine benutzerdefinierte Klasse namens `ErrorClass` für die Ausnahmebehandlung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d228-620">The following example illustrates the compiler error that results when a custom class named `ErrorClass` is used for exception handling.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
// Compilation produces a compiler error like the following:
//    Exceptions1.cs(26,16): error CS0155: The type caught or thrown must be derived from
//            System.Exception
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
' Compilation produces a compiler error like the following:
'    Exceptions1.vb(27) : error BC30665: 'Throw' operand must derive from 'System.Exception'.
'
'             Throw BadIndex
'             ~~~~~~~~~~~~~~
```

<span data-ttu-id="7d228-621">Um diesen Fehler zu beheben, muss die `ErrorClass`-Klasse von `System.Exception` erben.</span><span class="sxs-lookup"><span data-stu-id="7d228-621">To correct this error, the `ErrorClass` class must inherit from `System.Exception`.</span></span> <span data-ttu-id="7d228-622">Außerdem muss die Message-Eigenschaft außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-622">In addition, the Message property must be overridden.</span></span> <span data-ttu-id="7d228-623">Im folgenden Beispiel werden diese Fehler korrigiert, um eine CLS-kompatible `ErrorClass`-Klasse zu definieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-623">The following example corrects these errors to define an `ErrorClass` class that is CLS-compliant.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass : Exception
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public override string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass : Inherits Exception
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public Overrides ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
```

### <a name="attributes"></a><span data-ttu-id="7d228-624">Attribute</span><span class="sxs-lookup"><span data-stu-id="7d228-624">Attributes</span></span>

<span data-ttu-id="7d228-625">In .NET-Assemblys stellen benutzerdefinierte Attribute einen erweiterbaren Mechanismus zum Speichern benutzerdefinierter Attribute und zum Abrufen von Metadaten über Programmierobjekte wie Assemblys, Typen, Member und Methodenparameter bereit.</span><span class="sxs-lookup"><span data-stu-id="7d228-625">In .NET assemblies, custom attributes provide an extensible mechanism for storing custom attributes and retrieving metadata about programming objects, such as assemblies, types, members, and method parameters.</span></span> <span data-ttu-id="7d228-626">Benutzerdefinierte Attribute müssen von [System.Attribute](xref:System.Attribute) oder einem Typ abgeleitet werden, der von `System.Attribute` abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="7d228-626">Custom attributes must derive from [System.Attribute](xref:System.Attribute) or from a type derived from `System.Attribute`.</span></span>

<span data-ttu-id="7d228-627">Das folgende Beispiel verstößt gegen diese Regel.</span><span class="sxs-lookup"><span data-stu-id="7d228-627">The following example violates this rule.</span></span> <span data-ttu-id="7d228-628">Es wird eine `NumericAttribute`-Klasse definiert, die nicht von `System.Attribute` abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-628">It defines a `NumericAttribute` class that does not derive from `System.Attribute`.</span></span> <span data-ttu-id="7d228-629">Ein Compilerfehler entsteht nur, wenn das nicht CLS-kompatible Attribut angewendet wird, nicht aber, wenn die Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-629">A compiler error results only when the non-CLS-compliant attribute is applied, not when the class is defined.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

[AttributeUsageAttribute(AttributeTargets.Class | AttributeTargets.Struct)]
public class NumericAttribute
{
   private bool _isNumeric;

   public NumericAttribute(bool isNumeric)
   {
      _isNumeric = isNumeric;
   }

   public bool IsNumeric
   {
      get { return _isNumeric; }
   }
}

[Numeric(true)] public struct UDouble
{
   double Value;
}
// Compilation produces a compiler error like the following:
//    Attribute1.cs(22,2): error CS0616: 'NumericAttribute' is not an attribute class
//    Attribute1.cs(7,14): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

<AttributeUsageAttribute(AttributeTargets.Class Or AttributeTargets.Struct)> _
Public Class NumericAttribute
   Private _isNumeric As Boolean

   Public Sub New(isNumeric As Boolean)
      _isNumeric = isNumeric
   End Sub

   Public ReadOnly Property IsNumeric As Boolean
      Get
         Return _isNumeric
      End Get
   End Property
End Class

<Numeric(True)> Public Structure UDouble
   Dim Value As Double
End Structure
' Compilation produces a compiler error like the following:
'    error BC31504: 'NumericAttribute' cannot be used as an attribute because it
'    does not inherit from 'System.Attribute'.
'
'    <Numeric(True)> Public Structure UDouble
'     ~~~~~~~~~~~~~
```

<span data-ttu-id="7d228-630">Der Konstruktor oder die Eigenschaften eines CLS-kompatiblen Attributs können nur die folgenden Typen verfügbar machen:</span><span class="sxs-lookup"><span data-stu-id="7d228-630">The constructor or the properties of a CLS-compliant attribute can expose only the following types:</span></span>

* [<span data-ttu-id="7d228-631">Boolean</span><span class="sxs-lookup"><span data-stu-id="7d228-631">Boolean</span></span>](xref:System.Boolean)

* [<span data-ttu-id="7d228-632">Byte</span><span class="sxs-lookup"><span data-stu-id="7d228-632">Byte</span></span>](xref:System.Byte)

* [<span data-ttu-id="7d228-633">Char</span><span class="sxs-lookup"><span data-stu-id="7d228-633">Char</span></span>](xref:System.Char)

* [<span data-ttu-id="7d228-634">Double</span><span class="sxs-lookup"><span data-stu-id="7d228-634">Double</span></span>](xref:System.Double)

* [<span data-ttu-id="7d228-635">Int16</span><span class="sxs-lookup"><span data-stu-id="7d228-635">Int16</span></span>](xref:System.Int16)

* [<span data-ttu-id="7d228-636">Int32</span><span class="sxs-lookup"><span data-stu-id="7d228-636">Int32</span></span>](xref:System.Int32)

* [<span data-ttu-id="7d228-637">Int64</span><span class="sxs-lookup"><span data-stu-id="7d228-637">Int64</span></span>](xref:System.Int64)

* [<span data-ttu-id="7d228-638">Single</span><span class="sxs-lookup"><span data-stu-id="7d228-638">Single</span></span>](xref:System.Single)

* [<span data-ttu-id="7d228-639">String</span><span class="sxs-lookup"><span data-stu-id="7d228-639">String</span></span>](xref:System.String)

* [<span data-ttu-id="7d228-640">Type</span><span class="sxs-lookup"><span data-stu-id="7d228-640">Type</span></span>](xref:System.Type)

* <span data-ttu-id="7d228-641">Ein Enumerationstyp, dessen zugrunde liegender Typ `Byte`, `Int16`, `Int32` oder `Int64` ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-641">Any enumeration type whose underlying type is `Byte`, `Int16`, `Int32`, or `Int64`.</span></span>

<span data-ttu-id="7d228-642">Im folgenden Beispiel wird eine von [Attribute](xref:System.Attribute) abgeleitete `DescriptionAttribute`-Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="7d228-642">The following example defines a `DescriptionAttribute` class that derives from [Attribute](xref:System.Attribute).</span></span> <span data-ttu-id="7d228-643">Der Klassenkonstruktor verfügt über einen Parameter des Typs `Descriptor`, sodass die Klasse nicht CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-643">The class constructor has a parameter of type `Descriptor`, so the class is not CLS-compliant.</span></span> <span data-ttu-id="7d228-644">Beachten Sie, dass der C#-Compiler eine Warnung ausgibt, die Kompilierung aber erfolgreich durchführt.</span><span class="sxs-lookup"><span data-stu-id="7d228-644">The C# compiler emits a warning but compiles successfully.</span></span>

```csharp
using System;

[assembly:CLSCompliantAttribute(true)]

public enum DescriptorType { type, member };

public class Descriptor
{
   public DescriptorType Type;
   public String Description;
}

[AttributeUsage(AttributeTargets.All)]
public class DescriptionAttribute : Attribute
{
   private Descriptor desc;

   public DescriptionAttribute(Descriptor d)
   {
      desc = d;
   }

   public Descriptor Descriptor
   { get { return desc; } }
}
// Attempting to compile the example displays output like the following:
//       warning CS3015: 'DescriptionAttribute' has no accessible
//               constructors which use only CLS-compliant types
```

```vb
<Assembly:CLSCompliantAttribute(True)>

Public Enum DescriptorType As Integer
   Type = 0
   Member = 1
End Enum

Public Class Descriptor
   Public Type As DescriptorType
   Public Description As String
End Class

<AttributeUsage(AttributeTargets.All)> _
Public Class DescriptionAttribute : Inherits Attribute
   Private desc As Descriptor

   Public Sub New(d As Descriptor)
      desc = d
   End Sub

   Public ReadOnly Property Descriptor As Descriptor
      Get
         Return desc
      End Get
   End Property
End Class
```

## <a name="the-clscompliantattribute-attribute"></a><span data-ttu-id="7d228-645">Das CLSCompliantAttribute-Attribut</span><span class="sxs-lookup"><span data-stu-id="7d228-645">The CLSCompliantAttribute attribute</span></span>

<span data-ttu-id="7d228-646">Das [CLSCompliantAttribute](xref:System.CLSCompliantAttribute)-Attribut wird verwendet, um anzugeben, ob ein Programmelement mit der Common Language Specification kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-646">The [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute is used to indicate whether a program element complies with the Common Language Specification.</span></span> <span data-ttu-id="7d228-647">Der `CLSCompliantAttribute.CLSCompliantAttribute(Boolean)`-Konstruktor enthält einen einzelnen erforderlichen Parameter, *isCompliant*, der angibt, ob das Programmelement CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="7d228-647">The `CLSCompliantAttribute.CLSCompliantAttribute(Boolean)` constructor includes a single required parameter, *isCompliant*, that indicates whether the program element is CLS-compliant.</span></span>

<span data-ttu-id="7d228-648">Zur Kompilierzeit erkennt der Compiler nicht kompatible Elemente, von denen angenommen wird, dass sie CLS-kompatibel sind, und gibt eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="7d228-648">At compile time, the compiler detects non-compliant elements that are presumed to be CLS-compliant and emits a warning.</span></span> <span data-ttu-id="7d228-649">Der Compiler gibt keine Warnungen für die Typen oder Member aus, die explizit als nicht kompatibel deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-649">The compiler does not emit warnings for types or members that are explicitly declared to be non-compliant.</span></span>

<span data-ttu-id="7d228-650">Komponentenentwickler können das `CLSCompliantAttribute`-Attribut auf zwei Arten verwenden:</span><span class="sxs-lookup"><span data-stu-id="7d228-650">Component developers can use the `CLSCompliantAttribute` attribute in two ways:</span></span>

* <span data-ttu-id="7d228-651">Um die Teile der öffentlichen Schnittstelle zu definieren, die von einer CLS-kompatiblen Komponente und den nicht CLS-kompatiblen Teilen verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-651">To define the parts of the public interface exposed by a component that are CLS-compliant and the parts that are not CLS-compliant.</span></span> <span data-ttu-id="7d228-652">Wenn das Attribut verwendet wird, um bestimmte Programmelemente als CLS-kompatibel zu markieren, stellt seine Verwendung sicher, dass auf diese Elemente aus allen Sprachen und Tools zugegriffen werden kann, die auf .NET ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="7d228-652">When the attribute is used to mark particular program elements as CLS-compliant, its use guarantees that those elements are accessible from all languages and tools that target .NET.</span></span>

* <span data-ttu-id="7d228-653">Um sicherzustellen, dass die öffentliche Schnittstelle der Komponentenbibliothek nur Programmelemente verfügbar macht, die CLS-kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="7d228-653">To ensure that the component library's public interface exposes only program elements that are CLS-compliant.</span></span> <span data-ttu-id="7d228-654">Wenn Elemente nicht CLS-kompatibel sind, geben Compiler im Allgemeinen eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="7d228-654">If elements are not CLS-compliant, compilers will generally issue a warning.</span></span>

> [!WARNING]
> <span data-ttu-id="7d228-655">In einigen Fällen erzwingen CLS-kompatible Sprachcompiler Regeln unabhängig davon, ob das `CLSCompliantAttribute`-Attribut verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d228-655">In some cases, language compilers enforce CLS-compliant rules regardless of whether the `CLSCompliantAttribute` attribute is used.</span></span> <span data-ttu-id="7d228-656">Das Definieren eines `*static`-Members in einer Schnittstelle verstößt zum Beispiel gegen eine CLS-Regel.</span><span class="sxs-lookup"><span data-stu-id="7d228-656">For example, defining a `*static` member in an interface violates a CLS rule.</span></span> <span data-ttu-id="7d228-657">Wenn Sie jedoch einen `*static`-Member in einer Schnittstelle definieren, zeigt der C#-Compiler eine Fehlermeldung an, und beim Kompilieren der App tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="7d228-657">However, if you define a `*static` member in an interface, the C# compiler displays an error message and fails to compile the app.</span></span>

<span data-ttu-id="7d228-658">Das `CLSCompliantAttribute`-Attribut wird mit einem [AttributeUsageAttribute](xref:System.AttributeUsageAttribute)-Attribut markiert, das einen Wert von `AttributeTargets.All` aufweist.</span><span class="sxs-lookup"><span data-stu-id="7d228-658">The `CLSCompliantAttribute` attribute is marked with an [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) attribute that has a value of `AttributeTargets.All`.</span></span> <span data-ttu-id="7d228-659">Dieser Wert ermöglicht das Anwenden des `CLSCompliantAttribute`-Attributs auf jedem Programmelement, einschließlich Assemblys, Modulen, Typen (Klassen, Strukturen, Enumerationen, Schnittstellen und Delegaten), Typmembern (Konstruktoren, Methoden, Eigenschaften, Feldern und Ereignissen), Parametern, generischen Parametern und Rückgabewerten.</span><span class="sxs-lookup"><span data-stu-id="7d228-659">This value allows you to apply the `CLSCompliantAttribute` attribute to any program element, including assemblies, modules, types (classes, structures, enumerations, interfaces, and delegates), type members (constructors, methods, properties, fields, and events), parameters, generic parameters, and return values.</span></span> <span data-ttu-id="7d228-660">In der Praxis sollten Sie das Attribut allerdings nur auf Assemblys, Typen und Typmember anwenden.</span><span class="sxs-lookup"><span data-stu-id="7d228-660">However, in practice, you should apply the attribute only to assemblies, types, and type members.</span></span> <span data-ttu-id="7d228-661">Andernfalls ignorieren Compiler das Attribut und generieren weiterhin Compilerwarnungen, wenn sie einen nicht kompatiblen Parameter, einen generischen Parameter oder einen Rückgabewert in der öffentlichen Schnittstelle der Bibliothek vorfinden.</span><span class="sxs-lookup"><span data-stu-id="7d228-661">Otherwise, compilers ignore the attribute and continue to generate compiler warnings whenever they encounter a non-compliant parameter, generic parameter, or return value in your library's public interface.</span></span>

<span data-ttu-id="7d228-662">Der Wert des `CLSCompliantAttribute`-Attributs wird von enthaltenen Programmelementen geerbt.</span><span class="sxs-lookup"><span data-stu-id="7d228-662">The value of the `CLSCompliantAttribute` attribute is inherited by contained program elements.</span></span> <span data-ttu-id="7d228-663">Wenn beispielsweise eine Assembly als CLS-kompatibel markiert ist, sind die Typen auch CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-663">For example, if an assembly is marked as CLS-compliant, its types are also CLS-compliant.</span></span> <span data-ttu-id="7d228-664">Wenn ein Typ als CLS-kompatibel gekennzeichnet ist, sind seine geschachtelten Typen und Member auch CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-664">If a type is marked as CLS-compliant, its nested types and members are also CLS-compliant.</span></span>

<span data-ttu-id="7d228-665">Sie können die geerbte Kompatibilität explizit überschreiben, indem Sie das `CLSCompliantAttribute`- Attribut auf ein enthaltenes Programmelement anwenden.</span><span class="sxs-lookup"><span data-stu-id="7d228-665">You can explicitly override the inherited compliance by applying the `CLSCompliantAttribute` attribute to a contained program element.</span></span> <span data-ttu-id="7d228-666">Beispielsweise können Sie das `CLSCompliantAttribute`-Attribut mit einem *isCompliant*-Wert von `false` verwenden, um einen inkompatiblen Typ in einer kompatiblen Assembly zu definieren, und Sie können das Attribut mit einem *isCompliant*-Wert von `true` verwenden, um einen kompatiblen Typ in einer inkompatiblen Assembly zu definieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-666">For example, you can use the `CLSCompliantAttribute` attribute with an *isCompliant* value of `false` to define a non-compliant type in a compliant assembly, and you can use the attribute with an *isCompliant* value of `true` to define a compliant type in a non-compliant assembly.</span></span> <span data-ttu-id="7d228-667">Sie können auch nicht kompatible Member in einem kompatiblen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-667">You can also define non-compliant members in a compliant type.</span></span> <span data-ttu-id="7d228-668">Allerdings kann ein nicht kompatibler Typ keine kompatiblen Member aufweisen, sodass Sie das Attribut nicht mit einem *isCompliant*-Wert von `true` verwenden können, um die Vererbung eines nicht kompatiblen Typs zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="7d228-668">However, a non-compliant type cannot have compliant members, so you cannot use the attribute with an *isCompliant* value of `true` to override inheritance from a non-compliant type.</span></span>

<span data-ttu-id="7d228-669">Wenn Sie Komponenten entwickeln, sollten Sie stets das `CLSCompliantAttribute`- Attribut verwenden, um anzugeben, ob die Assembly, die Typen und die Member CLS-kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="7d228-669">When you are developing components, you should always use the `CLSCompliantAttribute` attribute to indicate whether your assembly, its types, and its members are CLS-compliant.</span></span>

<span data-ttu-id="7d228-670">So erstellen Sie CLS-kompatible Komponenten:</span><span class="sxs-lookup"><span data-stu-id="7d228-670">To create CLS-compliant components:</span></span>

1. <span data-ttu-id="7d228-671">Verwenden Sie `CLSCompliantAttribute`, um die Assembly als CLS-kompatibel zu markieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-671">Use the `CLSCompliantAttribute` to mark you assembly as CLS-compliant.</span></span>

2. <span data-ttu-id="7d228-672">Markieren Sie jeden öffentlich verfügbar gemachten, nicht CLS-kompatiblen Typ in der Assembly als nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-672">Mark any publicly exposed types in the assembly that are not CLS-compliant as non-compliant.</span></span>

3. <span data-ttu-id="7d228-673">Markieren Sie alle öffentlich verfügbar gemachten Member in CLS-kompatiblen Typen als nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7d228-673">Mark any publicly exposed members in CLS-compliant types as non-compliant.</span></span>

4. <span data-ttu-id="7d228-674">Stellen Sie eine CLS-kompatible Alternative für nicht CLS-kompatible Member bereit.</span><span class="sxs-lookup"><span data-stu-id="7d228-674">Provide a CLS-compliant alternative for non-CLS-compliant members.</span></span>

<span data-ttu-id="7d228-675">Wenn alle inkompatiblen Typen und Member erfolgreich markiert wurden, sollte der Compiler keine Kompatibilitätswarnungen ausgeben.</span><span class="sxs-lookup"><span data-stu-id="7d228-675">If you've successfully marked all your non-compliant types and members, your compiler should not emit any non-compliance warnings.</span></span> <span data-ttu-id="7d228-676">Allerdings sollten Sie angeben, welche Member nicht CLS-kompatibel sind und ihre CLS-kompatiblen Alternativen in der Produktdokumentation aufführen.</span><span class="sxs-lookup"><span data-stu-id="7d228-676">However, you should indicate which members are not CLS-compliant and list their CLS-compliant alternatives in your product documentation.</span></span>

<span data-ttu-id="7d228-677">Im folgenden Beispiel wird das `CLSCompliantAttribute`-Attribut verwendet, um eine CLS-kompatible Assembly und einen Typ, `CharacterUtilities`, zu definieren, der über zwei nicht CLS-kompatible Member verfügt.</span><span class="sxs-lookup"><span data-stu-id="7d228-677">The following example uses the `CLSCompliantAttribute` attribute to define a CLS-compliant assembly and a type, `CharacterUtilities`, that has two non-CLS-compliant members.</span></span> <span data-ttu-id="7d228-678">Da beide Member mit dem `CLSCompliant(false)`-Attribut markiert sind, generiert der Compiler keine Warnungen.</span><span class="sxs-lookup"><span data-stu-id="7d228-678">Because both members are tagged with the `CLSCompliant(false)` attribute, the compiler produces no warnings.</span></span> <span data-ttu-id="7d228-679">Die Klasse stellt auch eine CLS-kompatible Alternative für beide Methoden bereit.</span><span class="sxs-lookup"><span data-stu-id="7d228-679">The class also provides a CLS-compliant alternative for both methods.</span></span> <span data-ttu-id="7d228-680">Normalerweise würden der `ToUTF16`- Methode lediglich zwei Überladungen hinzugefügt werden, um CLS-kompatible Alternativen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7d228-680">Ordinarily, we would just add two overloads to the `ToUTF16` method to provide CLS-compliant alternatives.</span></span> <span data-ttu-id="7d228-681">Da Methoden aber nicht aufgrund des Rückgabewerts überladen werden können, sind die Namen der CLS-kompatiblen Methoden von den Namen der nicht kompatiblen Methoden unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="7d228-681">However, because methods cannot be overloaded based on return value, the names of the CLS-compliant methods are different from the names of the non-compliant methods.</span></span>

```csharp
using System;
using System.Text;

[assembly:CLSCompliant(true)]

public class CharacterUtilities
{
   [CLSCompliant(false)] public static ushort ToUTF16(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return Convert.ToUInt16(s[0]);
   }

   [CLSCompliant(false)] public static ushort ToUTF16(Char ch)
   {
      return Convert.ToUInt16(ch);
   }

   // CLS-compliant alternative for ToUTF16(String).
   public static int ToUTF16CodeUnit(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return (int) Convert.ToUInt16(s[0]);
   }

   // CLS-compliant alternative for ToUTF16(Char).
   public static int ToUTF16CodeUnit(Char ch)
   {
      return Convert.ToInt32(ch);
   }

   public bool HasMultipleRepresentations(String s)
   {
      String s1 = s.Normalize(NormalizationForm.FormC);
      return s.Equals(s1);
   }

   public int GetUnicodeCodePoint(Char ch)
   {
      if (Char.IsSurrogate(ch))
         throw new ArgumentException("ch cannot be a high or low surrogate.");

      return Char.ConvertToUtf32(ch.ToString(), 0);
   }

   public int GetUnicodeCodePoint(Char[] chars)
   {
      if (chars.Length > 2)
         throw new ArgumentException("The array has too many characters.");

      if (chars.Length == 2) {
         if (! Char.IsSurrogatePair(chars[0], chars[1]))
            throw new ArgumentException("The array must contain a low and a high surrogate.");
         else
            return Char.ConvertToUtf32(chars[0], chars[1]);
      }
      else {
         return Char.ConvertToUtf32(chars.ToString(), 0);
      }
   }
}
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class CharacterUtilities
   <CLSCompliant(False)> Public Shared Function ToUTF16(s As String) As UShort
      s = s.Normalize(NormalizationForm.FormC)
      Return Convert.ToUInt16(s(0))
   End Function

   <CLSCompliant(False)> Public Shared Function ToUTF16(ch As Char) As UShort
      Return Convert.ToUInt16(ch)
   End Function

   ' CLS-compliant alternative for ToUTF16(String).
   Public Shared Function ToUTF16CodeUnit(s As String) As Integer
      s = s.Normalize(NormalizationForm.FormC)
      Return CInt(Convert.ToInt16(s(0)))
   End Function

   ' CLS-compliant alternative for ToUTF16(Char).
   Public Shared Function ToUTF16CodeUnit(ch As Char) As Integer
      Return Convert.ToInt32(ch)
   End Function

   Public Function HasMultipleRepresentations(s As String) As Boolean
      Dim s1 As String = s.Normalize(NormalizationForm.FormC)
      Return s.Equals(s1)
   End Function

   Public Function GetUnicodeCodePoint(ch As Char) As Integer
      If Char.IsSurrogate(ch) Then
         Throw New ArgumentException("ch cannot be a high or low surrogate.")
      End If
      Return Char.ConvertToUtf32(ch.ToString(), 0)
   End Function

   Public Function GetUnicodeCodePoint(chars() As Char) As Integer
      If chars.Length > 2 Then
         Throw New ArgumentException("The array has too many characters.")
      End If
      If chars.Length = 2 Then
         If Not Char.IsSurrogatePair(chars(0), chars(1)) Then
            Throw New ArgumentException("The array must contain a low and a high surrogate.")
         Else
            Return Char.ConvertToUtf32(chars(0), chars(1))
         End If
      Else
         Return Char.ConvertToUtf32(chars.ToString(), 0)
      End If
   End Function
End Class
```

<span data-ttu-id="7d228-682">Wenn Sie eine App anstelle einer Bibliothek entwickeln, (das heißt, wenn Sie keine Typen oder Member verfügbar machen, die von anderen App-Entwicklern genutzt werden können), ist die CLS-Kompatibilität der Programmelemente, die von der App genutzt werden, nur relevant, wenn sie von Ihrer Sprache nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7d228-682">If you are developing an app rather than a library (that is, if you aren't exposing types or members that can be consumed by other app developers), the CLS compliance of the program elements that your app consumes are of interest only if your language does not support them.</span></span> <span data-ttu-id="7d228-683">In diesem Fall generiert der Sprachcompiler einen Fehler, wenn Sie versuchen, ein nicht CLS-kompatibles Element zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d228-683">In that case, your language compiler will generate an error when you try to use a non-CLS-compliant element.</span></span>

## <a name="cross-language-interoperability"></a><span data-ttu-id="7d228-684">Sprachübergreifende Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="7d228-684">Cross-language interoperability</span></span>

<span data-ttu-id="7d228-685">Der Begriff „Sprachunabhängigkeit“ kann mehrere Bedeutungen haben.</span><span class="sxs-lookup"><span data-stu-id="7d228-685">Language independence has a number of possible meanings.</span></span> <span data-ttu-id="7d228-686">Eine Bedeutung umfasst die nahtlose Nutzung von Typen, die in einer Sprache geschrieben werden, in einer App, die in einer anderen Sprache geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="7d228-686">One meaning involves seamlessly consuming types written in one language from an app written in another language.</span></span> <span data-ttu-id="7d228-687">Eine zweite Bedeutung, die in diesem Artikel hervorgehoben wird, umfasst die Kombination von Code aus mehreren Sprachen in einer einzelnen .NET-Assembly.</span><span class="sxs-lookup"><span data-stu-id="7d228-687">A second meaning, which is the focus of this article, involves combining code written in multiple languages into a single .NET assembly.</span></span>

<span data-ttu-id="7d228-688">Das folgende Beispiel veranschaulicht die sprachübergreifende Interoperabilität. Es wird die Klassenbibliothek Utilities.dll erstellt, die zwei Klassen einschließt: `NumericLib` und `StringLib`.</span><span class="sxs-lookup"><span data-stu-id="7d228-688">The following example illustrates cross-language interoperability by creating a class library named Utilities.dll that includes two classes, `NumericLib` and `StringLib`.</span></span> <span data-ttu-id="7d228-689">Die `NumericLib`-Klasse wurde in C# und die `StringLib`-Klasse in Visual Basic geschrieben.</span><span class="sxs-lookup"><span data-stu-id="7d228-689">The `NumericLib` class is written in C#, and the `StringLib` class is written in Visual Basic.</span></span> <span data-ttu-id="7d228-690">Im Folgenden sehen Sie den Quellcode für `StringUtil.vb`, der in der `StringLib`-Klasse einen einzelnen Member `ToTitleCase` enthält.</span><span class="sxs-lookup"><span data-stu-id="7d228-690">Here's the source code for `StringUtil.vb`, which includes a single member, `ToTitleCase`, in its `StringLib` class.</span></span>

```vb
Imports System.Collections.Generic
Imports System.Runtime.CompilerServices

Public Module StringLib
   Private exclusions As List(Of String)

   Sub New()
      Dim words() As String = { "a", "an", "and", "of", "the" }
      exclusions = New List(Of String)
      exclusions.AddRange(words)
   End Sub

   <Extension()> _
   Public Function ToTitleCase(title As String) As String
      Dim words() As String = title.Split()
      Dim result As String = String.Empty

      For ctr As Integer = 0 To words.Length - 1
         Dim word As String = words(ctr)
         If ctr = 0 OrElse Not exclusions.Contains(word.ToLower()) Then
            result += word.Substring(0, 1).ToUpper() + _
                      word.Substring(1).ToLower()
         Else
            result += word.ToLower()
         End If
         If ctr <= words.Length - 1 Then
            result += " "
         End If
      Next
      Return result
   End Function
End Module
```

<span data-ttu-id="7d228-691">Im Folgenden sehen Sie den Quellcode für "NumberUtil.cs", der eine `NumericLib`-Klasse mit zwei Membern definiert: `IsEven` und `NearZero`.</span><span class="sxs-lookup"><span data-stu-id="7d228-691">Here's the source code for NumberUtil.cs, which defines a `NumericLib` class that has two members, `IsEven` and `NearZero`.</span></span>

```csharp
using System;

public static class NumericLib
{
   public static bool IsEven(this IConvertible number)
   {
      if (number is Byte ||
          number is SByte ||
          number is Int16 ||
          number is UInt16 ||
          number is Int32 ||
          number is UInt32 ||
          number is Int64)
         return ((long) number) % 2 == 0;
      else if (number is UInt64)
         return ((ulong) number) %2 == 0;
      else
         throw new NotSupportedException("IsEven called for a non-integer value.");
   }

   public static bool NearZero(double number)
   {
      return number < .00001;
   }
}
```

<span data-ttu-id="7d228-692">Um die beiden Klassen in einer einzelnen Assembly zu verpacken, müssen Sie sie in Module kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7d228-692">To package the two classes in a single assembly, you must compile them into modules.</span></span> <span data-ttu-id="7d228-693">Verwenden Sie zum Kompilieren der Visual Basic-Quellcodedatei in einem Modul folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="7d228-693">To compile the Visual Basic source code file into a module, use this command:</span></span>

```console
vbc /t:module StringUtil.vb
```

<span data-ttu-id="7d228-694">Verwenden Sie zum Kompilieren der C#-Quellcodedatei in einem Modul folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="7d228-694">To compile the C# source code file into a module, use this command:</span></span>

```console
csc /t:module NumberUtil.cs
```

<span data-ttu-id="7d228-695">Verwenden Sie dann das Linktool (Link.exe), um die beiden Module in eine Assembly zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="7d228-695">You then use the Link tool (Link.exe) to compile the two modules into an assembly:</span></span>

```console
link numberutil.netmodule stringutil.netmodule /out:UtilityLib.dll /dll
```

<span data-ttu-id="7d228-696">Das folgende Beispiel ruft dann die `NumericLib.NearZero`-Methode und die `StringLib.ToTitleCase`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="7d228-696">The following example then calls the `NumericLib.NearZero` and `StringLib.ToTitleCase` methods.</span></span> <span data-ttu-id="7d228-697">Beachten Sie, dass sowohl der Visual Basic- als auch C#-Code auf die Methoden in beiden Klassen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="7d228-697">Both the Visual Basic code and the C# code are able to access the methods in both classes.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      Double dbl = 0.0 - Double.Epsilon;
      Console.WriteLine(NumericLib.NearZero(dbl));

      string s = "war and peace";
      Console.WriteLine(s.ToTitleCase());
   }
}
// The example displays the following output:
//       True
//       War and Peace
```

```vb
Module Example
   Public Sub Main()
      Dim dbl As Double = 0.0 - Double.Epsilon
      Console.WriteLine(NumericLib.NearZero(dbl))

      Dim s As String = "war and peace"
      Console.WriteLine(s.ToTitleCase())
   End Sub
End Module
' The example displays the following output:
'       True
'       War and Peace
```

<span data-ttu-id="7d228-698">Verwenden Sie zum Kompilieren des Visual Basic-Codes folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="7d228-698">To compile the Visual Basic code, use this command:</span></span>

```console
vbc example.vb /r:UtilityLib.dll
```

<span data-ttu-id="7d228-699">Zum Kompilieren mit C# ändern Sie den Namen des Compilers von vbc in csc und die Dateierweiterung von „.vb“ in „.cs“:</span><span class="sxs-lookup"><span data-stu-id="7d228-699">To compile with C#, change the name of the compiler from vbc to csc, and change the file extension from .vb to .cs:</span></span>

```console
csc example.cs /r:UtilityLib.dll
```
