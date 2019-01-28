---
title: Angeben vollständig gekennzeichneter Typnamen
ms.date: 03/14/2018
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9281906f5500d954f3a0c7abface4ee43adcb64d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628538"
---
# <a name="specifying-fully-qualified-type-names"></a><span data-ttu-id="f7713-102">Angeben vollständig gekennzeichneter Typnamen</span><span class="sxs-lookup"><span data-stu-id="f7713-102">Specifying Fully Qualified Type Names</span></span>
<span data-ttu-id="f7713-103">Sie müssen Typnamen angeben, um eine gültige Eingabe für verschiedene Reflektionsvorgänge zu haben.</span><span class="sxs-lookup"><span data-stu-id="f7713-103">You must specify type names to have valid input to various reflection operations.</span></span> <span data-ttu-id="f7713-104">Ein vollqualifizierter Typname besteht aus der Angabe eines Assemblynamens, eines Namespaces und eines Typnamens.</span><span class="sxs-lookup"><span data-stu-id="f7713-104">A fully qualified type name consists of an assembly name specification, a namespace specification, and a type name.</span></span> <span data-ttu-id="f7713-105">Angaben von Typnamen werden von Methoden wie <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> und <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> verwendet.</span><span class="sxs-lookup"><span data-stu-id="f7713-105">Type name specifications are used by methods such as <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>, and <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="grammar-for-type-names"></a><span data-ttu-id="f7713-106">Grammatik für Typnamen</span><span class="sxs-lookup"><span data-stu-id="f7713-106">Grammar for Type Names</span></span>  
 <span data-ttu-id="f7713-107">Die Grammatik definiert die Syntax formaler Sprachen.</span><span class="sxs-lookup"><span data-stu-id="f7713-107">The grammar defines the syntax of formal languages.</span></span> <span data-ttu-id="f7713-108">In der folgenden Tabelle werden lexikalische Regeln aufgelistet, die angeben, wie Sie eine gültige Eingabe erkennen können.</span><span class="sxs-lookup"><span data-stu-id="f7713-108">The following table lists lexical rules that describe how to recognize a valid input.</span></span> <span data-ttu-id="f7713-109">Terminale (diejenigen Elemente, die nicht weiter reduziert werden können) werden in Großbuchstaben dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f7713-109">Terminals (those elements that are not further reducible) are shown in all uppercase letters.</span></span> <span data-ttu-id="f7713-110">Nichtterminale (diejenigen Elemente, die noch weiter reduziert werden können) werden in Groß- und Kleinbuchstaben oder durch Zeichenfolgen in einfachen Anführungszeichen dargestellt. Dabei ist das einfache Anführungszeichen (') nicht Teil der Syntax.</span><span class="sxs-lookup"><span data-stu-id="f7713-110">Nonterminals (those elements that are further reducible) are shown in mixed-case or singly quoted strings, but the single quote (') is not a part of the syntax itself.</span></span> <span data-ttu-id="f7713-111">Das Pipezeichen (&#124;) kennzeichnet Regeln mit Unterregeln.</span><span class="sxs-lookup"><span data-stu-id="f7713-111">The pipe character (&#124;) denotes rules that have subrules.</span></span>  

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
    | ArrayTypeSpec
    | TypeName
    ;

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

## <a name="specifying-special-characters"></a><span data-ttu-id="f7713-112">Angeben von Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="f7713-112">Specifying Special Characters</span></span>  
 <span data-ttu-id="f7713-113">In einem Typnamen ist IDENTIFIER jeder gültige Name, der durch die Regeln der Sprache vorgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f7713-113">In a type name, IDENTIFIER is any valid name determined by the rules of a language.</span></span>  
  
 <span data-ttu-id="f7713-114">Verwenden Sie den umgekehrten Schrägstrich (\\) als Escapezeichen, um die folgenden Token abzutrennen, die als Teil von IDENTIFIER verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f7713-114">Use the backslash (\\) as an escape character to separate the following tokens when used as part of IDENTIFIER.</span></span>  
  
