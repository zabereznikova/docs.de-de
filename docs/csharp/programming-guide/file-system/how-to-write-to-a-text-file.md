---
title: "Gewusst wie: Schreiben in eine Textdatei (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TextWriter.WriteLine"
  - "StreamWriter.Close"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Dateien [C#], Textdateien"
  - "Text, Schreiben in Dateien [C#]"
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Schreiben in eine Textdatei (C#-Programmierhandbuch)
In diesen Beispielen werden verschiedene Möglichkeiten veranschaulicht, Text in eine Datei zu schreiben.  In den ersten zwei Beispielen werden statische Hilfsmethoden für die <xref:System.IO.File?displayProperty=fullName>\-Klasse verwendet, um jedes Element von „IEnumerable\<string\>“ und um eine Zeichenfolge in eine Textdatei zu schreiben.  In Beispiel 3 wird dargestellt, wie Text einer Datei hinzugefügt wird, wenn jede Zeile beim Schreiben in die Datei einzeln verarbeitet werden muss.  Die Beispiele 1–3 überschreiben alle vorhandenen Inhalte in der Datei. In Beispiel 4 wird jedoch gezeigt, wie einer vorhandenen Datei Text angefügt wird.  
  
 In allen diesen Beispielen werden Zeichenfolgenliterale in Dateien geschrieben. Sie sollten jedoch eher die <xref:System.String.Format%2A>\-Methode verwenden, die viele Steuerelemente enthält, mit denen verschiedene Wertetypen rechts\- oder linksbündig mit oder ohne Abstand in ein Feld geschrieben werden können.  Sie können auch das Feature für die C\#\-[Zeichenfolgeninterpolierung](../../../csharp/language-reference/keywords/interpolated-strings.md) verwenden.  
  
## Beispiel  
 [!code-cs[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/csFilesFolders/FileIteration.cs#3)]  
  
 In allen diesen Beispielen werden Zeichenfolgenliterale in Dateien geschrieben. Sie sollten jedoch eher die <xref:System.String.Format%2A>\-Methode verwenden, die viele Steuerelemente enthält, mit denen verschiedene Wertetypen rechts\- oder linksbündig mit oder ohne Abstand in ein Feld geschrieben werden können.  Sie können auch das Feature für die C\#\-[Zeichenfolgeninterpolierung](../../../csharp/language-reference/keywords/interpolated-strings.md) verwenden.  
  
## Robuste Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Die Datei ist bereits vorhanden und ist schreibgeschützt.  
  
-   Der Pfadname ist möglicherweise zu lang.  
  
-   Der Datenträger ist möglicherweise voll.  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Das Dateisystem und die Registrierung](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)   
 [Beispiel: Speichern einer Auflistung im Anwendungsspeicher](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)