---
title: Frameworkbibliotheken
description: Frameworkbibliotheken
keywords: .NET, .NET Core
author: richlander
ms.author: ronpet
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 7b77b6c1-8367-4602-bff3-91e4c05ac643
translationtype: Human Translation
ms.sourcegitcommit: 093b852fe1ed2307ebce914381fe47388b435c95
ms.openlocfilehash: c11f89522a97d60f5ffb8588f4500b64b5d2d6db

---

# <a name="framework-libraries"></a>Frameworkbibliotheken

.NET verfügt über einen umfangreichen Standardsatz an Klassenbibliotheken, die entweder als Basisklassenbibliotheken (Kernsatz) oder Frameworkklassenbibliotheken (vollständiger Satz) bezeichnet werden. Diese Bibliotheken bieten Implementierungen für viele allgemeine und App-spezifische Typen, Algorithmen und Hilfsprogrammfunktionen. Sowohl kommerzielle als auch communitybasierte Bibliotheken bauen auf den Frameworkklassenbibliotheken auf und bieten einfache, sofort einsatzbereite Bibliotheken für eine Vielzahl von Computingaufgaben.

Eine Teilmenge dieser Bibliotheken wird mit jeder .NET-Implementierung bereitgestellt. BCL-APIs (Base Class Library, Basisklassenbibliothek) werden in jeder .NET-Implementierung vorausgesetzt, weil sie von Entwicklern gewünscht und von beliebten Bibliotheken für die Ausführung benötigt werden. Über die BCL hinausgehende App-spezifische Bibliotheken – wie z.B. ASP.NET – sind nicht in allen .NET-Implementierungen verfügbar.

## <a name="base-class-libraries"></a>Basisklassenbibliotheken

Basisklassenbibliotheken stellen die meisten grundlegenden Typen und Hilfsprogrammfunktionen bereit und bilden die Grundlage für alle anderen .NET-Klassenbibliotheken. Sie sind darauf ausgerichtet, sehr allgemeine Implementierungen anzubieten, ohne einer bestimmten Arbeitsauslastung den Vorzug zu geben. Leistung ist immer ein wichtiger Gesichtspunkt, da je nach App unterschiedliche Richtlinien ein höheres Gewicht haben – z.B. niedrige Latenz gegenüber hohem Durchsatz oder geringer Arbeitsspeicherverbrauch gegenüber geringer CPU-Auslastung. Diese Bibliotheken sind generell auf hohe Leistung ausgelegt und versuchen, angesichts all der verschiedenen Leistungsanforderungen einen Mittelweg zu finden. Für die meisten Apps funktioniert diese Herangehensweise ziemlich gut.

## <a name="primitive-types"></a>Primitive Typen

.NET umfasst eine Reihe primitiver Typen, die (in unterschiedlichem Maß) in allen Programmen verwendet werden. Diese Typen enthalten Daten, beispielsweise Zahlen, Zeichenfolgen, Bytes und beliebige Objekte. Die Sprache C# enthält Schlüsselwörter für diese Typen. Unten finden Sie einen Beispielsatz dieser Typen, zusammen mit den entsprechenden C#-Schlüsselwörtern.

