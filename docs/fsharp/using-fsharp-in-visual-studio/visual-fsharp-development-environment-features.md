---
title: Funktionen der F#-Entwicklungsumgebung
description: "Erfahren Sie, welche Funktionen von Visual Studio 2012 in f# unterstützt werden."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 809e9a34-b271-4c87-8356-2426b44f4721
ms.openlocfilehash: 05727bf11eccfd64f823dd280b1a19210815ca5a
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2017
---
# <a name="visual-f-development-environment-features"></a>Funktionen der Visual F#-Entwicklungsumgebung

> [!NOTE]
Dieser Artikel ist nicht auf dem neuesten Stand mit den neuesten Visual Studio.  Es werden aktualisiert.

Dieses Thema enthält Informationen darüber, welche Funktionen von Visual Studio 2012 in f# unterstützt werden.

## <a name="project-features"></a>Projektfunktionen
In der folgenden Tabelle zusammengefasst, die Vorlagen, die in F#-Projekten zur Verfügung stehen. Weitere Informationen zu Projekt- und Elementvorlagen, finden Sie unter [NIB Erstellen von Projekten aus Vorlagen](https://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2).

|Typ "Template"|Beschreibung|Unterstützte Vorlagen|
|-------------|-----------|-------------------|
|Projektvorlagen|Typen von Projekten zur Verfügung, in der **neues Projekt** (Dialogfeld).|<ul><li>F#-Anwendung<br /></li><li>F#-Bibliothek<br /></li><li>F#-Lernprogramm<br /></li><li>Portable f#-Bibliothek<br /></li><ul/>|
|Elementvorlagen|Dateitypen, die zur Verfügung, in der **neues Element hinzufügen** (Dialogfeld).|<ul><li>F#-Quelldatei (sein)<br /></li><li>F#-Skript (".fsx")<br /></li><li>F#-Signaturdatei (".FSI")<br /></li><li>Die Konfigurationsdatei (config)<br /></li><li>Verbindung zur SQL-Datenbank (LINQ to SQL-Typ-Anbieter)<br /></li><li>Verbindung zur SQL-Datenbank (LINQ to Entities-Typanbieter)<br /></li><li>OData-Dienst-Verbindung (LINQ-Typanbieter)<br /></li><li>WSDL-Dienst-Verbindung (Typanbieter)<br /></li><li>XML-Datei (XML)<br /></li><li>Textdatei<br /></li><ul/>|
Wählen Sie zum Erstellen einer Anwendung, die eine eigenständige ausführbare Datei ausgeführt werden können, die F#-Projekt Anwendungstyp aus. So erstellen Sie eine Bibliothek (d. h. eine verwaltete Assembly oder. DLL-Datei) für die Verwendung in der Windows-desktop-Plattform, wählen Sie in f#-Bibliothek. Wählen Sie die Portable f#-Bibliothek, zum Erstellen einer portablen Bibliothek, die auf einer beliebigen unterstützten Plattform verwendet werden kann. F#-Portable Library-Projekte verweisen, eine Version von FSharp.Core.dll, der F#-Bibliothek zu erstellen, die mit Clientanwendungen verwendet werden können, die ausgeführt werden auf Plattformen wie Windows Store-apps, die .NET Framework 4.5, Xamarin.iOS und Xamarin.Android geeignet ist.

Weitere Informationen zu den Vorlagen für den Datenzugriff, finden Sie unter [Typanbieter](../tutorials/type-providers/index.md).

In der folgenden Tabelle werden die Projekteigenschaften Funktionen unterstützt und nicht in f# unterstützt zusammengefasst. Weitere Informationen finden Sie unter [Konfigurieren von Projekten](configuring-projects.md) und [Einführung in den Projekt-Designer](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7).

|Projekteinstellung|In f# unterstützt?|Notizen|
|---------------|----------------|-----|
|Ressourcendateien|Ja||
|Erstellen, Debuggen und Einstellungen für attributverweise|Ja||
|Festlegung von Zielversionen|Ja||
|Symbol und manifest|Nein|Über Compilerbefehlszeilenoptionen verfügbar.|
|ASP.NET Client-Dienste|Nein||
|ClickOnce|Nein|Verwenden Sie ein Clientprojekt in einer anderen .NET Framework-Sprache, falls zutreffend.|
|Starke Namen|Nein|Über Compilerbefehlszeilenoptionen verfügbar.|
|Assembly, die publishing und versionsverwaltung|Nein||
|Codeanalyse|Nein|Codeanalysetools können manuell oder als Teil eines Befehls nach dem Build ausgeführt werden.|
|Sicherheit (Ändern von Vertrauensebenen)|Nein||

