---
title: "Gewusst wie: Konvertieren vom RTF- ins Nur-Text-Format (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Zeichenfolgen [C#], Konvertieren von RTF"
ms.assetid: 3b386a87-899d-4d98-bc82-a980526ddaac
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Gewusst wie: Konvertieren vom RTF- ins Nur-Text-Format (C#-Programmierhandbuch)
Rich Text Format \(RTF\) ist ein Dokumentformat, das von Microsoft in den späten 1980igern entwickelt wurde, um den Austausch von Dokumenten zwischen Betriebssystemen zu ermöglichen.  Sowohl Microsoft Word als auch WordPad können RTF\-Dokumente lesen und schreiben.  In .NET Framework können Sie mit dem Steuerelement <xref:System.Windows.Forms.RichTextBox> ein Textverarbeitungsprogramm erstellen, das RTF unterstützt und einem Benutzer die Formatierung von Text in WYSIWIG ermöglicht.  
  
 Sie können auch das Steuerelement <xref:System.Windows.Forms.RichTextBox> verwenden, um die RTF\-Formatierungscodes aus einem Dokument programmgesteuert zu entfernen und es in reinen Text umzuwandeln.  Sie brauchen das Steuerelement nicht in ein Windows\-Formular einzubetten, um diese Operation durchzuführen.  
  
### So verwenden Sie das RichTextBox\-Steuerelement in einem Projekt  
  
1.  Fügen Sie einen Verweis zu System.Windows.Forms.dll hinzu.  
  
2.  Fügen Sie eine using\-Direktive für den `System.Windows.Forms`\-Namespace hinzu \(optional\).  
  
## Beispiel  
 Im folgenden Beispiel wird eine Beispiel\-RTF\-Datei in reinen Text.  Die Datei enthält RTF\-Formatierungen \(wie Schriftartinformationen\), vier Unicode\-Zeichen und vier erweiterte ASCII\-Zeichen.  Der Beispielcode öffnet die Datei, wird dessen Inhalt zu <xref:System.Windows.Forms.RichTextBox>, während RTF, den Inhalt als Text abruft, den Text in <xref:System.Windows.Forms.MessageBox> anzeigt und den Text in eine Datei im UTF\-8\-Format ausgibt.  
  
 `MessageBox` und die Ausgabedatei enthalten den folgenden Text:  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
  
```  
  
 [!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#33)]  
  
 RTF\-Zeichen werden in acht Bits codiert.  Allerdings können Benutzer Unicode\-Zeichen zusätzlich zu erweiterten ASCII\-Zeichen aus angegebenen Codeseiten angeben.  Da die <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName>\-Eigenschaft vom Typ [string](../../../csharp/language-reference/keywords/string.md) ist, werden die Zeichen als Unicode UTF\-16 codiert.  Alle erweiterten ASCII\- und Unicode\-Zeichen aus dem RTF\-Quelldokument werden in der Textausgabe ordnungsgemäß codiert.  
  
 Falls Sie die <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName>\-Methode zum Schreiben von Text auf Festplatte verwenden, wird der Text als UTF\-8 \(ohne Bytereihenfolgenmarkierung\) codiert.  
  
## Siehe auch  
 <xref:System.Windows.Forms.RichTextBox?displayProperty=fullName>   
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)