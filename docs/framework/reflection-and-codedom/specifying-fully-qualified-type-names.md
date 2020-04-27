---
title: Angeben vollständig gekennzeichneter Typnamen
ms.date: 02/21/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- reflection, fully qualified type names
- names [.NET Framework], assemblies
- tokens
- BNF
- assemblies [.NET Framework], names
- languages, grammar
- fully qualified type names
- type names
- special characters
- IDENTIFIER
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
ms.openlocfilehash: 707c71482196d789ed9a88db34af048ec57734fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130033"
---
# <a name="specifying-fully-qualified-type-names"></a><span data-ttu-id="c33e1-102">Angeben vollqualifizierter Typnamen</span><span class="sxs-lookup"><span data-stu-id="c33e1-102">Specifying fully qualified type names</span></span>

<span data-ttu-id="c33e1-103">Sie müssen Typnamen angeben, um eine gültige Eingabe für verschiedene Reflektionsvorgänge zu haben.</span><span class="sxs-lookup"><span data-stu-id="c33e1-103">You must specify type names to have valid input to various reflection operations.</span></span> <span data-ttu-id="c33e1-104">Ein vollqualifizierter Typname besteht aus der Angabe eines Assemblynamens, eines Namespaces und eines Typnamens.</span><span class="sxs-lookup"><span data-stu-id="c33e1-104">A fully qualified type name consists of an assembly name specification, a namespace specification, and a type name.</span></span> <span data-ttu-id="c33e1-105">Angaben von Typnamen werden von Methoden wie <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> und <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> verwendet.</span><span class="sxs-lookup"><span data-stu-id="c33e1-105">Type name specifications are used by methods such as <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>, and <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span></span>

## <a name="grammar-for-type-names"></a><span data-ttu-id="c33e1-106">Grammatik für Typnamen</span><span class="sxs-lookup"><span data-stu-id="c33e1-106">Grammar for type names</span></span>

 <span data-ttu-id="c33e1-107">Die Grammatik definiert die Syntax formaler Sprachen.</span><span class="sxs-lookup"><span data-stu-id="c33e1-107">The grammar defines the syntax of formal languages.</span></span> <span data-ttu-id="c33e1-108">In der folgenden Tabelle werden lexikalische Regeln aufgelistet, die angeben, wie Sie eine gültige Eingabe erkennen können.</span><span class="sxs-lookup"><span data-stu-id="c33e1-108">The following table lists lexical rules that describe how to recognize a valid input.</span></span> <span data-ttu-id="c33e1-109">Terminale (diejenigen Elemente, die nicht weiter reduziert werden können) werden in Großbuchstaben dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c33e1-109">Terminals (those elements that are not further reducible) are shown in all uppercase letters.</span></span> <span data-ttu-id="c33e1-110">Nichtterminale (diejenigen Elemente, die noch weiter reduziert werden können) werden in Groß- und Kleinbuchstaben oder durch Zeichenfolgen in einfachen Anführungszeichen dargestellt. Dabei ist das einfache Anführungszeichen (') nicht Teil der Syntax.</span><span class="sxs-lookup"><span data-stu-id="c33e1-110">Nonterminals (those elements that are further reducible) are shown in mixed-case or singly quoted strings, but the single quote (') is not a part of the syntax itself.</span></span> <span data-ttu-id="c33e1-111">Das Pipezeichen (&#124;) kennzeichnet Regeln mit Unterregeln.</span><span class="sxs-lookup"><span data-stu-id="c33e1-111">The pipe character (&#124;) denotes rules that have subrules.</span></span>

<!-- markdownlint-disable MD010 -->
```antlr
TypeSpec
    : ReferenceTypeSpec
    | SimpleTypeSpec
    ;

ReferenceTypeSpec
    : SimpleTypeSpec '&'
    ;

SimpleTypeSpec
    : PointerTypeSpec
    | GenericTypeSpec
    | TypeName
    ;

GenericTypeSpec
   : SimpleTypeSpec ` NUMBER