|<span data-ttu-id="f7713-115">Token</span><span class="sxs-lookup"><span data-stu-id="f7713-115">Token</span></span>|<span data-ttu-id="f7713-116">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="f7713-116">Meaning</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="f7713-117">\\,</span><span class="sxs-lookup"><span data-stu-id="f7713-117">\\,</span></span>|<span data-ttu-id="f7713-118">Assemblytrennzeichen</span><span class="sxs-lookup"><span data-stu-id="f7713-118">Assembly separator.</span></span>|  
|\\+|<span data-ttu-id="f7713-119">Trennzeichen für geschachtelte Typen</span><span class="sxs-lookup"><span data-stu-id="f7713-119">Nested type separator.</span></span>|  
|\\&|<span data-ttu-id="f7713-120">Verweistyp</span><span class="sxs-lookup"><span data-stu-id="f7713-120">Reference type.</span></span>|  
|\\*|<span data-ttu-id="f7713-121">Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="f7713-121">Pointer type.</span></span>|  
|<span data-ttu-id="f7713-122">\\[</span><span class="sxs-lookup"><span data-stu-id="f7713-122">\\[</span></span>|<span data-ttu-id="f7713-123">Arraydimensionstrennzeichen</span><span class="sxs-lookup"><span data-stu-id="f7713-123">Array dimension delimiter.</span></span>|  
|<span data-ttu-id="f7713-124">\\]</span><span class="sxs-lookup"><span data-stu-id="f7713-124">\\]</span></span>|<span data-ttu-id="f7713-125">Arraydimensionstrennzeichen</span><span class="sxs-lookup"><span data-stu-id="f7713-125">Array dimension delimiter.</span></span>|  
|<span data-ttu-id="f7713-126">\\.</span><span class="sxs-lookup"><span data-stu-id="f7713-126">\\.</span></span>|<span data-ttu-id="f7713-127">Verwenden Sie den umgekehrten Schrägstrich nur dann vor einem Punkt, wenn der Punkt in einer Arrayspezifikation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f7713-127">Use the backslash before a period only if the period is used in an array specification.</span></span> <span data-ttu-id="f7713-128">Punkte in NamespaceSpec akzeptieren keine umgekehrten Schrägstriche.</span><span class="sxs-lookup"><span data-stu-id="f7713-128">Periods in NamespaceSpec do not take the backslash.</span></span>|  
|<span data-ttu-id="f7713-129">\\\| Bei Bedarf kann der umgekehrte Schrägstrich als Zeichenfolgenliteral verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f7713-129">\\\|Backslash when needed as a string literal.</span></span>|  
  
 <span data-ttu-id="f7713-130">Beachten Sie, dass in allen TypeSpec-Komponenten außer AssemblyNameSpec Leerzeichen relevant sind.</span><span class="sxs-lookup"><span data-stu-id="f7713-130">Note that in all TypeSpec components except AssemblyNameSpec, spaces are relevant.</span></span> <span data-ttu-id="f7713-131">In AssemblyNameSpec sind Leerzeichen vor dem Trennzeichen „,“ (Komma) relevant, aber dahinter werden sie nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="f7713-131">In the AssemblyNameSpec, spaces before the ',' separator are relevant, but spaces after the ',' separator are ignored.</span></span>  
  
 <span data-ttu-id="f7713-132">Reflektionsklassen, wie z.B <xref:System.Type.FullName%2A?displayProperty=nameWithType>, geben den beschädigten Namen zurück, damit der zurückgegebene Name in einem Aufruf von <xref:System.Type.GetType%2A> verwendet werden kann, wie in `MyType.GetType(myType.FullName)`.</span><span class="sxs-lookup"><span data-stu-id="f7713-132">Reflection classes, such as <xref:System.Type.FullName%2A?displayProperty=nameWithType>, return the mangled name so that the returned name can be used in a call to <xref:System.Type.GetType%2A>, as in `MyType.GetType(myType.FullName)`.</span></span>  
  
 <span data-ttu-id="f7713-133">Der vollqualifizierte Name eines Typs kann z.B. `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly` sein.</span><span class="sxs-lookup"><span data-stu-id="f7713-133">For example, the fully qualified name for a type might be `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span></span>  
  
 <span data-ttu-id="f7713-134">Wenn der Namespace z.B. `Ozzy.Out+Back` ist, muss vor dem Pluszeichen ein umgekehrter Schrägstrich stehen.</span><span class="sxs-lookup"><span data-stu-id="f7713-134">If the namespace were `Ozzy.Out+Back`, then the plus sign must be preceded by a backslash.</span></span> <span data-ttu-id="f7713-135">Andernfalls interpretiert der Parser dieses als geschachteltes Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="f7713-135">Otherwise, the parser would interpret it as a nesting separator.</span></span> <span data-ttu-id="f7713-136">Die Reflektion gibt diese Zeichenfolge als `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly` aus.</span><span class="sxs-lookup"><span data-stu-id="f7713-136">Reflection emits this string as `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span></span>  
  
