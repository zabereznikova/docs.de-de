---
title: "Gewusst wie: Zeilenweises Lesen einer Textdatei (Visual&#160;C#) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Lesen von Textdateien, Zeilenweise"
  - "ReadLine-Methode [C#]"
  - "Textdateien [C#]"
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Zeilenweises Lesen einer Textdatei (Visual&#160;C#)
In diesem Beispiel wird mit der `ReadLine`\-Methode der `StreamReader`\-Klasse der Inhalt einer Textdatei Zeile für Zeile in eine Zeichenfolge gelesen.  Jede Textzeile wird in der `line`\-Zeichenfolge gespeichert und auf dem Bildschirm angezeigt.  
  
## Beispiel  
  
```  
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine (line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## Kompilieren des Codes  
 Kopieren Sie den Code, und fügen Sie ihn in die `Main`\-Methode einer Konsolenanwendung ein.  
  
 Ersetzen Sie `"c:\test.txt"` durch den Namen der tatsächlichen Datei.  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Die Datei ist möglicherweise nicht vorhanden.  
  
## .NET Framework-Sicherheit  
 Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.  So handelt es sich beispielsweise bei der Datei `myFile.cs` nicht unbedingt um eine C\#\-Quelldatei.  
  
## Siehe auch  
 <xref:System.IO?displayProperty=fullName>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Das Dateisystem und die Registrierung](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)