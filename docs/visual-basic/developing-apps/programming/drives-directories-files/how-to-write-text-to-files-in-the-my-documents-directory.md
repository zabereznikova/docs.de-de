---
title: "How to: Write Text to Files in the My Documents Directory in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "files, writing to"
  - "text, writing to files"
  - "examples [Visual Basic], text files"
  - "writing to files, in My Documents"
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Write Text to Files in the My Documents Directory in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Mit dem `My.Computer.FileSystem.SpecialDirectories`\-Objekt können Sie auf besondere Verzeichnisse zugreifen, z. B. das Verzeichnis **Eigene Dateien**.  
  
## Verfahren  
  
#### So schreiben Sie neue Textdateien im Verzeichnis Eigene Dateien  
  
1.  Verwenden Sie die `My.Computer.FileSystem.SpecialDirectories.MyDocuments`\-Eigenschaft, um den Pfad anzugeben.  
  
     [!code-vb[VbFileIOWrite#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_1.vb)]  
  
2.  Verwenden Sie die `WriteAllText`\-Methode, um Text in die angegebene Datei zu schreiben.  
  
     [!code-vb[VbVbcnMyFileSystem#14](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_2.vb)]  
  
## Beispiel  
 [!code-vb[VbFileIOWrite#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_3.vb)]  
  
## Kompilieren des Codes  
 Ersetzen Sie `test.txt` durch den Namen der Datei, in die Sie schreiben möchten.  
  
## Robuste Programmierung  
 Dieser Code löst alle Ausnahmen erneut aus, die beim Schreiben von Text in die Datei auftreten.  Sie können die Wahrscheinlichkeit von Ausnahmen durch Verwendung von Windows Forms\-Steuerelementen wie der [OpenFileDialog](../Topic/OpenFileDialog%20Component%20\(Windows%20Forms\).md)\-Komponente oder der [SaveFileDialog](../Topic/SaveFileDialog%20Component%20\(Windows%20Forms\).md)\-Komponente reduzieren. Diese schränken die Benutzerauswahl auf gültige Dateinamen ein.  Die Verwendung dieser Steuerelemente bietet jedoch keine absolute Sicherheit.  Das Dateisystem kann sich zwischen dem Zeitpunkt der Dateiauswahl und dem Zeitpunkt der Codeausführung ändern.  Beim Arbeiten mit Dateien ist daher fast immer eine Ausnahmebehandlung erforderlich.  
  
## .NET Framework-Sicherheit  
 Bei Ausführung in einem teilweise vertrauenswürdigen Kontext kann der Code aufgrund fehlender Berechtigungen eine Ausnahme auslösen.  Weitere Informationen finden Sie unter [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  
  
 In diesem Beispiel wird eine neue Datei erstellt.  Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine Erstellungsberechtigung für den Ordner.  Berechtigungen werden unter Verwendung von Zugriffssteuerungslisten festgelegt.  Wenn die Datei bereits existiert, benötigt die Anwendung lediglich die Schreibberechtigung, also eine geringere Berechtigung.  Aus Sicherheitsgründen sollte die Datei nach Möglichkeit während der Bereitstellung erstellt werden. Außerdem sollte nur die Leseberechtigung für eine einzelne Datei erteilt werden \(anstatt die Erstellungsberechtigung für einen Ordner zu gewähren\).  Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in den Stammordner oder den Ordner **Programme** zu schreiben.  Weitere Informationen finden Sie unter [ACL Technology Overview](http://msdn.microsoft.com/de-de/06fbf66d-6f02-4378-b863-b2f12e349045).  
  
## Siehe auch  
 <xref:System.IO.Path.Combine%2A?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>