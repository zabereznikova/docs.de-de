---
description: C#-Compileroptionen alphabetisch sortiert
title: C#-Compileroptionen alphabetisch sortiert
ms.date: 06/04/2020
helpviewer_keywords:
- compiler options [C#], listed alphabetically
- C# language, compiler options listed alphabetically
- Visual C# compiler, options listed alphabetically
- Visual C#, compiler options listed alphabetically
ms.assetid: 43535ea0-ca47-4a15-b528-615087a86092
ms.openlocfilehash: 6e1351eb9989abeaadebcb755ea9268fcff40a11
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125331"
---
# <a name="c-compiler-options-listed-alphabetically"></a>C#-Compileroptionen alphabetisch sortiert

Die folgenden Compileroptionen sind alphabetisch sortiert. Eine nach Kategorien sortierte Liste finden Sie unter [C#-Compileroptionen nach Kategorien sortiert](listed-by-category.md).

|Option|Zweck|
|------------|-------------|
|[@](response-file-compiler-option.md)|Liest eine Antwortdatei für mehrere Optionen.|
|[-?](help-compiler-option.md)|Zeigt eine Verwendungsmeldung für „stdout“ an.|
|-additionalfile|Benennt zusätzliche Dateien, die möglicherweise vom Analyzer verwendet werden, um Fehler oder Warnungen zu erzeugen, sich aber nicht direkt auf die Codegenerierung auswirken.|
|[-addmodule](addmodule-compiler-option.md)|Verknüpft die angegebenen Module mit dieser Assembly.|
|-analyzer|Führt die Analysetools aus dieser Assembly aus (Kurzform: -a)|
|[/appconfig](appconfig-compiler-option.md)|Gibt den Speicherort von „app.config“ zur Assemblybindungszeit an.|
|[-baseaddress](baseaddress-compiler-option.md)|Gibt die Basisadresse für die zu erstellende Bibliothek an.|
|[-bugreport](bugreport-compiler-option.md)|Erstellt eine Fehlerberichtsdatei. Diese Datei wird zusammen mit den Absturzinformationen gesendet, wenn sie zusammen mit „-errorreport:prompt“ oder „-errorreport:send“ verwendet wird.|
|[/checked](checked-compiler-option.md)|Führt dazu, dass der Compiler Überlaufprüfen generiert.|
|-checksumalgorithm:\<alg>|Gibt den Algorithmus zur Berechnung der Quelldateiprüfsumme an, der in der PDB-Datei gespeichert ist.  Unterstützte Werte: SHA256 (Standard) oder SHA1.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256. |
|[-codepage](codepage-compiler-option.md)|Gibt die beim Öffnen von Quelldateien zu verwendende Codepage an.|
|[-debug](debug-compiler-option.md)|Gibt Debuginformationen aus.|
|[-define](define-compiler-option.md)|Definiert Symbole für die bedingte Kompilierung.|
|[-delaysign](delaysign-compiler-option.md)|Signiert die Assembly verzögert, indem nur der öffentliche Teil des sicheren Schlüsselnamens verwendet wird.|
|[-deterministic](deterministic-compiler-option.md)|Bewirkt, dass der Compiler eine Assembly ausgibt, deren Inhalt im Binärformat über Kompilierungen identisch ist, wenn die Eingaben identisch sind.|
|[-doc](doc-compiler-option.md)|Gibt eine zu generierende XML-Dokumentationsdatei an.|
|-embed|Einbetten aller Quelldateien in die PDB-Datei.|
|-embed:\<file list>|Einbetten bestimmter Dateien in die PDB-Datei.|
|-errorendlocation|Ausgabezeile und -spalte des Zielstandorts jedes Fehlers.|
|-errorlog:\<file>|Angeben einer Datei für das Protokollieren der gesamten Compiler- und Analysetooldiagnose.|
|[-errorreport](errorreport-compiler-option.md)|Gibt an, wie interne Compilerfehler verarbeitet werden sollen: „prompt“, „send“ oder „none“. Der Standardwert ist „none“.|
|[-filealign](filealign-compiler-option.md)|Gibt die für die Ausgabedateiabschnitte verwendete Ausrichtung an.|
|[/fullpaths](fullpaths-compiler-option.md)|Weist den Compiler an, vollqualifizierte Pfade zu generieren.|
|[-help](help-compiler-option.md)|Zeigt eine Verwendungsmeldung für „stdout“ an.|
|[-highentropyva](highentropyva-compiler-option.md)|Gibt an, dass ASLR mit hoher Entropie unterstützt wird.|
|-incremental|Aktiviert die inkrementelle Kompilierung [veraltet].|
|[-keycontainer](keycontainer-compiler-option.md)|Gibt einen Schlüsselcontainer mit starkem Namen an.|
|[-keyfile](keyfile-compiler-option.md)|Gibt eine Schlüsseldatei mit starkem Namen an.|
|[-langversion:\<string>](langversion-compiler-option.md)|Sprachversion angeben: Default, ISO-1, ISO-2, 3, 4, 5, 6, 7, 7.1, 7.2, 7.3, oder Latest |
|[/lib](lib-compiler-option.md)|Gibt zusätzliche Verzeichnisse an, in denen nach Verweisen gesucht wird.|
|[-link](link-compiler-option.md)|Macht COM-Typinformationen in den angegebenen Assemblys für das Projekt verfügbar.|
|[-linkresource](linkresource-compiler-option.md)|Verknüpft die angegebene Ressource mit dieser Assembly.|
|[-main](main-compiler-option.md)|Gibt den Typ an, der den Einstiegspunkt enthält (alle anderen möglichen Einstiegspunkte werden ignoriert).|
|[-moduleassemblyname](moduleassemblyname-compiler-option.md)|Gibt eine Assembly an, auf deren nicht öffentliche Typen ein .NET-Modul zugreifen kann.|
|-modulename:\<string>|Geben Sie den Namen des Quellmoduls an|
|[-noconfig](noconfig-compiler-option.md)|Weist den Compiler an, die CSC.RSP-Datei nicht automatisch einzubeziehen.|
|[-nologo](nologo-compiler-option.md)|Unterdrückt die Compiler-Copyrightmeldung.|
|[-nostdlib](nostdlib-compiler-option.md)|Weist den Compiler an, die Standardbibliothek (mscorlib.dll) nicht zu referenzieren.|
|[-nowarn](nowarn-compiler-option.md)|Deaktiviert bestimmte Warnmeldungen.|
|[-nowin32manifest](nowin32manifest-compiler-option.md)|Weist den Compiler an, kein Anwendungsmanifest in die ausführbare Datei einzubetten.|
|[-nullable](nullable-compiler-option.md)|Mit diesen Argumenten wird die Option für den Nullable-Kontext angegeben.|
|[-optimize](optimize-compiler-option.md)|Aktiviert/deaktiviert Optimierungen.|
|[-out](out-compiler-option.md)|Gibt den Ausgabedateinamen an (Standard: Basisname der Datei mit der Hauptklasse oder erste Datei).|
|-parallel[+&#124;-]|Gibt an, ob parallele Builds (+) verwendet werden sollen.|
|[-pathmap](pathmap-compiler-option.md)|Gibt eine Zuordnung für die Quellpfadnamen an, die vom Compiler ausgegeben werden.|
|[/pdb](pdb-compiler-option.md)|Gibt den Dateinamen und den Speicherort der PDB-Datei an.|
|[-platform](platform-compiler-option.md)|Begrenzt, auf welcher Plattform dieser Code ausgeführt werden kann: x86, Itanium, x64, anycpu oder anycpu32bitpreferred. Der Standardwert lautet „anycpu“.|
|[/preferreduilang](preferreduilang-compiler-option.md)|Gibt die für die Compilerausgabe zu verwendende Sprache an.|
|[-publicsign](publicsign-compiler-option.md)|Wendet einen öffentlichen Schlüssel ohne Signieren der Assembly an. Legt jedoch das Bit in der Assembly fest, das angibt, dass die Assembly signiert ist.|
|[-recurse](recurse-compiler-option.md)|Schließt alle Dateien im aktuellen Verzeichnis und in den Unterverzeichnissen gemäß den Platzhalterspezifikationen ein.|
|[-reference](reference-compiler-option.md)|Verweist auf Metadaten aus den angegebenen Assemblydateien.|
|[/refout](refout-compiler-option.md)|Generiert eine Verweisassembly zusätzlich zur primären Assembly|
|[/refonly](refonly-compiler-option.md)|Generiert eine Verweisassembly statt der primären Assembly|
|-reportanalyzer|Berichten zusätzlicher Analysetoolinformationen, z.B. der Zeitpunkt der Ausführung.|
|[-resource](resource-compiler-option.md)|Bettet die angegebene Ressource ein.|
|-ruleset:\<file>|Geben Sie eine Regelsatzdatei an, die bestimmte Diagnosefunktionen deaktiviert.|
|[-subsystemversion](subsystemversion-compiler-option.md)|Gibt die mindestens erforderliche Version des Subsystems an, die die generierte ausführbare Datei verwenden kann.|
|[-target](target-compiler-option.md)|Gibt das Format der Ausgabedatei mit einer der folgenden Optionen an: [-target:appcontainerexe](target-appcontainerexe-compiler-option.md), [-target:exe](target-exe-compiler-option.md), [-target:library](target-library-compiler-option.md), [-target:module](target-module-compiler-option.md), [-target:winexe](target-winexe-compiler-option.md) und [-target:winmdobj](target-winmdobj-compiler-option.md).|
|[/unsafe](unsafe-compiler-option.md)|Ermöglicht [unsicheren](../keywords/unsafe.md) Code|
|[-utf8output](utf8output-compiler-option.md)|Gibt Compilermeldungen in einer UTF-8-Codierung aus.|
|-version|Anzeigen der Compilerversionsnummer und Beenden.|
|[/warn](warn-compiler-option.md)|Legt die Warnstufe fest (0–4).|
|[-warnaserror](warnaserror-compiler-option.md)|Meldet bestimmte Warnungen als Fehler.|
|[-win32icon](win32icon-compiler-option.md)|Verwendet dieses Symbol für die Ausgabe.|
|[-win32manifest](win32manifest-compiler-option.md)|Gibt eine benutzerdefinierte win32-Manifestdatei an.|
|[/win32res:](win32res-compiler-option.md)|Gibt die win32-Ressourcendatei (.res) an.|

## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](index.md)
- [C#-Compileroptionen nach Kategorien sortiert](listed-by-category.md)
- [Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile](how-to-set-environment-variables-for-the-visual-studio-command-line.md)
- [\<compiler>-Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)
