---
title: Konventionen für die Groß-/Kleinschreibung
description: Wenden Sie die Groß-/Kleinschreibung für Bezeichner, zusammengesetzte Wörter und gängige Begriffe an. Informationen zur Funktionsweise der Groß-/Kleinschreibung in .net
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 4903dc587d84ef36bfaa641cfbda59484266c23c
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767792"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="393ea-104">Konventionen für die Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="393ea-104">Capitalization Conventions</span></span>
<span data-ttu-id="393ea-105">Die Richtlinien in diesem Kapitel stellen eine einfache Methode für den Fall dar, dass, wenn Sie konsistent angewendet wird, Bezeichner für Typen, Member und Parameter leicht lesbar werden.</span><span class="sxs-lookup"><span data-stu-id="393ea-105">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>

## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="393ea-106">Regeln für die Groß Schreibung für Bezeichner</span><span class="sxs-lookup"><span data-stu-id="393ea-106">Capitalization Rules for Identifiers</span></span>
 <span data-ttu-id="393ea-107">Um Wörter in einem Bezeichner zu unterscheiden, sollten Sie den ersten Buchstaben jedes Worts im Bezeichner Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="393ea-107">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="393ea-108">Verwenden Sie keine Unterstriche zur Unterscheidung von Wörtern oder an einer beliebigen Stelle in bezeichlern.</span><span class="sxs-lookup"><span data-stu-id="393ea-108">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="393ea-109">Es gibt zwei geeignete Möglichkeiten, Bezeichner in Abhängigkeit von der Verwendung des Bezeichners zu nutzen:</span><span class="sxs-lookup"><span data-stu-id="393ea-109">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>

- <span data-ttu-id="393ea-110">Pascalschreibweise</span><span class="sxs-lookup"><span data-stu-id="393ea-110">PascalCasing</span></span>

- <span data-ttu-id="393ea-111">lowercamel</span><span class="sxs-lookup"><span data-stu-id="393ea-111">camelCasing</span></span>

 <span data-ttu-id="393ea-112">Die pascalidentifier-Konvention, die für alle Bezeichner mit Ausnahme von Parameternamen verwendet wird, erschließt das erste Zeichen jedes Worts (einschließlich der Akronyme über zwei Buchstaben), wie in den folgenden Beispielen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="393ea-112">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>

 `PropertyDescriptor`
 `HtmlTag`

 <span data-ttu-id="393ea-113">Ein Sonderfall wird für aus zwei Buchstaben bestehende Akronyme gestellt, in denen beide Buchstaben groß geschrieben werden, wie im folgenden Bezeichner zu sehen:</span><span class="sxs-lookup"><span data-stu-id="393ea-113">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>

 `IOStream`

 <span data-ttu-id="393ea-114">Die für Parameternamen verwendete Konvention für die Groß-/Kleinschreibung nutzt das erste Zeichen jedes Worts außer dem ersten Wort, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="393ea-114">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="393ea-115">Wie das Beispiel zeigt, sind zwei Buchstaben Akronyme, die mit einem Kamel Schreib Bezeichner beginnen, in Kleinbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="393ea-115">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 <span data-ttu-id="393ea-116">✔️ für alle öffentlichen Member, Typen und Namespace Namen, die aus mehreren Wörtern bestehen, die Pass-/Schreibweise verwenden.</span><span class="sxs-lookup"><span data-stu-id="393ea-116">✔️ DO use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>

 <span data-ttu-id="393ea-117">✔️ Verwenden Sie "CamelCase" für Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="393ea-117">✔️ DO use camelCasing for parameter names.</span></span>

 <span data-ttu-id="393ea-118">In der folgenden Tabelle werden die Regeln für die Groß-und Kleinschreibung für verschiedene Bezeichner Typen beschrieben</span><span class="sxs-lookup"><span data-stu-id="393ea-118">The following table describes the capitalization rules for different types of identifiers.</span></span>

