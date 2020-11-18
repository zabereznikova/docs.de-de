---
title: Speichern und Wiederherstellen von Zeitzonen
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- restoring time zones
- deserialization [.NET], time zones
- serialization [.NET], time zones
- time zone objects [.NET], restoring
- saving time zones
- time zone objects [.NET], deserializing
- time zones [.NET], saving
- time zones [.NET], restoring
- time zone objects [.NET], serializing
- time zone objects [.NET], saving
ms.assetid: 4028b310-e7ce-49d4-a646-1e83bfaf6f9d
ms.openlocfilehash: 0658bad6da078b6e44695a92b6cb2b22576f6424
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817574"
---
# <a name="saving-and-restoring-time-zones"></a>Speichern und Wiederherstellen von Zeitzonen

Die- <xref:System.TimeZoneInfo> Klasse basiert auf der Registrierung, um vordefinierte Zeit Zonendaten abzurufen. Die Registrierung ist jedoch eine dynamische Struktur. Außerdem werden die Zeitzoneninformationen, die in der Registrierung enthalten sind, vom Betriebssystem in erster Linie verwendet, um Zeit Anpassungen und Konvertierungen für das aktuelle Jahr zu verarbeiten. Dies hat zwei wesentliche Auswirkungen auf Anwendungen, die auf genaue Zeit Zonendaten basieren:

- Eine Zeitzone, die für eine Anwendung erforderlich ist, ist möglicherweise nicht in der Registrierung definiert, oder Sie wurde möglicherweise umbenannt oder aus der Registrierung entfernt.

- In einer Zeitzone, die in der Registrierung definiert ist, fehlen möglicherweise Informationen zu den speziellen Anpassungsregeln, die für historische Zeit Zonen Konvertierungen erforderlich sind.

Die- <xref:System.TimeZoneInfo> Klasse behandelt diese Einschränkungen durch die Unterstützung für die Serialisierung (Speicherung) und die Deserialisierung (Wiederherstellung) von Zeit Zonendaten.

## <a name="time-zone-serialization-and-deserialization"></a>Zeit Zonen-Serialisierung und-Deserialisierung

Das Speichern und Wiederherstellen einer Zeitzone durch serialisieren und Deserialisieren von Zeit Zonendaten umfasst nur zwei Methodenaufrufe:

- Sie können ein <xref:System.TimeZoneInfo> -Objekt serialisieren, indem Sie die-Methode des-Objekts aufrufen <xref:System.TimeZoneInfo.ToSerializedString%2A> . Die-Methode nimmt keine Parameter an und gibt eine Zeichenfolge zurück, die Zeitzoneninformationen enthält.

- Sie können ein- <xref:System.TimeZoneInfo> Objekt aus einer serialisierten Zeichenfolge deserialisieren, indem Sie diese Zeichenfolge an die- `static` `Shared` Methode (in Visual Basic) übergeben <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> .

## <a name="serialization-and-deserialization-scenarios"></a>Serialisierungs-und deserialisierungsszenarien

Durch die Möglichkeit, ein-Objekt in einer Zeichenfolge zu speichern (oder zu serialisieren) <xref:System.TimeZoneInfo> und es zur späteren Verwendung wiederherzustellen (bzw. zu deserialisieren), werden sowohl das-Hilfsprogramm als auch die Flexibilität der- <xref:System.TimeZoneInfo> Klasse erhöht. In diesem Abschnitt werden einige Situationen erläutert, in denen die Serialisierung und Deserialisierung am nützlichsten sind.

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a>Serialisieren und Deserialisieren von Zeit Zonendaten in einer Anwendung

Eine serialisierte Zeitzone kann aus einer Zeichenfolge wieder hergestellt werden, wenn Sie benötigt wird. Eine Anwendung kann dies tun, wenn die aus der Registrierung abgerufene Zeitzone nicht in der Lage ist, ein Datum und eine Uhrzeit in einem bestimmten Datumsbereich ordnungsgemäß zu konvertieren. Zeit Zonendaten in der Registrierung von Windows XP unterstützen z. b. eine einzelne Anpassungs Regel, während Zeitzonen, die in der Windows Vista-Registrierung definiert sind, in der Regel Informationen zu zwei Anpassungsregeln bereitstellen. Dies bedeutet, dass Verlaufs Zeit Konvertierungen ungenau sein können. Diese Einschränkung kann durch Serialisierung und Deserialisierung von Zeit Zonendaten bewältigt werden.

