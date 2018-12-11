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
author: KrzysztofCwalina
ms.openlocfilehash: 159635d6e3ce414c8fd45ff7f02a75fd7cbdfe7e
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131091"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="e3309-102">Konventionen für die Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="e3309-102">Capitalization Conventions</span></span>
<span data-ttu-id="e3309-103">Die Richtlinien in diesem Kapitel Layout, eine einfache Methode für die Verwendung von Fall, wenn stellen-IDs für Typen, Member und Parameter, die leicht lesbar konsistent angewendet.</span><span class="sxs-lookup"><span data-stu-id="e3309-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>  
  
## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="e3309-104">Regeln der Groß-/Kleinschreibung für Bezeichner</span><span class="sxs-lookup"><span data-stu-id="e3309-104">Capitalization Rules for Identifiers</span></span>  
 <span data-ttu-id="e3309-105">Profitieren Sie um Wörter in einem Bezeichner zu unterscheiden, die den ersten Buchstaben jedes Worts in den Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="e3309-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="e3309-106">Verwenden Sie keine Unterstriche um Wörter zu unterscheiden oder einfach eine beliebige Stelle in Bezeichnern.</span><span class="sxs-lookup"><span data-stu-id="e3309-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="e3309-107">Es gibt zwei geeignete Möglichkeiten, die Bezeichner, abhängig von der Verwendung des Bezeichners zu profitieren:</span><span class="sxs-lookup"><span data-stu-id="e3309-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>  
  
-   <span data-ttu-id="e3309-108">PascalCasing</span><span class="sxs-lookup"><span data-stu-id="e3309-108">PascalCasing</span></span>  
  
-   <span data-ttu-id="e3309-109">camelCasing</span><span class="sxs-lookup"><span data-stu-id="e3309-109">camelCasing</span></span>  
  
 <span data-ttu-id="e3309-110">Die PascalCasing-Konvention für alle Bezeichner, mit Ausnahme von Parameternamen, nutzt das erste Zeichen jedes Worts (einschließlich Akronyme über zwei Buchstaben), wie in den folgenden Beispielen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e3309-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 <span data-ttu-id="e3309-111">Ein besonderer Fall besteht für zwei Buchstaben bestehenden Akronyme, die in denen beiden Buchstaben in Großbuchstaben angegeben werden, wie in der folgenden Bezeichner dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e3309-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>  
  
 `IOStream`  
  
 <span data-ttu-id="e3309-112">Die CamelCasing-Konvention, die nur für Parameternamen verwendet nutzt das erste Zeichen jedes Worts mit Ausnahme des ersten Worts, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3309-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="e3309-113">Wie das Beispiel auch zeigt, sind zwei Buchstaben bestehenden Akronyme, die einen Bezeichner in Kamel-Schreibweise beginnen Kleinbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="e3309-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 <span data-ttu-id="e3309-114">**✓ DO** verwenden Sie PascalCasing für alle öffentlichen Member, Typnamen und Namespacenamen Namen aus mehreren Wörtern bestehen.</span><span class="sxs-lookup"><span data-stu-id="e3309-114">**✓ DO** use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>  
  
 <span data-ttu-id="e3309-115">**✓ DO** CamelCasing für Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e3309-115">**✓ DO** use camelCasing for parameter names.</span></span>  
  
 <span data-ttu-id="e3309-116">Die folgende Tabelle beschreibt die Regeln der Groß-/Kleinschreibung für verschiedene Arten von Bezeichnern.</span><span class="sxs-lookup"><span data-stu-id="e3309-116">The following table describes the capitalization rules for different types of identifiers.</span></span>  
  
