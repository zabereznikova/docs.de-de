---
title: UriTemplate und UriTemplateTable
ms.date: 03/30/2017
ms.assetid: 5cbbe03f-4a9e-4d44-9e02-c5773239cf52
ms.openlocfilehash: da34753867db17fd8ea1bd36bc705b3518d6d650
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976010"
---
# <a name="uritemplate-and-uritemplatetable"></a><span data-ttu-id="3c0c3-102">UriTemplate und UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="3c0c3-102">UriTemplate and UriTemplateTable</span></span>
<span data-ttu-id="3c0c3-103">Webentwickler müssen in der Lage sein, die Form und das Layout der URIs zu beschreiben, auf die ihre Dienste reagieren.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-103">Web developers require the ability to describe the shape and layout of the URIs that their services respond to.</span></span> <span data-ttu-id="3c0c3-104">Windows Communication Foundation (WCF) hat zwei neue Klassen hinzugefügt, um Entwicklern die Kontrolle über Ihre URIs zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-104">Windows Communication Foundation (WCF) added two new classes to give developers control over their URIs.</span></span> <span data-ttu-id="3c0c3-105"><xref:System.UriTemplate> und <xref:System.UriTemplateTable> bilden die Basis des URI-basierten Dispatchmoduls in WCF.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-105"><xref:System.UriTemplate> and <xref:System.UriTemplateTable> form the basis of the URI-based dispatch engine in WCF.</span></span> <span data-ttu-id="3c0c3-106">Diese Klassen können auch eigenständig verwendet werden, sodass Entwickler Vorlagen und den URI-Zuordnungsmechanismus nutzen können, ohne einen WCF-Dienst implementieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-106">These classes can also be used on their own, allowing developers to take advantage of templates and the URI mapping mechanism without implementing a WCF service.</span></span>  
  
## <a name="templates"></a><span data-ttu-id="3c0c3-107">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="3c0c3-107">Templates</span></span>  
 <span data-ttu-id="3c0c3-108">Eine Vorlage ist eine Möglichkeit, einen Satz relativer URIs zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-108">A template is a way to describe a set of relative URIs.</span></span> <span data-ttu-id="3c0c3-109">Der Satz von URI-Vorlagen in der folgenden Tabelle zeigt, wie ein System, das verschiedene Arten von Wetterdaten abruft, definiert werden könnte.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-109">The set of URI templates in the following table shows how a system that retrieves various types of weather information might be defined.</span></span>  
  
|<span data-ttu-id="3c0c3-110">Daten</span><span class="sxs-lookup"><span data-stu-id="3c0c3-110">Data</span></span>|<span data-ttu-id="3c0c3-111">Vorlage</span><span class="sxs-lookup"><span data-stu-id="3c0c3-111">Template</span></span>|  
|----------|--------------|  
|<span data-ttu-id="3c0c3-112">Nationale Vorhersage</span><span class="sxs-lookup"><span data-stu-id="3c0c3-112">National Forecast</span></span>|<span data-ttu-id="3c0c3-113">Wetter/national</span><span class="sxs-lookup"><span data-stu-id="3c0c3-113">weather/national</span></span>|  
|<span data-ttu-id="3c0c3-114">Bundeslandvorhersage</span><span class="sxs-lookup"><span data-stu-id="3c0c3-114">State Forecast</span></span>|<span data-ttu-id="3c0c3-115">Wetter/{Staat}</span><span class="sxs-lookup"><span data-stu-id="3c0c3-115">weather/{state}</span></span>|  
|<span data-ttu-id="3c0c3-116">Ortsvorhersage</span><span class="sxs-lookup"><span data-stu-id="3c0c3-116">City Forecast</span></span>|<span data-ttu-id="3c0c3-117">Wetter/{Bundesland}/{Stadt}</span><span class="sxs-lookup"><span data-stu-id="3c0c3-117">weather/{state}/{city}</span></span>|  
|<span data-ttu-id="3c0c3-118">Aktivitätsvorhersage</span><span class="sxs-lookup"><span data-stu-id="3c0c3-118">Activity Forecast</span></span>|<span data-ttu-id="3c0c3-119">Wetter/{Bundesland}/{Stadt}/{Aktivität}</span><span class="sxs-lookup"><span data-stu-id="3c0c3-119">weather/{state}/{city}/{activity}</span></span>|  
  
 <span data-ttu-id="3c0c3-120">In dieser Tabelle wird ein Satz strukturell ähnlicher URIs beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-120">This table describes a set of structurally similar URIs.</span></span> <span data-ttu-id="3c0c3-121">Jeder Eintrag ist eine URI-Vorlage.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-121">Each entry is a URI template.</span></span> <span data-ttu-id="3c0c3-122">Die Segmente in geschweiften Klammern beschreiben Variablen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-122">The segments in curly braces describe variables.</span></span> <span data-ttu-id="3c0c3-123">Die Segmente, die nicht in geschweifte Klammern eingefasst sind, beschreiben Literalzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-123">The segments not in curly braces describe literal strings.</span></span> <span data-ttu-id="3c0c3-124">Die WCF-Vorlagen Klassen ermöglichen es einem Entwickler, einen eingehenden URI zu akzeptieren, z. b. "/weather/WA/Seattle/Cycling", und ihn mit einer Vorlage zu vergleichen, die ihn beschreibt: "/Weather/{State}/{City}/{Activity}".</span><span class="sxs-lookup"><span data-stu-id="3c0c3-124">The WCF template classes allow a developer to take an incoming URI, for example, "/weather/wa/seattle/cycling", and match it to a template that describes it, "/weather/{state}/{city}/{activity}".</span></span>  
  
