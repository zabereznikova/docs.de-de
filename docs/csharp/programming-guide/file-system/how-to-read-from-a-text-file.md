---
title: "Gewusst wie: Lesen aus einer Textdatei (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "StreamReader.ReadToEnd"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Lesen von Daten, Textdateien"
  - "Lesen von Textdateien"
  - "Textdateien, Lesen"
  - "Textdateien, Schreiben in"
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Lesen aus einer Textdatei (C#-Programmierhandbuch)
In diesem Beispiel wird der Inhalt einer Textdatei, indem die statischen Methoden <xref:System.IO.File.ReadAllText%2A> und <xref:System.IO.File.ReadAllLines%2A> aus der <xref:System.IO.File?displayProperty=fullName>\-Klasse angewendet wird.  
  
 Ein Beispiel, in dem <xref:System.IO.StreamReader> verwendet wird, finden Sie unter [Gewusst wie: Zeilenweises Lesen einer Textdatei](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).  
  
> [!NOTE]
>  Die Dateien, die in diesem Beispiel verwendet werden, werden im Thema [Gewusst wie: Schreiben in eine Textdatei](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md) erstellt.  
  
## Beispiel  
 [!code-cs[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/csFilesFolders/FileIteration.cs#4)]  
  
## Kompilieren des Codes  
 Kopieren Sie den Code und fügen Sie ihn in eine C\#\-Konsolenanwendung ein.  
  
 Wenn Sie nicht die Textdateien von [Gewusst wie: Schreiben in eine Textdatei](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md) verwenden, ersetzen Sie das \- Argument auf `ReadAllText` und zu `ReadAllLines` durch den entsprechenden Pfad und Dateinamen auf dem Computer.  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Die Datei ist vorhanden ist nicht vorhanden oder nicht am angegebenen Speicherort.  Überprüfen Sie den Pfad und die Schreibweise des Dateinamens.  
  
## .NET Framework-Sicherheit  
 Verlassen Sie sich nicht auf den Namen einer Datei, um den Inhalt der Datei zu bestimmen.  Beispielsweise könnte die Datei `myFile.cs` keine C\#\-Quelldatei.  
  
## Siehe auch  
 <xref:System.IO?displayProperty=fullName>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Das Dateisystem und die Registrierung](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)