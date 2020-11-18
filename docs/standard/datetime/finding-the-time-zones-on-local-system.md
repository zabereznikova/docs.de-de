---
title: Suchen der in einem lokalen System definierten Zeitzonen
ms.date: 04/10/2017
helpviewer_keywords:
- time zones [.NET], local
- time zones [.NET], finding local system time zones
- time zone identifiers [.NET]
- local time zone access
- time zones [.NET], retrieving
- UTC times, finding local system time zones
- time zones [.NET], UTC
ms.assetid: 3f63b1bc-9a4b-4bde-84ea-ab028a80d3e1
ms.openlocfilehash: 02467e10494e72c83ad9521228f6c4151c4a6bd1
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817938"
---
# <a name="finding-the-time-zones-defined-on-a-local-system"></a>Suchen der in einem lokalen System definierten Zeitzonen

Die <xref:System.TimeZoneInfo>-Klasse macht keinen öffentlichen Konstruktor verfügbar. Demzufolge kann das `new`-Schlüsselwort nicht zum Erstellen eines neuen <xref:System.TimeZoneInfo>-Objekts verwendet werden. Stattdessen werden <xref:System.TimeZoneInfo>-Objekte entweder durch Abrufen von Informationen über vordefinierte Zeitzonen aus der Registrierung oder durch Erstellen einer benutzerdefinierten Zeitzone instanziiert. Dieses Thema behandelt die Instanziierung einer Zeitzone von den in der Registrierung gespeicherten Daten. Darüber hinaus ermöglichen die `static`-Eigenschaften (`shared` in Visual Basic) der <xref:System.TimeZoneInfo>-Klasse Zugriff auf die koordinierte Weltzeit (Universal Coordinated Time, UTC) und die lokale Zeitzone.

> [!NOTE]
> Für Zeitzonen, die nicht in der Registrierung definiert sind, können Sie benutzerdefinierte Zeitzonen durch Aufrufen der Überladungen der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>-Methode erstellen. Zum Erstellen einer benutzerdefinierten Zeitzone finden Sie unter Gewusst [wie: Erstellen von Zeitzonen ohne Anpassungsregeln](create-time-zones-without-adjustment-rules.md) und Gewusst [wie: Erstellen von Zeitzonen mit Anpassungsregeln](create-time-zones-with-adjustment-rules.md) . Darüber hinaus können Sie ein <xref:System.TimeZoneInfo>-Objekt durch Wiederherstellen aus einer serialisierten Zeichenfolge mit der <xref:System.TimeZoneInfo.FromSerializedString%2A>-Methode instanziieren. Die Serialisierung und Deserialisierung eines- <xref:System.TimeZoneInfo> Objekts wird in den Themen Gewusst [wie: Speichern von Zeitzonen in einer eingebetteten Ressource](save-time-zones-to-an-embedded-resource.md) und Gewusst [wie: Wiederherstellen von Zeitzonen aus eingebetteten Ressourcen](restore-time-zones-from-an-embedded-resource.md) erläutert.

## <a name="accessing-individual-time-zones"></a>Zugreifen auf einzelne Zeitzonen

Die <xref:System.TimeZoneInfo>-Klasse bietet zwei vordefinierte Zeitzonenobjekte, die die koordinierte Weltzeit und die lokale Zeitzone darstellen. Diese werden jeweils über die <xref:System.TimeZoneInfo.Utc%2A>- und die <xref:System.TimeZoneInfo.Local%2A>-Eigenschaft zur Verfügung gestellt. Anweisungen zum Zugreifen auf die UTC-Zeit oder die lokalen Zeitzonen finden Sie unter Gewusst [wie: Zugreifen auf die vordefinierte UTC und lokale Zeit Zonen Objekte](access-utc-and-local.md).

Sie können auch ein <xref:System.TimeZoneInfo>-Objekt instanziieren, das die in der Registrierung definierten Zeitzonen darstellt. Anweisungen zum Instanziieren eines bestimmten Zeit Zonen Objekts finden Sie unter Gewusst [wie: Instanziieren eines TimeZoneInfo-Objekts](instantiate-time-zone-info.md).

## <a name="time-zone-identifiers"></a>Zeit Zonen Bezeichner

Der Zeitzonenbezeichner ist ein Schlüsselfeld, das die Zeitzone eindeutig identifiziert. Während die meisten Schlüssel relativ kurz sind, ist der Zeitzonenbezeichner vergleichsweise lang. In den meisten Fällen entspricht der dazugehörige Wert der <xref:System.TimeZoneInfo.StandardName%2A?displayProperty=nameWithType>-Eigenschaft, die zum Bereitstellen des Namens der Standardzeit für die Zeitzone verwendet wird. Es gibt jedoch auch Ausnahmen. Die beste Möglichkeit, um sicherzustellen, dass Sie einen gültigen Bezeichner angeben, besteht darin, die auf Ihrem System verfügbaren Zeitzonen aufzulisten und die dazugehörigen IDs zur Kenntnis zu nehmen.

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
- [Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeit Zonen Objekte](access-utc-and-local.md)
- [Vorgehensweise: Instanziieren eines TimeZoneInfo-Objekts](instantiate-time-zone-info.md)
- [Umrechnen von Uhrzeiten zwischen Zeitzonen](converting-between-time-zones.md)
