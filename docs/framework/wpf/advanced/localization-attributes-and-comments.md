---
title: "Lokalisierungsattribute und -kommentare | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Lokalisierung, Attribute"
  - "Lokalisierung, Kommentare"
ms.assetid: ead2d9ac-b709-4ec1-a924-39927a29d02f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Lokalisierungsattribute und -kommentare
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Lokalisierungskommentare sind Eigenschaften innerhalb des [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]\-Quellcodes, die von Entwicklern geliefert werden, um Regeln und Hinweise für die Lokalisierung bereitzustellen.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Lokalisierungskommentare enthalten zwei Arten von Informationen: Lokalisierbarkeitsattribute und formfreie Lokalisierungskommentare.  Lokalisierbarkeitsattribute werden von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Lokalisierungs\-API verwendet, um anzugeben, welche Ressourcen lokalisiert werden sollen.  Formfreie Kommentare umfassen alle Informationen, die der Anwendungsentwickler einschließen möchte.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Localizer_Comments_"></a>   
## Lokalisierungskommentare  
 Wenn Entwickler von Markupanwendungen Anforderungen an bestimmte Elemente in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] stellen, wie Einschränkungen hinsichtlich Textlänge, Schriftfamilie oder Schriftgrad, können Sie diese Informationen den Lokalisierungsexperten mit Kommentaren im [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]\-Code übermitteln.  Das Hinzufügen von Kommentaren zu Quellcode funktioniert wie folgt:  
  
1.  Anwendungsentwickler fügen dem [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]\-Quellcode Lokalisierungskommentare hinzu.  
  
2.  Während des Buildprozesses können Sie in der PROJ\-Datei angeben, ob die formfreien Lokalisierungskommentare in der Assembly bleiben oder ob ein Teil oder alle der Kommentare entfernt werden sollen.  Die entfernten Kommentare werden in einer separaten Datei abgelegt.  Sie geben die Option mit einem `LocalizationDirectivesToLocFile`\-Tag an, z. B.:  
  
     `<LocalizationDirectivesToLocFile>` *value* `</LocalizationDirectivesToLocFile>`  
  
3.  Folgende Werte können zugewiesen werden:  
  
    -   **None** \- Sowohl Kommentare als auch Attribute bleiben in der Assembly. Es wird keine separate Datei generiert.  
  
    -   **CommentsOnly** \- Es werden nur die Kommentare aus der Assembly entfernt und in der separaten LocFile abgelegt.  
  
    -   **All** \- Es werden sowohl Kommentare als auch Attribute aus der Assembly entfernt und in einer separaten LocFile abgelegt.  
  
4.  Wenn lokalisierbare Ressourcen aus [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)] extrahiert werden, werden die Lokalisierbarkeitsattribute von der [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)]\-Lokalisierungs\-API berücksichtigt.  
  
5.  Lokalisierungskommentardateien, die nur formfreie Kommentare enthalten, werden zu einem späteren Zeitpunkt in den Lokalisierungsprozess integriert.  
  
 Das folgende Beispiel zeigt, wie einer [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]\-Datei Lokalisierungskommentare hinzugefügt werden.  
  
 `<TextBlock x:Id = "text01"`  
  
 `FontFamily = "Microsoft Sans Serif"`  
  
 `FontSize = "12"`  
  
 `Localization.Attributes = "$Content (Unmodifiable Readable Text)`  
  
 `FontFamily (Unmodifiable Readable)"`  
  
 `Localization.Comments = "$Content (Trademark)`  
  
 `FontSize (Trademark font size)" >`  
  
 `Microsoft`  
  
 `</TextBlock>`  
  
 Im vorherigen Beispiel enthält der Localization.Attributes\-Abschnitt die Lokalisierungsattribute und der Localization.Comments\-Abschnitt die formfreien Kommentare.  Die folgenden Tabellen zeigen dem Lokalisierungsexperten die Attribute und Kommentare und ihre Bedeutung.  
  
