---
title: XML-Zeichenentitäten und XAML
ms.date: 03/30/2017
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
ms.openlocfilehash: b4621da21200e6c9e2b174a0e2ba508a4f6bab92
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228197"
---
# <a name="xml-character-entities-and-xaml"></a>XML-Zeichenentitäten und XAML
XAML verwendet für Sonderzeichen in XML definierte Zeichenentitäten. In diesem Thema werden einige bestimmte Zeichenentitäten und allgemeine Überlegungen für andere XML-Konzepte in XAML beschrieben.  
  
<a name="character_entities_and_escaping_issues_that_are_unique_to_xaml"></a>   
## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a>XAML-spezifische Zeichenentitäten und Escape-Mechanismen  
 XAML-Markup verwendet in der Regel dieselben Zeichenentitäten und Escapesequenzen, die in XML definiert sind.  
  
 Die wichtigste Ausnahme besteht darin, dass Klammern ({ und }) in XAML eine Bedeutung haben. Sie dienen XAML-Prozessoren als Bezeichner, dass eine in Klammern eingeschlossene Zeichenfolge als Markuperweiterung interpretiert werden muss. Weitere Informationen zur Markuperweiterungen finden Sie unter [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).  
  
 Sie haben dennoch die Möglichkeit, die Klammern als Literalzeichen anzuzeigen, indem Sie eine Escapesequenz verwenden, die für XAML statt für XML spezifisch ist. Weitere Informationen finden Sie unter [ {} Escape-Sequence - Markuperweiterung](escape-sequence-markup-extension.md).  
  
 Beachten Sie, dass ein umgekehrter Schrägstrich (\\) erfordert keine Escapesequenz aus, wenn er als Zeichenfolge behandelt wird.  
  
<a name="xml_character_entities"></a>   
## <a name="xml-character-entities"></a>XML-Zeichenentitäten  
 Wie bereits erwähnt, werden die meisten Zeichenentitäten und Escape-Sequenzen, die beim Schreiben von XAML-Markup normalerweise verwendet werden, von XML definiert. Dieses Thema enthält keine vollständige Liste dieser Entitäten. Eine ausführlichere Referenz der Entitäten finden Sie in externer Dokumentation wie in XML-Spezifikationen. Aus praktischen Gründen enthält dieses Thema eine Liste der XML-Zeichenentitäten, die häufig für XAML-Markup verwendet werden.  
  
|Zeichen|Entität|Hinweise|  
|---------------|------------|-----------|  
|& (kaufmännisches und-Zeichen)|\&amp;|Muss sowohl in Attributwerten als auch in Elementinhalten verwendet werden.|  
|> (größer-als-Zeichen)|\&gt;|Für einen Attributwert muss verwendet werden, aber > ist in Elementinhalten zulässig, wenn der Inhalt eines Elements so lange wie < nicht vorausgeht.|  
|< (kleiner-als-Zeichen)|\&lt;|Für einen Attributwert muss verwendet werden, aber \< ist in Elementinhalten zulässig, wenn der Inhalt eines Elements so lange wie > werden nicht befolgt.|  
|" (gerades Anführungszeichen)|\&quot;|Muss in Attributwerten verwendet werden. Jedoch ist ein gerades Anführungszeichen (") in Elementinhalten zulässig. Beachten Sie, dass Attributwerte durch ein einzelnes gerades Anführungszeichen (') oder ein gerades Anführungszeichen (") umschlossen werden können. Das Zeichen, das zuerst vorkommt, wird als Umschließungszeichen für Attributwerte festgelegt, und das andere Zeichen kann im Wert als Literalzeichen verwendet werden.|  
|' (einfaches gerades Anführungszeichen)|\&apos;|Muss in Attributwerten verwendet werden. Jedoch ist ein einzelnes gerades Anführungszeichen (') in Elementinhalten zulässig. Beachten Sie, dass Attributwerte durch ein einzelnes gerades Anführungszeichen (') oder ein gerades Anführungszeichen (") umschlossen werden können. Das Zeichen, das zuerst vorkommt, wird als Umschließungszeichen für Attributwerte festgelegt, und das andere Zeichen kann im Wert als Literalzeichen verwendet werden.|  
|(Zuordnungen numerischer Zeichen)|&#*[Ganzzahl]* ; oder & #x *[Hexadezimalzahl]*;|XAML unterstützt die Zuordnung numerischer Zeichen in der aktiven Codierung.|  
|(geschütztes Leerzeichen)|&\#160; (vorausgesetzt, UTF-8-Codierung)|Bei Flussdokumentelementen oder Elementen für die Aufnahme von Text wie <xref:System.Windows.Controls.TextBox> von WPF werden geschützte Leerzeichen nicht außerhalb des Markups normalisiert, auch nicht für  `xml:space="default"`. (Weitere Informationen finden Sie unter [White-Space-Verarbeitung in XAML](whitespace-processing-in-xaml.md).)|  
  
<a name="xml_comment_format"></a>   
## <a name="xml-comment-format"></a>Format von XML-Kommentaren  
 XAML verwendet das XML-Kommentarformat: der Anfang des Kommentars ist `<!--`, das Ende des Kommentars ist `-->,` und die Sequenz `--` darf nicht innerhalb des Kommentars vorkommen.  
  
<a name="xml_processing_instructions"></a>   
## <a name="xml-processing-instructions"></a>XML-Verarbeitungsanweisungen  
 XAML behandelt XML-Verarbeitungsanweisungen gemäß den XML-Spezifikationen, die angeben, dass die Anweisungen übergeben werden müssen. XAML-Verarbeitung in .NET Framework-XAML-Dienste werden keine verarbeitungsanweisungen verwendet. Andere vorhandene Frameworks, die XAML verwenden, verwenden auch keine Verarbeitungsanweisungen von XAML.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
- [Markuperweiterungen und WPF-XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [XamlName-Grammatik](xamlname-grammar.md)
- [Leerzeichen in XAML verarbeitet](whitespace-processing-in-xaml.md)
