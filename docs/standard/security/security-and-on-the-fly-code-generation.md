---
title: "Security and On-the-Fly Code Generation | Microsoft Docs"
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
  - "code security, on-the-fly code generation"
  - "on-the-fly code generation"
  - "security [.NET Framework], on-the-fly code generation"
  - "secure coding, on-the-fly code generation"
ms.assetid: 6d221724-bb21-4d76-90c3-0ee2a2e69be2
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Security and On-the-Fly Code Generation
Einige Bibliotheken funktionieren, indem sie Code generieren und diesen ausführen, um einen Vorgang für den Aufrufer durchzuführen.  Das Grundproblem besteht darin, Code auf Veranlassung eines weniger vertrauenswürdigen Codes zu generieren und den generierten Code mit einer höheren Vertrauensebene auszuführen.  Das Problem ist noch gravierender, wenn der Aufrufer die Codegenerierung beeinflussen kann. Deshalb müssen Sie sicherstellen, dass nur Code generiert wird, den Sie als sicher erachten.  
  
 Sie müssen jederzeit genau wissen, welchen Code Sie erstellen.  Dies bedeutet, dass Sie unbedingte Kontrolle über alle Werte haben müssen, die von einem Benutzer stammen, egal, ob diese Werte in Anführungszeichen eingeschlossene Zeichenfolgen \(die mit Escapezeichen versehen werden sollten, damit sie keine unerwarteten Codeelemente enthalten können\), Bezeichner \(die daraufhin überprüft werden sollten, dass sie gültige Bezeichner sind\) oder etwas anderes sind.  Bezeichner können gefährlich sein, da eine kompilierte Assembly so geändert werden kann, dass ihre Bezeichner ungewöhnliche Zeichen enthalten, die die Assembly wahrscheinlich unbrauchbar machen \(obwohl dies selten ein Sicherheitsrisiko darstellt\).  
  
 Es wird empfohlen, dass Sie Code mit Reflektionsausgabe generieren, wodurch sich viele dieser Probleme vermeiden lassen.  
  
 Wenn Sie den Code kompilieren, sollten Sie überlegen, ob für Malware eine Möglichkeit besteht, den Code zu ändern.  Gibt es ein kleines Zeitfenster, in dem Malware den Quellcode auf dem Datenträger ändern kann, bevor der Quellcode vom Compiler gelesen wird oder bevor Ihr Code die DLL\-Datei lädt?  Ist dies der Fall, müssen Sie das Verzeichnis, das diese Dateien enthält, entsprechend mit Codezugriffssicherheit oder mit einer Zugriffssteuerungsliste im Dateisystem schützen.  
  
 Kann ein Aufrufer den generierten Code so beeinflussen, dass ein Compilerfehler verursacht wird, kann hier auch ein Sicherheitsrisiko vorhanden sein.  
  
 Führen Sie den generierten Code mit den geringst möglichen Berechtigungseinstellungen über <xref:System.Security.Permissions.SecurityAction> oder [Deny](http://msdn.microsoft.com/de-de/6b4d2e01-c504-4ac3-b50e-d6f5e7f5df25) aus.  
  
## Siehe auch  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)