## <a name="code-and-text-editor-features"></a>Code und Text-Editor-Funktionen
Die folgenden Funktionen von Visual Studiocode und Text-Editoren werden in f# unterstützt. Allgemeine Informationen zum Bearbeiten von Code in Visual Studio und der Text-Editor-Funktionen finden Sie unter [Schreiben von Code im Code- und Text-Editor](/visualstudio/ide/writing-code-in-the-code-and-text-editor).

|Funktion|Beschreibung|In f# unterstützt?|
|-------|-----------|----------------|
|Kommentieren Sie automatisch|Ermöglicht es Ihnen, den Kommentar zu kennzeichnen oder auszukommentieren Codeabschnitte.|Ja|
|Automatisch formatieren|Formatiert den Code mit Standardeinzug und Stil.|Nein|
|Lesezeichen|Ermöglicht Ihnen, stellen im Editor zu speichern.|Ja|
|Einzug ändern|Rückt hinzu oder entfernt Einzüge ausgewählte Zeilen.|Ja|
|[Suchen und Ersetzen von Text](/visualstudio/ide/finding-and-replacing-text)|Ermöglicht Ihnen das Suchen in einer Datei, einem Projekt oder einer Projektmappe und Text zu ändern.|Ja|
|Gehe zu Definition für .NET Framework-API|Wenn der Cursor in eine .NET Framework-API positioniert ist, zeigt Code aus .NET Framework-Metadaten generiert.|Nein|
|Gehe zu Definition für eine benutzerdefinierte API|Wann ist der Cursor auf eine Anwendung-Entität, die Sie Bewegen des Cursors an der Stelle im Code definiert, in dem die Entität definiert ist, ein.|Ja|
|Gehe zu Zeile|Ermöglicht es Ihnen, um zu einer bestimmten Zeile in einer Datei, durch die Nummer der Zeile zu wechseln.|Ja|
|Navigationsleisten am Anfang der Datei|Ermöglicht das Springen zu Positionen im Code durch, z. B. Funktionsnamen.|Ja|
|Gliederung Finden Sie unter [Gliederung](/visualstudio/ide/outlining).|Ermöglicht es Ihnen, Abschnitte des Codes erstellen Sie eine kompaktere Ansicht reduzieren.|Ja|
|Mit Tabstopps versehen|Leerzeichen konvertiert in Tabstopps.|Ja|
|Farbliche Kennzeichnung von Typen|Zeigt definierte Typnamen in einer speziellen Farbe.|Ja|
|Schnellsuche. Schnellsuche: Suchen und Ersetzen im Fenster angezeigt wird|Ermöglicht es Ihnen, in eine Datei oder ein Projekt gesucht werden soll.|Ja|

## <a name="intellisense-features"></a>IntelliSense-Funktionen
In der folgenden Tabelle werden die IntelliSense-Funktionen unterstützt und nicht in f# unterstützt zusammengefasst. Allgemeine Informationen zu IntelliSense finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense).

|Funktion|Beschreibung|In f# unterstützt?|
|-------|-----------|----------------|
|Automatisches Implementieren von Schnittstellen|Generiert Codestubs für Schnittstellenmethoden.|Nein|
|Codeausschnitte|Wird Code aus einer Bibliothek mit üblichen Konstrukte der Codierung in Themen eingefügt.|Nein|
|Wort vervollständigen|Speichert die Eingabe von Wörtern und Namen abschließen, während der Eingabe.|Ja|
|Zuerst nutzen-Beendigungsmodus|Wenn aktiviert, führt dazu, dass die erste Übereinstimmung auswählen, während der Eingabe nicht gewartet, bis Sie wählen Sie ein, oder drücken die wortvervollständigung **STRG + LEERTASTE**.|Nein|
|Generieren von code|Können Sie Stubcode für eine Vielzahl von Konstrukten zu generieren.|Nein|
|Member auflisten|Wenn Sie den Memberzugriffsoperator (.) eingeben, zeigt Member für einen Typ aus.|Ja|
|Organisieren von using-Direktiven/öffnen|Organisiert Namespaces verweist **mit** Anweisungen in c# oder **öffnen** Direktiven in F# erläutert werden.|Nein|
|Parameterinfo|Zeigt nützliche Informationen zu Parametern, während der Eingabe von eines Funktionsaufrufs.|Ja|
|QuickInfo|Zeigt die vollständige Deklaration für jeden Bezeichner im Code.|Ja|
Die Umgestaltung von f#-Code wird in Visual Studio 2012 nicht unterstützt.

## <a name="debugging-features"></a>Debugfunktionen
In der folgenden Tabelle sind die Funktionen, die verfügbar, beim Debuggen von F#-Code sind zusammengefasst. Allgemeine Informationen zu Visual Studio-Debugger, finden Sie unter [Debuggen in Visual Studio](https://msdn.microsoft.com/library/sc65sadd.aspx).

