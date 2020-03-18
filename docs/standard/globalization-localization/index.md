---
title: Globalisieren und Lokalisieren von .NET-Anwendungen
ms.date: 06/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- international applications [.NET]
- globalization [.NET], encoding
- global applications
- internationalization
- world-ready applications
- application development [.NET], globalization
- multilingual application development
ms.assetid: 9a59696b-d89b-45bd-946d-c75da4732d02
ms.openlocfilehash: eae1c38c2383d13bfb4dab83f2fe9551970b39f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73120883"
---
# <a name="globalizing-and-localizing-net-applications"></a>Globalisieren und Lokalisieren von .NET-Anwendungen

Die Entwicklung einer weltweit einsetzbaren Anwendung, einschließlich einer Anwendung, die in eine oder mehrere Sprachen lokalisiert werden kann, umfasst drei Schritte: Globalisierung, Prüfung der Lokalisierbarkeit und Lokalisierung.

[Globalisierung](globalization.md)

Dieser Schritt umfasst den Entwurf und die Codierung einer Anwendung, die kultur- und sprachneutral ist und die lokalisierten Benutzeroberflächen und regionalen Daten für alle Benutzer unterstützt. Er umfasst das Treffen von Entwurfs- und Programmierungsentscheidungen, die nicht auf kulturspezifischen Annahmen basieren. Während eine globalisierte Anwendung nicht lokalisiert wird, wird sie dennoch so entworfen und geschrieben, dass sie anschließend relativ einfach in eine oder mehrere Sprachen lokalisiert werden kann.

[Überprüfung der Lokalisierbarkeit](localizability-review.md)

Dieser Schritt umfasst den Review des Codes und des Entwurfs einer Anwendung, um sicherzustellen, dass sie problemlos lokalisiert werden kann, und um mögliche Hindernisse für die Lokalisierung zu ermitteln. Es wird außerdem überprüft, ob der ausführbare Code der Anwendung von den Ressourcen getrennt ist. Wenn die Globalisierungsphase effektiv war, bestätigt die Prüfung der Lokalisierbarkeit die Entwurfs- und Codierungsauswahlen, die während der Globalisierung getroffen wurden. Die Lokalisierbarkeitsphase identifiziert möglicherweise auch alle verbleibenden Probleme, damit der Quellcode einer Anwendung nicht während der Lokalisierungsphase geändert werden muss.

[Lokalisierung](localization.md)

Dieser Schritt umfasst die Anpassung einer Anwendung an bestimmte Kulturen und Regionen. Wenn die Globalisierungs- und Lokalisierbarkeitsschritte richtig durchgeführt wurden, sollte die Lokalisierung hauptsächlich die Übersetzung der Benutzeroberfläche umfassen.

Die Befolgung dieser drei Schritte bietet zwei Vorteile:

- Es ist keine Nachrüstung einer Anwendung mehr erforderlich, die nur eine Kultur, z. B. US-Englisch unterstützt, um zusätzliche Kulturen zu unterstützen.

- Dadurch ergeben sich lokalisierte Anwendungen, die stabiler sind und weniger Fehler haben.

.NET bietet umfangreiche Unterstützung für die Entwicklung weltweit einsetzbarer und lokalisierter Anwendungen. Zahlreiche Typmember in der .NET-Klassenbibliothek vereinfachen die Globalisierung, indem sie Werte zurückgeben, die die Konventionen der Kultur des aktuellen Benutzers oder einer angegebenen Kultur widerspiegeln. Außerdem unterstützt .NET Satellitenassemblys, die den Lokalisierungsprozess einer Anwendung erleichtern.

Weitere Informationen finden Sie in der [Dokumentation zur Globalisierung](/globalization/).

## <a name="in-this-section"></a>In diesem Abschnitt

[Globalisierung](globalization.md)

Erläutert die erste Phase der Erstellung einer weltweit einsetzbaren Anwendung, die das Entfernen und Codieren einer Anwendung involviert, die kultur- und sprachneutral ist.

[Überprüfung der Lokalisierbarkeit](localizability-review.md)

Erläutert die zweite Phase der Erstellung einer lokalisierten Anwendung, die das Identifizieren möglicher Hindernisse bei der Lokalisierung beinhaltet.

[Lokalisierung](localization.md)

Erläutert die finale Phase der Erstellung einer lokalisierten Anwendung, die das Anpassen der Benutzeroberfläche einer Anwendung für bestimmte Bereiche oder Länder beinhaltet.

[Kulturunabhängige Zeichenfolgenoperationen](culture-insensitive-string-operations.md)

Beschreibt die Verwendung von standardmäßig kulturabhängigen .NET-Methoden und -Klassen zum Abrufen kulturunabhängiger Ergebnisse.

[Empfehlungen für die Entwicklung weltweit einsatzfähiger Anwendungen](best-practices-for-developing-world-ready-apps.md)

Beschreibt empfohlene Vorgehensweisen zur Durchführung der Globalisierung, Lokalisierung und Entwicklung weltweit einsatzfähiger ASP.NET-Anwendungen.

## <a name="reference"></a>Verweis

- <xref:System.Globalization?displayProperty=nameWithType>-Namespace

   Enthält Klassen, mit denen kulturbezogene Informationen definiert werden. Dazu zählen Sprache, Land/Region, verwendete Kalender, Formatierungsmuster für Datumsangaben, Währungen und Zahlen sowie die Sortierreihenfolge für Zeichenfolgen.

- <xref:System.Resources>-Namespace

   Stellt Klassen zum Erstellen, Bearbeiten und Verwenden von Ressourcen bereit.

- <xref:System.Text>-Namespace

   Enthält Klassen, die die ASCII-, ANSI-, Unicode- und andere Zeichencodierungen darstellen.

- [Resgen.exe (Resource File Generator)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)

   Beschreibt die Verwendung von Resgen.exe zur Konvertierung von TXT-Dateien und RESX-Dateien (XML-basiertes Ressourcenformat) in binäre RESOURCES-Dateien der Common Language Runtime.

- [Winres.exe (Windows Forms Resource Editor-Tool)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)

   Beschreibt die Verwendung von Winres.exe zur Lokalisierung von Windows Forms-Formularen.