## <a name="uritemplate"></a><span data-ttu-id="3c0c3-125">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="3c0c3-125">UriTemplate</span></span>  
 <span data-ttu-id="3c0c3-126"><xref:System.UriTemplate> ist eine Klasse, die eine URI-Vorlage kapselt.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-126"><xref:System.UriTemplate> is a class that encapsulates a URI template.</span></span> <span data-ttu-id="3c0c3-127">Der Konstruktor nimmt einen Zeichenfolgenparameter, der die Vorlage definiert.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-127">The constructor takes a string parameter that defines the template.</span></span> <span data-ttu-id="3c0c3-128">Diese Zeichenfolge enthält die Vorlage in dem im nächsten Abschnitt beschriebenen Format.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-128">This string contains the template in the format described in the next section.</span></span> <span data-ttu-id="3c0c3-129">Die <xref:System.UriTemplate>-Klasse bietet Methoden, die die Zuordnung eines eingehenden URI zu einer Vorlage, die Generierung eines URI aus einer Vorlage, das Abrufen einer Sammlung von Variablennamen, die in der Vorlage verwendet werden, die Bestimmung, ob zwei Vorlagen gleichwertig sind, und die Ausgabe der Zeichenfolge der Vorlage ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-129">The <xref:System.UriTemplate> class provides methods that allow you match an incoming URI to a template, generate a URI from a template, retrieve a collection of variable names used in the template, determine whether two templates are equivalent, and return the template's string.</span></span>  
  
 <span data-ttu-id="3c0c3-130"><xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> nimmt eine Basisadresse und einen möglichen URI und versucht, den URI der Vorlage zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-130"><xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> takes a base address and a candidate URI and attempts to match the URI to the template.</span></span> <span data-ttu-id="3c0c3-131">Wenn die Zuordnung erfolgreich ist, wird eine <xref:System.UriTemplateMatch>-Instanz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-131">If the match is successful, a <xref:System.UriTemplateMatch> instance is returned.</span></span> <span data-ttu-id="3c0c3-132">Das <xref:System.UriTemplateMatch>-Objekt enthält einen Basis-URI, den möglichen URI, eine Name-Wert-Sammlung der Abfrageparameter, eine Matrix der Segmente des relativen Pfads, eine Name-Wert-Sammlung der Variablen, die zugeordnet wurden, die <xref:System.UriTemplate>-Instanz, die zum Durchführen der Zuordnung verwendet wurde, eine Zeichenfolge, die jeden nicht zugeordneten Teil des Kandidaten-URI enthält (wird verwendet, wenn die Vorlage über einen Platzhalter verfügt), und ein Objekt, das der Vorlage zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-132">The <xref:System.UriTemplateMatch> object contains a base URI, the candidate URI, a name/value collection of the query parameters, an array of the relative path segments, a name/value collection of variables that were matched, the <xref:System.UriTemplate> instance used to perform the match, a string that contains any unmatched portion of the candidate URI (used when the template has a wildcard), and an object that is associated with the template.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c0c3-133">Beim Vergleichen eines möglichen URIs mit einer Vorlage ignoriert die <xref:System.UriTemplate>-Klasse das Schema und die Portnummer.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-133">The <xref:System.UriTemplate> class ignores the scheme and port number when matching a candidate URI to a template.</span></span>  
  
 <span data-ttu-id="3c0c3-134">Zum Generieren eines URI aus einer Vorlage stehen zwei Methoden zur Verfügung: <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> und <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-134">There are two methods that allow you to generate a URI from a template, <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> and <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>.</span></span> <span data-ttu-id="3c0c3-135"><xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> akzeptiert eine Basisadresse und eine Name-Wert-Auflistung der Parameter.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-135"><xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> takes a base address and a name/value collection of parameters.</span></span> <span data-ttu-id="3c0c3-136">Wenn die Vorlage gebunden ist, werden diese Parameter durch Variablen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-136">These parameters are substituted for variables when the template is bound.</span></span> <span data-ttu-id="3c0c3-137"><xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> akzeptiert die Name-Wert-Paare und ersetzt sie von links nach rechts.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-137"><xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> takes the name/value pairs and substitutes them left to right.</span></span>  
  
 <span data-ttu-id="3c0c3-138"><xref:System.UriTemplate.ToString> gibt die Vorlagenzeichenfolge zurück,</span><span class="sxs-lookup"><span data-stu-id="3c0c3-138"><xref:System.UriTemplate.ToString> returns the template string.</span></span>  
  
 <span data-ttu-id="3c0c3-139">Die <xref:System.UriTemplate.PathSegmentVariableNames%2A>-Eigenschaft enthält eine Sammlung der Namen der Variablen, die innerhalb der Pfadsegmente in der Vorlagenzeichenfolge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-139">The <xref:System.UriTemplate.PathSegmentVariableNames%2A> property contains a collection of the names of the variables used within path segments in the template string.</span></span>  
  
 <span data-ttu-id="3c0c3-140"><xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> akzeptiert <xref:System.UriTemplate> als Parameter und gibt einen booleschen Wert zurück, der angibt, ob die beiden Vorlagen gleichwertig sind.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-140"><xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> takes a <xref:System.UriTemplate> as a parameter and returns a Boolean value that specifies whether the two templates are equivalent.</span></span> <span data-ttu-id="3c0c3-141">Weitere Informationen finden Sie im Abschnitt "Vorlagen Äquivalenz" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-141">For more information, see the Template Equivalence section later in this topic.</span></span>  
  
 <span data-ttu-id="3c0c3-142"><xref:System.UriTemplate> wurde für die Zusammenarbeit mit einem URI-Schema entwickelt, das der HTTP URI-Grammatik entspricht.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-142"><xref:System.UriTemplate> is designed to work with any URI scheme that conforms to the HTTP URI grammar.</span></span> <span data-ttu-id="3c0c3-143">Im Folgenden finden Sie Beispiele für unterstützte URI-Schemas:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-143">The following are examples of supported URI schemes.</span></span>  
  
- <span data-ttu-id="3c0c3-144">http://</span><span class="sxs-lookup"><span data-stu-id="3c0c3-144">http://</span></span>  
  
- <span data-ttu-id="3c0c3-145">https://</span><span class="sxs-lookup"><span data-stu-id="3c0c3-145">https://</span></span>  
  
- <span data-ttu-id="3c0c3-146">net.tcp://</span><span class="sxs-lookup"><span data-stu-id="3c0c3-146">net.tcp://</span></span>  
  
- <span data-ttu-id="3c0c3-147">net.pipe://</span><span class="sxs-lookup"><span data-stu-id="3c0c3-147">net.pipe://</span></span>  
  
- <span data-ttu-id="3c0c3-148">sb://</span><span class="sxs-lookup"><span data-stu-id="3c0c3-148">sb://</span></span>  
  
 <span data-ttu-id="3c0c3-149">Schemas wie "file://" und "urn://" entsprechen nicht der HTTP-URI-Grammatik und führen bei der Verwendung mit URI-Vorlagen zu unvorhersehbaren Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-149">Schemes like file:// and urn:// do not conform to the HTTP URI grammar and cause unpredictable results when used with URI templates.</span></span>  
  
