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
ms.openlocfilehash: 1ba99cda512bc5e18c646b09f26672a39c1cf53c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548191"
---
# <a name="xml-character-entities-and-xaml"></a>XML-Zeichenentitäten und XAML

XAML verwendet für Sonderzeichen in XML definierte Zeichenentitäten. In diesem Thema werden einige bestimmte Zeichenentitäten und allgemeine Überlegungen für andere XML-Konzepte in XAML beschrieben.

## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a>XAML-spezifische Zeichenentitäten und Escape-Mechanismen

XAML-Markup verwendet in der Regel dieselben Zeichenentitäten und Escapesequenzen, die in XML definiert sind.

Die wichtigste Ausnahme besteht darin, dass Klammern ({ und }) in XAML eine Bedeutung haben. Sie dienen XAML-Prozessoren als Bezeichner, dass eine in Klammern eingeschlossene Zeichenfolge als Markuperweiterung interpretiert werden muss. Weitere Informationen zur Markuperweiterungen finden Sie unter [Markup Extensions for XAML Overview](markup-extensions-overview.md).

Sie haben dennoch die Möglichkeit, die Klammern als Literalzeichen anzuzeigen, indem Sie eine Escapesequenz verwenden, die für XAML statt für XML spezifisch ist. Weitere Informationen finden Sie unter [ {} Escapesequenz: Markup Erweiterung](escape-sequence-markup-extension.md).

Beachten Sie, dass ein umgekehrter Schrägstrich ( \\ ) keine Escapesequenz erfordert, wenn er als Zeichenfolge behandelt wird.

## <a name="xml-character-entities"></a>XML-Zeichenentitäten

Wie bereits erwähnt, werden die meisten Zeichenentitäten und Escape-Sequenzen, die beim Schreiben von XAML-Markup normalerweise verwendet werden, von XML definiert. Dieses Thema enthält keine vollständige Liste dieser Entitäten. Eine ausführlichere Referenz der Entitäten finden Sie in externer Dokumentation wie in XML-Spezifikationen. Aus praktischen Gründen enthält dieses Thema eine Liste der XML-Zeichenentitäten, die häufig für XAML-Markup verwendet werden.

|Zeichen|Entität|Hinweise|
|---------------|------------|-----------|
|& (kaufmännisches Und-Zeichen)|\&amp;|Muss sowohl in Attributwerten als auch in Elementinhalten verwendet werden.|
|> (größer als-Zeichen)|\&gt;|Muss für einen Attribut Wert verwendet werden, > ist jedoch als Inhalt eines Elements zulässig, solange < nicht vor ihm steht.|
|< (kleiner-als-Zeichen)|\&lt;|Muss für einen Attribut Wert verwendet werden, \< is acceptable as the content of an element as long as > folgt jedoch nicht.|
|" (gerades Anführungszeichen)|\&quot;|Muss in Attributwerten verwendet werden. Jedoch ist ein gerades Anführungszeichen (") in Elementinhalten zulässig. Beachten Sie, dass Attributwerte durch ein einzelnes gerades Anführungszeichen (') oder ein gerades Anführungszeichen (") umschlossen werden können. Das Zeichen, das zuerst vorkommt, wird als Umschließungszeichen für Attributwerte festgelegt, und das andere Zeichen kann im Wert als Literalzeichen verwendet werden.|
|' (einfaches gerades Anführungszeichen)|\&apos;|Muss in Attributwerten verwendet werden. Jedoch ist ein einzelnes gerades Anführungszeichen (') in Elementinhalten zulässig. Beachten Sie, dass Attributwerte durch ein einzelnes gerades Anführungszeichen (') oder ein gerades Anführungszeichen (") umschlossen werden können. Das Zeichen, das zuerst vorkommt, wird als Umschließungszeichen für Attributwerte festgelegt, und das andere Zeichen kann im Wert als Literalzeichen verwendet werden.|
|(Zuordnungen numerischer Zeichen)|&#*[Integer]*; oder & # x *[HEX]*;|XAML unterstützt die Zuordnung numerischer Zeichen in der aktiven Codierung.|
|(geschütztes Leerzeichen)|&\#160; (vorausgesetzt UTF-8-Codierung)|Bei Flussdokumentelementen oder Elementen für die Aufnahme von Text wie <xref:System.Windows.Controls.TextBox> von WPF werden geschützte Leerzeichen nicht außerhalb des Markups normalisiert, auch nicht für  `xml:space="default"`. (Weitere Informationen finden Sie unter [Leerzeichen Verarbeitung in XAML](white-space-processing.md).)|

## <a name="xml-comment-format"></a>Format von XML-Kommentaren

XAML verwendet das XML-Kommentarformat: der Anfang des Kommentars ist `<!--`, das Ende des Kommentars ist `-->,` und die Sequenz `--` darf nicht innerhalb des Kommentars vorkommen.

## <a name="xml-processing-instructions"></a>XML-Verarbeitungsanweisungen

XAML behandelt XML-Verarbeitungsanweisungen gemäß den XML-Spezifikationen, die angeben, dass die Anweisungen übergeben werden müssen. Bei der XAML-Verarbeitung in .net XAML-Diensten werden keine Verarbeitungsanweisungen verwendet. Andere vorhandene Frameworks, die XAML verwenden, verwenden auch keine Verarbeitungsanweisungen von XAML.

## <a name="see-also"></a>Siehe auch

- [Übersicht über XAML (WPF)](../fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
- [XamlName-Grammatik](xamlname-grammar.md)
- [Leerstellenverarbeitung in XAML](white-space-processing.md)
