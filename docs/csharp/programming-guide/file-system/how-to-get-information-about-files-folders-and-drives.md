---
title: "Gewusst wie: Abrufen von Informationen &#252;ber Dateien, Ordner und Laufwerke (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Dateien [C#], Abrufen von Informationen zu"
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Gewusst wie: Abrufen von Informationen &#252;ber Dateien, Ordner und Laufwerke (C#-Programmierhandbuch)
In .NET Framework können Sie auf Dateisysteminformationen mit den folgenden Klassen zugreifen:  
  
-   <xref:System.IO.FileInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DirectoryInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DriveInfo?displayProperty=fullName>  
  
-   <xref:System.IO.Directory?displayProperty=fullName>  
  
-   <xref:System.IO.File?displayProperty=fullName>  
  
 Die <xref:System.IO.FileInfo>\-Klasse und die <xref:System.IO.DirectoryInfo>\-Klasse stellen eine Datei oder ein Verzeichnis dar und enthalten Eigenschaften, die viele der Dateiattribute verfügbar machen, die vom NTFS\-Dateisystem unterstützt werden.  Sie enthalten auch Methoden zum Öffnen, Schließen, Verschieben und Löschen von Dateien und Ordnern.  Sie können Instanzen dieser Klassen erstellen, indem Sie eine Zeichenfolge, die den Namen der Datei, des Ordners oder des Laufwerks darstellt, an den Konstruktor übergeben:  
  
```c#  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 Sie können die Namen der Dateien, Ordner oder Laufwerke auch mithilfe der Aufrufe von <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=fullName>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=fullName>, und <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=fullName> abrufen.  
  
 Die <xref:System.IO.Directory?displayProperty=fullName>\-Klasse und <xref:System.IO.File?displayProperty=fullName>\-Klasse stellen statische Methoden zum Abrufen von Informationen über Verzeichnisse und Dateien bereit.  
  
## Beispiel  
 Im folgenden Beispiel werden verschiedene Möglichkeiten veranschaulicht, auf Informationen über Dateien und Ordner zuzugreifen.  
  
 [!code-cs[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-get-information-about-files-folders-and-drives_1.cs)]  
  
## Robuste Programmierung  
 Wenn Sie vom Benutzer angegebene Pfadzeichenfolgen verarbeiten, sollten Sie auch Ausnahmen für die folgenden Bedingungen behandeln:  
  
-   Der Dateiname ist falsch formatiert.  Er enthält beispielsweise ungültige Zeichen oder besteht nur aus Leerzeichen.  
  
-   Der Dateiname ist NULL.  
  
-   Der Dateiname überschreitet die systemdefinierte maximale Länge.  
  
-   Der Dateiname enthält einen Doppelpunkt \(:\).  
  
 Wenn die Anwendung nicht über entsprechende Berechtigungen für den Lesezugriff auf die angegebene Datei verfügt, gibt die `Exists`\-Methode unabhängig vom Vorhandensein eines Pfads `false` zurück. Die Methode löst keine Ausnahme aus.  
  
## Siehe auch  
 <xref:System.IO?displayProperty=fullName>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Das Dateisystem und die Registrierung](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)