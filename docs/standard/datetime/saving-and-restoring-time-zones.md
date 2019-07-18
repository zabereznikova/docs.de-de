---
title: Speichern und Wiederherstellen von Zeitzonen
ms.date: 04/10/2017
ms.technology: dotnet-standard
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d783f9e0d098e472dcf67aea394804d6eef2662
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026522"
---
# <a name="saving-and-restoring-time-zones"></a>Speichern und Wiederherstellen von Zeitzonen

Die <xref:System.TimeZoneInfo> Klasse abhängig von der Registrierung zum Abrufen von Daten mit vordefinierten Zeitzone. Die Registrierung ist jedoch eine dynamische Struktur. Darüber hinaus wird die Zeitzone-Informationen, die die Registrierung enthält in erster Linie zum Behandeln von Anpassungen der Uhrzeit und Konvertierungen für das aktuelle Jahr vom Betriebssystem verwendet. Dies hat zwei wichtige Implikationen für Anwendungen, die auf genau Zeitzonendaten basieren:

* Eine Zeitzone, die von einer Anwendung erforderlich sind möglicherweise nicht in der Registrierung definiert, oder möglicherweise wurde Sie umbenannt oder aus der Registrierung entfernt werden.

* Eine Zeitzone, die in der Registrierung definiert ist, können Informationen zu bestimmten Anpassungsregeln fehlen, die für historische zeitzonenkonvertierungen erforderlich sind.

Die <xref:System.TimeZoneInfo> Klasse behebt diese Einschränkungen durch die Unterstützung für die Serialisierung (Speichern) und die Deserialisierung (Wiederherstellung) von Zeitzonendaten.

## <a name="time-zone-serialization-and-deserialization"></a>Zeitzonenserialisierung und Deserialisierung

Speichern und Wiederherstellen von einer Zeitzone durch Serialisierung und Deserialisierung von Zeitzonendaten umfasst nur zwei Methodenaufrufe auf:

* Sie können serialisieren eine <xref:System.TimeZoneInfo> -Objekt durch Aufrufen des Objekts <xref:System.TimeZoneInfo.ToSerializedString%2A> Methode. Die Methode nimmt keine Parameter und gibt eine Zeichenfolge, die Zeitzoneninformationen enthält.

* Sie Deserialisieren können eine <xref:System.TimeZoneInfo> Objekt aus einer serialisierten Zeichenfolge übergeben Sie diese Zeichenfolge in die `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> Methode.

## <a name="serialization-and-deserialization-scenarios"></a>Serialisierungs-und deserialisierungsszenarien

Die Möglichkeit zum Speichern (oder serialisieren) eine <xref:System.TimeZoneInfo> Objekt in eine Zeichenfolge und Wiederherstellen (oder Deserialisieren) für die spätere Verwendung erhöht sowohl die Flexibilität, als auch das Hilfsprogramm die <xref:System.TimeZoneInfo> Klasse. In diesem Abschnitt werden einige Situationen, in denen Serialisierung und Deserialisierung am nützlichsten sind.

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a>Serialisierung und Deserialisierung von Zeitzonendaten in einer Anwendung

Eine serialisierte Zeitzone kann aus einer Zeichenfolge wiederhergestellt werden, wenn er benötigt wird. Eine Anwendung Option diese, wenn die Zeitzone, die aus der Registrierung abgerufene korrekt zu einer Datums- und Uhrzeitangabe innerhalb eines bestimmten Zeitraums konvertieren kann. Zeit der Zonendaten in der Registrierung von Windows XP unterstützt beispielsweise eine Anpassungsregel, zwar in der Regel in der Windows Vista-Registrierung definierten Zeitzonen Informationen zwei Regeln zur zeitzonenanpassung berücksichtigt. Dies bedeutet, dass die historischen zeitkonvertierungen möglicherweise ungenau. Serialisierung und Deserialisierung von Zeitzonendaten können diese Einschränkung behandeln.

Im folgenden Beispiel eine benutzerdefinierte <xref:System.TimeZoneInfo> -Klasse, die ohne Anpassungsregeln wird zur Darstellung der USA definiert. Eastern Standard Time Zone von 1883 zu 1917, vor der Einführung der Sommerzeit in den Vereinigten Staaten. In einer Variablen, die der globale Bereich gilt, wird die benutzerdefinierte Zeitzone serialisiert. Die Zeitzone Konvertierungsmethode, `ConvertUtcTime`, wie oft die Coordinated Universal Time (UTC) konvertiert übergeben wird. Bei Datum und Uhrzeit wird in 1917 oder früher wird die benutzerdefinierte Eastern Standard Time Zone wird wiederhergestellt, aus einer serialisierten Zeichenfolge und ersetzt die Zeitzone, die aus der Registrierung abgerufen.

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a>Behandeln von Ausnahmen mit Zeitzone

Da es sich bei die Registrierung eine dynamische Struktur handelt, unterliegen seinen Inhalt, der versehentlich oder absichtlich geändert. Dies bedeutet, dass eine Zeitzone, die in der Registrierung definiert werden soll, und das ist erforderlich, damit eine Anwendung erfolgreich ausgeführt, möglicherweise fehlt. Ohne Unterstützung für die Zeitzone-Serialisierung und Deserialisierung, haben Sie kaum eine andere Wahl behandelt das resultierende <xref:System.TimeZoneNotFoundException> durch Beenden der Anwendung. Verwenden Sie die Zeitzonenserialisierung und Deserialisierung, Sie können jedoch verarbeiten einen unerwarteten <xref:System.TimeZoneNotFoundException> durch das Wiederherstellen der erforderlichen Zeitzone aus einer serialisierten Zeichenfolge und die Anwendung wird weiterhin ausgeführt.

Das folgende Beispiel erstellt und eine benutzerdefinierte Zeitzone Central Standard serialisiert. Anschließend wird versucht, das die Central Standard Time Zone aus der Registrierung abzurufen. Wenn der Abrufvorgang entweder eine <xref:System.TimeZoneNotFoundException> oder <xref:System.InvalidTimeZoneException>, deserialisiert der Zeitzone der Ausnahmehandler.

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a>Eine serialisierte Zeichenfolge speichern und Wiederherstellen bei Bedarf

In den vorherigen Beispielen Zeitzoneninformationen eine String-Variable gespeichert und bei Bedarf wiederhergestellt. Eingebettete jedoch die Zeichenfolge, die serialisierten Zeit enthält Informationen zur Zone selbst in einige Speichermedium, z. B. eine externe Datei, eine Ressourcendatei gespeichert werden kann, in der Anwendung oder der Registrierung. (Beachten Sie, dass Informationen über benutzerdefinierte Zeitzonen abgesehen von der Zeitzone-Schlüssel in der Registrierung des Systems gespeichert werden sollen.)

Speichern eine Zeichenfolge serialisiert Zeitzone auf diese Weise trennt, wird auch die Routine zum Erstellen von der Zeitzone von der Anwendung selbst. Beispielsweise kann eine Routine zum Erstellen von Zeitzonen ausführen und eine Datei, die historische Zeitzoneninformationen enthält, mit denen eine Anwendung erstellen. Die Datei kann dann mit der Anwendung installiert werden und kann geöffnet werden und eine oder mehrere der Zeitzonen kann deserialisiert werden, wenn die Anwendung benötigt.

Ein Beispiel eine eingebettete Ressource verwendet, um serialisierte Zeitzonendaten zu speichern, finden Sie unter [Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) und [Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
