---
title: "XML Character Entities and XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "&"
  - "&amp"
  - "&gt"
  - "&lt"
helpviewer_keywords: 
  - "XAML [XAML Services], special characters"
  - "ampersand (&) [XAML Services]"
  - "special characters [XAML Services]"
  - "apostrophe (') [XAML Services]"
  - "greater-than (>) character [XAML Services]"
  - "XAML [XAML Services], quotation mark (")"
  - "XAML [XAML Services], apostrophe (')"
  - "& (ampersand) [XAML Services]"
  - "XAML [XAML Services], & (ampersand)"
  - "XAML [XAML Services], escape sequence"
  - "quotation mark (") [XAML Services]"
  - "less-than (<) character [XAML Services]"
ms.assetid: 6896d0ce-74f7-420a-9ab4-de9bbf390e8d
caps.latest.revision: 23
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 21
---
# XML Character Entities and XAML
XAML verwendet für Sonderzeichen in XML definierte Zeichenentitäten.  In diesem Thema werden einige bestimmte Zeichenentitäten und allgemeine Überlegungen für andere XML\-Konzepte in XAML beschrieben.  
  
<a name="character_entities_and_escaping_issues_that_are_unique_to_xaml"></a>   
## XAML\-spezifische Zeichenentitäten und Escape\-Mechanismen  
 XAML\-Markup verwendet in der Regel dieselben Zeichenentitäten und Escapesequenzen, die in XML definiert sind.  
  
 Die wichtigste Ausnahme besteht darin, dass Klammern \({ und }\) in XAML eine Bedeutung haben. Sie dienen XAML\-Prozessoren als Bezeichner, dass eine in Klammern eingeschlossene Zeichenfolge als Markuperweiterung interpretiert werden muss.  Weitere Informationen zu Markuperweiterungen finden Sie unter [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
 Sie haben dennoch die Möglichkeit, die Klammern als Literalzeichen anzuzeigen, indem Sie eine Escapesequenz verwenden, die für XAML statt für XML spezifisch ist.  Weitere Informationen finden Sie unter [{} Escape Sequence \/ Markup Extension](../../../docs/framework/xaml-services/escape-sequence-markup-extension.md).  
  
 Beachten Sie, dass ein umgekehrter Schrägstrich \(\\\) keine Escapesequenz erfordert, wenn er als Zeichenfolge behandelt wird.  
  
<a name="xml_character_entities"></a>   
## XML\-Zeichenentitäten  
 Wie bereits erwähnt, werden die meisten Zeichenentitäten und Escape\-Sequenzen, die beim Schreiben von XAML\-Markup normalerweise verwendet werden, von XML definiert.  Dieses Thema enthält keine vollständige Liste dieser Entitäten. Eine ausführlichere Referenz der Entitäten finden Sie in externer Dokumentation wie in XML\-Spezifikationen.  Aus praktischen Gründen enthält dieses Thema eine Liste der XML\-Zeichenentitäten, die häufig für XAML\-Markup verwendet werden.  
  
|Zeichen|Entität|Notizen|  
|-------------|-------------|-------------|  
|& \(Und\)|&amp;|Muss sowohl in Attributwerten als auch in Elementinhalten verwendet werden.|  
|\> \(Größer als\-Zeichen\)|&gt;|Muss in Attributwerten verwendet werden, ist in Elementinhalten zulässig, wenn dem nicht \< vorausgeht.|  
|\< \(Kleiner als\-Zeichen\)|&lt;|Muss in Attributwerten verwendet werden, ist in Elementinhalten zulässig, wenn dem nicht \> folgt.|  
|" \(gerades Anführungszeichen\)|&quot;|Muss in Attributwerten verwendet werden. Jedoch ist ein gerades Anführungszeichen \("\) in Elementinhalten zulässig.  Beachten Sie, dass Attributwerte durch ein einzelnes gerades Anführungszeichen \('\) oder ein gerades Anführungszeichen \("\) umschlossen werden können. Das Zeichen, das zuerst vorkommt, wird als Umschließungszeichen für Attributwerte festgelegt, und das andere Zeichen kann im Wert als Literalzeichen verwendet werden.|  
|' \(einfaches gerades Anführungszeichen\)|&apos;|Muss in Attributwerten verwendet werden. Jedoch ist ein einzelnes gerades Anführungszeichen \('\) in Elementinhalten zulässig.  Beachten Sie, dass Attributwerte durch ein einzelnes gerades Anführungszeichen \('\) oder ein gerades Anführungszeichen \("\) umschlossen werden können. Das Zeichen, das zuerst vorkommt, wird als Umschließungszeichen für Attributwerte festgelegt, und das andere Zeichen kann im Wert als Literalzeichen verwendet werden.|  
|\(Zuordnungen numerischer Zeichen\)|&\#*\[Ganzzahl\]*; oder &\#x*\[Hexadezimalzahl\]*|XAML unterstützt die Zuordnung numerischer Zeichen in der aktiven Codierung.|  
|\(geschütztes Leerzeichen\)|&\#160; \(UTF\-8\-Codierung\)|Bei Flussdokumentelementen oder Elementen für die Aufnahme von Text wie <xref:System.Windows.Controls.TextBox> von WPF werden geschützte Leerzeichen nicht außerhalb des Markups normalisiert, auch nicht für  `xml:space="default"`.  \(Weitere Informationen finden Sie unter [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).\)|  
  
<a name="xml_comment_format"></a>   
## Format von XML\-Kommentaren  
 XAML verwendet das XML\-Kommentarformat: der Anfang des Kommentars ist `<!--`, das Ende des Kommentars ist `-->,` und die Sequenz `--` darf nicht innerhalb des Kommentars vorkommen.  
  
<a name="xml_processing_instructions"></a>   
## XML\-Verarbeitungsanweisungen  
 XAML behandelt XML\-Verarbeitungsanweisungen gemäß den XML\-Spezifikationen, die angeben, dass die Anweisungen übergeben werden müssen.  Bei XAML\-Verarbeitung in .NET Framework XAML\-Dienste werden keine Verarbeitungsanweisungen verwendet.  Andere vorhandene Frameworks, die XAML verwenden, verwenden auch keine Verarbeitungsanweisungen von XAML.  
  
## Siehe auch  
 [{} Escape Sequence \/ Markup Extension](../../../docs/framework/xaml-services/escape-sequence-markup-extension.md)   
 [Übersicht über XAML \(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Markuperweiterungen und WPF\-XAML](../../../ocs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [XamlName\-Grammatik](../../../docs/framework/xaml-services/xamlname-grammar.md)   
 [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)