PointerTypeSpec
    : SimpleTypeSpec '*'
    ;

ArrayTypeSpec
    : SimpleTypeSpec '[ReflectionDimension]'
    | SimpleTypeSpec '[ReflectionEmitDimension]'
    ;

ReflectionDimension
    : '*'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

ReflectionEmitDimension
    : '*'
    | Number '..' Number
    | Number '…'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

Number
    : [0-9]+
    ;

TypeName
    : NamespaceTypeName
    | NamespaceTypeName ',' AssemblyNameSpec
    ;

NamespaceTypeName
    : NestedTypeName
    | NamespaceSpec '.' NestedTypeName
    ;

NestedTypeName
    : IDENTIFIER
    | NestedTypeName '+' IDENTIFIER
    ;

NamespaceSpec
    : IDENTIFIER
    | NamespaceSpec '.' IDENTIFIER
    ;

AssemblyNameSpec
    : IDENTIFIER
    | IDENTIFIER ',' AssemblyProperties
    ;

AssemblyProperties
    : AssemblyProperty
    | AssemblyProperties ',' AssemblyProperty
    ;

AssemblyProperty
    : AssemblyPropertyName '=' AssemblyPropertyValue
    ;
```
<!-- markdownlint-enable MD010 -->

## <a name="specifying-special-characters"></a><span data-ttu-id="c33e1-112">Angeben von Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="c33e1-112">Specifying special characters</span></span>

<span data-ttu-id="c33e1-113">In einem Typnamen ist IDENTIFIER jeder gültige Name, der durch die Regeln der Sprache vorgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c33e1-113">In a type name, IDENTIFIER is any valid name determined by the rules of a language.</span></span>

<span data-ttu-id="c33e1-114">Verwenden Sie den umgekehrten Schrägstrich (\\) als Escapezeichen, um die folgenden Token abzutrennen, die als Teil von IDENTIFIER verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c33e1-114">Use the backslash (\\) as an escape character to separate the following tokens when used as part of IDENTIFIER.</span></span>

|<span data-ttu-id="c33e1-115">Token</span><span class="sxs-lookup"><span data-stu-id="c33e1-115">Token</span></span>|<span data-ttu-id="c33e1-116">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="c33e1-116">Meaning</span></span>|
|-----------|-------------|
|<span data-ttu-id="c33e1-117">\\,</span><span class="sxs-lookup"><span data-stu-id="c33e1-117">\\,</span></span>|<span data-ttu-id="c33e1-118">Assemblytrennzeichen</span><span class="sxs-lookup"><span data-stu-id="c33e1-118">Assembly separator.</span></span>|
|\\+|<span data-ttu-id="c33e1-119">Trennzeichen für geschachtelte Typen</span><span class="sxs-lookup"><span data-stu-id="c33e1-119">Nested type separator.</span></span>|
|\\&|<span data-ttu-id="c33e1-120">Verweistyp</span><span class="sxs-lookup"><span data-stu-id="c33e1-120">Reference type.</span></span>|
|\\*|<span data-ttu-id="c33e1-121">Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="c33e1-121">Pointer type.</span></span>|
|<span data-ttu-id="c33e1-122">\\[</span><span class="sxs-lookup"><span data-stu-id="c33e1-122">\\[</span></span>|<span data-ttu-id="c33e1-123">Arraydimensionstrennzeichen</span><span class="sxs-lookup"><span data-stu-id="c33e1-123">Array dimension delimiter.</span></span>|
|<span data-ttu-id="c33e1-124">\\]</span><span class="sxs-lookup"><span data-stu-id="c33e1-124">\\]</span></span>|<span data-ttu-id="c33e1-125">Arraydimensionstrennzeichen</span><span class="sxs-lookup"><span data-stu-id="c33e1-125">Array dimension delimiter.</span></span>|
|<span data-ttu-id="c33e1-126">\\</span><span class="sxs-lookup"><span data-stu-id="c33e1-126">\\.</span></span>|<span data-ttu-id="c33e1-127">Verwenden Sie den umgekehrten Schrägstrich nur dann vor einem Punkt, wenn der Punkt in einer Arrayspezifikation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c33e1-127">Use the backslash before a period only if the period is used in an array specification.</span></span> <span data-ttu-id="c33e1-128">Punkte in NamespaceSpec akzeptieren keine umgekehrten Schrägstriche.</span><span class="sxs-lookup"><span data-stu-id="c33e1-128">Periods in NamespaceSpec do not take the backslash.</span></span>|
|<span data-ttu-id="c33e1-129">\\\| Bei Bedarf kann der umgekehrte Schrägstrich als Zeichenfolgenliteral verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c33e1-129">\\\|Backslash when needed as a string literal.</span></span>|

<span data-ttu-id="c33e1-130">Beachten Sie, dass in allen TypeSpec-Komponenten außer AssemblyNameSpec Leerzeichen relevant sind.</span><span class="sxs-lookup"><span data-stu-id="c33e1-130">Note that in all TypeSpec components except AssemblyNameSpec, spaces are relevant.</span></span> <span data-ttu-id="c33e1-131">In AssemblyNameSpec sind Leerzeichen vor dem Trennzeichen „,“ (Komma) relevant, aber dahinter werden sie nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="c33e1-131">In the AssemblyNameSpec, spaces before the ',' separator are relevant, but spaces after the ',' separator are ignored.</span></span>

<span data-ttu-id="c33e1-132">Reflektionsklassen, wie z.B <xref:System.Type.FullName%2A?displayProperty=nameWithType>, geben den beschädigten Namen zurück, damit der zurückgegebene Name in einem Aufruf von <xref:System.Type.GetType%2A> verwendet werden kann, wie in `MyType.GetType(myType.FullName)`.</span><span class="sxs-lookup"><span data-stu-id="c33e1-132">Reflection classes, such as <xref:System.Type.FullName%2A?displayProperty=nameWithType>, return the mangled name so that the returned name can be used in a call to <xref:System.Type.GetType%2A>, as in `MyType.GetType(myType.FullName)`.</span></span>

<span data-ttu-id="c33e1-133">Der vollqualifizierte Name eines Typs kann z.B. `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly` sein.</span><span class="sxs-lookup"><span data-stu-id="c33e1-133">For example, the fully qualified name for a type might be `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span></span>

