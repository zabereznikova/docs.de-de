---
title: "XML-Zeichenentitäten und XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '&'
- '&amp'
- '&gt'
- '&lt'
helpviewer_keywords:
- XAML [XAML Services], special characters
- ampersand (&) [XAML Services]
- special characters [XAML Services]
- apostrophe (') [XAML Services]
- greater-than (>) character [XAML Services]
- XAML [XAML Services], quotation mark (")
- XAML [XAML Services], apostrophe (')
- '& (ampersand) [XAML Services]'
- XAML [XAML Services], & (ampersand)
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- less-than (<) character [XAML Services]
ms.assetid: 6896d0ce-74f7-420a-9ab4-de9bbf390e8d
caps.latest.revision: "23"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 5973c67b26e07bba69383cc625ff34493d825a41
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xml-character-entities-and-xaml"></a><span data-ttu-id="c716e-102">XML-Zeichenentitäten und XAML</span><span class="sxs-lookup"><span data-stu-id="c716e-102">XML Character Entities and XAML</span></span>
<span data-ttu-id="c716e-103">XAML verwendet für Sonderzeichen in XML definierte Zeichenentitäten.</span><span class="sxs-lookup"><span data-stu-id="c716e-103">XAML uses character entities defined in XML for special characters.</span></span> <span data-ttu-id="c716e-104">In diesem Thema werden einige bestimmte Zeichenentitäten und allgemeine Überlegungen für andere XML-Konzepte in XAML beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c716e-104">This topic describes some specific character entities and general considerations for other XML concepts in XAML.</span></span>  
  
<a name="character_entities_and_escaping_issues_that_are_unique_to_xaml"></a>   
## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a><span data-ttu-id="c716e-105">XAML-spezifische Zeichenentitäten und Escape-Mechanismen</span><span class="sxs-lookup"><span data-stu-id="c716e-105">Character Entities and Escaping Issues That Are Unique to XAML</span></span>  
 <span data-ttu-id="c716e-106">XAML-Markup verwendet in der Regel dieselben Zeichenentitäten und Escapesequenzen, die in XML definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c716e-106">XAML markup typically uses the same character entities and escape sequences that are defined in XML.</span></span>  
  
 <span data-ttu-id="c716e-107">Die wichtigste Ausnahme besteht darin, dass Klammern ({ und }) in XAML eine Bedeutung haben. Sie dienen XAML-Prozessoren als Bezeichner, dass eine in Klammern eingeschlossene Zeichenfolge als Markuperweiterung interpretiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="c716e-107">The main exception is that braces ({ and }) have significance in XAML because these characters inform a XAML processor that a character sequence enclosed by braces must be interpreted as a markup extension.</span></span> <span data-ttu-id="c716e-108">Weitere Informationen zur Markuperweiterungen finden Sie unter [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c716e-108">For more information about markup extensions, see [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span></span>  
  
 <span data-ttu-id="c716e-109">Sie haben dennoch die Möglichkeit, die Klammern als Literalzeichen anzuzeigen, indem Sie eine Escapesequenz verwenden, die für XAML statt für XML spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="c716e-109">However, you can still display the braces as literal characters by using an escape sequence that is particular to XAML instead of XML.</span></span> <span data-ttu-id="c716e-110">Weitere Informationen finden Sie unter [{} Escape Sequence - Markuperweiterung](escape-sequence-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="c716e-110">For more information, see [{} Escape Sequence - Markup Extension](escape-sequence-markup-extension.md).</span></span>  
  
 <span data-ttu-id="c716e-111">Beachten Sie, dass ein umgekehrter Schrägstrich (\\) eine Escapesequenz ist nicht erforderlich, wenn er als Zeichenfolge behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="c716e-111">Note that a backslash (\\) does not require an escape sequence when it is handled as a string.</span></span>  
  
<a name="xml_character_entities"></a>   
## <a name="xml-character-entities"></a><span data-ttu-id="c716e-112">XML-Zeichenentitäten</span><span class="sxs-lookup"><span data-stu-id="c716e-112">XML Character Entities</span></span>  
 <span data-ttu-id="c716e-113">Wie bereits erwähnt, werden die meisten Zeichenentitäten und Escape-Sequenzen, die beim Schreiben von XAML-Markup normalerweise verwendet werden, von XML definiert.</span><span class="sxs-lookup"><span data-stu-id="c716e-113">As mentioned previously, most character entities and escape sequences that are typically used to write XAML markup are defined by XML.</span></span> <span data-ttu-id="c716e-114">Dieses Thema enthält keine vollständige Liste dieser Entitäten. Eine ausführlichere Referenz der Entitäten finden Sie in externer Dokumentation wie in XML-Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="c716e-114">This topic does not provide the complete list of these entities; a detailed reference for the entities can be found in external documentation, such as in XML specifications.</span></span> <span data-ttu-id="c716e-115">Aus praktischen Gründen enthält dieses Thema eine Liste der XML-Zeichenentitäten, die häufig für XAML-Markup verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c716e-115">However, for convenience, this topic lists some of the specific XML character entities that are typically used in XAML markup.</span></span>  
  
|<span data-ttu-id="c716e-116">Zeichen</span><span class="sxs-lookup"><span data-stu-id="c716e-116">Character</span></span>|<span data-ttu-id="c716e-117">Entität</span><span class="sxs-lookup"><span data-stu-id="c716e-117">Entity</span></span>|<span data-ttu-id="c716e-118">Notizen</span><span class="sxs-lookup"><span data-stu-id="c716e-118">Notes</span></span>|  
|---------------|------------|-----------|  
|<span data-ttu-id="c716e-119">& (Und)</span><span class="sxs-lookup"><span data-stu-id="c716e-119">& (ampersand)</span></span>|&amp;|<span data-ttu-id="c716e-120">Muss sowohl in Attributwerten als auch in Elementinhalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c716e-120">Must be used both for attribute values and for content of an element.</span></span>|  
|<span data-ttu-id="c716e-121">> (Größer als-Zeichen)</span><span class="sxs-lookup"><span data-stu-id="c716e-121">> (greater-than character)</span></span>|&gt;|<span data-ttu-id="c716e-122">Muss in Attributwerten verwendet werden, ist in Elementinhalten zulässig, wenn dem nicht < vorausgeht.</span><span class="sxs-lookup"><span data-stu-id="c716e-122">Must be used for an attribute value, but > is acceptable as the content of an element as long as < does not precede it.</span></span>|  
|<span data-ttu-id="c716e-123">< (Kleiner als-Zeichen)</span><span class="sxs-lookup"><span data-stu-id="c716e-123">< (less-than character)</span></span>|&lt;|<span data-ttu-id="c716e-124">Muss ein Wert des Attributs verwendet werden, aber \< ist in Elementinhalten zulässig, wenn der Inhalt eines Elements solange > stimmt nicht überein.</span><span class="sxs-lookup"><span data-stu-id="c716e-124">Must be used for an attribute value, but \< is acceptable as the content of an element as long as > does not follow it.</span></span>|  
|<span data-ttu-id="c716e-125">" (gerades Anführungszeichen)</span><span class="sxs-lookup"><span data-stu-id="c716e-125">" (straight quotation mark)</span></span>|&quot;|<span data-ttu-id="c716e-126">Muss in Attributwerten verwendet werden. Jedoch ist ein gerades Anführungszeichen (") in Elementinhalten zulässig.</span><span class="sxs-lookup"><span data-stu-id="c716e-126">Must be used for an attribute value, but a straight quotation mark (") is acceptable as the content of an element.</span></span> <span data-ttu-id="c716e-127">Beachten Sie, dass Attributwerte durch ein einzelnes gerades Anführungszeichen (') oder ein gerades Anführungszeichen (") umschlossen werden können. Das Zeichen, das zuerst vorkommt, wird als Umschließungszeichen für Attributwerte festgelegt, und das andere Zeichen kann im Wert als Literalzeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c716e-127">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="c716e-128">' (einfaches gerades Anführungszeichen)</span><span class="sxs-lookup"><span data-stu-id="c716e-128">' (single straight quotation mark)</span></span>|&apos;|<span data-ttu-id="c716e-129">Muss in Attributwerten verwendet werden. Jedoch ist ein einzelnes gerades Anführungszeichen (') in Elementinhalten zulässig.</span><span class="sxs-lookup"><span data-stu-id="c716e-129">Must be used for an attribute value, but a single straight quotation mark (') is acceptable as the content of an element.</span></span> <span data-ttu-id="c716e-130">Beachten Sie, dass Attributwerte durch ein einzelnes gerades Anführungszeichen (') oder ein gerades Anführungszeichen (") umschlossen werden können. Das Zeichen, das zuerst vorkommt, wird als Umschließungszeichen für Attributwerte festgelegt, und das andere Zeichen kann im Wert als Literalzeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c716e-130">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="c716e-131">(Zuordnungen numerischer Zeichen)</span><span class="sxs-lookup"><span data-stu-id="c716e-131">(numeric character mappings)</span></span>|<span data-ttu-id="c716e-132">&#*[Ganzzahl]* ; oder & #x*[Hexadezimalzahl]*;</span><span class="sxs-lookup"><span data-stu-id="c716e-132">&#*[integer]*; or &#x*[hex]*;</span></span>|<span data-ttu-id="c716e-133">XAML unterstützt die Zuordnung numerischer Zeichen in der aktiven Codierung.</span><span class="sxs-lookup"><span data-stu-id="c716e-133">XAML supports numeric character mappings into the encoding that is active.</span></span>|  
|<span data-ttu-id="c716e-134">(geschütztes Leerzeichen)</span><span class="sxs-lookup"><span data-stu-id="c716e-134">(nonbreaking space)</span></span>|<span data-ttu-id="c716e-135">&\#160; (vorausgesetzt, UTF-8-Codierung)</span><span class="sxs-lookup"><span data-stu-id="c716e-135">&\#160; (assuming UTF-8 encoding)</span></span>|<span data-ttu-id="c716e-136">Bei Flussdokumentelementen oder Elementen für die Aufnahme von Text wie <xref:System.Windows.Controls.TextBox> von WPF werden geschützte Leerzeichen nicht außerhalb des Markups normalisiert, auch nicht für  `xml:space="default"`.</span><span class="sxs-lookup"><span data-stu-id="c716e-136">For flow document elements, or elements that take text such as the WPF <xref:System.Windows.Controls.TextBox>, nonbreaking spaces are not normalized out of the markup, even for `xml:space="default"`.</span></span> <span data-ttu-id="c716e-137">(Weitere Informationen finden Sie unter [Leerstellenverarbeitung in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).)</span><span class="sxs-lookup"><span data-stu-id="c716e-137">(For more information, see [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).)</span></span>|  
  
<a name="xml_comment_format"></a>   
## <a name="xml-comment-format"></a><span data-ttu-id="c716e-138">Format von XML-Kommentaren</span><span class="sxs-lookup"><span data-stu-id="c716e-138">XML Comment Format</span></span>  
 <span data-ttu-id="c716e-139">XAML verwendet das XML-Kommentarformat: der Anfang des Kommentars ist `<!--`, das Ende des Kommentars ist `-->,` und die Sequenz `--` darf nicht innerhalb des Kommentars vorkommen.</span><span class="sxs-lookup"><span data-stu-id="c716e-139">XAML uses the XML comment format: the start of the comment is `<!--`, the end of comment is `-->,` and the sequence `--` must not occur within the comment.</span></span>  
  
<a name="xml_processing_instructions"></a>   
## <a name="xml-processing-instructions"></a><span data-ttu-id="c716e-140">XML-Verarbeitungsanweisungen</span><span class="sxs-lookup"><span data-stu-id="c716e-140">XML Processing Instructions</span></span>  
 <span data-ttu-id="c716e-141">XAML behandelt XML-Verarbeitungsanweisungen gemäß den XML-Spezifikationen, die angeben, dass die Anweisungen übergeben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c716e-141">XAML handles XML processing instructions according to XML specifications, which state that the instructions must be passed through.</span></span> <span data-ttu-id="c716e-142">XAML-Verarbeitung in .NET Framework XAML Services verwendet nicht die verarbeitungsanweisungen.</span><span class="sxs-lookup"><span data-stu-id="c716e-142">XAML processing in .NET Framework XAML Services  does not use any processing instructions.</span></span> <span data-ttu-id="c716e-143">Andere vorhandene Frameworks, die XAML verwenden, verwenden auch keine Verarbeitungsanweisungen von XAML.</span><span class="sxs-lookup"><span data-stu-id="c716e-143">Other existing frameworks that use XAML also do not use processing instructions from XAML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c716e-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c716e-144">See Also</span></span>  
 [<span data-ttu-id="c716e-145">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="c716e-145">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="c716e-146">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="c716e-146">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="c716e-147">XamlName-Grammatik</span><span class="sxs-lookup"><span data-stu-id="c716e-147">XamlName Grammar</span></span>](../../../docs/framework/xaml-services/xamlname-grammar.md)  
 [<span data-ttu-id="c716e-148">Leerstellenverarbeitung in XAML</span><span class="sxs-lookup"><span data-stu-id="c716e-148">Whitespace Processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)