|<span data-ttu-id="393ea-119">Bezeichner</span><span class="sxs-lookup"><span data-stu-id="393ea-119">Identifier</span></span>|<span data-ttu-id="393ea-120">Schreibweise</span><span class="sxs-lookup"><span data-stu-id="393ea-120">Casing</span></span>|<span data-ttu-id="393ea-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="393ea-121">Example</span></span>|
|----------------|------------|-------------|
|<span data-ttu-id="393ea-122">Namespace</span><span class="sxs-lookup"><span data-stu-id="393ea-122">Namespace</span></span>|<span data-ttu-id="393ea-123">Pas</span><span class="sxs-lookup"><span data-stu-id="393ea-123">Pascal</span></span>|`namespace System.Security { ... }`|
|<span data-ttu-id="393ea-124">type</span><span class="sxs-lookup"><span data-stu-id="393ea-124">Type</span></span>|<span data-ttu-id="393ea-125">Pas</span><span class="sxs-lookup"><span data-stu-id="393ea-125">Pascal</span></span>|`public class StreamReader { ... }`|
|<span data-ttu-id="393ea-126">Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="393ea-126">Interface</span></span>|<span data-ttu-id="393ea-127">Pas</span><span class="sxs-lookup"><span data-stu-id="393ea-127">Pascal</span></span>|`public interface IEnumerable { ... }`|
|<span data-ttu-id="393ea-128">Methode</span><span class="sxs-lookup"><span data-stu-id="393ea-128">Method</span></span>|<span data-ttu-id="393ea-129">Pas</span><span class="sxs-lookup"><span data-stu-id="393ea-129">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|<span data-ttu-id="393ea-130">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="393ea-130">Property</span></span>|<span data-ttu-id="393ea-131">Pas</span><span class="sxs-lookup"><span data-stu-id="393ea-131">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|<span data-ttu-id="393ea-132">Ereignis</span><span class="sxs-lookup"><span data-stu-id="393ea-132">Event</span></span>|<span data-ttu-id="393ea-133">Pas</span><span class="sxs-lookup"><span data-stu-id="393ea-133">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|<span data-ttu-id="393ea-134">Feld</span><span class="sxs-lookup"><span data-stu-id="393ea-134">Field</span></span>|<span data-ttu-id="393ea-135">Pas</span><span class="sxs-lookup"><span data-stu-id="393ea-135">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|<span data-ttu-id="393ea-136">Enumerationswert</span><span class="sxs-lookup"><span data-stu-id="393ea-136">Enum value</span></span>|<span data-ttu-id="393ea-137">Pas</span><span class="sxs-lookup"><span data-stu-id="393ea-137">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|<span data-ttu-id="393ea-138">Parameter</span><span class="sxs-lookup"><span data-stu-id="393ea-138">Parameter</span></span>|<span data-ttu-id="393ea-139">Groß-/Kleinschreibung gemischt</span><span class="sxs-lookup"><span data-stu-id="393ea-139">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="393ea-140">Groß Schreibung von zusammengesetzten Wörtern und allgemeinen Begriffen</span><span class="sxs-lookup"><span data-stu-id="393ea-140">Capitalizing Compound Words and Common Terms</span></span>
 <span data-ttu-id="393ea-141">Die meisten zusammengesetzten Begriffe werden als einzelne Wörter für die Groß-/Kleinschreibung behandelt.</span><span class="sxs-lookup"><span data-stu-id="393ea-141">Most compound terms are treated as single words for purposes of capitalization.</span></span>

 <span data-ttu-id="393ea-142">❌Schreiben Sie nicht jedes Wort in so genannten zusammengesetzten Wörtern mit geschlossenen Formen.</span><span class="sxs-lookup"><span data-stu-id="393ea-142">❌ DO NOT capitalize each word in so-called closed-form compound words.</span></span>

 <span data-ttu-id="393ea-143">Dabei handelt es sich um zusammengesetzte Wörter, die als einzelnes Wort (z. b. Endpunkt)</span><span class="sxs-lookup"><span data-stu-id="393ea-143">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="393ea-144">Um Richtlinien für die Groß-/Kleinschreibung zu beachten, behandeln Sie ein zusammengesetztes Wort als einzelnes Wort.</span><span class="sxs-lookup"><span data-stu-id="393ea-144">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="393ea-145">Verwenden Sie ein Aktuelles Wörterbuch, um zu bestimmen, ob ein Verbund Wort in geschlossener Form geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="393ea-145">Use a current dictionary to determine if a compound word is written in closed form.</span></span>