### <a name="template-string-syntax"></a><span data-ttu-id="3c0c3-150">Vorlagenzeichenfolgen-Syntax</span><span class="sxs-lookup"><span data-stu-id="3c0c3-150">Template String Syntax</span></span>  
 <span data-ttu-id="3c0c3-151">Eine Vorlage besteht aus drei Teilen: einem Pfad, einer optionalen Abfrage und einem optionalen Fragment.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-151">A template has three parts: a path, an optional query, and an optional fragment.</span></span> <span data-ttu-id="3c0c3-152">Ein Beispiel finden Sie in der folgenden Vorlage:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-152">For an example, see the following template:</span></span>  
  
`"/weather/{state}/{city}?forecast={length)#frag1`  
  
 <span data-ttu-id="3c0c3-153">Der Pfad besteht aus "/Wetter/{Bundesland}/{Ort}", die Abfrage besteht aus "?forecast={Länge}, und das Fragment besteht aus "#frag1."</span><span class="sxs-lookup"><span data-stu-id="3c0c3-153">The path consists of "/weather/{state}/{city}", the query consists of "?forecast={length}, and the fragment consists of "#frag1".</span></span>  
  
 <span data-ttu-id="3c0c3-154">Führende und nachstehende Schrägstriche sind im Pfadausdruck optional.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-154">Leading and trailing slashes are optional in the path expression.</span></span> <span data-ttu-id="3c0c3-155">Sowohl der Abfrage- als auch der Fragmentausdruck kann vollständig weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-155">Both the query and fragment expressions can be omitted entirely.</span></span> <span data-ttu-id="3c0c3-156">Ein Pfad besteht aus einer Reihe von Segmenten, die durch '/' getrennt sind, wobei jedes Segment einen Literalwert, einen Variablennamen (geschrieben in {geschweiften Klammern}) oder einen Platzhalter (als '\*' geschrieben) aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-156">A path consists of a series of segments delimited by '/', each segment can have a literal value, a variable name (written in {curly braces}), or a wildcard (written as '\*').</span></span> <span data-ttu-id="3c0c3-157">In der vorherigen Vorlage ist das "\Wetter\"-Segment ein Literalwert, während "{Bundesland}" und "{Ort}" Variablen sind.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-157">In the previous template the "\weather\ segment is a literal value while "{state}" and "{city}" are variables.</span></span> <span data-ttu-id="3c0c3-158">Variablen nehmen Ihren Namen aus dem Inhalt Ihrer geschweiften Klammern und können später durch einen konkreten Wert ersetzt werden, um einen *geschlossenen URI*zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-158">Variables take their name from the contents of their curly braces and they can later be replaced with a concrete value to create a *closed URI*.</span></span> <span data-ttu-id="3c0c3-159">Der Platzhalter ist optional, kann jedoch nur am Ende des URIs angezeigt werden, wo er "der restliche Pfad" logisch entspricht.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-159">The wildcard is optional, but can only appear at the end of the URI, where it logically matches "the rest of the path".</span></span>  
  
 <span data-ttu-id="3c0c3-160">Der Abfrage Ausdruck gibt, sofern vorhanden, eine Reihe von ungeordneten Name-Wert-Paaren an, die durch ' & ' getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-160">The query expression, if present, specifies a series of unordered name/value pairs delimited by '&'.</span></span> <span data-ttu-id="3c0c3-161">Bei den Elementen des Abfrageausdrucks kann es sich entweder um Literalpaare (x=2) oder ein Variablenpaar (x={var}) handeln.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-161">Elements of the query expression can either be literal pairs (x=2) or a variable pair (x={var}).</span></span> <span data-ttu-id="3c0c3-162">Nur die rechte Seite der Abfrage kann einen variablen Ausdruck enthalten.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-162">Only the right side of the query can have a variable expression.</span></span> <span data-ttu-id="3c0c3-163">({someName} = {someValue} ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-163">({someName} = {someValue} is not allowed.</span></span> <span data-ttu-id="3c0c3-164">Ungepaarte Werte (?x) sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-164">Unpaired values (?x) are not permitted.</span></span> <span data-ttu-id="3c0c3-165">Es besteht kein Unterschied zwischen einem leeren Abfrageausdruck und einem Abfrageausdruck, der aus einem einzelnen "?" besteht (beide stehen für "jede Abfrage").</span><span class="sxs-lookup"><span data-stu-id="3c0c3-165">There is no difference between an empty query expression and a query expression consisting of just a single '?' (both mean "any query").</span></span>  
  
 <span data-ttu-id="3c0c3-166">Der Fragmentausdruck kann aus einem Literalwert bestehen, Variablen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-166">The fragment expression can consist of a literal value, no variables are allowed.</span></span>  
  
 <span data-ttu-id="3c0c3-167">Alle Vorlagenvariablennamen innerhalb einer Vorlagenzeichenfolge müssen eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-167">All template variable names within a template string must be unique.</span></span> <span data-ttu-id="3c0c3-168">Bei Namen von Vorlagenvariablen wird die Groß- und Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-168">Template variable names are case-insensitive.</span></span>  
  
 <span data-ttu-id="3c0c3-169">Beispiele für gültige Vorlagenzeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-169">Examples of valid template strings:</span></span>  
  
- <span data-ttu-id="3c0c3-170">""</span><span class="sxs-lookup"><span data-stu-id="3c0c3-170">""</span></span>  
  
- <span data-ttu-id="3c0c3-171">"/Schuh"</span><span class="sxs-lookup"><span data-stu-id="3c0c3-171">"/shoe"</span></span>  
  
- <span data-ttu-id="3c0c3-172">"/Shoe/\*"</span><span class="sxs-lookup"><span data-stu-id="3c0c3-172">"/shoe/\*"</span></span>  
  
- <span data-ttu-id="3c0c3-173">"{Schuh}/Boot"</span><span class="sxs-lookup"><span data-stu-id="3c0c3-173">"{shoe}/boat"</span></span>  
  
- <span data-ttu-id="3c0c3-174">"{Schuh}/{Boat}/Bed/{Quilt}"</span><span class="sxs-lookup"><span data-stu-id="3c0c3-174">"{shoe}/{boat}/bed/{quilt}"</span></span>  
  
- <span data-ttu-id="3c0c3-175">"Schuh/{Boots}"</span><span class="sxs-lookup"><span data-stu-id="3c0c3-175">"shoe/{boat}"</span></span>  
  
- <span data-ttu-id="3c0c3-176">"Schuh/{Boots}/\*"</span><span class="sxs-lookup"><span data-stu-id="3c0c3-176">"shoe/{boat}/\*"</span></span>  
  
- <span data-ttu-id="3c0c3-177">"Schuh/Boot? x = 2"</span><span class="sxs-lookup"><span data-stu-id="3c0c3-177">"shoe/boat?x=2"</span></span>  
  
- <span data-ttu-id="3c0c3-178">"Schuh/{Boot}? x = {Bed}"</span><span class="sxs-lookup"><span data-stu-id="3c0c3-178">"shoe/{boat}?x={bed}"</span></span>  
  
- <span data-ttu-id="3c0c3-179">"Schuh/{Boot}? x = {Bed} & y = Band"</span><span class="sxs-lookup"><span data-stu-id="3c0c3-179">"shoe/{boat}?x={bed}&y=band"</span></span>  
  
- <span data-ttu-id="3c0c3-180">"? x = {Schuh}"</span><span class="sxs-lookup"><span data-stu-id="3c0c3-180">"?x={shoe}"</span></span>  
  
- <span data-ttu-id="3c0c3-181">"Schuh? x = 3 & y = {var}</span><span class="sxs-lookup"><span data-stu-id="3c0c3-181">"shoe?x=3&y={var}</span></span>  
  
 <span data-ttu-id="3c0c3-182">Beispiele für ungültige Vorlagenzeichenfolgen sind:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-182">Examples of invalid template strings:</span></span>  
  
- <span data-ttu-id="3c0c3-183">"{Schuh}/{Shoe}/x = 2" – doppelte Variablennamen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-183">"{shoe}/{SHOE}/x=2" – Duplicate variable names.</span></span>  
  
- <span data-ttu-id="3c0c3-184">"{Schuh}/Boat/? Bed = {Schuh}" – doppelte Variablennamen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-184">"{shoe}/boat/?bed={shoe}" – Duplicate variable names.</span></span>  
  
- <span data-ttu-id="3c0c3-185">"? x = 2 & x = 3" – Name/Wert-Paare innerhalb einer Abfrage Zeichenfolge müssen eindeutig sein, auch wenn Sie Literale sind.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-185">"?x=2&x=3" – Name/value pairs within a query string must be unique, even if they are literals.</span></span>  
  
- <span data-ttu-id="3c0c3-186">"? x = 2 &" – Abfrage Zeichenfolge ist falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-186">"?x=2&" – Query string is malformed.</span></span>  
  
- <span data-ttu-id="3c0c3-187">"? 2 & x = {Schuh}" – Abfrage Zeichenfolge muss Name-Wert-Paare sein.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-187">"?2&x={shoe}" – Query string must be name/value pairs.</span></span>  
  
- <span data-ttu-id="3c0c3-188">"? y = 2 & & X = 3" – Abfrage Zeichenfolge muss Name-Wert-Paare sein, Namen dürfen nicht mit "&" beginnen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-188">"?y=2&&X=3" – Query string must be name value pairs, names cannot start with '&'.</span></span>  
  
### <a name="compound-path-segments"></a><span data-ttu-id="3c0c3-189">Zusammengesetzte Pfadsegmente</span><span class="sxs-lookup"><span data-stu-id="3c0c3-189">Compound Path Segments</span></span>  
 <span data-ttu-id="3c0c3-190">Bei zusammengesetzten Pfadsegmenten kann ein einzelnes URI-Pfadsegment mehrere Variablen sowie mit Literalwerten kombinierte Variablen enhalten.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-190">Compound path segments allow a single URI path segment to contain multiple variables as well as variables combined with literals.</span></span> <span data-ttu-id="3c0c3-191">Im Folgenden finden Sie Beispiele für gültige zusammengesetzte Pfadsegmente:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-191">The following are examples of valid compound path segments.</span></span>  
  
- <span data-ttu-id="3c0c3-192">/Dateiname.{Erw.}/</span><span class="sxs-lookup"><span data-stu-id="3c0c3-192">/filename.{ext}/</span></span>  
  
- <span data-ttu-id="3c0c3-193">/{Dateiname}.jpg/</span><span class="sxs-lookup"><span data-stu-id="3c0c3-193">/{filename}.jpg/</span></span>  
  
- <span data-ttu-id="3c0c3-194">/{Dateiname}.{Erw.}/</span><span class="sxs-lookup"><span data-stu-id="3c0c3-194">/{filename}.{ext}/</span></span>  
  
- <span data-ttu-id="3c0c3-195">/{a}.{b}Literalwert{c}({d})/</span><span class="sxs-lookup"><span data-stu-id="3c0c3-195">/{a}.{b}someLiteral{c}({d})/</span></span>  
  
 <span data-ttu-id="3c0c3-196">Im Folgenden finden Sie Beispiele für ungültige Pfadsegmente:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-196">The following are examples of invalid path segments.</span></span>  
  
- <span data-ttu-id="3c0c3-197">/{}-Variablen müssen benannt werden.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-197">/{} - Variables must be named.</span></span>  
  
- <span data-ttu-id="3c0c3-198">/{Schuh}{Boot} – Variablen müssen durch einen Literalwert getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-198">/{shoe}{boat} - Variables must be separated by a literal.</span></span>  
  
### <a name="matching-and-compound-path-segments"></a><span data-ttu-id="3c0c3-199">Zuordnung und zusammengesetzte Pfadsegmente</span><span class="sxs-lookup"><span data-stu-id="3c0c3-199">Matching and Compound Path Segments</span></span>  
 <span data-ttu-id="3c0c3-200">Zusammengesetzte Pfadsegmente ermöglichen Ihnen das Definieren einer UriTemplate mit mehreren Variablen in nur einem Pfadsegment.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-200">Compound path segments allow you to define a UriTemplate that has multiple variables within a single path segment.</span></span> <span data-ttu-id="3c0c3-201">Beispielsweise in der folgenden Vorlagen Zeichenfolge: "Adressen/{State}". {City} "zwei Variablen (State und City) werden innerhalb desselben Segments definiert.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-201">For example, in the following template string: "Addresses/{state}.{city}" two variables (state and city) are defined within the same segment.</span></span> <span data-ttu-id="3c0c3-202">Diese Vorlage entspricht einer URL, z. b. `http://example.com/Washington.Redmond`, aber Sie entspricht auch einer URL wie `http://example.com/Washington.Redmond.Microsoft`.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-202">This template would match a URL such as `http://example.com/Washington.Redmond` but it will also match an URL like `http://example.com/Washington.Redmond.Microsoft`.</span></span> <span data-ttu-id="3c0c3-203">Im letzteren Fall enthält die Zustands Variable "Washington", und die City-Variable enthält "Redmond. Microsoft".</span><span class="sxs-lookup"><span data-stu-id="3c0c3-203">In the latter case, the state variable will contain "Washington" and the city variable will contain "Redmond.Microsoft".</span></span> <span data-ttu-id="3c0c3-204">In diesem Fall entspricht jeder Text (mit Ausnahme von "/") der {city}-Variable.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-204">In this case any text (except ‘/’) will match the {city} variable.</span></span> <span data-ttu-id="3c0c3-205">Wenn Sie eine Vorlage erstellen möchten, die nicht dem "zusätzlichen" Text entspricht, platzieren Sie die Variable in einem separaten Vorlagen Segment, z. b. "Adressen/{State}/{City}".</span><span class="sxs-lookup"><span data-stu-id="3c0c3-205">If you want a template that will not match the "extra" text, place the variable in a separate template segment, for example: "Addresses/{state}/{city}.</span></span>  
  
### <a name="named-wildcard-segments"></a><span data-ttu-id="3c0c3-206">Benannte Platzhaltersegmente</span><span class="sxs-lookup"><span data-stu-id="3c0c3-206">Named Wildcard Segments</span></span>  
 <span data-ttu-id="3c0c3-207">Ein benanntes Platzhalter Segment ist ein beliebiges Pfad Variablen Segment, dessen Variablenname mit dem Platzhalter Zeichen "\*" beginnt.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-207">A named wildcard segment is any path variable segment whose variable name begins with the wildcard character ‘\*’.</span></span> <span data-ttu-id="3c0c3-208">Die folgende Vorlagenzeichenfolge enthält ein benanntes Platzhaltersegment mit dem Namen "Schuh".</span><span class="sxs-lookup"><span data-stu-id="3c0c3-208">The following template string contains a named wildcard segment named "shoe".</span></span>  
  
`"literal/{*shoe}"`  
  
 <span data-ttu-id="3c0c3-209">Für Platzhaltersegmente gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-209">Wildcard segments must follow the following rules:</span></span>  
  
- <span data-ttu-id="3c0c3-210">Für jede Vorlagenzeichenfolge kann höchstens ein benanntes Platzhaltersegment vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-210">There can be at most one named wildcard segment for each template string.</span></span>  
  
- <span data-ttu-id="3c0c3-211">Ein benanntes Platzhaltersegment muss sich im am weitesten rechts stehenden Segment des Pfads befinden.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-211">A named wildcard segment must appear at the right-most segment in the path.</span></span>  
  
- <span data-ttu-id="3c0c3-212">Ein benanntes Platzhaltersegment kann nicht zusammen mit einem anonymen Platzhaltersegment innerhalb der gleichen Vorlagenzeichenfolge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-212">A named wildcard segment cannot coexist with an anonymous wildcard segment within the same template string.</span></span>  
  
- <span data-ttu-id="3c0c3-213">Der Name eines benannten Platzhaltersegments muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-213">The name of a named wildcard segment must be unique.</span></span>  
  
- <span data-ttu-id="3c0c3-214">Benannte Platzhaltersegmente können keine Standardwerte besitzen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-214">Named wildcard segments cannot have default values.</span></span>  
  
- <span data-ttu-id="3c0c3-215">Benannte Platzhalter Segmente dürfen nicht auf "/" enden.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-215">Named wildcard segments cannot end with "/".</span></span>  
  
### <a name="default-variable-values"></a><span data-ttu-id="3c0c3-216">Standardvariablenwerte</span><span class="sxs-lookup"><span data-stu-id="3c0c3-216">Default Variable Values</span></span>  
 <span data-ttu-id="3c0c3-217">Standardvariablenwerte ermöglichen das Angeben von Standardwerten für Variablen innerhalb einer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-217">Default variable values allow you to specify default values for variables within a template.</span></span> <span data-ttu-id="3c0c3-218">Standardvariablen können mit den geschweiften Klammern, durch die die Variable deklariert wird, oder durch eine an den UriTemplate-Konstruktor weitergegebene Sammlung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-218">Default variables can be specified with the curly braces that declare the variable or as a collection passed to the UriTemplate constructor.</span></span> <span data-ttu-id="3c0c3-219">Die folgende Vorlage zeigt zwei Möglichkeiten, eine <xref:System.UriTemplate> mit Variablen mit Standardwerten anzugeben:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-219">The following template shows two ways to specify a <xref:System.UriTemplate> with variables with default values.</span></span>  
  
```csharp
UriTemplate t = new UriTemplate("/test/{a=1}/{b=5}");  
```  
  
 <span data-ttu-id="3c0c3-220">In dieser Vorlage werden die Variable `a` mit dem Standardwert `1` und die Variable `b` mit dem Standardwert `5` deklariert.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-220">This template declares a variable named `a` with a default value of `1` and a variable named `b` with a default value of `5`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c0c3-221">Nur Pfadsegmentvariablen können Standardwerte besitzen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-221">Only path segment variables are allowed to have default values.</span></span> <span data-ttu-id="3c0c3-222">Bei Abfragezeichenfolgenvariablen, zusammengesetzten Segmentvariablen sowie bei benannten Platzhaltervariablen sind Standardwerte nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-222">Query string variables, compound segment variables, and named wildcard variables are not permitted to have default values.</span></span>  
  
 <span data-ttu-id="3c0c3-223">Im folgenden Code wird die Behandlung von Standardvariablenwerten beim Abgleichen eines möglichen URI gezeigt:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-223">The following code shows how default variable values are handled when matching a candidate URI.</span></span>  
  
```csharp
Uri baseAddress = new Uri("http://localhost:8000/");

UriTemplate t = new UriTemplate("/{state=WA}/{city=Redmond}/", true);
Uri candidate = new Uri("http://localhost:8000/OR");

UriTemplateMatch m1 = t.Match(baseAddress, candidate);

Console.WriteLine($"Template: {t}");
Console.WriteLine($"Candidate URI: {candidate}");

// Display contents of BoundVariables
Console.WriteLine("BoundVariables:");
foreach (string key in m1.BoundVariables.AllKeys)
{
    Console.WriteLine($"\t{key}={m1.BoundVariables[key]}");
}
// The output of the above code is  
// Template: /{state=WA}/{city=Redmond}/
// Candidate URI: http://localhost:8000/OR
// BoundVariables:
//         STATE=OR
//         CITY=Redmond
```  
  
> [!NOTE]
> <span data-ttu-id="3c0c3-224">Ein URI, wie z. b. `http://localhost:8000///`, stimmt nicht mit der im vorangehenden Code aufgelisteten Vorlage, es gibt jedoch einen URI wie `http://localhost:8000/`.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-224">A URI such as `http://localhost:8000///` does not match the template listed in the preceding code, however a URI such as `http://localhost:8000/` does.</span></span>  
  
 <span data-ttu-id="3c0c3-225">Im folgenden Code wird die Behandlung von Standardvariablenwerten beim Erstellen eines URI mit einer Vorlage veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-225">The following code shows how default variable values are handled when creating a URI with a template.</span></span>  
  
```csharp
Uri baseAddress = new Uri("http://localhost:8000/");  
Dictionary<string,string> defVals = new Dictionary<string,string> {{"a","1"}, {"b", "5"}};  
UriTemplate t = new UriTemplate("/test/{a}/{b}", defVals);  
NameValueCollection vals = new NameValueCollection();  
vals.Add("a", "10");  
  
Uri boundUri = t.BindByName(baseAddress, vals);  
Console.WriteLine("BaseAddress: {0}", baseAddress);  
Console.WriteLine("Template: {0}", t.ToString());  
  
Console.WriteLine("Values: ");  
foreach (string key in vals.AllKeys)  
{  
    Console.WriteLine("\tKey = {0}, Value = {1}", key, vals[key]);  
}  
Console.WriteLine("Bound URI: {0}", boundUri);  
  
// The output of the preceding code is  
// BaseAddress: http://localhost:8000/  
// Template: /test/{a}/{b}  
// Values:  
//     Key = a, Value = 10  
// Bound URI: http://localhost:8000/test/10/5  
```  
  
<span data-ttu-id="3c0c3-226">Erhält eine Variable den Standardwert `null`, gelten einige zusätzliche Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-226">When a variable is given a default value of `null` there are some additional constraints.</span></span> <span data-ttu-id="3c0c3-227">Eine Variable kann den Standardwert `null` besitzen, wenn sich die Variable im am weitesten rechts befindlichen Segment der Vorlagenzeichenfolge befindet oder wenn alle Segmente rechts des Segments jeweils den Standardwert `null` besitzen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-227">A variable can have a default value of `null` if the variable is contained within the right most segment of the template string or if all segments to the right of the segment have default values of `null`.</span></span> <span data-ttu-id="3c0c3-228">Im Folgenden finden Sie gültige Vorlagenzeichenfolgen mit dem Standardwert `null`:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-228">The following are valid template strings with default values of `null`:</span></span>  
  
- `UriTemplate t = new UriTemplate("shoe/{boat=null}");`

- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=null}");`
  