|Lokalisierungsattribute|Bedeutung|  
|-----------------------------|---------------|  
|$Content \(Unmodifiable Readable Text\)|Der Inhalt des TextBlock\-Elements kann nicht geändert werden.  Lokalisierungsexperten können das Wort "Microsoft" nicht ändern.  Der Inhalt ist für den Lokalisierungsexperten sichtbar \(Readable\).  Die Kategorie des Inhalts ist Text.|  
|FontFamily \(Unmodifiable Readable\)|Die FontFamily\-Eigenschaft des TextBlock\-Elements kann nicht geändert werden, ist aber für den Lokalisierungsexperten sichtbar.|  
  
|Formfreie Lokalisierungskommentare|Bedeutung|  
|----------------------------------------|---------------|  
|$Content \(Trademark\)|Der Anwendungsentwickler teilt dem Lokalisierungsexperten mit, dass der Inhalt im TextBlock\-Element eine Marke ist.|  
|FontSize \(Trademark font size\)|Der Anwendungsentwickler gibt an, dass die FontSize\-Eigenschaft der Standardmarkengröße entsprechen soll.|  
  
### Lokalisierbarkeitsattribute  
 Die Informationen in Localization.Attributes enthalten eine Liste von Paaren: den Namen des Zielwerts und die zugeordneten Lokalisierungswerte.  Der Zielname kann ein Eigenschaftenname oder der spezielle $Content\-Name sein.  Wenn es sich um einen Eigenschaftennamen handelt, ist der Zielwert der Wert der Eigenschaft.  Wenn es sich um $Content handelt, ist der Zielwert der Inhalt des Elements.  
  
 Es gibt drei Typen von Attributen:  
  
-   **Category**.  Gibt an, ob ein Wert in einem Lokalisierungstool geändert werden kann.  Siehe <xref:System.Windows.LocalizabilityAttribute.Category%2A>.  
  
-   **Readability**.  Gibt an, ob ein Lokalisierungstool einen Wert lesen \(und anzeigen\) kann.  Siehe <xref:System.Windows.LocalizabilityAttribute.Readability%2A>.  
  
-   **Modifiability**.  Gibt an, ob ein Lokalisierungstool das Ändern eines Werts zulässt.  Siehe <xref:System.Windows.LocalizabilityAttribute.Modifiability%2A>.  
  
 Diese Attribute können in jeder Reihenfolge durch ein Leerzeichen getrennt angegeben werden.  Falls doppelte Attribute angegeben werden, überschreibt das letzte Attribut die vorherigen Attribute.  So legt Localization.Attributes \= "Unmodifiable Modifiable" beispielsweise Modifiability auf Modifiable fest, da es sich hierbei um den letzten Wert handelt.  
  
 Modifiability und Readability sind selbsterklärend.  Das Category\-Attribut stellt vordefinierte Kategorien bereit, die den Lokalisierungsexperten beim Übersetzen von Text unterstützen.  Kategorien wie Text, Label und Title geben dem Lokalisierungsexperten Informationen zum Übersetzen des Texts.  Es gibt auch spezielle Kategorien: None, Inherit, Ignore und NeverLocalize.  
  
 In der folgenden Tabelle wird die Bedeutung der speziellen Kategorien dargestellt.  
  
|Kategorie|Bedeutung|  
|---------------|---------------|  
|None|Der Zielwert besitzt keine definierte Kategorie.|  
|Inherit|Der Zielwert erbt seine Kategorie von seinem übergeordneten Element.|  
|Ignorieren|Der Zielwert wird im Lokalisierungsprozess ignoriert.  Ignore wirkt sich nur auf den aktuellen Wert aus.  Untergeordnete Knoten werden nicht beeinflusst.|  
|NeverLocalize|Der aktuelle Wert kann nicht lokalisiert werden.  Diese Kategorie wird von den untergeordneten Elementen eines Elements geerbt.|  
  
<a name="Localization_Comments"></a>   
## Lokalisierungskommentare  
 Localization.Comments enthält formfreie Zeichenfolgen, die den Zielwert betreffen.  Anwendungsentwickler können Informationen hinzufügen, um Lokalisierungsexperten Hinweise zur Übersetzung des Anwendungstexts zu geben.  Das Format der Kommentare kann jede Zeichenfolge sein, die von "\(\)" umgeben ist.  Verwenden Sie '\\' als Escapezeichen.  
  
## Siehe auch  
 [Globalisierung für WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)   
 [Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)   
 [Verwenden eines Rasters für automatisches Layout](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)   
 [Lokalisieren einer Anwendung](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)