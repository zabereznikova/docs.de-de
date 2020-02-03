---
title: Konventionen für die Groß-/Kleinschreibung
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 8af4a15e1e5b34c38b14c6b547cf44801bbf13e6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741762"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="3f3aa-102">Konventionen für die Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="3f3aa-102">Capitalization Conventions</span></span>
<span data-ttu-id="3f3aa-103">Die Richtlinien in diesem Kapitel stellen eine einfache Methode für den Fall dar, dass, wenn Sie konsistent angewendet wird, Bezeichner für Typen, Member und Parameter leicht lesbar werden.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>

## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="3f3aa-104">Regeln für die Groß Schreibung für Bezeichner</span><span class="sxs-lookup"><span data-stu-id="3f3aa-104">Capitalization Rules for Identifiers</span></span>
 <span data-ttu-id="3f3aa-105">Um Wörter in einem Bezeichner zu unterscheiden, sollten Sie den ersten Buchstaben jedes Worts im Bezeichner Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="3f3aa-106">Verwenden Sie keine Unterstriche zur Unterscheidung von Wörtern oder an einer beliebigen Stelle in bezeichlern.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="3f3aa-107">Es gibt zwei geeignete Möglichkeiten, Bezeichner in Abhängigkeit von der Verwendung des Bezeichners zu nutzen:</span><span class="sxs-lookup"><span data-stu-id="3f3aa-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>

- <span data-ttu-id="3f3aa-108">Pascalschreibweise</span><span class="sxs-lookup"><span data-stu-id="3f3aa-108">PascalCasing</span></span>

- <span data-ttu-id="3f3aa-109">lowercamel</span><span class="sxs-lookup"><span data-stu-id="3f3aa-109">camelCasing</span></span>

 <span data-ttu-id="3f3aa-110">Die pascalidentifier-Konvention, die für alle Bezeichner mit Ausnahme von Parameternamen verwendet wird, erschließt das erste Zeichen jedes Worts (einschließlich der Akronyme über zwei Buchstaben), wie in den folgenden Beispielen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="3f3aa-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>

 `PropertyDescriptor`
 `HtmlTag`

 <span data-ttu-id="3f3aa-111">Ein Sonderfall wird für aus zwei Buchstaben bestehende Akronyme gestellt, in denen beide Buchstaben groß geschrieben werden, wie im folgenden Bezeichner zu sehen:</span><span class="sxs-lookup"><span data-stu-id="3f3aa-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>

 `IOStream`

 <span data-ttu-id="3f3aa-112">Die für Parameternamen verwendete Konvention für die Groß-/Kleinschreibung nutzt das erste Zeichen jedes Worts außer dem ersten Wort, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="3f3aa-113">Wie das Beispiel zeigt, sind zwei Buchstaben Akronyme, die mit einem Kamel Schreib Bezeichner beginnen, in Kleinbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 <span data-ttu-id="3f3aa-114">✔️ für alle öffentlichen Member, Typen und Namespace Namen, die aus mehreren Wörtern bestehen, die Pass-/Schreibweise verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-114">✔️ DO use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>

 <span data-ttu-id="3f3aa-115">✔️ Verwenden Sie "CamelCase" für Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-115">✔️ DO use camelCasing for parameter names.</span></span>

 <span data-ttu-id="3f3aa-116">In der folgenden Tabelle werden die Regeln für die Groß-und Kleinschreibung für verschiedene Bezeichner Typen beschrieben</span><span class="sxs-lookup"><span data-stu-id="3f3aa-116">The following table describes the capitalization rules for different types of identifiers.</span></span>