|Funktion|Beschreibung|In f# unterstützt?|
|-------|-----------|----------------|
|Fenster |Enthält die automatische oder temporäre Variablen.|Nein|
|Haltepunkte|Ermöglicht das Anhalten der Ausführung von Code zu bestimmten Zeitpunkten während des Debuggens.|Ja|
|Bedingte Haltepunkte|Aktiviert Breakpoints, die eine Bedingung zu testen, die bestimmt, ob die Ausführung anhalten soll.|Ja|
|Bearbeiten und Fortfahren|Ermöglicht es Code geändert und kompiliert werden, wie Sie ein aktives Programm debuggen, ohne zu beenden, und der Debugger neu gestartet werden.|Nein|
|Ausdrucksauswertung|Wertet aus, und Code zur Laufzeit führt.|Nein, aber der C#-Ausdrucksauswerter kann verwendet werden, obwohl Sie C#-Syntax verwenden müssen.|
|Verlaufsbezogenes debugging|Ermöglicht es Ihnen, die zuvor ausgeführten Code schrittweise.|Ja|
|Lokalfenster|Zeigt lokal definierte Werte und Variablen.|Ja|
|Ausführen bis Cursor|Ermöglicht es Ihnen, Code auszuführen, bis die Zeile, die den Cursor enthält erreicht ist.|Ja|
|Einzelschritt|Ermöglicht das Fortsetzen der Ausführung und verschieben Sie in einem beliebigen Funktionsaufruf.|Ja|
|Prozedurschritt|Ermöglicht das Fortsetzen der Ausführung im aktuellen Stapelrahmen und abwarten, bis alle Funktionsaufrufe.|Ja|

## <a name="additional-tools"></a>Zusätzliche Tools
In der folgenden Tabelle werden die Unterstützung für f# in Visual Studio-Tools zusammengefasst.

|Tool|Beschreibung|In f# unterstützt?|
|----|-----------|----------------|
|Aufrufhierarchie|Zeigt Aufrufe die geschachtelte Struktur der Funktion im Code.|Nein|
|Codemetrik|Sammelt Informationen zu Ihrem Code, z. B. Zeilenanzahl an.|Nein|
|Klassenansicht|Stellt eine basierende Ansicht des Codes in einem Projekt.|Nein|
|[Fenster „Fehlerliste“](/visualstudio/ide/reference/error-list-window)|Zeigt eine Liste von Fehlern im Code.|Ja|
|[F# Interactive](../tutorials/fsharp-interactive/index.md)|Ermöglicht es, Ihnen (oder kopieren und Einfügen) F#-code und führen Sie es sofort, unabhängig von der Erstellung des Projekts. F# Interactive-Fenster wird eine Read, Evaluate, Print Loop (REPL).|Ja|
|Objektkatalog|Ermöglicht es Ihnen so zeigen Sie die Typen in einer Assembly an.|F#-Typen erscheinen in kompilierten Assemblys erscheinen nicht genau so, wie Sie sie erstellen. Durchsuchen Sie die kompilierte Darstellung eines f#-Typen, aber Sie können nicht die Typen anzeigen, wie sie von f# angezeigt werden.|
|[Ausgabefenster](/visualstudio/ide/reference/output-window)|Zeigt die Buildausgabe an.|Ja|
|Leistungsanalyse|Stellt Tools zum Messen der Leistung des Codes bereit.|Ja|
|Eigenschaftenfenster|Zeigt an, und ermöglicht die Bearbeitung der Eigenschaften des Objekts in der Entwicklungsumgebung, die Fokus besitzt.|Ja|
|[Server-Explorer](https://msdn.microsoft.com/library/x603htbk.aspx)|Bietet Methoden zum interagieren mit einer Vielzahl von Serverressourcen.|Ja|
|Projektmappen-Explorer|Ermöglicht das Anzeigen und Verwalten von Projekten und Dateien.|Ja|
|Aufgabenliste|Ermöglicht es Ihnen, Arbeitsaufgaben, die für Ihren Code verwalten.|Ja|
|Testprojekte|Bietet Funktionen, mit denen Sie den Code zu testen.|Nein|
|Werkzeugkasten|Zeigt die Registerkarten, die draggable-Objekte, z. B. Steuerelementen und Abschnitten mit Text oder Code enthalten.|Ja|

## <a name="see-also"></a>Siehe auch
 [Erste Schritte mit f# in Visual Studio](../get-started/get-started-visual-studio.md)  
 [Konfigurieren von Projekten](configuring-projects.md)  
