---
title: "&#196;nderungen am System.Uri-Namespace in Version 2.0 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 35883fe9-2d09-4d8b-80ca-cf23a941e459
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &#196;nderungen am System.Uri-Namespace in Version 2.0
Mehrere Änderungen wurden an der <xref:System.Uri?displayProperty=fullName>\-Klasse vorgenommen.  Diese Änderungen korrigiert falsches Verhalten, verbesserten Benutzerfreundlichkeit und erweiterten Sicherheit.  
  
## Veraltete und veraltete Member  
 Konstruktoren:  
  
-   Alle Konstruktoren, die einen `dontEscape`\-Parameter haben.  
  
 Methoden:  
  
-   <xref:System.Uri.CheckSecurity%2A>  
  
-   <xref:System.Uri.Escape%2A>  
  
-   <xref:System.Uri.Canonicalize%2A>  
  
-   <xref:System.Uri.Parse%2A>  
  
-   <xref:System.Uri.IsReservedCharacter%2A>  
  
-   <xref:System.Uri.IsBadFileSystemCharacter%2A>  
  
-   <xref:System.Uri.IsExcludedCharacter%2A>  
  
-   <xref:System.Uri.EscapeString%2A>  
  
## Änderungen  
  
-   Für URI\-Schemen, die bekannt, um einen Abfragenteil \(Datei, FTP und andere\) nicht verfügen, "?" Zeichen wird immer mit Escapezeichen versehen und wird nicht als den Beginn eines <xref:System.Uri.Query%2A> Teils.  
  
-   Bei impliziten Datei URI \(des Formulars "c:\\directory\\file @name.txt"\), das Fragmentzeichen \("\# "\) wird immer mit Escapezeichen versehen, es sei denn, voll unescaping angefordert wird, oder <xref:System.Uri.LocalPath%2A>`true` ist.  
  
-   UNC\-Hostnamenunterstützung wurde entfernt; die IDN\-Spezifikation für die Darstellung von internationalen Hostnamen wurde angenommen.  
  
-   <xref:System.Uri.LocalPath%2A> gibt immer eine vollständig Zeichenfolge ohne Escapezeichen zurück.  
  
-   <xref:System.Uri.ToString%2A> jedoch nicht unescape ein "% mit Escapezeichen", "? " oder "&#124;" Zeichen.  
  
-   <xref:System.Uri.Equals%2A> enthält nun den <xref:System.Uri.Query%2A> Anteil an der Gleichheitsüberprüfung ein.  
  
-   Operatoren "\=\=" und "\! \=" werden überschrieben und zu <xref:System.Uri.Equals%2A> die Methode verknüpft.  
  
-   <xref:System.Uri.IsLoopback%2A> bietet jetzt konsistente Ergebnisse.  
  
-   Der URI "`file:///path`" wird nicht mehr in "file:\/\/path" übersetzt.  
  
-   "\#" wird jetzt als Hostnamenabschlusszeichen erkannt.  Das heißt, "http:\/\/consoto.com\#fragment" wird jetzt auf "http:\/\/contoso.com\/\#fragment" konvertiert.  
  
-   Ein Fehler, um einen Basis\-URI mit einem kombinierten Fragment wurde korrigiert.  
  
-   Ein Fehler in <xref:System.Uri.HostNameType%2A> behoben ist.  
  
-   Ein Fehler in NNTP\-Analyse behoben ist.  
  
-   Ein URI im Format HTTP:contoso.com löst jetzt eine Analyseausnahme aus.  
  
-   Das Framework ordnungsgemäß behandelt userinfo in einem URI.  
  
-   URI\-Pfadkomprimierung ist festgelegt, damit ein unterbrochenes URI das Dateisystem über dem Stamm nicht durchlaufen kann.  
  
## Siehe auch  
 <xref:System.Uri?displayProperty=fullName>