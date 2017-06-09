---
title: "Gewusst wie: Entfernen von ung&#252;ltigen Zeichen aus einer Zeichenfolge | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Reguläre Ausdrücke, Beispiele"
  - "Bereinigen einer Eingabe"
  - "Benutzereingabe, Beispiele"
  - "Reguläre Ausdrücke von .NET Framework, Beispiele"
  - "Reguläre Ausdrücke [.NET Framework], Beispiele"
  - "Regex.Replace-Methode"
  - "Entfernen ungültiger Zeichen"
  - "Replace-Methode"
  - "Validieren von Benutzereingaben"
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Entfernen von ung&#252;ltigen Zeichen aus einer Zeichenfolge
Im folgenden Beispiel wird die statische <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=fullName>\-Methode verwendet, um ungültige Zeichen aus einer Zeichenfolge zu entfernen.  
  
## Beispiel  
 Sie können mit der in diesem Beispiel definierten `CleanInput`\-Methode potenziell gefährliche Zeichen entfernen, die in ein Textfeld für Benutzereingaben eingegeben wurden.  In diesem Fall entfernt `CleanInput` alle nicht alphanumerischen Zeichen außer Punkten \(.\), @\-Zeichen und Bindestrichen \(\-\) und gibt die verbleibende Zeichenfolge zurück.  Sie können das Muster für reguläre Ausdrücke jedoch so ändern, dass alle Zeichen entfernt werden, die nicht in einer Eingabezeichenfolge enthalten sein sollen.  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 Das Muster eines regulären Ausdrucks `[^\w\.@-]` entspricht jedem Zeichen, bei dem es sich nicht um ein Wortzeichen, einen Punkt, ein @\-Zeichen oder einen Bindestrich handelt.  Ein Wortzeichen ist ein beliebiger Buchstabe, eine Dezimalstelle oder eine Interpunktionsverbindung, z. B. der Unterstrich.  Jedes Zeichen, das diesem Muster entspricht, wird durch <xref:System.String.Empty?displayProperty=fullName> ersetzt, das die durch das Ersatzmuster definierte Zeichenfolge ist.  Um zusätzliche Zeichen in der Benutzereingabe zu ermöglichen, fügen Sie diese Zeichen der Zeichenklasse im Muster für reguläre Ausdrücke hinzu.  Beispielsweise lässt das Muster für reguläre Ausdrücke `[^\w\.@-\\%]` auch ein Prozentsymbol und einen umgekehrten Schrägstrich in einer Eingabezeichenfolge zu.  
  
## Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](../../../docs/standard/base-types/regular-expressions.md)