<span data-ttu-id="c33e1-134">Wenn der Namespace z.B. `Ozzy.Out+Back` ist, muss vor dem Pluszeichen ein umgekehrter Schrägstrich stehen.</span><span class="sxs-lookup"><span data-stu-id="c33e1-134">If the namespace were `Ozzy.Out+Back`, then the plus sign must be preceded by a backslash.</span></span> <span data-ttu-id="c33e1-135">Andernfalls interpretiert der Parser dieses als geschachteltes Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="c33e1-135">Otherwise, the parser would interpret it as a nesting separator.</span></span> <span data-ttu-id="c33e1-136">Die Reflektion gibt diese Zeichenfolge als `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly` aus.</span><span class="sxs-lookup"><span data-stu-id="c33e1-136">Reflection emits this string as `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span></span>

## <a name="specifying-assembly-names"></a><span data-ttu-id="c33e1-137">Angeben von Assemblynamen</span><span class="sxs-lookup"><span data-stu-id="c33e1-137">Specifying assembly names</span></span>

<span data-ttu-id="c33e1-138">Eine Assemblynamenspezifikation muss mindestens den wörtlichen Namen (IDENTIFIER) der Assembly enthalten.</span><span class="sxs-lookup"><span data-stu-id="c33e1-138">The minimum information required in an assembly name specification is the textual name (IDENTIFIER) of the assembly.</span></span> <span data-ttu-id="c33e1-139">Auf den IDENTIFIER kann eine durch Kommas getrennte Liste von Eigenschaft/Wert-Paaren folgen, wie in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c33e1-139">You can follow the IDENTIFIER by a comma-separated list of property/value pairs as described in the following table.</span></span> <span data-ttu-id="c33e1-140">Das Benennen von IDENTIFIER sollte die Regeln für das Benennen von Dateien einhalten.</span><span class="sxs-lookup"><span data-stu-id="c33e1-140">IDENTIFIER naming should follow the rules for file naming.</span></span> <span data-ttu-id="c33e1-141">Beim IDENTIFIER wird Groß- und Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="c33e1-141">The IDENTIFIER is case-insensitive.</span></span>

|<span data-ttu-id="c33e1-142">Name der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c33e1-142">Property name</span></span>|<span data-ttu-id="c33e1-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c33e1-143">Description</span></span>|<span data-ttu-id="c33e1-144">Zulässige Werte</span><span class="sxs-lookup"><span data-stu-id="c33e1-144">Allowable values</span></span>|
|-------------------|-----------------|----------------------|
|<span data-ttu-id="c33e1-145">**Version**</span><span class="sxs-lookup"><span data-stu-id="c33e1-145">**Version**</span></span>|<span data-ttu-id="c33e1-146">Assemblyversionsnummer</span><span class="sxs-lookup"><span data-stu-id="c33e1-146">Assembly version number</span></span>|<span data-ttu-id="c33e1-147">*Major.Minor.Build.Revision*, wobei es sich bei *Major*, *Minor*, *Build* und *Revision* um ganze Zahlen zwischen 0 und einschließlich 65535 handelt</span><span class="sxs-lookup"><span data-stu-id="c33e1-147">*Major.Minor.Build.Revision*, where *Major*, *Minor*, *Build*, and *Revision* are integers between 0 and 65535 inclusive.</span></span>|
|<span data-ttu-id="c33e1-148">**PublicKey**</span><span class="sxs-lookup"><span data-stu-id="c33e1-148">**PublicKey**</span></span>|<span data-ttu-id="c33e1-149">Vollständiger öffentlicher Schlüssel</span><span class="sxs-lookup"><span data-stu-id="c33e1-149">Full public key</span></span>|<span data-ttu-id="c33e1-150">Zeichenfolgenwert des vollständigen öffentlichen Schlüssels im Hexadezimalformat.</span><span class="sxs-lookup"><span data-stu-id="c33e1-150">String value of full public key in hexadecimal format.</span></span> <span data-ttu-id="c33e1-151">Geben Sie einen NULL-Verweis an (**Nothing** in Visual Basic), um eine private Assembly explizit zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="c33e1-151">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="c33e1-152">**PublicKeyToken**</span><span class="sxs-lookup"><span data-stu-id="c33e1-152">**PublicKeyToken**</span></span>|<span data-ttu-id="c33e1-153">Öffentliches Schlüsseltoken (8-Byte-Hash des vollständigen öffentlichen Schlüssels)</span><span class="sxs-lookup"><span data-stu-id="c33e1-153">Public key token (8-byte hash of the full public key)</span></span>|<span data-ttu-id="c33e1-154">Zeichenfolgenwert des öffentlichen Schlüsseltokens im Hexadezimalformat.</span><span class="sxs-lookup"><span data-stu-id="c33e1-154">String value of public key token in hexadecimal format.</span></span> <span data-ttu-id="c33e1-155">Geben Sie einen NULL-Verweis an (**Nothing** in Visual Basic), um eine private Assembly explizit zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="c33e1-155">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="c33e1-156">**Kultur**</span><span class="sxs-lookup"><span data-stu-id="c33e1-156">**Culture**</span></span>|<span data-ttu-id="c33e1-157">Assemblykultur</span><span class="sxs-lookup"><span data-stu-id="c33e1-157">Assembly culture</span></span>|<span data-ttu-id="c33e1-158">Kultur der Assembly im Format RFC-1766 oder auch „neutral“ bei sprachunabhängigen (nicht Satelliten) Assemblys.</span><span class="sxs-lookup"><span data-stu-id="c33e1-158">Culture of the assembly in RFC-1766 format, or "neutral" for language-independent (nonsatellite) assemblies.</span></span>|
|<span data-ttu-id="c33e1-159">**Benutzerdefiniert**</span><span class="sxs-lookup"><span data-stu-id="c33e1-159">**Custom**</span></span>|<span data-ttu-id="c33e1-160">Ein benutzerdefiniertes Binary Large Object (BLOB)</span><span class="sxs-lookup"><span data-stu-id="c33e1-160">Custom binary large object (BLOB).</span></span> <span data-ttu-id="c33e1-161">Dies wird aktuell nur in Assemblys genutzt, die vom [Native Image Generator (Ngen)](../tools/ngen-exe-native-image-generator.md) generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c33e1-161">This is currently used only in assemblies generated by the [Native Image Generator (Ngen)](../tools/ngen-exe-native-image-generator.md).</span></span>|<span data-ttu-id="c33e1-162">Benutzerdefinierte Zeichenfolgen, die vom Native Image Generator-Tool verwendet werden, um den Assemblycache zu informieren, das die Assembly, die gerade installiert wird, ein natives Image ist und deshalb im nativen Imagecache installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="c33e1-162">Custom string used by the Native Image Generator tool to notify the assembly cache that the assembly being installed is a native image, and is therefore to be installed in the native image cache.</span></span> <span data-ttu-id="c33e1-163">Dies wird auch als ZAP-Zeichenfolge bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c33e1-163">Also called a zap string.</span></span>|

<span data-ttu-id="c33e1-164">In folgendem Beispiel wird ein **Assemblyname** für eine einfach benannte Assembly mit einer Standardkultur dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c33e1-164">The following example shows an **AssemblyName** for a simply named assembly with default culture.</span></span>

```csharp
com.microsoft.crypto, Culture=""
```

<span data-ttu-id="c33e1-165">In folgendem Beispiel wird einen vollständig angegebenen Verweis auf eine Assembly mit starkem Namen mit der Kultur „en“ dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c33e1-165">The following example shows a fully specified reference for a strongly named assembly with culture "en".</span></span>

```csharp
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

