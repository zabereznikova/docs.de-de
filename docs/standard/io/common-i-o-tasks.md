---
title: Allgemeine E/A-Aufgaben
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- I/O, common tasks
ms.assetid: bf00c380-706a-4e38-b829-454a480629fc
ms.openlocfilehash: 9474d6c0340583e285a6dc47933c602f799f121d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287421"
---
# <a name="common-io-tasks"></a>Allgemeine E/A-Aufgaben
Der <xref:System.IO>-Namespace stellt mehrere Klassen bereit, die verschiedene Aktionen ermöglichen, z. B. Lese- und Schreibvorgänge für Dateien, Verzeichnisse und Streams. Weitere Informationen finden Sie unter [File and Stream I/O (Datei- und Datenstrom-E/A)](index.md).  
  
## <a name="common-file-tasks"></a>Allgemeine Dateiaufgaben  
  
|Aufgabe|Siehe das Beispiel in diesem Thema:|  
|-------------------|--------------------------------------|  
|Erstellen einer Textdatei|<xref:System.IO.File.CreateText%2A?displayProperty=nameWithType> -Methode<br /><br /> <xref:System.IO.FileInfo.CreateText%2A?displayProperty=nameWithType> -Methode<br /><br /> <xref:System.IO.File.Create%2A?displayProperty=nameWithType> -Methode<br /><br /> <xref:System.IO.FileInfo.Create%2A?displayProperty=nameWithType> -Methode|  
|Schreiben von Text in eine Datei|[Gewusst wie: Schreiben von Text in eine Datei](how-to-write-text-to-a-file.md)<br /><br /> [Vorgehensweise: Schreiben einer Textdatei (C++/CLI)](/cpp/dotnet/how-to-write-a-text-file-cpp-cli)|  
|Lesen aus einer Textdatei|[Gewusst wie: Lesen von Text aus einer Datei](how-to-read-text-from-a-file.md)|  
|Anfügen von Text an eine Datei|[Gewusst wie: Öffnen und Anfügen an eine Protokolldatei](how-to-open-and-append-to-a-log-file.md)<br /><br /> <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType> -Methode<br /><br /> <xref:System.IO.FileInfo.AppendText%2A?displayProperty=nameWithType> -Methode|  
|Umbenennen oder Verschieben einer Datei|<xref:System.IO.File.Move%2A?displayProperty=nameWithType> -Methode<br /><br /> <xref:System.IO.FileInfo.MoveTo%2A?displayProperty=nameWithType> -Methode|  
|Löschen einer Datei|<xref:System.IO.File.Delete%2A?displayProperty=nameWithType> -Methode<br /><br /> <xref:System.IO.FileInfo.Delete%2A?displayProperty=nameWithType> -Methode|  
|Kopieren einer Datei|<xref:System.IO.File.Copy%2A?displayProperty=nameWithType> -Methode<br /><br /> <xref:System.IO.FileInfo.CopyTo%2A?displayProperty=nameWithType> -Methode|  
|Abrufen der Größe einer Datei|<xref:System.IO.FileInfo.Length%2A?displayProperty=nameWithType>-Eigenschaft|  
|Abrufen der Attribute einer Datei|<xref:System.IO.File.GetAttributes%2A?displayProperty=nameWithType> -Methode|  
|Festlegen der Attribute einer Datei|<xref:System.IO.File.SetAttributes%2A?displayProperty=nameWithType> -Methode|  
|Bestimmen, ob eine Datei vorhanden ist|<xref:System.IO.File.Exists%2A?displayProperty=nameWithType> -Methode|  
|Lesen aus einer Binärdatei|[Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei](how-to-read-and-write-to-a-newly-created-data-file.md)|  
|Schreiben in eine Binärdatei|[Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei](how-to-read-and-write-to-a-newly-created-data-file.md)|  
|Abrufen einer Dateierweiterung|<xref:System.IO.Path.GetExtension%2A?displayProperty=nameWithType> -Methode|  
|Abrufen des vollqualifizierten Pfads einer Datei|<xref:System.IO.Path.GetFullPath%2A?displayProperty=nameWithType> -Methode|  
|Abrufen des Dateinamens und der Dateierweiterung aus einem Pfad|<xref:System.IO.Path.GetFileName%2A?displayProperty=nameWithType> -Methode|  
|Ändern der Erweiterung einer Datei|<xref:System.IO.Path.ChangeExtension%2A?displayProperty=nameWithType> -Methode|  
  
## <a name="common-directory-tasks"></a>Allgemeine Verzeichnisaufgaben  
  
|Aufgabe|Siehe das Beispiel in diesem Thema:|  
|-------------------|--------------------------------------|  
|Zugreifen auf eine Datei in einem speziellen Ordner wie z. B. "Eigene Dateien"|[Gewusst wie: Schreiben von Text in eine Datei](how-to-write-text-to-a-file.md)|  
|Erstellen eines Verzeichnisses|<xref:System.IO.Directory.CreateDirectory%2A?displayProperty=nameWithType> -Methode<br /><br /> <xref:System.IO.FileInfo.Directory%2A?displayProperty=nameWithType>-Eigenschaft|  
|Erstellen eines Unterverzeichnisses|<xref:System.IO.DirectoryInfo.CreateSubdirectory%2A?displayProperty=nameWithType> -Methode|  
|Umbenennen oder Verschieben eines Verzeichnisses|<xref:System.IO.Directory.Move%2A?displayProperty=nameWithType> -Methode<br /><br /> <xref:System.IO.DirectoryInfo.MoveTo%2A?displayProperty=nameWithType> -Methode|  
|Kopieren eines Verzeichnisses|[Gewusst wie: Kopieren von Verzeichnissen](how-to-copy-directories.md)|  
|Löschen eines Verzeichnisses|<xref:System.IO.Directory.Delete%2A?displayProperty=nameWithType> -Methode<br /><br /> <xref:System.IO.DirectoryInfo.Delete%2A?displayProperty=nameWithType> -Methode|  
|Anzeigen der Dateien und Unterverzeichnisse in einem Verzeichnis|[Gewusst wie: Auflisten von Verzeichnissen und Dateien](how-to-enumerate-directories-and-files.md)|  
|Suchen der Größe eines Verzeichnisses|<xref:System.IO.Directory?displayProperty=nameWithType>-Klasse|  
|Bestimmen, ob ein Verzeichnis vorhanden ist|<xref:System.IO.Directory.Exists%2A?displayProperty=nameWithType> -Methode|  
  
## <a name="see-also"></a>Weitere Informationen

- [Datei- und Stream-E/A](index.md)
- [Erstellen von Streams](composing-streams.md)
- [Asynchronous File I/O](asynchronous-file-i-o.md)