## <a name="specifying-assembly-names"></a><span data-ttu-id="f7713-137">Angeben von Assemblynamen</span><span class="sxs-lookup"><span data-stu-id="f7713-137">Specifying Assembly Names</span></span>  
 <span data-ttu-id="f7713-138">Eine Assemblynamenspezifikation muss mindestens den wörtlichen Namen (IDENTIFIER) der Assembly enthalten.</span><span class="sxs-lookup"><span data-stu-id="f7713-138">The minimum information required in an assembly name specification is the textual name (IDENTIFIER) of the assembly.</span></span> <span data-ttu-id="f7713-139">Auf den IDENTIFIER kann eine durch Kommas getrennte Liste von Eigenschaft/Wert-Paaren folgen, wie in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f7713-139">You can follow the IDENTIFIER by a comma-separated list of property/value pairs as described in the following table.</span></span> <span data-ttu-id="f7713-140">Das Benennen von IDENTIFIER sollte die Regeln für das Benennen von Dateien einhalten.</span><span class="sxs-lookup"><span data-stu-id="f7713-140">IDENTIFIER naming should follow the rules for file naming.</span></span> <span data-ttu-id="f7713-141">Beim IDENTIFIER wird Groß- und Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="f7713-141">The IDENTIFIER is case-insensitive.</span></span>  
  