- `UriTemplate t = new UriTemplate("{shoe=1}/{boat=null}");`

 <span data-ttu-id="3c0c3-229">Im folgenden sind ungültige Vorlagen Zeichenfolgen mit den Standardwerten `null`aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-229">The following are invalid template strings with default values of `null`:</span></span>  
  
- `UriTemplate t = new UriTemplate("{shoe=null}/boat"); // null default must be in the right most path segment`
  
- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=x}/{bed=null}"); // shoe cannot have a null default because boat does not have a default null value`

### <a name="default-values-and-matching"></a><span data-ttu-id="3c0c3-230">Standardwerte und Vergleich</span><span class="sxs-lookup"><span data-stu-id="3c0c3-230">Default Values and Matching</span></span>  
 <span data-ttu-id="3c0c3-231">Beim Vergleichen eines möglichen URI mit einer Vorlage mit Standardwerten werden die Standardwerte in der <xref:System.UriTemplateMatch.BoundVariables%2A>-Sammlung platziert, wenn im möglichen URI keine Werte angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-231">When matching a candidate URI with a template that has default values, the default values are placed in the <xref:System.UriTemplateMatch.BoundVariables%2A> collection if values are not specified in the candidate URI.</span></span>  
  
### <a name="template-equivalence"></a><span data-ttu-id="3c0c3-232">Vorlagenäquivalenz</span><span class="sxs-lookup"><span data-stu-id="3c0c3-232">Template Equivalence</span></span>  
 <span data-ttu-id="3c0c3-233">Zwei Vorlagen werden als *strukturell äquivalent* bezeichnet, wenn alle Literale der Vorlage übereinstimmen und Sie Variablen in denselben Segmenten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-233">Two templates are said to be *structurally equivalent* when all of the templates' literals match and they have variables in the same segments.</span></span> <span data-ttu-id="3c0c3-234">Beispielsweise sind die folgenden Vorlagen strukturell äquivalent:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-234">For example the following templates are structurally equivalent:</span></span>  
  
