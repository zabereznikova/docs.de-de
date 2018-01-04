---
title: Allgemeine Benennungskonventionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5e5c09c4db8e65d836c7afc7cb78c1f9e32bab65
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="general-naming-conventions"></a><span data-ttu-id="22650-102">Allgemeine Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="22650-102">General Naming Conventions</span></span>
<span data-ttu-id="22650-103">Dieser Abschnitt beschreibt allgemeine Benennungskonventionen angeben, die auf Wortwahl, beziehen Richtlinien zur Verwendung von Abkürzungen und Akronyme und Empfehlungen zum Vermeiden Sie die Verwendung von sprachspezifischen Namen.</span><span class="sxs-lookup"><span data-stu-id="22650-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>  
  
## <a name="word-choice"></a><span data-ttu-id="22650-104">Word-Auswahl</span><span class="sxs-lookup"><span data-stu-id="22650-104">Word Choice</span></span>  
 <span data-ttu-id="22650-105">**Führen Sie ✓** übersichtlich Bezeichnernamen auswählen.</span><span class="sxs-lookup"><span data-stu-id="22650-105">**✓ DO** choose easily readable identifier names.</span></span>  
  
 <span data-ttu-id="22650-106">Angenommen, eine Eigenschaft namens `HorizontalAlignment` ist Englisch-lesbarer als `AlignmentHorizontal`.</span><span class="sxs-lookup"><span data-stu-id="22650-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>  
  
 <span data-ttu-id="22650-107">**Führen Sie ✓** ziehen Sie Lesbarkeit Knappheit zu finden.</span><span class="sxs-lookup"><span data-stu-id="22650-107">**✓ DO** favor readability over brevity.</span></span>  
  
 <span data-ttu-id="22650-108">Der Eigenschaftenname `CanScrollHorizontally` ist besser als `ScrollableX` (eine unbekannte Verweis auf die X-Achse).</span><span class="sxs-lookup"><span data-stu-id="22650-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>  
  
 <span data-ttu-id="22650-109">**X nicht** Unterstriche, Bindestriche oder andere nicht alphanumerischen Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="22650-109">**X DO NOT** use underscores, hyphens, or any other nonalphanumeric characters.</span></span>  
  
 <span data-ttu-id="22650-110">**X nicht** verwenden Ungarischer Notation benannt.</span><span class="sxs-lookup"><span data-stu-id="22650-110">**X DO NOT** use Hungarian notation.</span></span>  
  
 <span data-ttu-id="22650-111">**X vermeiden** Bezeichner, die häufig mit Schlüsselwörtern in Konflikt mit der übrigen Programmiersprachen verwendet.</span><span class="sxs-lookup"><span data-stu-id="22650-111">**X AVOID** using identifiers that conflict with keywords of widely used programming languages.</span></span>  
  
 <span data-ttu-id="22650-112">Gemäß der Regel 4 der Common Language Specification (CLS) müssen alle kompatible Sprachen einen Mechanismus bereit, der Zugriff auf benannte Elemente ermöglicht, die ein Schlüsselwort für diese Sprache nicht als Bezeichner verwendet.</span><span class="sxs-lookup"><span data-stu-id="22650-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="22650-113">C#-, verwendet z. B. das @-Zeichen als Escapezeichen Mechanismus in diesem Fall.</span><span class="sxs-lookup"><span data-stu-id="22650-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="22650-114">Allerdings ist es immer noch eine gute Idee, häufige oder gemeinsame Schlüsselwörter vermeiden, da es sehr viel schwieriger, eine Methode mit der-Escapesequenz als ohne sie zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="22650-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>  
  
## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="22650-115">Verwenden von Abkürzungen und Akronyme</span><span class="sxs-lookup"><span data-stu-id="22650-115">Using Abbreviations and Acronyms</span></span>  
 <span data-ttu-id="22650-116">**X nicht** Abkürzungen oder Kontraktionen als Teil des Bezeichnernamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="22650-116">**X DO NOT** use abbreviations or contractions as part of identifier names.</span></span>  
  
 <span data-ttu-id="22650-117">Verwenden Sie z. B. `GetWindow` statt `GetWin`.</span><span class="sxs-lookup"><span data-stu-id="22650-117">For example, use `GetWindow` rather than `GetWin`.</span></span>  
  
 <span data-ttu-id="22650-118">**X nicht** verwenden Sie Akronyme, die nicht weit verbreitete und sogar, wenn sie, falls erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="22650-118">**X DO NOT** use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>  
  