|<span data-ttu-id="f7713-142">Name der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="f7713-142">Property name</span></span>|<span data-ttu-id="f7713-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7713-143">Description</span></span>|<span data-ttu-id="f7713-144">Zulässige Werte</span><span class="sxs-lookup"><span data-stu-id="f7713-144">Allowable values</span></span>|  
|-------------------|-----------------|----------------------|  
|<span data-ttu-id="f7713-145">**Version**</span><span class="sxs-lookup"><span data-stu-id="f7713-145">**Version**</span></span>|<span data-ttu-id="f7713-146">Assemblyversionsnummer</span><span class="sxs-lookup"><span data-stu-id="f7713-146">Assembly version number</span></span>|<span data-ttu-id="f7713-147">*Major.Minor.Build.Revision*, wobei es sich bei *Major*, *Minor*, *Build* und *Revision* um ganze Zahlen zwischen 0 und einschließlich 65535 handelt</span><span class="sxs-lookup"><span data-stu-id="f7713-147">*Major.Minor.Build.Revision*, where *Major*, *Minor*, *Build*, and *Revision* are integers between 0 and 65535 inclusive.</span></span>|  
|<span data-ttu-id="f7713-148">**PublicKey**</span><span class="sxs-lookup"><span data-stu-id="f7713-148">**PublicKey**</span></span>|<span data-ttu-id="f7713-149">Vollständiger öffentlicher Schlüssel</span><span class="sxs-lookup"><span data-stu-id="f7713-149">Full public key</span></span>|<span data-ttu-id="f7713-150">Zeichenfolgenwert des vollständigen öffentlichen Schlüssels im Hexadezimalformat.</span><span class="sxs-lookup"><span data-stu-id="f7713-150">String value of full public key in hexadecimal format.</span></span> <span data-ttu-id="f7713-151">Geben Sie einen NULL-Verweis an (**Nothing** in Visual Basic), um eine private Assembly explizit zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="f7713-151">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|  
|<span data-ttu-id="f7713-152">**PublicKeyToken**</span><span class="sxs-lookup"><span data-stu-id="f7713-152">**PublicKeyToken**</span></span>|<span data-ttu-id="f7713-153">Öffentliches Schlüsseltoken (8-Byte-Hash des vollständigen öffentlichen Schlüssels)</span><span class="sxs-lookup"><span data-stu-id="f7713-153">Public key token (8-byte hash of the full public key)</span></span>|<span data-ttu-id="f7713-154">Zeichenfolgenwert des öffentlichen Schlüsseltokens im Hexadezimalformat.</span><span class="sxs-lookup"><span data-stu-id="f7713-154">String value of public key token in hexadecimal format.</span></span> <span data-ttu-id="f7713-155">Geben Sie einen NULL-Verweis an (**Nothing** in Visual Basic), um eine private Assembly explizit zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="f7713-155">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|  
|<span data-ttu-id="f7713-156">**Kultur**</span><span class="sxs-lookup"><span data-stu-id="f7713-156">**Culture**</span></span>|<span data-ttu-id="f7713-157">Assemblykultur</span><span class="sxs-lookup"><span data-stu-id="f7713-157">Assembly culture</span></span>|<span data-ttu-id="f7713-158">Kultur der Assembly im Format RFC-1766 oder auch „neutral“ bei sprachunabhängigen (nicht Satelliten) Assemblys.</span><span class="sxs-lookup"><span data-stu-id="f7713-158">Culture of the assembly in RFC-1766 format, or "neutral" for language-independent (nonsatellite) assemblies.</span></span>|  
|<span data-ttu-id="f7713-159">**Benutzerdefiniert**</span><span class="sxs-lookup"><span data-stu-id="f7713-159">**Custom**</span></span>|<span data-ttu-id="f7713-160">Ein benutzerdefiniertes Binary Large Object (BLOB)</span><span class="sxs-lookup"><span data-stu-id="f7713-160">Custom binary large object (BLOB).</span></span> <span data-ttu-id="f7713-161">Dies wird aktuell nur in Assemblys genutzt, die vom [Native Image Generator (Ngen)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f7713-161">This is currently used only in assemblies generated by the [Native Image Generator (Ngen)](../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>|<span data-ttu-id="f7713-162">Benutzerdefinierte Zeichenfolgen, die vom Native Image Generator-Tool verwendet werden, um den Assemblycache zu informieren, das die Assembly, die gerade installiert wird, ein natives Image ist und deshalb im nativen Imagecache installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="f7713-162">Custom string used by the Native Image Generator tool to notify the assembly cache that the assembly being installed is a native image, and is therefore to be installed in the native image cache.</span></span> <span data-ttu-id="f7713-163">Dies wird auch als ZAP-Zeichenfolge bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f7713-163">Also called a zap string.</span></span>|  
  
 <span data-ttu-id="f7713-164">In folgendem Beispiel wird ein **Assemblyname** für eine einfach benannte Assembly mit einer Standardkultur dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f7713-164">The following example shows an **AssemblyName** for a simply named assembly with default culture.</span></span>  
  
```csharp  
com.microsoft.crypto, Culture=""   
```  
  
 <span data-ttu-id="f7713-165">In folgendem Beispiel wird einen vollständig angegebenen Verweis auf eine Assembly mit starkem Namen mit der Kultur „en“ dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f7713-165">The following example shows a fully specified reference for a strongly named assembly with culture "en".</span></span>  
  
```csharp  
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,  
    Version=1.0.0.0   
```  
  
 <span data-ttu-id="f7713-166">In folgenden Beispielen wird jeweils ein teilweise angegebenen **Assemblyname** dargestellt, der entweder von einer stark oder einfach benannten Assembly erfüllt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f7713-166">The following examples each show a partially specified **AssemblyName**, which can be satisfied by either a strong or a simply named assembly.</span></span>  
  
```csharp  
com.microsoft.crypto  
com.microsoft.crypto, Culture=""  
com.microsoft.crypto, Culture=en   
```  
  
 <span data-ttu-id="f7713-167">In folgenden Beispielen wird jeweils ein teilweise angegebenen **Assemblyname** dargestellt, der von einer einfach benannten Assembly erfüllt werden muss.</span><span class="sxs-lookup"><span data-stu-id="f7713-167">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a simply named assembly.</span></span>  
  
```csharp  
com.microsoft.crypto, Culture="", PublicKeyToken=null   
com.microsoft.crypto, Culture=en, PublicKeyToken=null  
```  
  
 <span data-ttu-id="f7713-168">In folgenden Beispielen wird jeweils ein teilweise angegebenen **Assemblyname** dargestellt, der von einer stark benannten Assembly erfüllt werden muss.</span><span class="sxs-lookup"><span data-stu-id="f7713-168">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a strongly named assembly.</span></span>  
  
```csharp  
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012  
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,  
    Version=1.0.0.0  
```  
  
## <a name="specifying-pointers"></a><span data-ttu-id="f7713-169">Angeben von Zeigern</span><span class="sxs-lookup"><span data-stu-id="f7713-169">Specifying Pointers</span></span>  
 <span data-ttu-id="f7713-170">SimpleTypeSpec\* stellt einen nicht verwalteten Zeiger dar.</span><span class="sxs-lookup"><span data-stu-id="f7713-170">SimpleTypeSpec\* represents an unmanaged pointer.</span></span> <span data-ttu-id="f7713-171">Um z.B. einen Zeiger auf den Typ „MyType“ zu erhalten, verwenden Sie `Type.GetType("MyType*")`.</span><span class="sxs-lookup"><span data-stu-id="f7713-171">For example, to get a pointer to type MyType, use `Type.GetType("MyType*")`.</span></span> <span data-ttu-id="f7713-172">Um einen Zeiger auf den Typ „MyType“ zu erhalten, verwenden Sie `Type.GetType("MyType**")`.</span><span class="sxs-lookup"><span data-stu-id="f7713-172">To get a pointer to a pointer to type MyType, use `Type.GetType("MyType**")`.</span></span>  
  
## <a name="specifying-references"></a><span data-ttu-id="f7713-173">Angeben von Verweisen</span><span class="sxs-lookup"><span data-stu-id="f7713-173">Specifying References</span></span>  
 <span data-ttu-id="f7713-174">SimpleTypeSpe & stellt einen nicht verwalteten Zeiger oder Verweis dar.</span><span class="sxs-lookup"><span data-stu-id="f7713-174">SimpleTypeSpec & represents a managed pointer or reference.</span></span> <span data-ttu-id="f7713-175">Um z.B. einen Verweis auf den Typ „MyType“ zu erhalten, verwenden Sie `Type.GetType("MyType &")`.</span><span class="sxs-lookup"><span data-stu-id="f7713-175">For example, to get a reference to type MyType, use `Type.GetType("MyType &")`.</span></span> <span data-ttu-id="f7713-176">Beachten Sie, dass Verweise im Gegensatz zu Zeigern auf eine Ebene beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="f7713-176">Note that unlike pointers, references are limited to one level.</span></span>  
  
## <a name="specifying-arrays"></a><span data-ttu-id="f7713-177">Angeben von Arrays</span><span class="sxs-lookup"><span data-stu-id="f7713-177">Specifying Arrays</span></span>  
 <span data-ttu-id="f7713-178">In der BNF-Grammatik gilt ReflectionEmitDimension nur für unvollständige Typdefinitionen, die mit <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="f7713-178">In the BNF Grammar, ReflectionEmitDimension only applies to incomplete type definitions retrieved using <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f7713-179">Unvollständige Typdefinitionen sind <xref:System.Reflection.Emit.TypeBuilder>-Objekte, die mit <xref:System.Reflection.Emit?displayProperty=nameWithType> erstellt wurden, auf denen <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> jedoch nicht aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="f7713-179">Incomplete type definitions are <xref:System.Reflection.Emit.TypeBuilder> objects constructed using <xref:System.Reflection.Emit?displayProperty=nameWithType> but on which <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> has not been called.</span></span> <span data-ttu-id="f7713-180">ReflectionDimension kann verwendet werden, um jede vollständige Typdefinition abzurufen, d.h. jeder geladene Typ.</span><span class="sxs-lookup"><span data-stu-id="f7713-180">ReflectionDimension can be used to retrieve any type definition that has been completed, that is, a type that has been loaded.</span></span>  
  
 <span data-ttu-id="f7713-181">Auf Arrays wird in der Reflektion zugegriffen, indem der Rang des Arrays angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="f7713-181">Arrays are accessed in reflection by specifying the rank of the array:</span></span>  
  
-   <span data-ttu-id="f7713-182">`Type.GetType("MyArray[]")` ruft ein eindimensionales Array mit der unteren Grenze 0 ab.</span><span class="sxs-lookup"><span data-stu-id="f7713-182">`Type.GetType("MyArray[]")` gets a single-dimension array with 0 lower bound.</span></span>  
  
-   <span data-ttu-id="f7713-183">`Type.GetType("MyArray[*]")` ruft ein eindimensionales Array mit unbekannter unterer Grenze ab.</span><span class="sxs-lookup"><span data-stu-id="f7713-183">`Type.GetType("MyArray[*]")` gets a single-dimension array with unknown lower bound.</span></span>  
  
-   <span data-ttu-id="f7713-184">`Type.GetType("MyArray[][]")` ruft das Array eines zweidimensionalen Arrays ab.</span><span class="sxs-lookup"><span data-stu-id="f7713-184">`Type.GetType("MyArray[][]")` gets a two-dimensional array's array.</span></span>  
  
-   <span data-ttu-id="f7713-185">`Type.GetType("MyArray[*,*]")` und `Type.GetType("MyArray[,]")` rufen ein rechteckiges zweidimensionales Array mit unbekannter unterer Grenze ab.</span><span class="sxs-lookup"><span data-stu-id="f7713-185">`Type.GetType("MyArray[*,*]")` and `Type.GetType("MyArray[,]")` gets a rectangular two-dimensional array with unknown lower bounds.</span></span>  
  
 <span data-ttu-id="f7713-186">Beachten Sie `MyArray[] != MyArray[*]`, aus Perspektive der Runtime, aber für mehrdimensionale Arrays sind die beiden Notationen gleich.</span><span class="sxs-lookup"><span data-stu-id="f7713-186">Note that from a runtime point of view, `MyArray[] != MyArray[*]`, but for multidimensional arrays, the two notations are equivalent.</span></span> <span data-ttu-id="f7713-187">D.h., `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` ergibt **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="f7713-187">That is, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` evaluates to **true**.</span></span>  
  
 <span data-ttu-id="f7713-188">`MyArray[0..5]` gibt für **ModuleBuilder.GetType** ein eindimensionales Array mit der Größe 6 und einer unteren Grenze von 0 an.</span><span class="sxs-lookup"><span data-stu-id="f7713-188">For **ModuleBuilder.GetType**, `MyArray[0..5]` indicates a single-dimension array with size 6, lower bound 0.</span></span> <span data-ttu-id="f7713-189">`MyArray[4…]` gibt ein eindimensionales Array mit unbekannter Größe und einer unteren Grenze von 4 an.</span><span class="sxs-lookup"><span data-stu-id="f7713-189">`MyArray[4…]` indicates a single-dimension array of unknown size and lower bound 4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7713-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7713-190">See also</span></span>
- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f7713-191">Anzeigen von Typinformationen</span><span class="sxs-lookup"><span data-stu-id="f7713-191">Viewing Type Information</span></span>](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)
