---
title: Serialisieren und Deserialisieren von JSON C# mit-.net
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: b43c3f6fd8ca56aaa99fffd40317920ee7600a2c
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802712"
---
# <a name="json-serialization-in-net---overview"></a>JSON-Serialisierung in .net-Übersicht

Der `System.Text.Json`-Namespace stellt Funktionen zum Serialisieren und Deserialisieren von JavaScript Object Notation (JSON) bereit.

Der Bibliotheks Entwurf hebt eine hohe Leistung und eine geringe Speicher Belegung für eine umfangreiche Featuregruppe hervor. Die integrierte UTF-8-Unterstützung optimiert den Prozess des Lesens und Schreibens von JSON-Text, der als UTF-8 codiert ist. Dies ist die häufigste Codierung für Daten im Web und Dateien auf dem Datenträger.

Die Bibliothek stellt außerdem Klassen zum Arbeiten mit einem Dokument Objektmodell (DOM) im Arbeitsspeicher bereit. Diese Funktion ermöglicht den zufälligen schreibgeschützten Zugriff auf die Elemente in einer JSON-Datei oder Zeichenfolge. 

## <a name="how-to-get-the-library"></a>Vorgehensweise beim erhalten der Bibliothek

* Die Bibliothek ist als Teil des gemeinsamen [.net Core 3,0](https://aka.ms/netcore3download) -Frameworks integriert.
* Installieren Sie das nuget-Paket " [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) " für andere Ziel-Frameworks. Das Paket unterstützt Folgendes:
  * .NET Standard 2,0 und höhere Versionen
  * .NET Framework 4.6.1 und spätere Versionen
  * .Net Core 2,0, 2,1 und 2,2

## <a name="additional-resources"></a>Weitere Ressourcen

* [Verwenden der Bibliothek](system-text-json-how-to.md)
* [Quellcode](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Text.Json)
* [API-Referenz](xref:System.Text.Json)
* [Roadmap](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Text.Json/roadmap/README.md)
* GitHub-Probleme im dotnet/corefx-Repository
  * [Erörterung der Entwicklung von "System. Text. JSON"](https://github.com/dotnet/corefx/issues/33115) <!-- TODO: Issues are still not moved to the new repo-->
  * [Alle System. Text. JSON-Probleme](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [System. Text. JSON-Probleme mit der Bezeichnung JSON-funktionsdoc](https://github.com/dotnet/runtime/labels/json-functionality-doc)