## <a name="avoiding-language-specific-names"></a><span data-ttu-id="22650-119">Vermeiden von sprachspezifischen Namen</span><span class="sxs-lookup"><span data-stu-id="22650-119">Avoiding Language-Specific Names</span></span>  
 <span data-ttu-id="22650-120">**Führen Sie ✓** verwenden semantisch interessante Namen anstelle der Language-spezifische Schlüsselwörter für Typnamen.</span><span class="sxs-lookup"><span data-stu-id="22650-120">**✓ DO** use semantically interesting names rather than language-specific keywords for type names.</span></span>  
  
 <span data-ttu-id="22650-121">Beispielsweise `GetLength` ist ein besserer Name als `GetInt`.</span><span class="sxs-lookup"><span data-stu-id="22650-121">For example, `GetLength` is a better name than `GetInt`.</span></span>  
  
 <span data-ttu-id="22650-122">**Führen Sie ✓** verwenden Sie eine generische CLR-Typnamen, anstatt einen sprachspezifischen Namen, in den seltenen Fällen, wenn ein Bezeichner keine semantische Bedeutung außer seinem Typ aufweist.</span><span class="sxs-lookup"><span data-stu-id="22650-122">**✓ DO** use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>  
  
 <span data-ttu-id="22650-123">Z. B. eine Methode zum Konvertieren von <xref:System.Int64> heißen `ToInt64`, nicht `ToLong` (da <xref:System.Int64> ist ein CLR-Name für die c#-bestimmten Alias `long`).</span><span class="sxs-lookup"><span data-stu-id="22650-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="22650-124">Die folgende Tabelle enthält einige Basisdatentypen mithilfe der CLR-Typnamen (sowie die zugehörigen Typnamen für c#, Visual Basic und C++).</span><span class="sxs-lookup"><span data-stu-id="22650-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>  
  
|<span data-ttu-id="22650-125">C#</span><span class="sxs-lookup"><span data-stu-id="22650-125">C#</span></span>|<span data-ttu-id="22650-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22650-126">Visual Basic</span></span>|<span data-ttu-id="22650-127">C++</span><span class="sxs-lookup"><span data-stu-id="22650-127">C++</span></span>|<span data-ttu-id="22650-128">CLR</span><span class="sxs-lookup"><span data-stu-id="22650-128">CLR</span></span>|  
|---------|------------------|-----------|---------|  
|<span data-ttu-id="22650-129">**sbyte**</span><span class="sxs-lookup"><span data-stu-id="22650-129">**sbyte**</span></span>|<span data-ttu-id="22650-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="22650-130">**SByte**</span></span>|<span data-ttu-id="22650-131">**char**</span><span class="sxs-lookup"><span data-stu-id="22650-131">**char**</span></span>|<span data-ttu-id="22650-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="22650-132">**SByte**</span></span>|  
|<span data-ttu-id="22650-133">**byte**</span><span class="sxs-lookup"><span data-stu-id="22650-133">**byte**</span></span>|<span data-ttu-id="22650-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="22650-134">**Byte**</span></span>|<span data-ttu-id="22650-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="22650-135">**unsigned char**</span></span>|<span data-ttu-id="22650-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="22650-136">**Byte**</span></span>|  
|<span data-ttu-id="22650-137">**short**</span><span class="sxs-lookup"><span data-stu-id="22650-137">**short**</span></span>|<span data-ttu-id="22650-138">**Short**</span><span class="sxs-lookup"><span data-stu-id="22650-138">**Short**</span></span>|<span data-ttu-id="22650-139">**short**</span><span class="sxs-lookup"><span data-stu-id="22650-139">**short**</span></span>|<span data-ttu-id="22650-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="22650-140">**Int16**</span></span>|  
|<span data-ttu-id="22650-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="22650-141">**ushort**</span></span>|<span data-ttu-id="22650-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="22650-142">**UInt16**</span></span>|<span data-ttu-id="22650-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="22650-143">**unsigned short**</span></span>|<span data-ttu-id="22650-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="22650-144">**UInt16**</span></span>|  
|<span data-ttu-id="22650-145">**int**</span><span class="sxs-lookup"><span data-stu-id="22650-145">**int**</span></span>|<span data-ttu-id="22650-146">**Integer**</span><span class="sxs-lookup"><span data-stu-id="22650-146">**Integer**</span></span>|<span data-ttu-id="22650-147">**int**</span><span class="sxs-lookup"><span data-stu-id="22650-147">**int**</span></span>|<span data-ttu-id="22650-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="22650-148">**Int32**</span></span>|  
|<span data-ttu-id="22650-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="22650-149">**uint**</span></span>|<span data-ttu-id="22650-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="22650-150">**UInt32**</span></span>|<span data-ttu-id="22650-151">**unsigned int**</span><span class="sxs-lookup"><span data-stu-id="22650-151">**unsigned int**</span></span>|<span data-ttu-id="22650-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="22650-152">**UInt32**</span></span>|  
|<span data-ttu-id="22650-153">**long**</span><span class="sxs-lookup"><span data-stu-id="22650-153">**long**</span></span>|<span data-ttu-id="22650-154">**Long**</span><span class="sxs-lookup"><span data-stu-id="22650-154">**Long**</span></span>|<span data-ttu-id="22650-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="22650-155">**__int64**</span></span>|<span data-ttu-id="22650-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="22650-156">**Int64**</span></span>|  
|<span data-ttu-id="22650-157">**ulong**</span><span class="sxs-lookup"><span data-stu-id="22650-157">**ulong**</span></span>|<span data-ttu-id="22650-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="22650-158">**UInt64**</span></span>|<span data-ttu-id="22650-159">**__int64 ohne Vorzeichen**</span><span class="sxs-lookup"><span data-stu-id="22650-159">**unsigned __int64**</span></span>|<span data-ttu-id="22650-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="22650-160">**UInt64**</span></span>|  
|<span data-ttu-id="22650-161">**float**</span><span class="sxs-lookup"><span data-stu-id="22650-161">**float**</span></span>|<span data-ttu-id="22650-162">**Single**</span><span class="sxs-lookup"><span data-stu-id="22650-162">**Single**</span></span>|<span data-ttu-id="22650-163">**float**</span><span class="sxs-lookup"><span data-stu-id="22650-163">**float**</span></span>|<span data-ttu-id="22650-164">**Single**</span><span class="sxs-lookup"><span data-stu-id="22650-164">**Single**</span></span>|  
|<span data-ttu-id="22650-165">**double**</span><span class="sxs-lookup"><span data-stu-id="22650-165">**double**</span></span>|<span data-ttu-id="22650-166">**Double**</span><span class="sxs-lookup"><span data-stu-id="22650-166">**Double**</span></span>|<span data-ttu-id="22650-167">**double**</span><span class="sxs-lookup"><span data-stu-id="22650-167">**double**</span></span>|<span data-ttu-id="22650-168">**Double**</span><span class="sxs-lookup"><span data-stu-id="22650-168">**Double**</span></span>|  
|<span data-ttu-id="22650-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="22650-169">**bool**</span></span>|<span data-ttu-id="22650-170">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="22650-170">**Boolean**</span></span>|<span data-ttu-id="22650-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="22650-171">**bool**</span></span>|<span data-ttu-id="22650-172">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="22650-172">**Boolean**</span></span>|  
|<span data-ttu-id="22650-173">**char**</span><span class="sxs-lookup"><span data-stu-id="22650-173">**char**</span></span>|<span data-ttu-id="22650-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="22650-174">**Char**</span></span>|<span data-ttu-id="22650-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="22650-175">**wchar_t**</span></span>|<span data-ttu-id="22650-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="22650-176">**Char**</span></span>|  
|<span data-ttu-id="22650-177">**string**</span><span class="sxs-lookup"><span data-stu-id="22650-177">**string**</span></span>|<span data-ttu-id="22650-178">**String**</span><span class="sxs-lookup"><span data-stu-id="22650-178">**String**</span></span>|<span data-ttu-id="22650-179">**String**</span><span class="sxs-lookup"><span data-stu-id="22650-179">**String**</span></span>|<span data-ttu-id="22650-180">**String**</span><span class="sxs-lookup"><span data-stu-id="22650-180">**String**</span></span>|  
|<span data-ttu-id="22650-181">**object**</span><span class="sxs-lookup"><span data-stu-id="22650-181">**object**</span></span>|<span data-ttu-id="22650-182">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="22650-182">**Object**</span></span>|<span data-ttu-id="22650-183">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="22650-183">**Object**</span></span>|<span data-ttu-id="22650-184">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="22650-184">**Object**</span></span>|  
  
 <span data-ttu-id="22650-185">**Führen Sie ✓** verwenden Sie einen allgemeinen Namen, z. B. `value` oder `item`, anstatt wiederholen den Typnamen in den seltenen Fällen, wenn ein Bezeichner keine semantische Bedeutung hat und der Typ des Parameters nicht wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="22650-185">**✓ DO**  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>  
  
## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="22650-186">Benennen die neue Versionen der vorhandenen-APIs</span><span class="sxs-lookup"><span data-stu-id="22650-186">Naming New Versions of Existing APIs</span></span>  
 <span data-ttu-id="22650-187">**Führen Sie ✓** einen ähnlichen Namen wie der alte-API verwenden, wenn neue Versionen einer vorhandenen API zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="22650-187">**✓ DO** use a name similar to the old API when creating new versions of an existing API.</span></span>  
  
 <span data-ttu-id="22650-188">Dadurch wird um die Beziehung zwischen der APIs zu markieren.</span><span class="sxs-lookup"><span data-stu-id="22650-188">This helps to highlight the relationship between the APIs.</span></span>  
  
 <span data-ttu-id="22650-189">**Führen Sie ✓** bevorzugen Sie ein Suffix anstelle ein Präfix an, dass eine neue Version einer vorhandenen API hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="22650-189">**✓ DO** prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>  
  
 <span data-ttu-id="22650-190">Dadurch wird die Ermittlung unterstützt, beim Durchsuchen der Dokumentation, oder Verwenden von Intellisense.</span><span class="sxs-lookup"><span data-stu-id="22650-190">This will assist discovery when browsing documentation, or using Intellisense.</span></span> <span data-ttu-id="22650-191">Die alte Version der API wird in der Nähe der neuen APIs organisiert werden, da die meisten Browsern und Intellisense Bezeichner in alphabetischer Reihenfolge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="22650-191">The old version of the API will be organized close to the new APIs, because most browsers and Intellisense show identifiers in alphabetical order.</span></span>  
  
 <span data-ttu-id="22650-192">**✓ GGF.** mithilfe eines brandneuen, jedoch aussagekräftigen-Bezeichners, anstatt ein Suffix oder Präfix.</span><span class="sxs-lookup"><span data-stu-id="22650-192">**✓ CONSIDER** using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>  
  
 <span data-ttu-id="22650-193">**Führen Sie ✓** ein numerisches Suffix verwenden, um eine neue Version einer vorhandenen API anzugeben, insbesondere, wenn der vorhandene Name der API der einzige Name, die sinnvoll ist (d. h., wenn es sich um einen Industriestandard ist) und wenn jeder sinnvolle hinzufügen Suffix (oder Ändern des Namens) keine app Ropriate-Option.</span><span class="sxs-lookup"><span data-stu-id="22650-193">**✓ DO** use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>  
  
 <span data-ttu-id="22650-194">**X nicht** verwenden, die "Ex" (oder ähnlich)-Suffix für einen Bezeichner zur Unterscheidung von einer früheren Version der gleichen-API.</span><span class="sxs-lookup"><span data-stu-id="22650-194">**X DO NOT** use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>  
  
 <span data-ttu-id="22650-195">**Führen Sie ✓** verwenden Sie das Suffix "64", bei der Einführung von Versionen von APIs, die für eine 64-Bit-Ganzzahl (eine lange ganze Zahl) anstelle von 32-Bit-Ganzzahl ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="22650-195">**✓ DO** use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="22650-196">Sie müssen nur so vorgehen möchten, wenn die vorhandene 32-Bit-API vorhanden ist. Führen Sie es für die neuen APIs mit nur einer 64-Bit-Version.</span><span class="sxs-lookup"><span data-stu-id="22650-196">You only need to take this approach when the existing 32-bit API exists; don’t do it for brand new APIs with only a 64-bit version.</span></span>  
  
 <span data-ttu-id="22650-197">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="22650-197">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="22650-198">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="22650-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22650-199">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22650-199">See Also</span></span>  
 [<span data-ttu-id="22650-200">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="22650-200">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="22650-201">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="22650-201">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
