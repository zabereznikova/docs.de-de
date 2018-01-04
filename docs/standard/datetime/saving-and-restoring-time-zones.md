---
title: Speichern und Wiederherstellen von Zeitzonen
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- restoring time zones
- deserialization [.NET Framework], time zones
- serialization [.NET Framework], time zones
- time zone objects [.NET Framework], restoring
- saving time zones
- time zone objects [.NET Framework], deserializing
- time zones [.NET Framework], saving
- time zones [.NET Framework], restoring
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 4028b310-e7ce-49d4-a646-1e83bfaf6f9d
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d9451b1b0ff41f32c31ef3574b5684ae5a02e252
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="saving-and-restoring-time-zones"></a>Speichern und Wiederherstellen von Zeitzonen

Die <xref:System.TimeZoneInfo> Klasse stützt sich auf die Registrierung zum Abrufen von Daten mit vordefinierten Zeitzone. Allerdings ist die Registrierung einer dynamischen Struktur. Darüber hinaus wird die Registrierung enthält Zeitzoneninformationen vom Betriebssystem verwendet, in erster Linie zum Behandeln von Anpassungen der Uhrzeit und Konvertierungen für das laufende Jahr. Dies hat zwei wichtige Implikationen für Anwendungen, die genau Zeitzonendaten abhängig:

* Eine Zeitzone, die von einer Anwendung erforderlich ist, kann nicht in der Registrierung definiert werden, oder möglicherweise wurde Sie umbenannt oder entfernt Sie aus der Registrierung.

* Eine Zeitzone, die in der Registrierung definiert ist, kann Informationen zu bestimmten Anpassungsregeln fehlen, die für historische zeitzonenkonvertierungen erforderlich sind.

Die <xref:System.TimeZoneInfo> Klasse behebt diese Einschränkungen durch die Unterstützung für die Serialisierung (Speichern) und der Deserialisierung (Wiederherstellen), der Zeitzonendaten.

## <a name="time-zone-serialization-and-deserialization"></a>Zeitzonenserialisierung und Deserialisierung

Speichern und Wiederherstellen einer Zeitzone durch serialisieren und Deserialisieren von Zeitzonendaten umfasst nur zwei Methodenaufrufe:

* Sie können serialisieren eine <xref:System.TimeZoneInfo> Objekt durch Aufrufen des Objekts <xref:System.TimeZoneInfo.ToSerializedString%2A> Methode. Die Methode nimmt keine Parameter und gibt eine Zeichenfolge, die Zeitzoneninformationen enthält.

