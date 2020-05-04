---
title: Serialisieren und Deserialisieren von JSON mit C# – .NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 660a2831aa6a807486fc47eae880bcd11347c547
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159545"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>JSON-Serialisierung und -Deserialisierung (Marshalling und Rückgängigmachen von Marshalling) in .NET: Überblick

Der `System.Text.Json`-Namespace bietet Funktionalitäten zum Serialisieren in und Deserialisieren aus JSON (JavaScript Object Notation).

Beim Entwerfen der Bibliothek wurde mehr Wert auf eine hohe Leistung und eine geringe Arbeitsspeicherbelegung gelegt als auf eine große Bandbreite von Features. Die integrierte UTF-8-Unterstützung optimiert den Prozess des Lesens und Schreibens von JSON-Text, der als UTF-8 codiert ist. Dies ist die am häufigsten verwendete Codierung für Daten im Web und Dateien auf Datenträgern.

Die Bibliothek stellt außerdem Klassen für die Arbeit mit einem In-Memory-Dokumentobjektmodell (DOM) bereit. Diese Funktion ermöglicht einen zufälligen schreibgeschützten Zugriff auf die Elemente in einer JSON-Datei oder -Zeichenfolge.

## <a name="how-to-get-the-library"></a>Abrufen der Bibliothek

* Die Bibliothek ist im freigegebenen [.NET Core 3.0](https://aka.ms/netcore3download)-Framework enthalten.
* Installieren Sie für andere Zielframeworks das NuGet-Paket [System.Text.Json](https://www.nuget.org/packages/System.Text.Json). Das Paket unterstützt:
  * .NET Standard 2.0 und höhere Versionen
  * .NET Framework 4.7.2 und höhere Versionen
  * .NET Core 2.0, 2.1 und 2.2

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [Serialisierung und Deserialisierung (Marshalling und Rückgängigmachen von Marshalling) von JSON in .NET](system-text-json-how-to.md)
* [Migration von Newtonsoft.Json in System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Schreiben von benutzerdefinierten Konvertern für JSON-Serialisierung (Marshalling) in .NET](system-text-json-converters-how-to.md)
* [System.Text.Json-Quellcode](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
* [System.Text.Json.Serialization-API-Referenz](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
