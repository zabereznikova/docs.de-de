---
title: Für Datei-E/A-Vorgänge und die Arbeit mit dem Dateisystem in .NET Framework verwendete Klassen
ms.date: 07/20/2015
helpviewer_keywords:
- file I/O classes
ms.assetid: 4a5ca924-eea8-4a95-a5f0-6ac10de276a3
ms.openlocfilehash: fe70f8fb655579049bb36fc324d04530259d25f2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348929"
---
# <a name="classes-used-in-net-framework-file-io-and-the-file-system-visual-basic"></a>Für Datei-E/A-Vorgänge und die Arbeit mit dem Dateisystem in .NET Framework verwendete Klassen (Visual Basic)

In den folgenden Tabellen sind die Klassen aufgelistet, die häufig für .NET Framework-Datei-E/A verwendet werden, kategorisiert in Datei-E/A-Klassen, Klassen zum Erstellen von Streams und Klassen zum Lesen und Schreiben in Streams.  
  
Eine umfassendere Auflistung finden Sie unter [Übersicht über die Klassenbibliothek](../../../../standard/class-library-overview.md).  
  
## <a name="basic-io-classes-for-files-drives-and-directories"></a>Grundlegende E/A-Klassen für Dateien, Laufwerke und Verzeichnisse  

 In der folgenden Tabelle werden die wichtigsten Klassen aufgeführt und beschrieben, die für Datei-E/A verwendet werden.  
  
|Klasse|BESCHREIBUNG|  
|-----------|-----------------|  
|<xref:System.IO.Directory?displayProperty=nameWithType>|Stellt statische Methoden zum Erstellen, Verschieben und Auflisten über Verzeichnisse und Unterverzeichnisse hinweg zur Verfügung.|  
|<xref:System.IO.DirectoryInfo?displayProperty=nameWithType>|Stellt Instanzmethoden zum Erstellen, Verschieben und Auflisten über Verzeichnisse und Unterverzeichnisse hinweg zur Verfügung.|  
|<xref:System.IO.DriveInfo?displayProperty=nameWithType>|Stellt Instanzmethoden zum Erstellen, Verschieben und Auflisten über Laufwerke hinweg zur Verfügung.|  
|<xref:System.IO.File?displayProperty=nameWithType>|Stellt statische Methoden zum Erstellen, Kopieren, Löschen, Verschieben und Öffnen von Dateien zur Verfügung und unterstützt das Erstellen eines `FileStream`.|  
|<xref:System.IO.FileAccess?displayProperty=nameWithType>|Definiert Konstanten für den Lese-, Schreib- oder Lese-/Schreibzugriff auf eine Datei.|  
|<xref:System.IO.FileAttributes?displayProperty=nameWithType>|Stellt Attribute für Dateien und Verzeichnisse wie `Archive`, `Hidden` und `ReadOnly` bereit.|  
|<xref:System.IO.FileInfo?displayProperty=nameWithType>|Stellt statische Methoden zum Erstellen, Kopieren, Löschen, Verschieben und Öffnen von Dateien zur Verfügung und unterstützt das Erstellen eines `FileStream`.|  
|<xref:System.IO.FileMode?displayProperty=nameWithType>|Steuert, wie eine Datei geöffnet wird. Dieser Parameter wird in vielen der Konstruktoren für `FileStream` und `IsolatedStorageFileStream` sowie für die `Open`-Methoden von <xref:System.IO.File> und <xref:System.IO.FileInfo> angegeben.|  
|<xref:System.IO.FileShare?displayProperty=nameWithType>|Definiert Konstanten für das Steuern des Zugriffstyps von anderen Dateistreams auf dieselbe Datei.|  
|<xref:System.IO.Path?displayProperty=nameWithType>|Stellt Methoden und Eigenschaften für die Verarbeitung von Verzeichniszeichenfolgen zur Verfügung.|  
|<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>|Steuert den Zugriff von Dateien und Ordnern durch Definieren der Berechtigungen <xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> und <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>.|  
  