* Deserialisieren Sie können ein <xref:System.TimeZoneInfo> Objekt aus einer serialisierten Zeichenfolge durch Übergeben dieser Zeichenfolge an die `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> Methode.

## <a name="serialization-and-deserialization-scenarios"></a>Serialisierung und Deserialisierung Szenarien

Die Fähigkeit zum Speichern (oder serialisieren) eine <xref:System.TimeZoneInfo> Objekt in eine Zeichenfolge, und stellen Sie wieder her (bzw. zu deserialisierenden) für die spätere Verwendung erhöht das Hilfsprogramm und die Flexibilität der <xref:System.TimeZoneInfo> Klasse. In diesem Abschnitt werden einige Situationen, in denen Serialisierung und Deserialisierung besonders hilfreich sind.

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a>Serialisieren und Deserialisieren von Zeitzonendaten in einer Anwendung

Eine serialisierte Zeitzone kann aus einer Zeichenfolge wiederhergestellt werden, wenn er benötigt wird. Eine Anwendung möglicherweise vorgehen, wenn die Zeitzone aus der Registrierung abgerufene nicht ordnungsgemäß einer Datums- und Uhrzeitangabe innerhalb eines bestimmten Zeitraums konvertieren kann. Zeitzonendaten in der Registrierung von Windows XP unterstützt z. B. eine Anpassungsregel, während in der Regel in der Windows Vista-Registrierung definierten Zeitzonen Informationen über zwei Anpassungsregeln bereitstellen. Dies bedeutet, dass Verlaufsdaten Time-Konvertierungen ungenau sein können. Serialisierung und Deserialisierung von Zeitzonendaten können diese Einschränkung zu behandeln.

Im folgenden Beispiel wird eine benutzerdefinierte <xref:System.TimeZoneInfo> -Klasse, die ohne Anpassungsregeln wird definiert, um den USA darzustellen Eastern Standard Time Zone von 1883 1917, vor der Einführung der Sommerzeit in den Vereinigten Staaten. Die benutzerdefinierten Zeitzone wird in einer Variablen serialisiert, die der globale Bereich gilt. Die Konvertierungsmethode Zeitzone `ConvertUtcTime`, wie oft die Coordinated Universal Time (UTC) konvertiert übergeben wird. Tritt das Datum und die Uhrzeit in 1917 oder früher, wird der benutzerdefinierten Zeitzone Eastern Standard wird aus einer serialisierten Zeichenfolge wiederhergestellt und ersetzt die Zeitzone aus der Registrierung abgerufen.

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a>Behandeln von Ausnahmen mit Zeitzone

Da es sich bei die Registrierung eine dynamische Struktur handelt, unterliegen seinen Inhalt versehentlich oder absichtlich geändert. Dies bedeutet, dass eine Zeitzone, die in der Registrierung definiert werden soll, und dies ist erforderlich, damit eine Anwendung erfolgreich ausgeführt, nicht vorhanden sein können. Ohne Unterstützung für die Zeitzonenserialisierung und Deserialisierung, haben Sie etwas Wahl behandelt das resultierende <xref:System.TimeZoneNotFoundException> durch Beenden der Anwendung. Mithilfe von Zeitzonenserialisierung und Deserialisierung, Sie können jedoch verarbeiten unerwartete <xref:System.TimeZoneNotFoundException> durch das Wiederherstellen der erforderlichen Zeitzone aus einer serialisierten Zeichenfolge, und die Anwendung wird weiterhin ausgeführt.

Das folgende Beispiel erstellt und eine benutzerdefinierte Zeitzone Central Normalzeit serialisiert. Anschließend wird versucht, die zentralen standardmäßigen Zeitzone aus der Registrierung abzurufen. Wenn der Abrufvorgang entweder eine <xref:System.TimeZoneNotFoundException> oder ein <xref:System.InvalidTimeZoneException>, deserialisiert der Ausnahmehandler die Zeitzone.

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a>Das Speichern einer serialisierten Zeichenfolge und Wiederherstellen bei Bedarf

In den vorherigen Beispielen haben Zeitzoneninformationen an eine Zeichenfolgenvariable gespeichert und bei Bedarf wiederhergestellt. Die Zeichenfolge, die serialisierten enthält Zeitzoneninformationen selbst in einigen Speichermedium, z. B. eine externe Datei, eine Ressourcendatei gespeichert werden kann jedoch in der Anwendung oder die Registrierung eingebettet sind. (Beachten Sie, dass Informationen über benutzerdefinierte Zeitzonen abgesehen von der Zeitzonenschlüssel in der Registrierung gespeichert werden muss.)

Speichern einer serialisierten Zeitzonenzeichenfolge auf diese Weise werden außerdem die Routine zum Erstellen von Zeitzonen aus der Anwendung selbst getrennt. Beispielsweise kann eine Routine zum Erstellen von Zeitzonen ausführen und erstellen eine Datendatei, die historische Zeitzoneninformationen enthält, die eine Anwendung verwenden können. Die Datendatei kann dann mit der Anwendung installiert werden und kann geöffnet werden und mindestens eines seiner Zeitzonen können deserialisiert werden, wenn die Anwendung erforderlich sind.

Ein Beispiel, das eine eingebettete Ressource zum Speichern von Daten des serialisierten Zeitzone verwendet, finden Sie unter [wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) und [Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