- <span data-ttu-id="3c0c3-235">/a/{var1}/b b/{var2}? x = 1 & y = 2</span><span class="sxs-lookup"><span data-stu-id="3c0c3-235">/a/{var1}/b b/{var2}?x=1&y=2</span></span>  
  
- <span data-ttu-id="3c0c3-236">a/{x}/b% 20b/{var1}? y = 2 & x = 1</span><span class="sxs-lookup"><span data-stu-id="3c0c3-236">a/{x}/b%20b/{var1}?y=2&x=1</span></span>  
  
- <span data-ttu-id="3c0c3-237">a/{y}/B% 20b/{z}/? y = 2 & x = 1</span><span class="sxs-lookup"><span data-stu-id="3c0c3-237">a/{y}/B%20B/{z}/?y=2&x=1</span></span>  
  
 <span data-ttu-id="3c0c3-238">Hierbei müssen noch einige Punkte beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-238">A few things to notice:</span></span>  
  
- <span data-ttu-id="3c0c3-239">Wenn eine Vorlage führende Schrägstriche enthält, wird nur der erste ignoriert.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-239">If a template contains leading slashes, only the first one is ignored.</span></span>  
  
- <span data-ttu-id="3c0c3-240">Wenn Vorlagenzeichenfolgen auf strukturelle Äquivalenz verglichen werden, wird die Groß-/Kleinschreibungen bei den Variablennamen und Pfadsegmenten ignoriert; bei den Abfragezeichenfolgen muss sie beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-240">When comparing template strings for structural equivalence, case is ignored for variable names and path segments, query strings are case sensitive.</span></span>  
  
