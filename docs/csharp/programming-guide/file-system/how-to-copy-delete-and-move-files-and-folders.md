---
title: "Gewusst wie: Kopieren, L&#246;schen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "E/A [C#]"
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Kopieren, L&#246;schen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)
In den folgenden Beispielen wird dargestellt, wie Dateien und Ordner synchron mithilfe der <xref:System.IO.File?displayProperty=fullName>\-Klasse, der <xref:System.IO.Directory?displayProperty=fullName>\-Klasse, der <xref:System.IO.FileInfo?displayProperty=fullName>\-Klasse und der <xref:System.IO.DirectoryInfo?displayProperty=fullName>\-Klasse aus dem <xref:System.IO?displayProperty=fullName>\-Namespace kopiert, verschoben und gelöscht werden.  In diesen Beispielen wird keinerlei Statusanzeige oder andere Benutzeroberfläche bereitgestellt.  Wenn Sie ein Standardstatusdialogfeld bereitstellen möchten, finden Sie unter [Gewusst wie: Bereitstellen eines Statusdialogfelds für Dateioperationen](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md) weitere Informationen.  
  
 Verwenden Sie <xref:System.IO.FileSystemWatcher?displayProperty=fullName>, um Ereignisse bereitzustellen, mit denen Sie bei der Bearbeitung von mehreren Dateien den Status berechnen können.  Eine andere Methode zum Plattformaufruf besteht im Abrufen der relevanten dateibezogenen Methoden in der Windows\-Shell.  Weitere Informationen über das asynchrone Ausführen dieser Dateioperationen finden Sie unter [Asynchrone Datei\-E\/A](../Topic/Asynchronous%20File%20I-O.md).  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Dateien und Verzeichnisse kopiert werden.  
  
 [!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/csFilesFolders/FileIteration.cs#7)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Dateien und Verzeichnisse verschoben werden.  
  
 [!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/csFilesFolders/FileIteration.cs#8)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Dateien und Verzeichnisse gelöscht werden.  
  
 [!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/csFilesFolders/FileIteration.cs#9)]  
  
## Siehe auch  
 <xref:System.IO?displayProperty=fullName>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Das Dateisystem und die Registrierung](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)   
 [Gewusst wie: Bereitstellen eines Statusdialogfelds für Dateioperationen](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md)   
 [Datei\- und Stream\-E\/A](../Topic/File%20and%20Stream%20I-O.md)   
 [Allgemeine E\/A\-Aufgaben](../Topic/Common%20I-O%20Tasks.md)