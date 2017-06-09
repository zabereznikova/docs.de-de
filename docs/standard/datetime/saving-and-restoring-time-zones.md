---
title: "Speichern und Wiederherstellen von Zeitzonen | Microsoft Docs"
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
  - "Deserialisierung [.NET Framework], Zeitzonen"
  - "Wiederherstellen von Zeitzonen"
  - "Speichern von Zeitzonen"
  - "Serialisierung [.NET Framework], Zeitzonen"
  - "Zeitzonenobjekte [.NET Framework], Deserialisieren"
  - "Zeitzonenobjekte [.NET Framework], Wiederherstellen"
  - "Zeitzonenobjekte [.NET Framework], Speichern"
  - "Zeitzonenobjekte [.NET Framework], Serialisieren"
  - "Zeitzonen [.NET Framework], Wiederherstellen"
  - "Zeitzonen [.NET Framework], Speichern"
ms.assetid: 4028b310-e7ce-49d4-a646-1e83bfaf6f9d
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Speichern und Wiederherstellen von Zeitzonen
Die <xref:System.TimeZoneInfo>\-Klasse stützt sich auf die Registrierung, um Daten vordefinierter Zeitzonen abzurufen.  Bei der Registrierung handelt es sich jedoch um eine dynamische Struktur.  Zudem werden die Zeitzonendaten in der Registrierung vom Betriebssystem in erster Linie dazu verwendet, Zeitanpassungen und \-umstellungen für das aktuelle Jahr vorzunehmen.  Dies hat zwei wesentliche Auswirkungen auf Anwendungen, die genaue Zeitzonendaten benötigen:  
  
-   Eine Zeitzone, die von einer Anwendung benötigt wird, ist möglicherweise nicht in der Registrierung definiert oder wurde umbenannt bzw. aus der Registrierung entfernt.  
  
-   Eine in der Registrierung definierte Zeitzone verfügt möglicherweise nicht über alle Daten zu bestimmten Anpassungsregeln, die für die Konvertierung historischer Zeitzonen notwendig sind.  
  
 Die <xref:System.TimeZoneInfo>\-Klasse geht auf diese Einschränkungen ein, indem sie das Serialisieren \(Speichern\) und Deserialisieren \(Wiederherstellen\) von Zeitzonendaten unterstützt.  
  
## Zeitzonenserialisierung und \-deserialisierung  
 Zum Speichern und Wiederherstellen einer Zeitzone durch Serialisierung und Deserialisierung von Zeitzonendaten müssen nur zwei Methodenaufrufe verwendet werden:  
  
-   Sie können ein <xref:System.TimeZoneInfo>\-Objekt serialisieren, indem Sie die <xref:System.TimeZoneInfo.ToSerializedString%2A>\-Methode des Objekts aufrufen.  Die Methode enthält keine Parameter und gibt eine Zeichenfolge mit den Zeitzonendaten zurück.  
  
-   Sie können ein <xref:System.TimeZoneInfo>\-Objekt aus einer serialisierten Zeichenfolge deserialisieren, indem Sie diese Zeichenfolge an die `static` \(`Shared` in Visual Basic\) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=fullName>\-Methode übergeben.  
  
## Szenarien für die Serialisierung und Deserialisierung  
 Durch die Möglichkeit, ein <xref:System.TimeZoneInfo>\-Objekt in einer Zeichenfolge zu speichern \(zu serialisieren\) und zur späteren Verwendung wiederherzustellen \(zu deserialisieren\), werden sowohl die Nützlichkeit als auch die Flexibilität der <xref:System.TimeZoneInfo>\-Klasse erhöht.  In diesem Abschnitt werden einige Situationen erläutert, in denen die Serialisierung und Deserialisierung am nützlichsten sind.  
  