- <span data-ttu-id="3c0c3-241">Abfragezeichenfolgen sind unsortiert.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-241">Query strings are unordered.</span></span>  
  
## <a name="uritemplatetable"></a><span data-ttu-id="3c0c3-242">UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="3c0c3-242">UriTemplateTable</span></span>  
 <span data-ttu-id="3c0c3-243">Die Klasse <xref:System.UriTemplateTable> stellt eine assoziative Tabelle aus <xref:System.UriTemplate>-Objekten dar, die an ein Objekt nach Wahl des Entwicklers gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-243">The <xref:System.UriTemplateTable> class represents an associative table of <xref:System.UriTemplate> objects bound to an object of the developer's choosing.</span></span> <span data-ttu-id="3c0c3-244"><xref:System.UriTemplateTable> muss vor Aufruf von <xref:System.UriTemplate> mindestens eine <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> enthalten.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-244">A <xref:System.UriTemplateTable> must contain at least one <xref:System.UriTemplate> prior to calling <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span> <span data-ttu-id="3c0c3-245">Der Inhalt einer <xref:System.UriTemplateTable> kann geändert werden, bis <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-245">The contents of a <xref:System.UriTemplateTable> can be changed until <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="3c0c3-246">Die Überprüfung wird ausgeführt, wenn <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-246">Validation is performed when <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="3c0c3-247">Der Typ der ausgeführten Validierung hängt vom Wert des Parameters `allowMultiple` zur <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> ab.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-247">The type of validation performed depends upon the value of the `allowMultiple` parameter to <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span>  
  
 <span data-ttu-id="3c0c3-248">Wenn <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> bei Übergabe in `false` aufgerufen wird, überprüft die <xref:System.UriTemplateTable>, dass sich keine Vorlagen in der Tabelle befinden.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-248">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `false`, the <xref:System.UriTemplateTable> checks to make sure there are no templates in the table.</span></span> <span data-ttu-id="3c0c3-249">Wenn strukturell äquivalente Vorlagen gefunden werden, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-249">If it finds any structurally equivalent templates, it throws an exception.</span></span> <span data-ttu-id="3c0c3-250">Dies wird zusammen mit <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> verwendet, wenn sichergestellt werden soll, dass nur eine Vorlage einem eingehenden URI entspricht.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-250">This is used in conjunction with <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> when you want to ensure only one template matches an incoming URI.</span></span>  
  
 <span data-ttu-id="3c0c3-251">Wenn <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> bei der Übergabe von `true` aufgerufen wird, lässt <xref:System.UriTemplateTable> mehrere strukturell äquivalente Vorlagen in einer <xref:System.UriTemplateTable> zu.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-251">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `true`, <xref:System.UriTemplateTable> allows multiple, structurally-equivalent templates to be contained within a <xref:System.UriTemplateTable>.</span></span>  
  
 <span data-ttu-id="3c0c3-252">Wenn ein Satz <xref:System.UriTemplate>-Objekte, die einer <xref:System.UriTemplateTable> hinzugefügt sind, Abfragezeichenfolgen enthält, dürfen sie nicht mehrdeutig sein.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-252">If a set of <xref:System.UriTemplate> objects added to a <xref:System.UriTemplateTable> contain query strings they must not be ambiguous.</span></span> <span data-ttu-id="3c0c3-253">Identische Abfragezeichenfolgen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-253">Identical query strings are allowed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c0c3-254">Zwar lässt die <xref:System.UriTemplateTable> Basisadressen mit HTTP-fremden Schemas zu, Schema und Portnummer werden beim Vergleichen möglicher URIs mit Vorlagen jedoch ignoriert.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-254">While the <xref:System.UriTemplateTable> allows base addresses that use schemes other than HTTP, the scheme and port number are ignored when matching candidate URIs to templates.</span></span>  
  
