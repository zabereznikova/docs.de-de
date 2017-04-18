---
title: "Für Datei-E/A-Vorgänge und Dateisystem in .NET Framework verwendete Klassen (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- file I/O classes
ms.assetid: 4a5ca924-eea8-4a95-a5f0-6ac10de276a3
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6bf3902995531768b8b065aca70790c16d77b0ce
ms.lasthandoff: 03/13/2017

---
# <a name="classes-used-in-net-framework-file-io-and-the-file-system-visual-basic"></a>Für Datei-E/A-Vorgänge und die Arbeit mit dem Dateisystem in .NET Framework verwendete Klassen (Visual Basic)
In den folgenden Tabellen sind die Klassen aufgelistet, die häufig für .NET Framework-Datei-E/A verwendet werden, kategorisiert in Datei-E/A-Klassen, Klassen zum Erstellen von Streams und Klassen zum Lesen und Schreiben in Streams.  
  
 Für das Betreten der [!INCLUDE[dnprdnlong](../../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)]-Dokumentation und eine umfassendere Auflistung siehe [Übersicht über die Klassenbibliothek](https://msdn.microsoft.com/library/hfa3fa08).  
  
## <a name="basic-io-classes-for-files-drives-and-directories"></a>Grundlegende E/A-Klassen für Dateien, Laufwerke und Verzeichnisse  
 In der folgenden Tabelle werden die wichtigsten Klassen aufgeführt und beschrieben, die für Datei-E/A verwendet werden.  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|<xref:System.IO.Directory?displayProperty=fullName>|Stellt statische Methoden zum Erstellen, Verschieben und Auflisten über Verzeichnisse und Unterverzeichnisse hinweg zur Verfügung.|  
|<xref:System.IO.DirectoryInfo?displayProperty=fullName>|Stellt Instanzmethoden zum Erstellen, Verschieben und Auflisten über Verzeichnisse und Unterverzeichnisse hinweg zur Verfügung.|  
|<xref:System.IO.DriveInfo?displayProperty=fullName>|Stellt Instanzmethoden zum Erstellen, Verschieben und Auflisten über Laufwerke hinweg zur Verfügung.|  
|<xref:System.IO.File?displayProperty=fullName>|Stellt statische Methoden zum Erstellen, Kopieren, Löschen, Verschieben und Öffnen von Dateien zur Verfügung und unterstützt das Erstellen eines `FileStream`.|  
|<xref:System.IO.FileAccess?displayProperty=fullName>|Definiert Konstanten für den Lese-, Schreib- oder Lese-/Schreibzugriff auf eine Datei.|  
|<xref:System.IO.FileAttributes?displayProperty=fullName>|Stellt Attribute für Dateien und Verzeichnisse wie `Archive`, `Hidden` und `ReadOnly` bereit.|  
|<xref:System.IO.FileInfo?displayProperty=fullName>|Stellt statische Methoden zum Erstellen, Kopieren, Löschen, Verschieben und Öffnen von Dateien zur Verfügung und unterstützt das Erstellen eines `FileStream`.|  
|<xref:System.IO.FileMode?displayProperty=fullName>|Steuert, wie eine Datei geöffnet wird. Dieser Parameter wird in vielen der Konstruktoren für `FileStream` und `IsolatedStorageFileStream` sowie für die `Open`-Methoden von <xref:System.IO.File>und <xref:System.IO.FileInfo> angegeben.|  
|<xref:System.IO.FileShare?displayProperty=fullName>|Definiert Konstanten für das Steuern des Zugriffstyps von anderen Dateistreams auf dieselbe Datei.|  
|<xref:System.IO.Path?displayProperty=fullName>|Stellt Methoden und Eigenschaften für die Verarbeitung von Verzeichniszeichenfolgen zur Verfügung.|  
|<xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>|Steuert den Zugriff auf Dateien und Ordner durch Definieren der Berechtigungen <xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> und <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>.|  
  
## <a name="classes-used-to-create-streams"></a>Klassen zum Erstellen von Streams  
 In der folgenden Tabelle werden die wichtigsten Klassen aufgeführt und beschrieben, die zum Erstellen von Streams verwendet werden.  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|<xref:System.IO.BufferedStream?displayProperty=fullName>|Fügt eine Pufferebene zu Lese- und Schreibvorgängen auf einem anderen Stream hinzu.|  
|<xref:System.IO.FileStream?displayProperty=fullName>|Unterstützt den zufälligen Zugriff auf Dateien über die <xref:System.IO.FileStream.Seek%2A>-Methode. <xref:System.IO.FileStream> öffnet Dateien standardmäßig synchron, unterstützt aber auch den asynchronen Vorgang.|  
|<xref:System.IO.MemoryStream?displayProperty=fullName>|Erstellt einen Stream, der den Arbeitsspeicher anstatt einer Datei als Sicherungsspeicher verwendet.|  
|<xref:System.Net.Sockets.NetworkStream?displayProperty=fullName>|Stellt den zugrunde liegenden Datenstrom für den Netzwerkzugriff bereit.|  
|<xref:System.Security.Cryptography.CryptoStream?displayProperty=fullName>|Definiert einen Stream, der Datenstreams mit kryptografischen Transformationen verknüpft.|  
  
## <a name="classes-used-to-read-from-and-write-to-streams"></a>Klassen, die zum Lesen aus und Schreiben an Streams verwendet werden  
 Die folgende Tabelle zeigt die spezifischen Klassen, die zum Lesen aus und Schreiben an Dateien mit Streams verwendet werden.  
  
|**Klasse**|**Beschreibung**|  
|---------------|---------------------|  
|<xref:System.IO.BinaryReader?displayProperty=fullName>|Liest codierte Zeichenfolgen und primitive Datentypen aus einem <xref:System.IO.FileStream>.|  
|<xref:System.IO.BinaryWriter?displayProperty=fullName>|Schreibt codierte Zeichenfolgen und primitive Datentypen an einen <xref:System.IO.FileStream>.|  
|<xref:System.IO.StreamReader?displayProperty=fullName>|Liest Zeichen aus einem <xref:System.IO.FileStream> und verwendet dabei <xref:System.IO.StreamReader.CurrentEncoding%2A>, um Zeichen in Bytes und umgekehrt zu konvertieren. <xref:System.IO.StreamReader> verfügt über einen Konstruktor, der versucht, das richtige <xref:System.IO.StreamReader.CurrentEncoding%2A> für einen Stream basierend auf dem Vorhandensein einer <xref:System.IO.StreamReader.CurrentEncoding%2A>-spezifischen Präambel wie einer Bytereihenfolge-Marke zu ermitteln.|  
|<xref:System.IO.StreamWriter?displayProperty=fullName>|Schreibt Zeichen an einen `FileStream` und verwendet dabei <xref:System.IO.StreamWriter.Encoding%2A>, um Zeichen in Bytes zu konvertieren.|  
|<xref:System.IO.StringReader?displayProperty=fullName>|Liest Zeichen aus einem `String`. Die Ausgabe kann entweder ein Stream in einer beliebigen Codierung oder ein `String` sein.|  
|<xref:System.IO.StringWriter?displayProperty=fullName>|Schreibt Zeichen an einen `String`. Die Ausgabe kann entweder ein Stream in einer beliebigen Codierung oder ein `String` sein.|  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Datenströmen](https://msdn.microsoft.com/library/e4y2dch9)   
 [Datei- und Stream-E/A](https://msdn.microsoft.com/library/k3352a4t)   
 [Asynchrone Datei-E/A](https://msdn.microsoft.com/library/kztecsys)   
 [Grundlagen zu Datei-E/A-Vorgängen und dem Dateisystem in .NET Framework (Visual Basic)](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)
