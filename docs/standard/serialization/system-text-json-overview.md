---
title: Serialisieren und Deserialisieren von JSON mit C# – .NET
description: In dieser Übersicht wird die Funktionalität des System.Text.Json-Namespace zum Serialisieren in JSON und Deserialisieren aus JSON in .NET beschrieben.
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: cb5c15c2a5c336e2d5b4a3754fa7a02a370602f3
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009884"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>JSON-Serialisierung und -Deserialisierung (Marshalling und Rückgängigmachen von Marshalling) in .NET: Überblick

Der `System.Text.Json`-Namespace bietet Funktionalitäten zum Serialisieren in und Deserialisieren aus JSON (JavaScript Object Notation).

Beim Entwerfen der Bibliothek wurde mehr Wert auf eine hohe Leistung und eine geringe Arbeitsspeicherbelegung gelegt als auf eine große Bandbreite von Features. Die integrierte UTF-8-Unterstützung optimiert den Prozess des Lesens und Schreibens von JSON-Text, der als UTF-8 codiert ist. Dies ist die am häufigsten verwendete Codierung für Daten im Web und Dateien auf Datenträgern.

Die Bibliothek stellt außerdem Klassen für die Arbeit mit einem In-Memory-Dokumentobjektmodell (DOM) bereit. Diese Funktion ermöglicht einen zufälligen schreibgeschützten Zugriff auf die Elemente in einer JSON-Datei oder -Zeichenfolge.

## <a name="how-to-get-the-library"></a>Abrufen der Bibliothek

* Die Bibliothek ist als Teil des gemeinsamen Frameworks für .NET Core 3.0 und höhere Versionen integriert.
* Installieren Sie für frühere Framework-Versionen das NuGet-Paket [System.Text.Json](https://www.nuget.org/packages/System.Text.Json). Das Paket unterstützt:

  * .NET Standard 2.0 und höhere Versionen
  * .NET Framework 4.7.2 und höhere Versionen
  * .NET Core 2.0, 2.1 und 2.2

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [Serialisierung und Deserialisierung (Marshalling und Rückgängigmachen von Marshalling) von JSON in .NET](system-text-json-how-to.md)
* [Instanziieren von JsonSerializerOptions-Instanzen](system-text-json-configure-options.md)
* [Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung](system-text-json-character-casing.md)
* [Anpassen von Eigenschaftsnamen und -werten](system-text-json-customize-properties.md)
* [Ignorieren von Eigenschaften](system-text-json-ignore-properties.md)
* [Zulassen von ungültigem JSON-Code](system-text-json-invalid-json.md)
* [Verarbeiten von Überlauf-JSON](system-text-json-handle-overflow.md)
* [Beibehalten von Verweisen](system-text-json-preserve-references.md)
* [Unveränderliche Typen und nicht öffentliche Zugriffsmethoden](system-text-json-immutability.md)
* [Polymorphe Serialisierung](system-text-json-polymorphism.md)
* [Migrieren von Newtonsoft.Json zu System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Anpassen der Zeichencodierung](system-text-json-character-encoding.md)
* [Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer](write-custom-serializer-deserializer.md)
* [Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung](system-text-json-converters-how-to.md)
* [Unterstützung von DateTime und DateTimeOffset](../datetime/system-text-json-support.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
* [System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)