### <a name="query-string-ambiguity"></a><span data-ttu-id="3c0c3-255">Abfragezeichenfolgenmehrdeutigkeit</span><span class="sxs-lookup"><span data-stu-id="3c0c3-255">Query String Ambiguity</span></span>  
 <span data-ttu-id="3c0c3-256">Vorlagen, die einen äquivalenten Pfad teilen, enthalten mehrdeutige Abfragezeichenfolgen, wenn es einen URI gibt, der mehr als einer Vorlage entspricht.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-256">Templates that share an equivalent path contain ambiguous query strings if there is a URI that matches more than one template.</span></span>  
  
 <span data-ttu-id="3c0c3-257">Die folgenden Sätze von Abfragezeichenfolgen sind in sich selbst eindeutig:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-257">The following sets of query strings are unambiguous within themselves:</span></span>  
  
- <span data-ttu-id="3c0c3-258">?x=1</span><span class="sxs-lookup"><span data-stu-id="3c0c3-258">?x=1</span></span>  
  
- <span data-ttu-id="3c0c3-259">?x=2</span><span class="sxs-lookup"><span data-stu-id="3c0c3-259">?x=2</span></span>  
  
- <span data-ttu-id="3c0c3-260">?x=3</span><span class="sxs-lookup"><span data-stu-id="3c0c3-260">?x=3</span></span>  
  
- <span data-ttu-id="3c0c3-261">? x = 1 & y = {var}</span><span class="sxs-lookup"><span data-stu-id="3c0c3-261">?x=1&y={var}</span></span>  
  
