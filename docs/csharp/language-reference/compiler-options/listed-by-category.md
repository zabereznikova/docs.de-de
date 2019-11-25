---
title: C#-Compileroptionen nach Kategorien sortiert
ms.date: 05/15/2018
helpviewer_keywords:
- Visual C# compiler, options listed by category
- compiler options [C#], listed by category
- Visual C#, compiler options listed by category
ms.assetid: 96437ecc-6502-4cd3-b070-e9386a298e83
ms.openlocfilehash: 5cd5607c25dabd8f56ebb58366116666e8e649ea
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972707"
---
# <a name="c-compiler-options-listed-by-category"></a>C#-Compileroptionen nach Kategorien sortiert

Die folgenden Compileroptionen sind nach Kategorien sortiert. Eine alphabetische Liste finden Sie unter [C#-Compileroptionen alphabetisch sortiert](listed-alphabetically.md).

## <a name="optimization"></a>Optimierung

|Option|Zweck|
|------------|-------------|
|[-filealign](filealign-compiler-option.md)|Gibt die Größe der Abschnitte in der Ausgabedatei an.|
|[-optimize](optimize-compiler-option.md)|Aktiviert/deaktiviert Optimierungen.|

## <a name="output-files"></a>Ausgabedateien

|Option|Zweck|
|------------|-------------|
|[-deterministic](deterministic-compiler-option.md)|Bewirkt, dass der Compiler eine Assembly ausgibt, deren Inhalt im Binärformat über Kompilierungen identisch ist, wenn die Eingaben identisch sind.|
|[-doc](doc-compiler-option.md)|Gibt eine XML-Datei an, in die verarbeitete Dokumentationskommentare geschrieben werden sollen.|
|[-out](out-compiler-option.md)|Gibt die Ausgabedatei an.|
|[-pathmap](pathmap-compiler-option.md)|Gibt eine Zuordnung für die Quellpfadnamen an, die vom Compiler ausgegeben werden.|
|[/pdb](pdb-compiler-option.md)|Gibt den Dateinamen und den Speicherort der PDB-Datei an.|
|[-platform](platform-compiler-option.md)|Gibt die Ausgabeplattform an.|
|[/preferreduilang](preferreduilang-compiler-option.md)|Geben Sie eine Sprache für die Kompilierungsausgabe an.|
|[/refout](refout-compiler-option.md)|Generiert eine Verweisassembly zusätzlich zur primären Assembly|
|[/refonly](refonly-compiler-option.md)|Generiert eine Verweisassembly statt der primären Assembly|
|[-target](target-compiler-option.md)|Gibt das Format der Ausgabedatei mit einer der folgenden Optionen an: [-target:appcontainerexe](target-appcontainerexe-compiler-option.md), [-target:exe](target-exe-compiler-option.md), [-target:library](target-library-compiler-option.md), [-target:module](target-module-compiler-option.md), [-target:winexe](target-winexe-compiler-option.md) oder [-target:winmdobj](target-winmdobj-compiler-option.md).|
|-modulename:\<string>|Geben Sie den Namen des Quellmoduls an|

## <a name="net-framework-assemblies"></a>.NET Framework-Assemblys

|Option|Zweck|
|------------|-------------|
|[-addmodule](addmodule-compiler-option.md)|Gibt eine oder mehrere Module an, die Bestandteil dieser Assembly sein sollen.|
|[-delaysign](delaysign-compiler-option.md)|Weist den Compiler an, den öffentlichen Schlüssel hinzuzufügen, die Assembly jedoch nicht zu signieren.|
|[-keycontainer](keycontainer-compiler-option.md)|Gibt den Namen des kryptografischen Schlüsselcontainers an.|
|[-keyfile](keyfile-compiler-option.md)|Gibt den Dateinamen mit dem kryptografischen Schlüssel an.|
|[/lib](lib-compiler-option.md)|Gibt den Speicherort der Assemblys an, auf den durch [-reference](reference-compiler-option.md) verwiesen wird.|
|[-nostdlib](nostdlib-compiler-option.md)|Weist den Compiler an, die Standardbibliothek (mscorlib.dll) nicht zu importieren.|
|[-publicsign](publicsign-compiler-option.md)|Wendet einen öffentlichen Schlüssel ohne Signieren der Assembly an. Legt jedoch das Bit in der Assembly fest, das angibt, dass die Assembly signiert ist.|
|[-reference](reference-compiler-option.md)|Importiert Metadaten aus einer Datei, die eine Assembly enthält.|
|-analyzer|Führt die Analyzer aus dieser Assembly aus (Kurzform: /a).|
|-additionalfile|Benennt zusätzliche Dateien, die möglicherweise vom Analyzer verwendet werden, um Fehler oder Warnungen zu erzeugen, sich aber nicht direkt auf die Codegenerierung auswirken.|
|-embed|Einbetten aller Quelldateien in die PDB-Datei.|
|-embed:\<Dateiliste>|Einbetten bestimmter Dateien in die PDB-Datei.|
## <a name="debuggingerror-checking"></a>Debuggen/Fehlerüberprüfung

|Option|Zweck|
|------------|-------------|
|[-bugreport](bugreport-compiler-option.md)|Erstellt eine Datei mit Informationen, die das Melden eines Bugs erleichtern.|
|[/checked](checked-compiler-option.md)|Gibt an, ob Ganzzahlarithmetik, die die Grenzen des Datentyps überschreitet, zur Laufzeit eine Ausnahme auslöst.|
|[-debug](debug-compiler-option.md)|Weisen den Compiler an, Debuginformationen auszugeben.|
|[-errorreport](errorreport-compiler-option.md)|Legt das Verhalten der Fehlerberichterstattung fest.|
|[/fullpaths](fullpaths-compiler-option.md)|Gibt den absoluten Pfad zur Datei in der Compilerausgabe an.|
|[-nowarn](nowarn-compiler-option.md)|Unterdrückt die Generierung von bestimmten Warnungen durch den Compiler.|
|[/warn](warn-compiler-option.md)|Legt die Warnstufe fest.|
|[-warnaserror](warnaserror-compiler-option.md)|Stuft Warnungen zu Fehlern hoch.|
|-ruleset:\<file>|Geben Sie eine Regelsatzdatei an, die bestimmte Diagnosefunktionen deaktiviert.|

## <a name="preprocessor"></a>Präprozessor

|Option|Zweck|
|------------|-------------|
|[-define](define-compiler-option.md)|Definiert Präprozessorsymbole.|

## <a name="resources"></a>Ressourcen

|Option|Zweck|
|------------|-------------|
|[-link](link-compiler-option.md)|Macht COM-Typinformationen in den angegebenen Assemblys für das Projekt verfügbar.|
|[-linkresource](linkresource-compiler-option.md)|Erstellt einen Link zu einer verwalteten Ressource.|
|[-resource](resource-compiler-option.md)|Bettet eine .NET Framework-Ressource in die Ausgabedatei ein.|
|[-win32icon](win32icon-compiler-option.md)|Gibt eine ICO-Datei an, die in die Ausgabedatei eingefügt werden soll.|
|[/win32res:](win32res-compiler-option.md)|Gibt eine Win32-Ressource an, die in die Ausgabedatei eingefügt werden soll.|

## <a name="miscellaneous"></a>Verschiedenes

|Option|Zweck|
|------------|-------------|
|[@](response-file-compiler-option.md)|Legt eine Antwortdatei fest.|
|[-?](help-compiler-option.md)|Listet Compileroptionen in „stdout“ auf.|
|[-baseaddress](baseaddress-compiler-option.md)|Gibt die bevorzugte Basisadresse an, unter der eine DLL geladen werden soll.|
|[-codepage](codepage-compiler-option.md)|Gibt die für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.|
|[-help](help-compiler-option.md)|Listet Compileroptionen in „stdout“ auf.|
|[-highentropyva](highentropyva-compiler-option.md)|Gibt an, dass die ausführbare Datei Address Space Layout Randomization (ASLR) unterstützt.|
|[-langversion](langversion-compiler-option.md)|Sprachversion angeben: Default, ISO-1, ISO-2, 3, 4, 5, 6, 7, 7.1, 7.2, 7.3 oder Latest |
|[-main](main-compiler-option.md)|Gibt den Speicherort der **Main**-Methode an.|
|[-noconfig](noconfig-compiler-option.md)|Weist den Compiler an, nicht mit „csc.rsp“ zu kompilieren.|
|[-nologo](nologo-compiler-option.md)|Unterdrückt Compilerbannerinformationen.|
|[-recurse](recurse-compiler-option.md)|Durchsucht Unterverzeichnisse nach zu kompilierenden Quelldateien.|
|[-subsystemversion](subsystemversion-compiler-option.md)|Gibt die mindestens erforderliche Version des Subsystems an, die die generierte ausführbare Datei verwenden kann.|
|[/unsafe](unsafe-compiler-option.md)|Aktiviert die Kompilierung von Code, der das Schlüsselwort [unsafe](../keywords/unsafe.md) verwendet.|
|[-utf8output](utf8output-compiler-option.md)|Zeigt die Compilerausgabe mit UTF-8-Codierung an.|
|-parallel[+&#124;-]|Gibt an, ob parallele Builds (+) verwendet werden sollen.|
|-checksumalgorithm:\<alg>|Gibt den Algorithmus zur Berechnung der Quelldateiprüfsumme an, der in der PDB-Datei gespeichert ist.  Unterstützte Werte: SHA-1 (Standard) oder SHA-256.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|

## <a name="obsolete-options"></a>Veraltete Optionen

|Option|Zweck|
|---|---|
|-incremental|Aktiviert die inkrementelle Kompilierung.|

## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](index.md)
- [C#-Compileroptionen alphabetisch sortiert](listed-alphabetically.md)
- [Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile](how-to-set-environment-variables-for-the-visual-studio-command-line.md)