|<span data-ttu-id="3f3aa-117">Bezeichner</span><span class="sxs-lookup"><span data-stu-id="3f3aa-117">Identifier</span></span>|<span data-ttu-id="3f3aa-118">Schreibweise</span><span class="sxs-lookup"><span data-stu-id="3f3aa-118">Casing</span></span>|<span data-ttu-id="3f3aa-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f3aa-119">Example</span></span>|
|----------------|------------|-------------|
|<span data-ttu-id="3f3aa-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="3f3aa-120">Namespace</span></span>|<span data-ttu-id="3f3aa-121">Pas</span><span class="sxs-lookup"><span data-stu-id="3f3aa-121">Pascal</span></span>|`namespace System.Security { ... }`|
|<span data-ttu-id="3f3aa-122">type</span><span class="sxs-lookup"><span data-stu-id="3f3aa-122">Type</span></span>|<span data-ttu-id="3f3aa-123">Pas</span><span class="sxs-lookup"><span data-stu-id="3f3aa-123">Pascal</span></span>|`public class StreamReader { ... }`|
|<span data-ttu-id="3f3aa-124">Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f3aa-124">Interface</span></span>|<span data-ttu-id="3f3aa-125">Pas</span><span class="sxs-lookup"><span data-stu-id="3f3aa-125">Pascal</span></span>|`public interface IEnumerable { ... }`|
|<span data-ttu-id="3f3aa-126">Methode</span><span class="sxs-lookup"><span data-stu-id="3f3aa-126">Method</span></span>|<span data-ttu-id="3f3aa-127">Pas</span><span class="sxs-lookup"><span data-stu-id="3f3aa-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|<span data-ttu-id="3f3aa-128">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3f3aa-128">Property</span></span>|<span data-ttu-id="3f3aa-129">Pas</span><span class="sxs-lookup"><span data-stu-id="3f3aa-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|<span data-ttu-id="3f3aa-130">Ereignis</span><span class="sxs-lookup"><span data-stu-id="3f3aa-130">Event</span></span>|<span data-ttu-id="3f3aa-131">Pas</span><span class="sxs-lookup"><span data-stu-id="3f3aa-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|<span data-ttu-id="3f3aa-132">Feld</span><span class="sxs-lookup"><span data-stu-id="3f3aa-132">Field</span></span>|<span data-ttu-id="3f3aa-133">Pas</span><span class="sxs-lookup"><span data-stu-id="3f3aa-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|<span data-ttu-id="3f3aa-134">Enumerationswert</span><span class="sxs-lookup"><span data-stu-id="3f3aa-134">Enum value</span></span>|<span data-ttu-id="3f3aa-135">Pas</span><span class="sxs-lookup"><span data-stu-id="3f3aa-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|<span data-ttu-id="3f3aa-136">Parameter</span><span class="sxs-lookup"><span data-stu-id="3f3aa-136">Parameter</span></span>|<span data-ttu-id="3f3aa-137">Groß-/Kleinschreibung gemischt</span><span class="sxs-lookup"><span data-stu-id="3f3aa-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="3f3aa-138">Groß Schreibung von zusammengesetzten Wörtern und allgemeinen Begriffen</span><span class="sxs-lookup"><span data-stu-id="3f3aa-138">Capitalizing Compound Words and Common Terms</span></span>
 <span data-ttu-id="3f3aa-139">Die meisten zusammengesetzten Begriffe werden als einzelne Wörter für die Groß-/Kleinschreibung behandelt.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>

 <span data-ttu-id="3f3aa-140">❌ dürfen nicht jedes Wort in so genannten zusammengesetzten Wörtern mit geschlossenen Formen Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-140">❌ DO NOT capitalize each word in so-called closed-form compound words.</span></span>

 <span data-ttu-id="3f3aa-141">Dabei handelt es sich um zusammengesetzte Wörter, die als einzelnes Wort (z. b. Endpunkt)</span><span class="sxs-lookup"><span data-stu-id="3f3aa-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="3f3aa-142">Um Richtlinien für die Groß-/Kleinschreibung zu beachten, behandeln Sie ein zusammengesetztes Wort als einzelnes Wort.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="3f3aa-143">Verwenden Sie ein Aktuelles Wörterbuch, um zu bestimmen, ob ein Verbund Wort in geschlossener Form geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>

|<span data-ttu-id="3f3aa-144">Pas</span><span class="sxs-lookup"><span data-stu-id="3f3aa-144">Pascal</span></span>|<span data-ttu-id="3f3aa-145">Groß-/Kleinschreibung gemischt</span><span class="sxs-lookup"><span data-stu-id="3f3aa-145">Camel</span></span>|<span data-ttu-id="3f3aa-146">Not</span><span class="sxs-lookup"><span data-stu-id="3f3aa-146">Not</span></span>|
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

## <a name="case-sensitivity"></a><span data-ttu-id="3f3aa-147">Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="3f3aa-147">Case Sensitivity</span></span>
 <span data-ttu-id="3f3aa-148">Für Sprachen, die in der CLR ausgeführt werden können, ist es nicht erforderlich, die Groß-/Kleinschreibung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="3f3aa-149">Auch wenn Ihre Sprache Sie unterstützt, sind andere Sprachen, die möglicherweise auf Ihr Framework zugreifen, nicht.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="3f3aa-150">Alle APIs, die extern zugänglich sind, können sich daher nicht allein auf die Groß-/Kleinschreibung verlassen, um zwischen zwei Namen im gleichen Kontext zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>

 <span data-ttu-id="3f3aa-151">❌ nicht davon ausgehen, dass bei allen Programmiersprachen die Groß-/Kleinschreibung beachtet wird</span><span class="sxs-lookup"><span data-stu-id="3f3aa-151">❌ DO NOT assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="3f3aa-152">Das sind sie nicht.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-152">They are not.</span></span> <span data-ttu-id="3f3aa-153">Namen dürfen nicht allein durch die Groß-/Kleinschreibung abweichen</span><span class="sxs-lookup"><span data-stu-id="3f3aa-153">Names cannot differ by case alone.</span></span>

 <span data-ttu-id="3f3aa-154">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="3f3aa-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="3f3aa-155">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="3f3aa-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="3f3aa-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f3aa-156">See also</span></span>

- [<span data-ttu-id="3f3aa-157">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3f3aa-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="3f3aa-158">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="3f3aa-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