- <span data-ttu-id="3c0c3-262">? x = 2 & z = {var}</span><span class="sxs-lookup"><span data-stu-id="3c0c3-262">?x=2&z={var}</span></span>  
  
- <span data-ttu-id="3c0c3-263">?x=3</span><span class="sxs-lookup"><span data-stu-id="3c0c3-263">?x=3</span></span>  
  
- <span data-ttu-id="3c0c3-264">?x=1</span><span class="sxs-lookup"><span data-stu-id="3c0c3-264">?x=1</span></span>  
  
- <span data-ttu-id="3c0c3-265">?</span><span class="sxs-lookup"><span data-stu-id="3c0c3-265">?</span></span>  
  
- <span data-ttu-id="3c0c3-266">?</span><span class="sxs-lookup"><span data-stu-id="3c0c3-266">?</span></span> <span data-ttu-id="3c0c3-267">x={var}</span><span class="sxs-lookup"><span data-stu-id="3c0c3-267">x={var}</span></span>  
  
- <span data-ttu-id="3c0c3-268">?</span><span class="sxs-lookup"><span data-stu-id="3c0c3-268">?</span></span>  
  
- <span data-ttu-id="3c0c3-269">? m = get & c = RSS</span><span class="sxs-lookup"><span data-stu-id="3c0c3-269">?m=get&c=rss</span></span>  
  
- <span data-ttu-id="3c0c3-270">? m = Put & c = RSS</span><span class="sxs-lookup"><span data-stu-id="3c0c3-270">?m=put&c=rss</span></span>  
  
- <span data-ttu-id="3c0c3-271">? m = get & c = Atom</span><span class="sxs-lookup"><span data-stu-id="3c0c3-271">?m=get&c=atom</span></span>  
  
- <span data-ttu-id="3c0c3-272">? m = Put & c = Atom</span><span class="sxs-lookup"><span data-stu-id="3c0c3-272">?m=put&c=atom</span></span>  
  
 <span data-ttu-id="3c0c3-273">Die folgenden Abfragezeichenfolgenvorlagen sind in sich selbst mehrdeutig:</span><span class="sxs-lookup"><span data-stu-id="3c0c3-273">The following sets of query string templates are ambiguous within themselves:</span></span>  
  
- <span data-ttu-id="3c0c3-274">?x=1</span><span class="sxs-lookup"><span data-stu-id="3c0c3-274">?x=1</span></span>  
  
- <span data-ttu-id="3c0c3-275">?x={var}</span><span class="sxs-lookup"><span data-stu-id="3c0c3-275">?x={var}</span></span>  
  
 <span data-ttu-id="3c0c3-276">"x=1" – passt zu beiden Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-276">"x=1" - Matches both templates.</span></span>  
  
- <span data-ttu-id="3c0c3-277">?x=1</span><span class="sxs-lookup"><span data-stu-id="3c0c3-277">?x=1</span></span>  
  
- <span data-ttu-id="3c0c3-278">?y=2</span><span class="sxs-lookup"><span data-stu-id="3c0c3-278">?y=2</span></span>  
  
 <span data-ttu-id="3c0c3-279">"x = 1 & y = 2" entspricht beiden Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-279">"x=1&y=2" matches both templates.</span></span> <span data-ttu-id="3c0c3-280">Das liegt daran, dass eine Abfragezeichenfolge mehr Abfragezeichenfolgen-Variablen enthalten kann als die Vorlage, zu der sie passt.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-280">This is because a query string may contain more query string variables then the template it matches.</span></span>  
  
- <span data-ttu-id="3c0c3-281">?x=1</span><span class="sxs-lookup"><span data-stu-id="3c0c3-281">?x=1</span></span>  
  
- <span data-ttu-id="3c0c3-282">? x = 1 & y = {var}</span><span class="sxs-lookup"><span data-stu-id="3c0c3-282">?x=1&y={var}</span></span>  
  
 <span data-ttu-id="3c0c3-283">"x = 1 & y = 3" entspricht beiden Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="3c0c3-283">"x=1&y=3" matches both templates.</span></span>  
  
- <span data-ttu-id="3c0c3-284">? x = 3 & y = 4</span><span class="sxs-lookup"><span data-stu-id="3c0c3-284">?x=3&y=4</span></span>  
  
- <span data-ttu-id="3c0c3-285">? x = 3 & z = 5</span><span class="sxs-lookup"><span data-stu-id="3c0c3-285">?x=3&z=5</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c0c3-286">Die Zeichen "á" und "Á" gelten als unterschiedliche Zeichen, wenn sie als Teil eines URI-Pfads oder eines <xref:System.UriTemplate>-Pfadsegmentliterals verwendet werden. (Die Zeichen "a" und "A" gelten hingegen als gleich.)</span><span class="sxs-lookup"><span data-stu-id="3c0c3-286">The characters á and Á are considered to be different characters when they appear as part of a URI path or <xref:System.UriTemplate> path segment literal (but the characters a and A are considered to be the same).</span></span> <span data-ttu-id="3c0c3-287">Die Zeichen á und Á gelten als gleiche Zeichen, wenn sie als Teil einer <xref:System.UriTemplate> {Variablenname} oder einer Abfragezeichenfolge erscheinen (a und A gelten ebenfalls als gleiche Zeichen).</span><span class="sxs-lookup"><span data-stu-id="3c0c3-287">The characters á and Á are considered to be the same characters when they appear as part of a <xref:System.UriTemplate> {variableName} or a query string (and a and A are also considered to be the same characters).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c0c3-288">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c0c3-288">See also</span></span>

- [<span data-ttu-id="3c0c3-289">Überblick über das WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="3c0c3-289">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)
- [<span data-ttu-id="3c0c3-290">Objektmodell für WCF-Web-HTTP-Programmierung</span><span class="sxs-lookup"><span data-stu-id="3c0c3-290">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)
- [<span data-ttu-id="3c0c3-291">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="3c0c3-291">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
- [<span data-ttu-id="3c0c3-292">UriTemplate-Tabelle</span><span class="sxs-lookup"><span data-stu-id="3c0c3-292">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [<span data-ttu-id="3c0c3-293">UriTemplate-Tabellenverteiler</span><span class="sxs-lookup"><span data-stu-id="3c0c3-293">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