<span data-ttu-id="c33e1-166">In folgenden Beispielen wird jeweils ein teilweise angegebenen **Assemblyname** dargestellt, der entweder von einer stark oder einfach benannten Assembly erfüllt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c33e1-166">The following examples each show a partially specified **AssemblyName**, which can be satisfied by either a strong or a simply named assembly.</span></span>

```csharp
com.microsoft.crypto
com.microsoft.crypto, Culture=""
com.microsoft.crypto, Culture=en
```

<span data-ttu-id="c33e1-167">In folgenden Beispielen wird jeweils ein teilweise angegebenen **Assemblyname** dargestellt, der von einer einfach benannten Assembly erfüllt werden muss.</span><span class="sxs-lookup"><span data-stu-id="c33e1-167">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a simply named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=null
com.microsoft.crypto, Culture=en, PublicKeyToken=null
```

<span data-ttu-id="c33e1-168">In folgenden Beispielen wird jeweils ein teilweise angegebenen **Assemblyname** dargestellt, der von einer stark benannten Assembly erfüllt werden muss.</span><span class="sxs-lookup"><span data-stu-id="c33e1-168">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a strongly named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

## <a name="specifying-generic-types"></a><span data-ttu-id="c33e1-169">Angeben von generischen Typen</span><span class="sxs-lookup"><span data-stu-id="c33e1-169">Specifying generic types</span></span>

<span data-ttu-id="c33e1-170">SimpleTypeSpec\`NUMBER stellt einen offenen generischen Typ mit 1 bis *n* generischen Typparametern dar.</span><span class="sxs-lookup"><span data-stu-id="c33e1-170">SimpleTypeSpec\`NUMBER represents an open generic type with from 1 to *n* generic type parameters.</span></span> <span data-ttu-id="c33e1-171">Um beispielsweise den Verweis auf den offenen generischen Typ List\<T> oder den geschlossenen generischen Typ List\<String> zu erhalten, verwenden Sie ``Type.GetType("System.Collections.Generic.List`1")``. Um einen Verweis auf den generischen Typ Dictionary\<TKey,TValue> zu erhalten, verwenden Sie ``Type.GetType("System.Collections.Generic.Dictionary`2")``.</span><span class="sxs-lookup"><span data-stu-id="c33e1-171">For example, to get reference to the open generic type List\<T> or the closed generic type List\<String>, use ``Type.GetType("System.Collections.Generic.List`1")`` To get a reference to the generic type Dictionary\<TKey,TValue>, use ``Type.GetType("System.Collections.Generic.Dictionary`2")``.</span></span>

## <a name="specifying-pointers"></a><span data-ttu-id="c33e1-172">Angeben von Zeigern</span><span class="sxs-lookup"><span data-stu-id="c33e1-172">Specifying pointers</span></span>

<span data-ttu-id="c33e1-173">SimpleTypeSpec\* stellt einen nicht verwalteten Zeiger dar.</span><span class="sxs-lookup"><span data-stu-id="c33e1-173">SimpleTypeSpec\* represents an unmanaged pointer.</span></span> <span data-ttu-id="c33e1-174">Um z.B. einen Zeiger auf den Typ „MyType“ zu erhalten, verwenden Sie `Type.GetType("MyType*")`.</span><span class="sxs-lookup"><span data-stu-id="c33e1-174">For example, to get a pointer to type MyType, use `Type.GetType("MyType*")`.</span></span> <span data-ttu-id="c33e1-175">Um einen Zeiger auf den Typ „MyType“ zu erhalten, verwenden Sie `Type.GetType("MyType**")`.</span><span class="sxs-lookup"><span data-stu-id="c33e1-175">To get a pointer to a pointer to type MyType, use `Type.GetType("MyType**")`.</span></span>

## <a name="specifying-references"></a><span data-ttu-id="c33e1-176">Angeben von Verweisen</span><span class="sxs-lookup"><span data-stu-id="c33e1-176">Specifying references</span></span>

<span data-ttu-id="c33e1-177">SimpleTypeSpe & stellt einen nicht verwalteten Zeiger oder Verweis dar.</span><span class="sxs-lookup"><span data-stu-id="c33e1-177">SimpleTypeSpec & represents a managed pointer or reference.</span></span> <span data-ttu-id="c33e1-178">Um z.B. einen Verweis auf den Typ „MyType“ zu erhalten, verwenden Sie `Type.GetType("MyType &")`.</span><span class="sxs-lookup"><span data-stu-id="c33e1-178">For example, to get a reference to type MyType, use `Type.GetType("MyType &")`.</span></span> <span data-ttu-id="c33e1-179">Beachten Sie, dass Verweise im Gegensatz zu Zeigern auf eine Ebene beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="c33e1-179">Note that unlike pointers, references are limited to one level.</span></span>

## <a name="specifying-arrays"></a><span data-ttu-id="c33e1-180">Angeben von Arrays</span><span class="sxs-lookup"><span data-stu-id="c33e1-180">Specifying arrays</span></span>

<span data-ttu-id="c33e1-181">In der BNF-Grammatik gilt ReflectionEmitDimension nur für unvollständige Typdefinitionen, die mit <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="c33e1-181">In the BNF Grammar, ReflectionEmitDimension only applies to incomplete type definitions retrieved using <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c33e1-182">Unvollständige Typdefinitionen sind <xref:System.Reflection.Emit.TypeBuilder>-Objekte, die mit <xref:System.Reflection.Emit?displayProperty=nameWithType> erstellt wurden, auf denen <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> jedoch nicht aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="c33e1-182">Incomplete type definitions are <xref:System.Reflection.Emit.TypeBuilder> objects constructed using <xref:System.Reflection.Emit?displayProperty=nameWithType> but on which <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> has not been called.</span></span> <span data-ttu-id="c33e1-183">ReflectionDimension kann verwendet werden, um jede vollständige Typdefinition abzurufen, d.h. jeder geladene Typ.</span><span class="sxs-lookup"><span data-stu-id="c33e1-183">ReflectionDimension can be used to retrieve any type definition that has been completed, that is, a type that has been loaded.</span></span>

<span data-ttu-id="c33e1-184">Auf Arrays wird in der Reflektion zugegriffen, indem der Rang des Arrays angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="c33e1-184">Arrays are accessed in reflection by specifying the rank of the array:</span></span>

- <span data-ttu-id="c33e1-185">`Type.GetType("MyArray[]")` ruft ein eindimensionales Array mit der unteren Grenze 0 ab.</span><span class="sxs-lookup"><span data-stu-id="c33e1-185">`Type.GetType("MyArray[]")` gets a single-dimension array with 0 lower bound.</span></span>

- <span data-ttu-id="c33e1-186">`Type.GetType("MyArray[*]")` ruft ein eindimensionales Array mit unbekannter unterer Grenze ab.</span><span class="sxs-lookup"><span data-stu-id="c33e1-186">`Type.GetType("MyArray[*]")` gets a single-dimension array with unknown lower bound.</span></span>
- <span data-ttu-id="c33e1-187">`Type.GetType("MyArray[][]")` ruft das Array eines zweidimensionalen Arrays ab.</span><span class="sxs-lookup"><span data-stu-id="c33e1-187">`Type.GetType("MyArray[][]")` gets a two-dimensional array's array.</span></span>

- <span data-ttu-id="c33e1-188">`Type.GetType("MyArray[*,*]")` und `Type.GetType("MyArray[,]")` rufen ein rechteckiges zweidimensionales Array mit unbekannter unterer Grenze ab.</span><span class="sxs-lookup"><span data-stu-id="c33e1-188">`Type.GetType("MyArray[*,*]")` and `Type.GetType("MyArray[,]")` gets a rectangular two-dimensional array with unknown lower bounds.</span></span>

<span data-ttu-id="c33e1-189">Beachten Sie `MyArray[] != MyArray[*]`, aus Perspektive der Runtime, aber für mehrdimensionale Arrays sind die beiden Notationen gleich.</span><span class="sxs-lookup"><span data-stu-id="c33e1-189">Note that from a runtime point of view, `MyArray[] != MyArray[*]`, but for multidimensional arrays, the two notations are equivalent.</span></span> <span data-ttu-id="c33e1-190">D.h., `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` ergibt **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="c33e1-190">That is, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` evaluates to **true**.</span></span>

<span data-ttu-id="c33e1-191">`MyArray[0..5]` gibt für **ModuleBuilder.GetType** ein eindimensionales Array mit der Größe 6 und einer unteren Grenze von 0 an.</span><span class="sxs-lookup"><span data-stu-id="c33e1-191">For **ModuleBuilder.GetType**, `MyArray[0..5]` indicates a single-dimension array with size 6, lower bound 0.</span></span> <span data-ttu-id="c33e1-192">`MyArray[4…]` gibt ein eindimensionales Array mit unbekannter Größe und einer unteren Grenze von 4 an.</span><span class="sxs-lookup"><span data-stu-id="c33e1-192">`MyArray[4…]` indicates a single-dimension array of unknown size and lower bound 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="c33e1-193">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c33e1-193">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c33e1-194">Anzeigen von Typinformationen</span><span class="sxs-lookup"><span data-stu-id="c33e1-194">Viewing Type Information</span></span>](viewing-type-information.md)
