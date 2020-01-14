---
title: Serialisieren und Deserialisieren von JSON C# mit-.net
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: c05783963ba521109fb542f247ec9e62fdb5c2d9
ms.sourcegitcommit: dfad244ba549702b649bfef3bb057e33f24a8fb2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2020
ms.locfileid: "75904645"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>JSON-Serialisierung und-Deserialisierung (Marshalling und Unmarshalling) in .net-Overview

Der `System.Text.Json`-Namespace stellt Funktionen zum Serialisieren und Deserialisieren von JavaScript Object Notation (JSON) bereit.

Der Bibliotheks Entwurf hebt eine hohe Leistung und eine geringe Speicher Belegung für eine umfangreiche Featuregruppe hervor. Die integrierte UTF-8-Unterstützung optimiert den Prozess des Lesens und Schreibens von JSON-Text, der als UTF-8 codiert ist. Dies ist die häufigste Codierung für Daten im Web und Dateien auf dem Datenträger.

Die Bibliothek stellt außerdem Klassen zum Arbeiten mit einem Dokument Objektmodell (DOM) im Arbeitsspeicher bereit. Diese Funktion ermöglicht den zufälligen schreibgeschützten Zugriff auf die Elemente in einer JSON-Datei oder Zeichenfolge. 

## <a name="how-to-get-the-library"></a>Vorgehensweise beim erhalten der Bibliothek

* Die Bibliothek ist als Teil des gemeinsamen [.net Core 3,0](https://aka.ms/netcore3download) -Frameworks integriert.
* Installieren Sie das nuget-Paket " [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) " für andere Ziel-Frameworks. Das Paket unterstützt Folgendes:
  * .NET Standard 2,0 und höhere Versionen
  * .NET Framework 4.7.2 und spätere Versionen
  * .Net Core 2,0, 2,1 und 2,2

## <a name="additional-resources"></a>Weitere Ressourcen

* [Verwenden der Bibliothek](system-text-json-how-to.md)
* [Vorgehensweise beim Migrieren von "newtonsoft. JSON"](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Schreiben von Konvertern](system-text-json-converters-how-to.md)
* [System. Text. JSON-Quellcode](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [System. Text. JSON-API-Referenz](xref:System.Text.Json)
* [System. Text. JSON. Serialization-API-Referenz](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
