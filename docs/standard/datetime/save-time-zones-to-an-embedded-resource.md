---
title: "Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zeitzonenobjekte [.NET Framework], Speichern"
  - "Zeitzonenobjekte [.NET Framework], Serialisieren"
  - "Zeitzonen [.NET Framework], Speichern"
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource
Für eine Anwendung, die Zeitzonen unterstützt, muss häufig eine bestimmte Zeitzone vorhanden sein.  Da die Verfügbarkeit einzelner <xref:System.TimeZoneInfo>\-Objekte jedoch von den Daten abhängt, die in der Registrierung des lokalen Systems gespeichert sind, können selbst normalerweise vorhandene Zeitzonen fehlen.  Darüber hinaus werden Daten über benutzerdefinierte Zeitzonen, die mit der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>\-Methode instanziiert werden, nicht zusammen mit anderen Zeitzonendaten in der Registrierung gespeichert.  Um sicherzustellen, dass diese Zeitzonen zur Verfügung stehen, wenn sie benötigt werden, können Sie sie durch Serialisierung speichern und zu einem späteren Zeitpunkt durch Deserialisierung wiederherstellen.  
  
 In der Regel erfolgt die Serialisierung eines <xref:System.TimeZoneInfo>\-Objekts unabhängig von der Anwendung, die Zeitzonen unterstützt.  Je nachdem, welcher Datenspeicher zum Speichern serialisierter <xref:System.TimeZoneInfo>\-Objekte verwendet wird, werden Zeitzonendaten möglicherweise als Teil einer Einrichtungs\- oder Installationsroutine serialisiert \(wenn die Daten zum Beispiel in einem Anwendungsschlüssel der Registrierung gespeichert werden\) oder als Teil einer Dienstprogrammroutine, die vor dem Kompilieren der endgültigen Anwendung ausgeführt wird \(wenn zum Beispiel die serialisierten Daten in einer .NET XML\-Ressourcendatei \(.resx\) gespeichert werden\).  
  
 Außer einer Ressourcendatei, die zusammen mit der Anwendung kompiliert wird, können zahlreiche weitere Datenspeicher für Zeitzonendaten verwendet werden.  Hierzu gehört Folgendes:  
  
-   Die Registrierung.  Beachten Sie, dass eine Anwendung zur Speicherung benutzerdefinierter Zeitzonendaten die Unterschlüssel ihres eigenen Anwendungsschlüssels verwenden sollte, anstatt die Unterschlüssel von HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Time Zones zu verwenden.  
  
-   Konfigurationsdateien  
  
-   Andere Systemdateien  
  
### So speichern Sie eine Zeitzone durch Serialisierung in eine RESX\-Datei  
  
1.  Rufen Sie eine vorhandene Zeitzone ab, oder erstellen Sie eine neue Zeitzone.  
  
     Informationen zum Abrufen einer vorhandenen Zeitzone finden Sie unter [Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte](../../../docs/standard/datetime/access-utc-and-local.md) und [Gewusst wie: Instanziieren eines TimeZoneInfo\-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md).  
  
     Rufen Sie zum Erstellen einer neuen Zeitzone eine der Überladungen der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>\-Methode auf.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) und [Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).  
  
2.  Rufen Sie die <xref:System.TimeZoneInfo.ToSerializedString%2A>\-Methode auf, um eine Zeichenfolge zu erstellen, die die Daten der Zeitzonen enthält.  
  
3.  Instanziieren Sie ein <xref:System.IO.StreamWriter>\-Objekt, indem Sie den Namen sowie optional den Pfad zur RESX\-Datei des <xref:System.IO.StreamWriter>\-Klassenkonstruktors angeben.  
  
4.  Instanziieren Sie ein <xref:System.Resources.ResXResourceWriter>\-Objekt, indem Sie das <xref:System.IO.StreamWriter>\-Objekt an den <xref:System.Resources.ResXResourceWriter>\-Klassenkonstruktor übergeben.  
  
5.  Übergeben Sie die serialisierte Zeichenfolge der Zeitzone an die <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=fullName>\-Methode.  
  
6.  Rufen Sie die <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=fullName>\-Methode auf.  
  
7.  Rufen Sie die <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=fullName>\-Methode auf.  
  
8.  Schließen Sie das <xref:System.IO.StreamWriter>\-Objekt, indem Sie seine <xref:System.IO.StreamWriter.Close%2A>\-Methode aufrufen.  
  
9. Fügen Sie die generierte RESX\-Datei dem Visual Studio\-Projekt der Anwendung hinzu.  
  
10. Stellen Sie anhand des **Eigenschaftenfensters** in Visual Studio sicher, dass für die **Buildvorgang**\-Eigenschaft der RESX\-Datei die Option **Eingebettete Ressource** festgelegt ist.  
  
## Beispiel  
 Im folgenden Beispiel werden ein <xref:System.TimeZoneInfo>\-Objekt, das Central Normalzeit darstellt, sowie ein <xref:System.TimeZoneInfo>\-Objekt, das die Zeitzone für Palmer Station in der Antarktis darstellt, in einer .NET XML\-Ressourcendatei mit dem Namen SerializedTimeZones.resx serialisiert.  Central Normalzeit ist in der Regel in der Registrierung definiert, und bei Palmer Station, Antarktis handelt es sich um eine benutzerdefinierte Zeitzone.  
  
 [!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
 [!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]  
  
 In diesem Beispiel werden <xref:System.TimeZoneInfo>\-Objekte serialisiert, damit sie beim Kompilieren in einer Ressourcendatei verfügbar sind.  
  
 Da durch die <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=fullName>\-Methode vollständige Headerinformationen zu einer .NET XML\-Ressourcendatei hinzugefügt werden, kann sie nicht zum Hinzufügen von Ressourcen zu einer vorhandenen Datei verwendet werden.  Im Beispiel wird hierbei so verfahren, dass die Datei SerializedTimeZones.resx gesucht wird, und wenn sie vorhanden ist, alle Ressourcen außer den beiden serialisierten Zeitzonen in einem allgemeinen <xref:System.Collections.Generic.Dictionary%602>\-Objekt gespeichert werden.  Die vorhandene Datei wird dann gelöscht, und die vorhandenen Ressourcen werden einer neuen SerializedTimeZones.resx\-Datei hinzugefügt.  Die Daten der serialisierten Zeitzonen werden dieser Datei ebenfalls hinzugefügt.  
  
 Die Schlüsselfelder \(oder **Name**\) von Ressourcen sollten keine eingebetteten Leerzeichen enthalten.  Die <xref:System.String.Replace%28System.String%2CSystem.String%29>\-Methode wird aufgerufen, um alle eingebetteten Leerzeichen in Zeitzonenbezeichnern zu entfernen, bevor diese der Ressourcendatei zugewiesen werden.  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein Verweis auf System.Windows.Forms.dll und System.Core.dll muss dem Projekt hinzugefügt werden.  
  
-   Die folgenden Namespaces müssen importiert werden:  
  
     [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
     [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)   
 [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)   
 [Gewusst wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)