|<span data-ttu-id="e3309-117">ID</span><span class="sxs-lookup"><span data-stu-id="e3309-117">Identifier</span></span>|<span data-ttu-id="e3309-118">Schreibweise</span><span class="sxs-lookup"><span data-stu-id="e3309-118">Casing</span></span>|<span data-ttu-id="e3309-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e3309-119">Example</span></span>|  
|----------------|------------|-------------|  
|<span data-ttu-id="e3309-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="e3309-120">Namespace</span></span>|<span data-ttu-id="e3309-121">Pascal-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="e3309-121">Pascal</span></span>|`namespace System.Security { ... }`|  
|<span data-ttu-id="e3309-122">Typ</span><span class="sxs-lookup"><span data-stu-id="e3309-122">Type</span></span>|<span data-ttu-id="e3309-123">Pascal-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="e3309-123">Pascal</span></span>|`public class StreamReader { ... }`|  
|<span data-ttu-id="e3309-124">Interface</span><span class="sxs-lookup"><span data-stu-id="e3309-124">Interface</span></span>|<span data-ttu-id="e3309-125">Pascal-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="e3309-125">Pascal</span></span>|`public interface IEnumerable { ... }`|  
|<span data-ttu-id="e3309-126">Methode</span><span class="sxs-lookup"><span data-stu-id="e3309-126">Method</span></span>|<span data-ttu-id="e3309-127">Pascal-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="e3309-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|<span data-ttu-id="e3309-128">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e3309-128">Property</span></span>|<span data-ttu-id="e3309-129">Pascal-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="e3309-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|<span data-ttu-id="e3309-130">event</span><span class="sxs-lookup"><span data-stu-id="e3309-130">Event</span></span>|<span data-ttu-id="e3309-131">Pascal-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="e3309-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|<span data-ttu-id="e3309-132">Feld</span><span class="sxs-lookup"><span data-stu-id="e3309-132">Field</span></span>|<span data-ttu-id="e3309-133">Pascal-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="e3309-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|<span data-ttu-id="e3309-134">Enum-Wert</span><span class="sxs-lookup"><span data-stu-id="e3309-134">Enum value</span></span>|<span data-ttu-id="e3309-135">Pascal-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="e3309-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|<span data-ttu-id="e3309-136">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3309-136">Parameter</span></span>|<span data-ttu-id="e3309-137">Camel</span><span class="sxs-lookup"><span data-stu-id="e3309-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="e3309-138">Profitieren Sie von einer zusammengesetzten Wörter und Begriffe</span><span class="sxs-lookup"><span data-stu-id="e3309-138">Capitalizing Compound Words and Common Terms</span></span>  
 <span data-ttu-id="e3309-139">Die meisten zusammengesetzten Wörter werden als einzelne Wörter für Zwecke der Groß-/Kleinschreibung behandelt.</span><span class="sxs-lookup"><span data-stu-id="e3309-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>  
  
 <span data-ttu-id="e3309-140">**X DO NOT** jedes Wort in so genannten geschlossener Form zusammengesetzte Wörter profitieren.</span><span class="sxs-lookup"><span data-stu-id="e3309-140">**X DO NOT** capitalize each word in so-called closed-form compound words.</span></span>  
  
 <span data-ttu-id="e3309-141">Hierbei handelt es sich um zusammengesetzte Wörter, die als einzelnes Wort, z. B. Endpunkt geschrieben.</span><span class="sxs-lookup"><span data-stu-id="e3309-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="e3309-142">Behandeln Sie ein zusammengesetztes Wort in geschlossener Form als einzelnes Wort, für die Richtlinien zur Groß-und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="e3309-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="e3309-143">Verwenden Sie einen aktuellen Wörterbuch, um zu bestimmen, ob ein zusammengesetztes Wort in geschlossene Form geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="e3309-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>  
  
|<span data-ttu-id="e3309-144">Pascal-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="e3309-144">Pascal</span></span>|<span data-ttu-id="e3309-145">Camel</span><span class="sxs-lookup"><span data-stu-id="e3309-145">Camel</span></span>|<span data-ttu-id="e3309-146">Not</span><span class="sxs-lookup"><span data-stu-id="e3309-146">Not</span></span>|  
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
  
## <a name="case-sensitivity"></a><span data-ttu-id="e3309-147">Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="e3309-147">Case Sensitivity</span></span>  
 <span data-ttu-id="e3309-148">Sprachen, die in der CLR ausgeführt werden können sind zur Unterstützung der Instanzenmethode, nicht erforderlich, obwohl einige führen.</span><span class="sxs-lookup"><span data-stu-id="e3309-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="e3309-149">Auch wenn Ihre Sprache unterstützt wird, werden nicht anderen Sprachen, die Ihr Framework zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="e3309-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="e3309-150">Alle APIs, die extern zugegriffen werden kann, werden verlässlich nicht aus diesem Grund Fall allein, zur Unterscheidung zwischen zwei Namen im selben Kontext.</span><span class="sxs-lookup"><span data-stu-id="e3309-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>  
  
 <span data-ttu-id="e3309-151">**X DO NOT** wird davon ausgegangen, dass alle Programmiersprachen die Groß-/Kleinschreibung beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="e3309-151">**X DO NOT** assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="e3309-152">Das sind sie nicht.</span><span class="sxs-lookup"><span data-stu-id="e3309-152">They are not.</span></span> <span data-ttu-id="e3309-153">Namen dürfen sich nicht allein Groß-/Kleinschreibung unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="e3309-153">Names cannot differ by case alone.</span></span>  
  
 <span data-ttu-id="e3309-154">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="e3309-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e3309-155">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="e3309-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3309-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3309-156">See also</span></span>

- [<span data-ttu-id="e3309-157">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="e3309-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="e3309-158">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="e3309-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
