---
title: "Classes Used in .NET Framework File I/O and the File System (Visual Basic) | Microsoft Docs"
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
  - "file I/O classes"
ms.assetid: 4a5ca924-eea8-4a95-a5f0-6ac10de276a3
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Classes Used in .NET Framework File I/O and the File System (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

In der folgenden Tabelle werden die Klassen aufgeführt, die im Allgemeinen für Datei\-E\/A\-Vorgänge in .NET Framework verwendet werden, unterteilt in Datei\-E\/A\-Klassen, Klassen für das Erstellen von Streams und Klassen für das Lesen und Schreiben von Streams.  
  
 Eine ausführlichere Auflistung finden Sie in der Dokumentation zu [!INCLUDE[dnprdnlong](../../../../csharp/programming-guide/events/includes/dnprdnlong-md.md)] unter [Übersicht über die Klassenbibliothek](../Topic/.NET%20Framework%20Class%20Library%20Overview.md).  
  
## Grundlegende E\/A\-Klassen für Dateien, Laufwerke und Verzeichnisse  
 In der folgenden Tabelle werden die wichtigsten für Datei\-E\/A\-Vorgänge verwendeten Klassen aufgeführt und beschrieben.  
  
|Klasse|Beschreibung|  
|------------|------------------|  
|<xref:System.IO.Directory?displayProperty=fullName>|Stellt statische Methoden zum Erstellen, Verschieben und Auflisten von Verzeichnissen und Unterverzeichnissen zur Verfügung.|  
|<xref:System.IO.DirectoryInfo?displayProperty=fullName>|Stellt Instanzmethoden zum Erstellen, Verschieben und Auflisten von Verzeichnissen und Unterverzeichnissen zur Verfügung.|  
|<xref:System.IO.DriveInfo?displayProperty=fullName>|Stellt Instanzmethoden für das Erstellen, Verschieben und Auflisten von Laufwerken zur Verfügung.|  
|<xref:System.IO.File?displayProperty=fullName>|Stellt statische Methoden für das Erstellen, Kopieren, Löschen, Verschieben und Öffnen von Dateien zur Verfügung und unterstützt das Erstellen eines `FileStream`.|  
|<xref:System.IO.FileAccess?displayProperty=fullName>|Definiert Konstanten für Lese\-, Schreib\- oder Lese\-\/Schreibzugriff auf eine Datei.|  
|<xref:System.IO.FileAttributes?displayProperty=fullName>|Stellt Attribute für Dateien und Verzeichnisse bereit, z. B. `Archive`, `Hidden` und `ReadOnly`.|  
|<xref:System.IO.FileInfo?displayProperty=fullName>|Stellt statische Methoden für das Erstellen, Kopieren, Löschen, Verschieben und Öffnen von Dateien zur Verfügung und unterstützt das Erstellen eines `FileStream`.|  
|<xref:System.IO.FileMode?displayProperty=fullName>|Legt fest, wie eine Datei geöffnet wird.  Dieser Parameter wird in vielen der Konstruktoren für `FileStream` und `IsolatedStorageFileStream` sowie für die `Open`\-Methoden von <xref:System.IO.File> und <xref:System.IO.FileInfo> angegeben.|  
|<xref:System.IO.FileShare?displayProperty=fullName>|Definiert Konstanten, mit denen die Art des Zugriffs anderer Dateistreams auf dieselbe Datei festgelegt werden kann.|  
|<xref:System.IO.Path?displayProperty=fullName>|Stellt Methoden und Eigenschaften für die Verarbeitung von Verzeichniszeichenfolgen bereit.|  
|<xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>|Legt durch Definition der Berechtigungen <xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> und <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> den Zugriff auf Dateien und Ordner fest.|  
  
## Klassen für die Erstellung von Streams  
 In der folgenden Tabelle werden die wichtigsten Klassen für die Erstellung von Streams aufgeführt und beschrieben.  
  
|Klasse|Beschreibung|  
|------------|------------------|  
|<xref:System.IO.BufferedStream?displayProperty=fullName>|Fügt eine Pufferungsschicht für Lese\- und Schreibvorgänge in einem anderen Stream hinzu.|  
|<xref:System.IO.FileStream?displayProperty=fullName>|Unterstützt über die <xref:System.IO.FileStream.Seek%2A>\-Methode den zufälligen Zugriff auf Dateien.  <xref:System.IO.FileStream> öffnet Dateien standardmäßig synchron, unterstützt aber auch asynchrone Vorgänge.|  
|<xref:System.IO.MemoryStream?displayProperty=fullName>|Erstellt einen Stream, der keine Datei, sondern den Arbeitsspeicher als Sicherungsspeicher verwendet.|  
|<xref:System.Net.Sockets.NetworkStream?displayProperty=fullName>|Stellt den zugrunde liegenden Datenstream für den Netzwerkzugriff bereit.|  
|<xref:System.Security.Cryptography.CryptoStream?displayProperty=fullName>|Definiert einen Stream, der Datenstreams mit kryptografischen Transformationen verknüpft.|  
  
## Klassen für das Lesen und Schreiben von Streams  
 In der folgenden Tabelle werden die einzelnen Klassen aufgeführt, die für das Lesen und Schreiben von Streams verwendet werden.  
  
|**Klasse**|**Beschreibung**|  
|----------------|----------------------|  
|<xref:System.IO.BinaryReader?displayProperty=fullName>|Liest codierte Zeichenfolgen und primitive Datentypen aus einem <xref:System.IO.FileStream>.|  
|<xref:System.IO.BinaryWriter?displayProperty=fullName>|Schreibt codierte Zeichenfolgen und primitive Datentypen in einen <xref:System.IO.FileStream>.|  
|<xref:System.IO.StreamReader?displayProperty=fullName>|Liest Zeichen aus einem <xref:System.IO.FileStream>\-Objekt und konvertiert Zeichen mithilfe von <xref:System.IO.StreamReader.CurrentEncoding%2A> in Bytes und umgekehrt.  <xref:System.IO.StreamReader> verfügt über einen Konstruktor, der die richtige <xref:System.IO.StreamReader.CurrentEncoding%2A>\-Eigenschaft für den jeweiligen Stream ermittelt, und zwar auf Basis einer vorhandenen <xref:System.IO.StreamReader.CurrentEncoding%2A>\-spezifischen Präambel, z. B. einer Markierung für die Bytereihenfolge.|  
|<xref:System.IO.StreamWriter?displayProperty=fullName>|Schreibt Zeichen in einen `FileStream`. Dabei wird <xref:System.IO.StreamWriter.Encoding%2A> für die Konvertierung von Zeichen in Bytes verwendet.|  
|<xref:System.IO.StringReader?displayProperty=fullName>|Liest Zeichen aus einem `String`.  Die Ausgabe kann entweder ein Stream in einer beliebigen Codierung oder ein `String` sein.|  
|<xref:System.IO.StringWriter?displayProperty=fullName>|Schreibt Zeichen in einen `String`.  Die Ausgabe kann entweder ein Stream in einer beliebigen Codierung oder ein `String` sein.|  
  
## Siehe auch  
 [Erstellen von Streams](../Topic/Composing%20Streams.md)   
 [Datei\- und Stream\-E\/A](../Topic/File%20and%20Stream%20I-O.md)   
 [Asynchrone Datei\-E\/A](../Topic/Asynchronous%20File%20I-O.md)   
 [Grundlagen zu Datei\-E\/A\-Vorgängen und dem Dateisystem in .NET Framework \(Visual Basic\)](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)