## <a name="classes-used-to-create-streams"></a>Klassen zum Erstellen von Streams  

 In der folgenden Tabelle werden die wichtigsten Klassen aufgeführt und beschrieben, die zum Erstellen von Streams verwendet werden.  
  
|Klasse|BESCHREIBUNG|  
|-----------|-----------------|  
|<xref:System.IO.BufferedStream?displayProperty=nameWithType>|Fügt eine Pufferebene zu Lese- und Schreibvorgängen auf einem anderen Stream hinzu.|  
|<xref:System.IO.FileStream?displayProperty=nameWithType>|Unterstützt den zufälligen Zugriff auf Dateien über die <xref:System.IO.FileStream.Seek%2A>-Methode. <xref:System.IO.FileStream> öffnet Dateien standardmäßig synchron, unterstützt aber auch den asynchronen Vorgang.|  
|<xref:System.IO.MemoryStream?displayProperty=nameWithType>|Erstellt einen Stream, der den Arbeitsspeicher anstatt einer Datei als Sicherungsspeicher verwendet.|  
|<xref:System.Net.Sockets.NetworkStream?displayProperty=nameWithType>|Stellt den zugrunde liegenden Datenstrom für den Netzwerkzugriff bereit.|  
|<xref:System.Security.Cryptography.CryptoStream?displayProperty=nameWithType>|Definiert einen Stream, der Datenstreams mit kryptografischen Transformationen verknüpft.|  
  
## <a name="classes-used-to-read-from-and-write-to-streams"></a>Klassen, die zum Lesen aus und Schreiben an Streams verwendet werden  

 Die folgende Tabelle zeigt die spezifischen Klassen, die zum Lesen aus und Schreiben an Dateien mit Streams verwendet werden.  
  
|**Klasse**|**Beschreibung**|  
|---------------|---------------------|  
|<xref:System.IO.BinaryReader?displayProperty=nameWithType>|Liest codierte Zeichenfolgen und primitive Datentypen aus einem <xref:System.IO.FileStream>.|  
|<xref:System.IO.BinaryWriter?displayProperty=nameWithType>|Schreibt codierte Zeichenfolgen und primitive Datentypen in einen <xref:System.IO.FileStream>.|  
|<xref:System.IO.StreamReader?displayProperty=nameWithType>|Liest Zeichen aus einem <xref:System.IO.FileStream>, wobei <xref:System.IO.StreamReader.CurrentEncoding%2A> zum Konvertieren von Zeichen in und aus Bytes verwendet wird. <xref:System.IO.StreamReader> verfügt über einen Konstruktor, der basierend auf dem Vorhandensein einer <xref:System.IO.StreamReader.CurrentEncoding%2A>-spezifischen Präambel (z.B. einer Bytereihenfolge-Marke) versucht, die richtige <xref:System.IO.StreamReader.CurrentEncoding%2A> für einen bestimmten Stream zu ermitteln.|  
|<xref:System.IO.StreamWriter?displayProperty=nameWithType>|Schreibt Zeichen in einen `FileStream`, wobei <xref:System.IO.StreamWriter.Encoding%2A> zum Konvertieren von Zeichen in und aus Bytes verwendet wird.|  
|<xref:System.IO.StringReader?displayProperty=nameWithType>|Liest Zeichen aus einem `String`. Die Ausgabe kann entweder ein Stream in einer beliebigen Codierung oder ein `String` sein.|  
|<xref:System.IO.StringWriter?displayProperty=nameWithType>|Schreibt Zeichen an einen `String`. Die Ausgabe kann entweder ein Stream in einer beliebigen Codierung oder ein `String` sein.|  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Streams](../../../../standard/io/composing-streams.md)
- [Datei- und Stream-E/A](../../../../standard/io/index.md)
- [Asynchronous File I/O](../../../../standard/io/asynchronous-file-i-o.md)
- [Grundlagen zu Datei-E/A-Vorgängen und dem Dateisystem in .NET Framework (Visual Basic)](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)
