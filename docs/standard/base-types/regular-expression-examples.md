---
title: Beispiele für reguläre Ausdrücke
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- regular expressions [.NET Framework], examples
- regular expressions [.NET Framework]
- strings [.NET Framework], regular expressions
ms.assetid: e9fd53f2-ed56-4b09-b2ea-e9bc9d65e6d6
ms.openlocfilehash: 788fa2a6793e14189def4c30a0baf0d4a5cf6b0a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128096"
---
# <a name="regular-expression-examples"></a><span data-ttu-id="06381-102">Beispiele für reguläre Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="06381-102">Regular Expression Examples</span></span>
<span data-ttu-id="06381-103">Dieser Abschnitt enthält Codebeispiele, die die Verwendung regulärer Ausdrücke in üblichen Anwendungen veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="06381-103">This section contains code examples that illustrate the use of regular expressions in common applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="06381-104">Der Namespace <xref:System.Web.RegularExpressions> enthält eine Reihe von Objekten für reguläre Ausdrücke, die vordefinierte Muster für reguläre Ausdrucke zum Analysieren von Zeichenfolgen aus HTML-, XML- und ASP.NET-Dokumenten implementieren.</span><span class="sxs-lookup"><span data-stu-id="06381-104">The <xref:System.Web.RegularExpressions> namespace contains a number of regular expression objects that implement predefined regular expression patterns for parsing strings from HTML, XML, and ASP.NET documents.</span></span> <span data-ttu-id="06381-105">Die Klasse <xref:System.Web.RegularExpressions.TagRegex> identifiziert beispielsweise Starttags in einer Zeichenfolge und die Klasse <xref:System.Web.RegularExpressions.CommentRegex> ASP.NET-Kommentare in einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="06381-105">For example, the <xref:System.Web.RegularExpressions.TagRegex> class identifies start tags in a string and the <xref:System.Web.RegularExpressions.CommentRegex> class identifies ASP.NET comments in a string.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="06381-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="06381-106">In This Section</span></span>  
 [<span data-ttu-id="06381-107">Anpassen von mit VSTU Beispiel: Suchen nach HREFs</span><span class="sxs-lookup"><span data-stu-id="06381-107">Example: Scanning for HREFs</span></span>](../../../docs/standard/base-types/regular-expression-example-scanning-for-hrefs.md)  
 <span data-ttu-id="06381-108">Enthält ein Beispiel zum Durchsuchen einer Eingabezeichenfolge, bei dem alle href="..."-Werte sowie ihre Position innerhalb der Zeichenfolge ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="06381-108">Provides an example that searches an input string and prints out all the href="…" values and their locations in the string.</span></span>  
  
 [<span data-ttu-id="06381-109">Anpassen von mit VSTU Beispiel: Ändern von Datumsformaten</span><span class="sxs-lookup"><span data-stu-id="06381-109">Example: Changing Date Formats</span></span>](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)  
 <span data-ttu-id="06381-110">Enthält ein Beispiel, in dem Datumsangaben im Format „mm/tt/jj“ durch Datumsangaben im Format „tt-mm-jj“ ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="06381-110">Provides an example that replaces dates in the form mm/dd/yy with dates in the form dd-mm-yy.</span></span>  
  
 [<span data-ttu-id="06381-111">Vorgehensweise: Extrahieren eines Protokolls und einer Portnummer aus einer URL</span><span class="sxs-lookup"><span data-stu-id="06381-111">How to: Extract a Protocol and Port Number from a URL</span></span>](../../../docs/standard/base-types/how-to-extract-a-protocol-and-port-number-from-a-url.md)  
 <span data-ttu-id="06381-112">Enthält ein Beispiel, in dem ein Protokoll und eine Portnummer aus einer Zeichenfolge extrahiert werden, die eine URL enthält.</span><span class="sxs-lookup"><span data-stu-id="06381-112">Provides an example that extracts a protocol and port number from a string that contains a URL.</span></span> <span data-ttu-id="06381-113">http://www.contoso.com:8080/letters/readme.html gibt beispielsweise "http:8080" zurück.</span><span class="sxs-lookup"><span data-stu-id="06381-113">For example, "http://www.contoso.com:8080/letters/readme.html" returns "http:8080".</span></span>  
  
 [<span data-ttu-id="06381-114">Vorgehensweise: Entfernen von ungültigen Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="06381-114">How to: Strip Invalid Characters from a String</span></span>](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)  
 <span data-ttu-id="06381-115">Enthält ein Beispiel, in dem ungültige, nicht alphanumerische Zeichen aus einer Zeichenfolge entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="06381-115">Provides an example that strips invalid non-alphanumeric characters from a string.</span></span>  
  
 [<span data-ttu-id="06381-116">Vorgehensweise: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen</span><span class="sxs-lookup"><span data-stu-id="06381-116">How to: Verify that Strings Are in Valid Email Format</span></span>](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)  
 <span data-ttu-id="06381-117">Enthält ein Beispiel, mit dem überprüft werden kann, ob eine Zeichenfolge in einem gültigen E-Mail-Format vorliegt.</span><span class="sxs-lookup"><span data-stu-id="06381-117">Provides an example that verifies that a string is in valid email format.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="06381-118">Referenz</span><span class="sxs-lookup"><span data-stu-id="06381-118">Reference</span></span>  
 <xref:System.Text.RegularExpressions>  
 <span data-ttu-id="06381-119">Enthält Informationen zu einer Klassenbibliotheksreferenz für den .NET-Namespace **System.Text.RegularExpressions**.</span><span class="sxs-lookup"><span data-stu-id="06381-119">Provides class library reference information for the .NET **System.Text.RegularExpressions** namespace.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="06381-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="06381-120">Related Sections</span></span>  
 [<span data-ttu-id="06381-121">Reguläre Ausdrücke von .NET</span><span class="sxs-lookup"><span data-stu-id="06381-121">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="06381-122">Übersicht über die programmiersprachenbezogenen Aspekte von regulären Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="06381-122">Provides an overview of the programming language aspect of regular expressions.</span></span>  
  
 [<span data-ttu-id="06381-123">Das Objektmodell für reguläre Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="06381-123">The Regular Expression Object Model</span></span>](../../../docs/standard/base-types/the-regular-expression-object-model.md)  
 <span data-ttu-id="06381-124">Beschreibt die Klassen für reguläre Ausdrücke, die im `System.Text.RegularExpression`-Namespace enthalten sind, und enthält Beispiele für deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="06381-124">Describes the regular expression classes contained in the `System.Text.RegularExpression` namespace and provides examples of their use.</span></span>  
  
 [<span data-ttu-id="06381-125">Einzelheiten zum Verhalten regulärer Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="06381-125">Details of Regular Expression Behavior</span></span>](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)  
 <span data-ttu-id="06381-126">Ausführliche Informationen zu den Funktionen und dem Verhalten von regulären Ausdrücken in .NET.</span><span class="sxs-lookup"><span data-stu-id="06381-126">Provides information about the capabilities and behavior of .NET regular expressions.</span></span>  
  
 [<span data-ttu-id="06381-127">Sprachelemente für reguläre Ausdrücke – Kurzübersicht</span><span class="sxs-lookup"><span data-stu-id="06381-127">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 <span data-ttu-id="06381-128">Informationen zu Zeichensatz, Operatoren und Konstrukten, mit denen Sie reguläre Ausdrücke definieren können.</span><span class="sxs-lookup"><span data-stu-id="06381-128">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
