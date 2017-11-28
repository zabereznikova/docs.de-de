---
title: C#-Compileroptionen nach Kategorien sortiert
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- Visual C# compiler, options listed by category
- compiler options [C#], listed by category
- Visual C#, compiler options listed by category
ms.assetid: 96437ecc-6502-4cd3-b070-e9386a298e83
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c95c5c3d1c7ea2461e9bda9a1d58464e97ccc688
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="c-compiler-options-listed-by-category"></a>C#-Compileroptionen nach Kategorien sortiert
Die folgenden Compileroptionen sind nach Kategorien sortiert. Eine alphabetische Liste finden Sie unter [C#-Compileroptionen alphabetisch sortiert](../../../csharp/language-reference/compiler-options/listed-alphabetically.md).  
  
### <a name="optimization"></a>Optimierung  
  
|Option|Zweck|  
|------------|-------------|  
|[/filealign](../../../csharp/language-reference/compiler-options/filealign-compiler-option.md)|Gibt die Größe der Abschnitte in der Ausgabedatei an.|  
|[/optimize](../../../csharp/language-reference/compiler-options/optimize-compiler-option.md)|Aktiviert/deaktiviert Optimierungen.|  
  
### <a name="output-files"></a>Ausgabedateien  
  
|Option|Zweck|  
|------------|-------------|  
|[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)|Gibt eine XML-Datei an, in die verarbeitete Dokumentationskommentare geschrieben werden sollen.|  
|[/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md)|Gibt die Ausgabedatei an.|  
|[/pdb](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md)|Gibt den Dateinamen und den Speicherort der PDB-Datei an.|  
|[/platform](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)|Gibt die Ausgabeplattform an.|  
|[/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Geben Sie eine Sprache für die Compilerausgabe an.|  
|[/refout](refout-compiler-option.md)|Generiert eine Verweisassembly zusätzlich zur primären Assembly|  
|[/refonly](refonly-compiler-option.md)|Generiert eine Verweisassembly statt der primären Assembly|  
|[/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md)|Gibt das Format der Ausgabedatei mit einer der folgenden Optionen an: [/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md), [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md), [/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md), [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) oder [/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md).|  
|/modulename:\<string>|Geben Sie den Namen des Quellmoduls an|  
  
### <a name="net-framework-assemblies"></a>.NET Framework-Assemblys  
  
|Option|Zweck|  
|------------|-------------|  
|[/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)|Gibt eine oder mehrere Module an, die Bestandteil dieser Assembly sein sollen.|  
|[/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)|Weist den Compiler an, den öffentlichen Schlüssel hinzuzufügen, die Assembly jedoch nicht zu signieren.|  
|[/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md)|Gibt den Namen des kryptografischen Schlüsselcontainers an.|  
|[/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)|Gibt den Dateinamen mit dem kryptografischen Schlüssel an.|  
|[/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md)|Gibt den Speicherort der Assemblys an, auf den durch [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) verwiesen wird.|  
|[/nostdlib](../../../csharp/language-reference/compiler-options/nostdlib-compiler-option.md)|Weist den Compiler an, die Standardbibliothek (mscorlib.dll) nicht zu importieren.|  
|[/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)|Importiert Metadaten aus einer Datei, die eine Assembly enthält.|  
|/analyzer|Führt die Analyzer aus dieser Assembly aus (Kurzform: /a).|  
|/additionalfile|Benennt zusätzliche Dateien, die möglicherweise vom Analyzer verwendet werden, um Fehler oder Warnungen zu erzeugen, sich aber nicht direkt auf die Codegenerierung auswirken.|  
  
### <a name="debuggingerror-checking"></a>Debuggen/Fehlerüberprüfung  
  
|Option|Zweck|  
|------------|-------------|  
|[/bugreport](../../../csharp/language-reference/compiler-options/bugreport-compiler-option.md)|Erstellt eine Datei mit Informationen, die das Melden eines Bugs erleichtern.|  
|[/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md)|Gibt an, ob Ganzzahlarithmetik, die die Grenzen des Datentyps überschreitet, zur Laufzeit eine Ausnahme auslöst.|  
|[/debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md)|Weisen den Compiler an, Debuginformationen auszugeben.|  
|[/errorreport](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)|Legt das Verhalten der Fehlerberichterstattung fest.|  
|[/fullpaths](../../../csharp/language-reference/compiler-options/fullpaths-compiler-option.md)|Gibt den absoluten Pfad zur Datei in der Compilerausgabe an.|  
|[/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md)|Unterdrückt die Generierung von bestimmten Warnungen durch den Compiler.|  
|[/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md)|Legt die Warnstufe fest.|  
|[/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md)|Stuft Warnungen zu Fehlern hoch.|  
|/ruleset:\<file>|Geben Sie eine Regelsatzdatei an, die bestimmte Diagnosefunktionen deaktiviert.|  
  
### <a name="preprocessor"></a>Präprozessor  
  
|Option|Zweck|  
|------------|-------------|  
|[/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md)|Definiert Präprozessorsymbole.|  
  
### <a name="resources"></a>Ressourcen  
  
|Option|Zweck|  
|------------|-------------|  
|[/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md)|Macht COM-Typinformationen in den angegebenen Assemblys für das Projekt verfügbar.|  
|[/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)|Erstellt einen Link zu einer verwalteten Ressource.|  
|[/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)|Bettet eine .NET Framework-Ressource in die Ausgabedatei ein.|  
|[/win32icon](../../../csharp/language-reference/compiler-options/win32icon-compiler-option.md)|Gibt eine ICO-Datei an, die in die Ausgabedatei eingefügt werden soll.|  
|[/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md)|Gibt eine Win32-Ressource an, die in die Ausgabedatei eingefügt werden soll.|  
  
### <a name="miscellaneous"></a>Sonstiges  
  
|Option|Zweck|  
|------------|-------------|  
|[@](../../../csharp/language-reference/compiler-options/response-file-compiler-option.md)|Legt eine Antwortdatei fest.|  
|[/?](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|Listet Compileroptionen in „stdout“ auf.|  
|[/baseaddress](../../../csharp/language-reference/compiler-options/baseaddress-compiler-option.md)|Gibt die bevorzugte Basisadresse an, unter der eine DLL geladen werden soll.|  
|[/codepage](../../../csharp/language-reference/compiler-options/codepage-compiler-option.md)|Gibt die für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.|  
|[/help](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|Listet Compileroptionen in „stdout“ auf.|  
|[/highentropyva](../../../csharp/language-reference/compiler-options/highentropyva-compiler-option.md)|Gibt an, dass die ausführbare Datei Address Space Layout Randomization (ASLR) unterstützt.|  
|[/langversion](../../../csharp/language-reference/compiler-options/langversion-compiler-option.md)|Gibt den Sprachversionsmodus an: Default, ISO-1, ISO-2, 3, 4, 5, 6, 7, 7.1 oder Latest. |  
|[/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md)|Gibt den Speicherort der **Main**-Methode an.|  
|[/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)|Weist den Compiler an, nicht mit „csc.rsp“ zu kompilieren.|  
|[/nologo](../../../csharp/language-reference/compiler-options/nologo-compiler-option.md)|Unterdrückt Compilerbannerinformationen.|  
|[/recurse](../../../csharp/language-reference/compiler-options/recurse-compiler-option.md)|Durchsucht Unterverzeichnisse nach zu kompilierenden Quelldateien.|  
|[/subsystemversion](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)|Gibt die mindestens erforderliche Version des Subsystems an, die die generierte ausführbare Datei verwenden kann.|  
|[/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)|Aktiviert die Kompilierung von Code, der das Schlüsselwort [unsafe](../../../csharp/language-reference/keywords/unsafe.md) verwendet.|  
|[/utf8output](../../../csharp/language-reference/compiler-options/utf8output-compiler-option.md)|Zeigt die Compilerausgabe mit UTF-8-Codierung an.|  
|/parallel[+&#124;-]|Gibt an, ob parallele Builds (+) verwendet werden sollen.|  
|/checksumalgorithm:\<alg>|Gibt den Algorithmus zur Berechnung der Quelldateiprüfsumme an, der in der PDB-Datei gespeichert ist.  Unterstützte Werte sind SHA1 (Standard) oder SHA256.|  
  
## <a name="obsolete-options"></a>Veraltete Optionen  
  
|Option|Zweck|  
|---|---|  
|/incremental|Aktiviert die inkrementelle Kompilierung.|  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
 [C#-Compileroptionen alphabetisch sortiert](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  
 [Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)
