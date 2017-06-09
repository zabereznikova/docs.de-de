---
title: "Security and Public Read-only Array Fields | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "security [.NET Framework], public read-only array fields"
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Security and Public Read-only Array Fields
Verwenden Sie niemals schreibgeschützte öffentliche Arrayfelder aus verwalteten Bibliotheken, um die Sicherheit und das Verhalten von Anwendungen im Grenzbereich zu definieren, da schreibgeschützte öffentliche Arrayfelder geändert werden können.  
  
## Hinweise  
 Einige .NET Framework\-Klassen umfassen schreibgeschützte öffentliche Felder, die plattformspezifische Begrenzungsparameter enthalten.  Das <xref:System.IO.Path.InvalidPathChars>\-Feld ist z. B. ein Array, das die Zeichen beschreibt, die in der Zeichenfolge eines Dateipfads nicht zulässig sind.  Es sind viele ähnliche Felder in .NET Framework vorhanden.  
  
 Die Werte von öffentlichen schreibgeschützten Feldern \(z. B. <xref:System.IO.Path.InvalidPathChars>\) können durch vom Benutzer geschriebenen Code oder Code geändert werden, der in derselben Anwendungsdomäne verwendet wird.  Sie sollten schreibgeschützte öffentliche Arrayfelder nicht auf diese Weise dazu verwenden, das Verhalten von Anwendungen im Grenzbereich zu definieren.  Dies könnte dazu führen, dass bösartiger Code die Begrenzungsdefinitionen ändert und den Code auf unerwartete Weise verwendet.  
  
 In Version 2.0 und späteren Versionen von .NET Framework müssen Sie Methoden verwenden, die keine öffentlichen Arrayfelder verwenden, sondern ein neues Array zurückgeben.  Beispielsweise sollten Sie anstelle des Feldes <xref:System.IO.Path.InvalidPathChars> die <xref:System.IO.Path.GetInvalidPathChars%2A>\-Methode verwenden.  
  
 Beachten Sie, dass die .NET Framework\-Typen Begrenzungstypen nicht mithilfe öffentlicher Felder intern definieren.  Stattdessen werden von .NET Framework hierfür separate private Felder verwendet.  Durch das Ändern der Werte dieser öffentlichen Felder wird nicht das Verhalten von .NET Framework\-Typen geändert.  
  
## Siehe auch  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)