### Serialisieren und Deserialisieren von Zeitzonendaten in einer Anwendung  
 Eine serialisierte Zeitzone kann bei Bedarf aus einer Zeichenfolge wiederhergestellt werden.  Dies kann von einer Anwendung durchgeführt werden, wenn mit einer aus der Registrierung abgerufenen Zeitzone das Datum und die Uhrzeit in einem bestimmten Datumsbereich nicht ordnungsgemäß konvertiert werden können.  So unterstützen zum Beispiel die Zeitzonendaten in der Registrierung von Windows XP eine einzelne Anpassungsregel, während die in der Registrierung von Windows Vista definierten Zeitzonen in der Regel Informationen zu zwei Anpassungsregeln bereitstellen.  Dies bedeutet, dass historische Zeitkonvertierungen möglicherweise ungenau sind.  Durch die Serialisierung und Deserialisierung von Zeitzonendaten kann diese Einschränkung umgangen werden.  
  
 Im folgenden Beispiel wird eine benutzerdefinierte <xref:System.TimeZoneInfo>\-Klasse, die keine Anpassungsregeln verwendet, definiert, um die Zeitzone Eastern Normalzeit von 1883 bis 1917, vor der Einführung der Sommerzeit in den USA dargestellt.  Die benutzerdefinierte Zeitzone ist in einer Variablen mit globaler Gültigkeit serialisiert.  An die Konvertierungsmethode der Zeitzone, `ConvertUtcTime`, wird eine koordinierte Weltzeit \(Coordinated Universal Time, UTC\) zur Konvertierung übergeben.  Wenn Datum und Uhrzeit im oder vor dem Jahr 1917 liegen, wird die benutzerdefinierte Zeitzone für Eastern Normalzeit aus einer serialisierten Zeichenfolge wiederhergestellt und ersetzt die aus der Registrierung abgerufene Zeitzone.  
  
 [!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
 [!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]  
  
### Behandlung von Zeitzonenausnahmen  
 Da die Registrierung eine dynamische Struktur darstellt, kann ihr Inhalt versehentlich oder absichtlich geändert werden.  Dies kann bedeuten, dass eine Zeitzone, die für die ordnungsgemäße Ausführung einer Anwendung notwendig ist und in der Registrierung definiert sein sollte, möglicherweise fehlt.  Wenn die Serialisierung und Deserialisierung von Zeitzonen nicht unterstützt wird, kann die resultierende <xref:System.TimeZoneNotFoundException> nur durch Beenden der Anwendung behandelt werden.  Bei Verwendung der Zeitzonenserialisierung und \-deserialsierung kann eine unerwartete <xref:System.TimeZoneNotFoundException> jedoch behandelt werden, indem Sie die benötigte Zeitzone aus einer serialisierten Zeichenfolge wiederherstellen, sodass die Anwendung weiter ausgeführt wird.  
  
 Im folgenden Beispiel wird eine benutzerdefinierte Zeitzone Central Normalzeit erstellt und serialisiert.  Anschließend wird versucht, die Zeitzone Central Normalzeit aus der Registrierung abzurufen.  Wenn durch den Abrufvorgang entweder eine <xref:System.TimeZoneNotFoundException> oder eine <xref:System.InvalidTimeZoneException> ausgelöst wird, deserialisiert der Ausnahmehandler die Zeitzone.  
  
 [!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
 [!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]  
  
### Speichern einer serialisierten Zeichenfolge und Wiederherstellen bei Bedarf  
 In den vorherigen Beispielen wurden Zeitzonendaten in einer Zeichenfolgevariablen gespeichert und bei Bedarf wiederhergestellt.  Die Zeichenfolge mit den serialisierten Zeitzonendaten selbst kann jedoch in einem beliebigen Speichermedium gespeichert werden, zum Beispiel in einer externen Datei, in einer in die Anwendung eingebetteten Ressourcendatei oder in der Registrierung. \(Beachten Sie, dass Daten über benutzerdefinierte Zeitzonen getrennt von den Zeitzonenschlüsseln des Systems in der Registrierung gespeichert werden sollten.\)  
  
 Indem eine serialisierte Zeitzonenzeichenfolge auf diese Weise gespeichert wird, wird die Erstellungsroutine für die Zeitzone auch von der Anwendung selbst getrennt.  Eine Zeitzonenerstellungsroutine kann zum Beispiel eine Datendatei mit historischen Zeitzonendaten, die von der Anwendung verwendet werden können, ausführen und erstellen.  Die Datendatei kann dann zusammen mit der Anwendung installiert werden. Sie kann geöffnet werden, und eine oder mehrere Zeitzonen in der Datei können deserialisiert werden, wenn sie von der Anwendung benötigt werden.  
  
 Ein Beispiel für die Verwendung einer eingebetteten Ressource zum Speichern serialisierter Zeitzonendaten finden Sie unter [Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) und [Gewusst wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)