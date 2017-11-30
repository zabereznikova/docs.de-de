---
title: "Beispiele für reguläre Ausdrücke"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- regular expressions [.NET Framework], examples
- regular expressions [.NET Framework]
- strings [.NET Framework], regular expressions
ms.assetid: e9fd53f2-ed56-4b09-b2ea-e9bc9d65e6d6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d7fa8fe2bade9f20f71f846c717d79d6b6ffb36
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-examples"></a><span data-ttu-id="da03b-102">Beispiele für reguläre Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="da03b-102">Regular Expression Examples</span></span>
<span data-ttu-id="da03b-103">Dieser Abschnitt enthält Codebeispiele, die die Verwendung regulärer Ausdrücke in üblichen Anwendungen veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="da03b-103">This section contains code examples that illustrate the use of regular expressions in common applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da03b-104">Die <xref:System.Web.RegularExpressions> Namespace enthält eine Reihe von Objekten für reguläre Ausdrücke, die vordefinierte reguläre Ausdrucksmuster für das Analysieren von Zeichenfolgen aus HTML, XML und ASP.NET Dokumenten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="da03b-104">The <xref:System.Web.RegularExpressions> namespace contains a number of regular expression objects that implement predefined regular expression patterns for parsing strings from HTML, XML, and ASP.NET documents.</span></span> <span data-ttu-id="da03b-105">Z. B. die <xref:System.Web.RegularExpressions.TagRegex> Klasse identifiziert Starttags in einer Zeichenfolge und der <xref:System.Web.RegularExpressions.CommentRegex> Klasse identifiziert ASP.NET Kommentare in einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="da03b-105">For example, the <xref:System.Web.RegularExpressions.TagRegex> class identifies start tags in a string and the <xref:System.Web.RegularExpressions.CommentRegex> class identifies ASP.NET comments in a string.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da03b-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="da03b-106">In This Section</span></span>  
 [<span data-ttu-id="da03b-107">Beispiel: Suchen nach HREFs</span><span class="sxs-lookup"><span data-stu-id="da03b-107">Example: Scanning for HREFs</span></span>](../../../docs/standard/base-types/regular-expression-example-scanning-for-hrefs.md)  
 <span data-ttu-id="da03b-108">Enthält ein Beispiel, das durchsucht eine Eingabezeichenfolge und druckt alle Href = "..." Werte, sowie deren Standorte in der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="da03b-108">Provides an example that searches an input string and prints out all the href="…" values and their locations in the string.</span></span>  
  
 [<span data-ttu-id="da03b-109">Beispiel: Ändern von Datumsformaten</span><span class="sxs-lookup"><span data-stu-id="da03b-109">Example: Changing Date Formats</span></span>](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)  
 <span data-ttu-id="da03b-110">Enthält ein Beispiel, das Datum im Format mm/tt/jj mit Datumsangaben im Format Dd-mm-Yy ersetzt.</span><span class="sxs-lookup"><span data-stu-id="da03b-110">Provides an example that replaces dates in the form mm/dd/yy with dates in the form dd-mm-yy.</span></span>  
  
 [<span data-ttu-id="da03b-111">Gewusst wie: Extrahieren eines Protokolls und einer Portnummer aus einer URL</span><span class="sxs-lookup"><span data-stu-id="da03b-111">How to: Extract a Protocol and Port Number from a URL</span></span>](../../../docs/standard/base-types/how-to-extract-a-protocol-and-port-number-from-a-url.md)  
 <span data-ttu-id="da03b-112">Enthält ein Beispiel, das ein Protokoll und Port-Nummer aus einer Zeichenfolge extrahiert, die eine URL enthält.</span><span class="sxs-lookup"><span data-stu-id="da03b-112">Provides an example that extracts a protocol and port number from a string that contains a URL.</span></span> <span data-ttu-id="da03b-113">Beispiel: „http://www.contoso.com:8080/letters/readme.html“ gibt „http:8080“ zurück.</span><span class="sxs-lookup"><span data-stu-id="da03b-113">For example, "http://www.contoso.com:8080/letters/readme.html" returns "http:8080".</span></span>  
  
 [<span data-ttu-id="da03b-114">Gewusst wie: Entfernen von ungültigen Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="da03b-114">How to: Strip Invalid Characters from a String</span></span>](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)  
 <span data-ttu-id="da03b-115">Enthält ein Beispiel, das ungültige nicht-alphanumerische Zeichen aus einer Zeichenfolge entfernt.</span><span class="sxs-lookup"><span data-stu-id="da03b-115">Provides an example that strips invalid non-alphanumeric characters from a string.</span></span>  
  
 [<span data-ttu-id="da03b-116">Gewusst wie: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen</span><span class="sxs-lookup"><span data-stu-id="da03b-116">How to: Verify that Strings Are in Valid Email Format</span></span>](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)  
 <span data-ttu-id="da03b-117">Enthält ein Beispiel, das Sie verwenden können, um sicherzustellen, dass eine Zeichenfolge gültiges e-Mail-Format aufweist.</span><span class="sxs-lookup"><span data-stu-id="da03b-117">Provides an example that you can use to verify that a string is in valid email format.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="da03b-118">Verweis</span><span class="sxs-lookup"><span data-stu-id="da03b-118">Reference</span></span>  
 <xref:System.Text.RegularExpressions>  
 <span data-ttu-id="da03b-119">Klassenbibliotheksreferenz für .NET bietet **System.Text.RegularExpressions** Namespace.</span><span class="sxs-lookup"><span data-stu-id="da03b-119">Provides class library reference information for the .NET **System.Text.RegularExpressions** namespace.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="da03b-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="da03b-120">Related Sections</span></span>  
 [<span data-ttu-id="da03b-121">Reguläre Ausdrücke von .NET</span><span class="sxs-lookup"><span data-stu-id="da03b-121">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="da03b-122">Übersicht über die programmiersprachenbezogenen Aspekte von regulären Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="da03b-122">Provides an overview of the programming language aspect of regular expressions.</span></span>  
  
 [<span data-ttu-id="da03b-123">Das Objektmodell für reguläre Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="da03b-123">The Regular Expression Object Model</span></span>](../../../docs/standard/base-types/the-regular-expression-object-model.md)  
 <span data-ttu-id="da03b-124">Beschreibt die Klassen für reguläre Ausdrücke enthalten, die der `System.Text.RegularExpression` Namespace sowie Beispiele für deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="da03b-124">Describes the regular expression classes contained in the `System.Text.RegularExpression` namespace and provides examples of their use.</span></span>  
  
 [<span data-ttu-id="da03b-125">Einzelheiten zum Verhalten regulärer Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="da03b-125">Details of Regular Expression Behavior</span></span>](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)  
 <span data-ttu-id="da03b-126">Enthält Informationen zu den Funktionen und das Verhalten von regulären Ausdrücken von .NET.</span><span class="sxs-lookup"><span data-stu-id="da03b-126">Provides information about the capabilities and behavior of .NET regular expressions.</span></span>  
  
 [<span data-ttu-id="da03b-127">Sprachelemente für reguläre Ausdrücke – Kurzübersicht</span><span class="sxs-lookup"><span data-stu-id="da03b-127">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 <span data-ttu-id="da03b-128">Informationen zu Zeichensatz, Operatoren und Konstrukten, mit denen Sie reguläre Ausdrücke definieren können.</span><span class="sxs-lookup"><span data-stu-id="da03b-128">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