*   [System.Object](https://msdn.microsoft.com/library/system.object.aspx) ([object](https://msdn.microsoft.com/library/9kkx3h3c.aspx)): Die ultimative Basisklasse im CLR-Typsystem. Sie bildet den Stamm der Typhierarchie.
*   [System.Int16](https://msdn.microsoft.com/library/system.int16.aspx) ([short](https://msdn.microsoft.com/library/ybs77ex4.aspx)): Ein ganzzahliger 16-Bit-Typ mit Vorzeichen. Es gibt auch einen [UInt16](https://msdn.microsoft.com/library/system.uint16.aspx)-Typ ohne Vorzeichen.
*   [System.Int32](https://msdn.microsoft.com/library/system.int32.aspx) ([int](https://msdn.microsoft.com/library/5kzh1b5w.aspx)): Ein ganzzahliger 32-Bit-Typ mit Vorzeichen. Es gibt auch einen [UInt32](https://msdn.microsoft.com/library/x0sksh43.aspx)-Typ ohne Vorzeichen.
*   [System.Single](https://msdn.microsoft.com/library/system.single.aspx) ([float](https://msdn.microsoft.com/library/b1e65aza.aspx)): Ein 32-Bit-Gleitkommatyp.
*   [System.Decimal](https://msdn.microsoft.com/library/system.decimal.aspx) ([decimal](https://msdn.microsoft.com/library/364x0z75.aspx)): Ein 128-Bit-Dezimaltyp.
*   [System.Byte](https://msdn.microsoft.com/library/system.byte.aspx) ([byte](https://msdn.microsoft.com/library/5bdb6693.aspx)): Ein 8-Bit-Ganzzahltyp ohne Vorzeichen, der ein Byte Arbeitsspeicher darstellt.
*   [System.Boolean](https://msdn.microsoft.com/library/system.boolean.aspx) ([bool](https://msdn.microsoft.com/library/c8f5xwh7.aspx)): Ein boolescher Typ, der „true“ oder „false“ darstellt.
*   [System.Char](https://msdn.microsoft.com/library/system.char.aspx) ([char](https://msdn.microsoft.com/library/x9h8tsay.aspx)): Ein numerischer 16-Bit-Typ, der ein Unicode-Zeichen darstellt.
*   [System.String](https://msdn.microsoft.com/library/system.string.aspx) ([string](https://msdn.microsoft.com/library/362314fe.aspx)): Stellt eine Reihe von Zeichen dar. Unterscheidet sich von `char[]`, ermöglicht aber die Indizierung für jedes einzelne `char` in der `string`.

## <a name="data-structures"></a>Datenstrukturen

.NET umfasst eine Reihe von Datenstrukturen, die die Arbeitsgrundlage für nahezu alle .NET-Apps darstellen. Die meisten sind Auflistungen, es gibt jedoch auch andere Typen.

*   [Array](https://msdn.microsoft.com/library/system.array.aspx): Stellt ein Array aus stark typisierten Objekten dar, auf die über einen Index zugegriffen werden kann. Verfügt konstruktionsbedingt über eine festgelegte Größe.
*   [List](https://msdn.microsoft.com/library/6sh2ey19.aspx): Stellt eine stark typisierte Liste von Objekten dar, auf die über einen Index zugegriffen werden kann. Die Größe wird nach Bedarf automatisch angepasst.
*   [Dictionary](https://msdn.microsoft.com/library/xfhwa508.aspx): Stellt eine Auflistung aus Werten dar, die durch einen Schlüssel indiziert werden. Auf die Werte kann über einen Schlüssel zugegriffen werden. Die Größe wird nach Bedarf automatisch angepasst.
*   [Uri](https://msdn.microsoft.com/library/system.uri.aspx): Stellt eine Objektdarstellung eines URIs (Uniform Resource Identifier) sowie einfachen Zugriff auf die Teile des URIs bereit.
*   [DateTime](https://msdn.microsoft.com/library/system.datetime.aspx): Stellt einen Zeitpunkt dar, der üblicherweise als Datum und Uhrzeit dargestellt wird.

## <a name="utility-apis"></a>Hilfsprogramm-APIs

.NET umfasst eine Reihe von Hilfsprogramm-APIs, die Funktionen für viele wichtige Aufgaben bereitstellen.

*   [HttpClient](https://msdn.microsoft.com/library/system.net.http.httpclient.aspx): Eine API zum Senden von HTTP-Anforderungen und Empfangen von HTTP-Antworten aus einer Ressource, die durch einen URI identifiziert wird.
*   [XDocument](https://msdn.microsoft.com/library/system.xml.linq.xdocument.aspx): Eine API zum Laden und Abfragen von XML-Dokumenten mit LINQ.
*   [StreamReader](https://msdn.microsoft.com/library/system.io.streamreader.aspx): Eine API zum Lesen von Dateien ([StreamWriter](https://msdn.microsoft.com/library/system.io.stringwriter.aspx)). Kann zum Schreiben von Dateien verwendet werden.

## <a name="app-model-apis"></a>App-Modell-APIs

Es gibt viele App-Modelle von unterschiedlichen Herstellern, die mit .NET verwendet werden können.

*   [ASP.NET](http://asp.net): Stellt ein Webframework zum Erstellen von Websites und -diensten bereit. Unterstützt unter Windows, Linux und macOS (je nach ASP.NET-Version).



<!--HONumber=Nov16_HO3-->