|<span data-ttu-id="393ea-146">Pas</span><span class="sxs-lookup"><span data-stu-id="393ea-146">Pascal</span></span>|<span data-ttu-id="393ea-147">Groß-/Kleinschreibung gemischt</span><span class="sxs-lookup"><span data-stu-id="393ea-147">Camel</span></span>|<span data-ttu-id="393ea-148">Not</span><span class="sxs-lookup"><span data-stu-id="393ea-148">Not</span></span>|
|------------|-----------|---------|
|`BitFlag`|`bitFlag`|`Bitflag`|
|`Callback`|`callback`|`CallBack`|
|`Canceled`|`canceled`|`Cancelled`|
|`DoNot`|`doNot`|`Don't`|
|`Email`|`email`|`EMail`|
|`Endpoint`|`endpoint`|`EndPoint`|
|`FileName`|`fileName`|`Filename`|
|`Gridline`|`gridline`|`GridLine`|
|`Hashtable`|`hashtable`|`HashTable`|
|`Id`|`id`|`ID`|
|`Indexes`|`indexes`|`Indices`|
|`LogOff`|`logOff`|`LogOut`|
|`LogOn`|`logOn`|`LogIn`|
|`Metadata`|`metadata`|`MetaData, metaData`|
|`Multipanel`|`multipanel`|`MultiPanel`|
|`Multiview`|`multiview`|`MultiView`|
|`Namespace`|`namespace`|`NameSpace`|
|`Ok`|`ok`|`OK`|
|`Pi`|`pi`|`PI`|
|`Placeholder`|`placeholder`|`PlaceHolder`|
|`SignIn`|`signIn`|`SignOn`|
|`SignOut`|`signOut`|`SignOff`|
|`UserName`|`userName`|`Username`|
|`WhiteSpace`|`whiteSpace`|`Whitespace`|
|`Writable`|`writable`|`Writeable`|

## <a name="case-sensitivity"></a><span data-ttu-id="393ea-149">Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="393ea-149">Case Sensitivity</span></span>
 <span data-ttu-id="393ea-150">Für Sprachen, die in der CLR ausgeführt werden können, ist es nicht erforderlich, die Groß-/Kleinschreibung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="393ea-150">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="393ea-151">Auch wenn Ihre Sprache Sie unterstützt, sind andere Sprachen, die möglicherweise auf Ihr Framework zugreifen, nicht.</span><span class="sxs-lookup"><span data-stu-id="393ea-151">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="393ea-152">Alle APIs, die extern zugänglich sind, können sich daher nicht allein auf die Groß-/Kleinschreibung verlassen, um zwischen zwei Namen im gleichen Kontext zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="393ea-152">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>

 <span data-ttu-id="393ea-153">❌Nehmen Sie nicht an, dass die Groß-/Kleinschreibung für alle Programmiersprachen</span><span class="sxs-lookup"><span data-stu-id="393ea-153">❌ DO NOT assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="393ea-154">Das sind sie nicht.</span><span class="sxs-lookup"><span data-stu-id="393ea-154">They are not.</span></span> <span data-ttu-id="393ea-155">Namen dürfen nicht allein durch die Groß-/Kleinschreibung abweichen</span><span class="sxs-lookup"><span data-stu-id="393ea-155">Names cannot differ by case alone.</span></span>

 <span data-ttu-id="393ea-156">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="393ea-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="393ea-157">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="393ea-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="393ea-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="393ea-158">See also</span></span>

- [<span data-ttu-id="393ea-159">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="393ea-159">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="393ea-160">Benennungs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="393ea-160">Naming Guidelines</span></span>](naming-guidelines.md)