Im folgenden Beispiel wird eine benutzerdefinierte <xref:System.TimeZoneInfo> Klasse ohne Anpassungsregeln definiert, um die US-Zeitzone von 1883 bis 1917 vor der Einführung der Sommerzeit im USA darzustellen. Die benutzerdefinierte Zeitzone wird in einer Variablen serialisiert, die über einen globalen Gültigkeitsbereich verfügt. Die Zeit Zonen Konvertierungsmethode, `ConvertUtcTime` , wird für die Konvertierung koordinierte Weltzeit (UTC) überschritten. Wenn das Datum und die Uhrzeit in 1917 oder früher auftreten, wird die benutzerdefinierte Eastern Standard-Zeitzone aus einer serialisierten Zeichenfolge wieder hergestellt und ersetzt die Zeitzone, die aus der Registrierung abgerufen wurde.

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a>Behandeln von Zeit Zonen Ausnahmen

Da es sich bei der Registrierung um eine dynamische Struktur handelt, können deren Inhalte versehentlich oder absichtlich geändert werden. Dies bedeutet, dass eine Zeitzone, die in der Registrierung definiert werden soll und die für eine erfolgreiche Ausführung einer Anwendung erforderlich ist, möglicherweise nicht vorhanden ist. Ohne Unterstützung der Zeit Zonen-Serialisierung und-Deserialisierung haben Sie nur wenige Möglichkeiten, das zu verarbeiten, <xref:System.TimeZoneNotFoundException> indem Sie die Anwendung beenden. Mithilfe der Zeit Zonen-Serialisierung und-Deserialisierung können Sie jedoch einen unerwarteten verarbeiten, <xref:System.TimeZoneNotFoundException> indem Sie die erforderliche Zeitzone aus einer serialisierten Zeichenfolge wiederherstellen, und die Anwendung wird weiterhin ausgeführt.

Im folgenden Beispiel wird eine benutzerdefinierte zentrale Standard Zeitzone erstellt und serialisiert. Anschließend wird versucht, die zentrale Standard Zeitzone aus der Registrierung abzurufen. Wenn der Abruf Vorgang entweder eine <xref:System.TimeZoneNotFoundException> oder eine auslöst <xref:System.InvalidTimeZoneException> , deserialisiert der Ausnahmehandler die Zeitzone.

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a>Speichern einer serialisierten Zeichenfolge und deren Wiederherstellung bei Bedarf

In den vorherigen Beispielen wurden Zeitzoneninformationen in einer Zeichen folgen Variablen gespeichert und bei Bedarf wieder hergestellt. Allerdings kann die Zeichenfolge, die serialisierte Zeitzoneninformationen enthält, selbst in einem Speichermedium gespeichert werden, z. b. in einer externen Datei, einer in die Anwendung eingebetteten Ressourcen Datei oder in der Registrierung. (Beachten Sie, dass Informationen über benutzerdefinierte Zeitzonen getrennt von den Zeit Zonen Schlüsseln des Systems in der Registrierung gespeichert werden sollten.)

Durch das Speichern einer serialisierten Zeit Zonen Zeichenfolge auf diese Weise wird auch die Zeit Zonen Erstellungs Routine von der Anwendung selbst getrennt. Beispielsweise kann eine Zeit Zonen Erstellungs Routine ausgeführt werden und eine Datendatei erstellen, die historische Zeitzoneninformationen enthält, die von einer Anwendung verwendet werden können. Die Datendatei kann dann mit der Anwendung installiert werden, und Sie kann geöffnet werden, und eine oder mehrere der zugehörigen Zeitzonen können deserialisiert werden, wenn Sie von der Anwendung benötigt werden.

Ein Beispiel, in dem eine eingebettete Ressource zum Speichern von serialisierten Zeit Zonendaten verwendet wird, finden Sie unter Gewusst [wie: Speichern von Zeitzonen in einer eingebetteten Ressource](save-time-zones-to-an-embedded-resource.md) und Gewusst [wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](restore-time-zones-from-an-embedded-resource.md).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
