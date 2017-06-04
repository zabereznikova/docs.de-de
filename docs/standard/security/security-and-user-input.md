---
title: "Security and User Input | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "security [.NET Framework], user input"
  - "user input, security"
  - "secure coding, user input"
  - "code security, user input"
ms.assetid: 9141076a-96c9-4b01-93de-366bb1d858bc
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# Security and User Input
Benutzerdaten, bei denen es sich um beliebige Eingaben handeln kann \(Daten aus einer Webanforderung oder einer URL, Eingaben in Steuerelemente einer Microsoft Windows Forms\-Anwendung usw.\), können Code beeinträchtigen, da diese Daten häufig direkt als Parameter zum Aufrufen von anderem Code verwendet werden.  Diese Situation ähnelt einem Angriff durch bösartigen Code, der Ihren Code mit ungewöhnlichen Parametern aufruft. Es sollten dieselben Vorsichtsmaßnahmen ergriffen werden.  Die Sicherheit bei Benutzereingaben ist im Grunde schwieriger zu gewährleisten, da kein Stapelrahmen zum Verfolgen der möglicherweise nicht vertrauenswürdigen Daten vorhanden ist.  
  
 Diese Sicherheitslücken sind am schwierigsten zu finden, da sie sich zwar in Code befinden können, der mit der Sicherheit scheinbar nicht in Bezug steht, aber dennoch ein Gateway für die Übergabe bösartiger Daten an anderen Code darstellen.  Verfolgen Sie bei der Suche nach solchen Fehlern alle Arten von Eingabedaten, schätzen Sie den Bereich möglicher Werte ein, und ermitteln Sie, ob der Code mit Zugriff auf diese Daten alle diese Fälle behandeln kann.  Sie können diese Fehler beheben, indem Sie Bereiche überprüfen und sämtliche Eingaben zurückweisen, die vom Code nicht behandelt werden können.  
  
 Im Folgenden sind einige wichtige Überlegungen zu Benutzerdaten aufgeführt:  
  
-   Alle Benutzerdaten in einer Serverantwort werden im Kontext der Site des Servers auf dem Client ausgeführt.  Wenn der Webserver Benutzerdaten empfängt und in die zurückgegebene Webseite einfügt, kann beispielsweise ein **\<script\>**\-Tag eingebunden und ob als vom Server ausgeführt.  
  
-   Beachten Sie, dass der Client beliebige URLs anfordern kann.  
  
-   Berücksichtigen Sie, dass komplizierte oder ungültige Pfade auftreten können:  
  
    -   . \\, äußerst lange Pfade.  
  
    -   Verwendung von Platzhalterzeichen \(\*\)  
  
    -   Tokenerweiterung \(%token%\)  
  
    -   Ungewöhnliche Pfadbildungen mit besonderer Bedeutung  
  
    -   Alternative Streamnamen des Dateisystems, z. B. `filename::$DATA`  
  
    -   Kurze Versionen von Dateinamen, z. B. `longfi~1` für `longfilename`  
  
-   Denken Sie daran, dass durch Eval\(userdata\) jede Aktion ausgeführt werden kann.  
  
-   Besondere Vorsicht ist beim späten Binden an einen Namen geboten, der Benutzerdaten enthält.  
  
-   Beim Arbeiten mit Webdaten müssen die zulässigen unterschiedlichen Formen von Escapezeichen berücksichtigt werden, zum Beispiel:  
  
    -   Hexadezimale Escapezeichen \(%nn\)  
  
    -   Unicode\-Escapezeichen \(%nnn\)  
  
    -   UTF\-8\-Escapezeichen mit Überlänge \(%nn%nn\)  
  
    -   Doppelte Escapezeichen \(%nn wird zu %mmnn, wobei %mm das Escapezeichen für '%' darstellt\)  
  
-   Besondere Vorsicht ist bei Benutzernamen geboten, die mehrere kanonische Formen aufweisen können.  In Microsoft Windows 2000 kann z. B. häufig die Form MYDOMAIN\\*Benutzername* oder die Form *Benutzername*@mydomain.example.com verwendet werden.  
  
## Siehe auch  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)