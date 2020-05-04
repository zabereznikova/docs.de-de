---
title: Compileroptionen nach Kategorien sortiert
ms.date: 04/12/2018
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: fbe36f7a-7cfa-4f77-a8d4-2be5958568e3
ms.openlocfilehash: 8b6c142041024e672fe42c8c6f2d3ebe7b07cd65
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344810"
---
# <a name="visual-basic-compiler-options-listed-by-category"></a>Visual Basic-Compileroptionen nach Kategorien sortiert
Die Visual Basic-Befehlszeilencompiler bietet eine Alternative zum Kompilieren von Programmen in der integrierten Entwicklungsumgebung (IDE) von Visual Studio. Es folgt eine Liste der Befehlszeilen-Compileroptionen von Visual Basic (nach Funktionskategorie sortiert).  

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]
  
## <a name="compiler-output"></a>Compilerausgabe  
  
|Option|Zweck|  
|---|---|  
|[-nologo](../../../visual-basic/reference/command-line-compiler/nologo.md)|Unterdrückt Compilerbannerinformationen.|  
|[-utf8output](../../../visual-basic/reference/command-line-compiler/utf8output.md)|Zeigt die Compilerausgabe mit UTF-8-Codierung an.|  
|[-verbose](../../../visual-basic/reference/command-line-compiler/verbose.md)|Gibt Zusatzinformationen während der Kompilierung aus.|  
|`-modulename:<string>`|Geben Sie den Namen des Quellmoduls an|  
|[/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Geben Sie eine Sprache für die Kompilierungsausgabe an.|
  
## <a name="optimization"></a>Optimierung  
  
|Option|Zweck|  
|---|---|  
|[-filealign](../../../visual-basic/reference/command-line-compiler/filealign.md)|Gibt die Ausrichtung der Abschnitte der Ausgabedatei an.|  
|[-optimize](../../../visual-basic/reference/command-line-compiler/optimize.md)|Aktiviert/deaktiviert Optimierungen.|  
  
## <a name="output-files"></a>Ausgabedateien  
  
|Option|Zweck|  
|---|---|  
|[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)|Verarbeitet Dokumentationskommentare zu einer XML-Datei.|  
|[-deterministic](../../../visual-basic/reference/command-line-compiler/deterministic.md)|Bewirkt, dass der Compiler eine Assembly ausgibt, deren Inhalt im Binärformat über Kompilierungen identisch ist, wenn die Eingaben identisch sind.|
|[-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)|Legt den Compiler als Ziel für .NET Compact Framework fest|  
|[-out](../../../visual-basic/reference/command-line-compiler/out.md)|Gibt eine Ausgabedatei an.|  
|[/refonly](refonly-compiler-option.md)|Gibt nur eine Referenzassembly aus|
|[/refout](refout-compiler-option.md)|Gibt den Namen des Ausgabepfads einer Referenzassembly an|
|[-target](../../../visual-basic/reference/command-line-compiler/target.md)|Gibt das Format der Ausgabe an.|  
  
## <a name="net-assemblies"></a>.NET-Assemblys  
  
|Option|Zweck|  
|---|---|  
|[-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)|Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.|  
|[-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)|Gibt an, ob die Assembly vollständig oder teilweise signiert wird.|  
|[-imports](../../../visual-basic/reference/command-line-compiler/imports.md)|Importiert einen Namespace aus einer angegebenen Assembly.|  
|[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)|Gibt einen Schlüsselcontainernamen für ein Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.|  
|[-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)|Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.|  
|[-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)|Gibt den Speicherort der Assemblys an, auf die durch die [-reference](../../../visual-basic/reference/command-line-compiler/reference.md)-Option verwiesen wird.|  
|[-reference](../../../visual-basic/reference/command-line-compiler/reference.md)|Importiert Metadaten aus einer Assembly.|  
|[-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)|Gibt den Namen der Assembly an, zu der dieses Modul gehört.|  
|`-analyzer`|Führt die Analysetools aus dieser Assembly aus (Kurzform: -a)|  
|`-additionalfile`|Benennt zusätzliche Dateien, die möglicherweise vom Analyzer verwendet werden, um Fehler oder Warnungen zu erzeugen, sich aber nicht direkt auf die Codegenerierung auswirken.|  
  
## <a name="debuggingerror-checking"></a>Debuggen/Fehlerüberprüfung  
  
|Option|Zweck|  
|---|---|  
|[-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)|Erstellt eine Datei mit Informationen, die das Melden eines Bugs erleichtern.|  
|[-debug](../../../visual-basic/reference/command-line-compiler/debug.md)|Erzeugt Debuginformationen.|  
|[-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)|Unterdrückt die Compilerfunktion zum Generieren von Warnungen.|  
|[-quiet](../../../visual-basic/reference/command-line-compiler/quiet.md)|Verhindert, dass der Compiler Code für syntaxbezogene Fehler und Warnungen anzeigt.|  
|[-removeintchecks](../../../visual-basic/reference/command-line-compiler/removeintchecks.md)|Deaktiviert Überprüfungen auf Ganzzahlüberlauf|  
|[-warnaserror](../../../visual-basic/reference/command-line-compiler/warnaserror.md)|Stuft Warnungen zu Fehlern hoch.|  
|`-ruleset:<file>`|Geben Sie eine Regelsatzdatei an, die bestimmte Diagnosefunktionen deaktiviert.|  
  
## <a name="help"></a>Hilfe  
  
|Option|Zweck|  
|---|---|  
|[-?](../../../visual-basic/reference/command-line-compiler/help.md)|Zeigt die Compileroptionen an. Dieser Befehl entspricht der Angabe der `-help`-Option. Es findet keine Kompilierung statt.|  
|[-help](../../../visual-basic/reference/command-line-compiler/help.md)|Zeigt die Compileroptionen an. Dieser Befehl entspricht der Angabe der `-?`-Option. Es findet keine Kompilierung statt.|  
  
## <a name="language"></a>Sprache  
  
|Option|Zweck|  
|---|---|  
|[-langversion](../../../visual-basic/reference/command-line-compiler/langversion.md)|Sprachversion angeben: 9&#124;9.0&#124;10&#124;10.0&#124;11&#124;11.0.|  
|[-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)|Erzwingt explizite Variablendeklaration.|  
|[-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)|Erzwingt strenge Typsemantik.|  
|[-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)|Gibt an, ob Zeichenfolgenvergleiche binär sein oder gebietsschemaspezifische Textsemantik verwenden sollen.|  
|[-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)|Ermöglicht die Verwendung von lokalem Typrückschluss in Variablendeklarationen.|  
  
## <a name="preprocessor"></a>Präprozessor  
  
|Option|Zweck|  
|---|---|  
|[-define](../../../visual-basic/reference/command-line-compiler/define.md)|Definiert Symbole für bedingte Kompilierung.|  
  
## <a name="resources"></a>Ressourcen  
  
|Option|Zweck|  
|---|---|  
|[-linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)|Erstellt einen Link zu einer verwalteten Ressource.|  
|[-resource](../../../visual-basic/reference/command-line-compiler/resource.md)|Bettet eine verwaltete Ressource in eine Assembly ein.|  
|[-win32icon](../../../visual-basic/reference/command-line-compiler/win32icon.md)|Fügt eine ICO-Datei in die Ausgabedatei ein.|  
|[-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)|Fügt eine Win32-Ressource in die Ausgabedatei ein.|  
  
## <a name="miscellaneous"></a>Verschiedenes  
  
|Option|Zweck|  
|---|---|  
|[@ (Antwortdatei festlegen)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)|Legt eine Antwortdatei fest.|  
|[-baseaddress](../../../visual-basic/reference/command-line-compiler/baseaddress.md)|Gibt die Basisadresse einer DLL an.|  
|[-codepage](../../../visual-basic/reference/command-line-compiler/codepage.md)|Gibt die für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.|  
|[-errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)|Gibt an, wie interne Compilerfehler vom Visual Basic-Compiler gemeldet werden sollen|  
|[-highentropyva](../../../visual-basic/reference/command-line-compiler/highentropyva.md)|Informiert den Windows-Kernel, ob eine bestimmte ausführbare Datei ASLR mit hoher Entropie (Address Space Layout Randomization, Zufällige Anordnung des Layouts des Adressraums) unterstützt.|  
|[-main](../../../visual-basic/reference/command-line-compiler/main.md)|Gibt die Klasse an, die die `Sub Main`-Prozedur enthält, die beim Start verwendet werden soll|  
|[-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)|Führen Sie die Kompilierung nicht mit Vbc.rsp durch.|  
|[-nostdlib](../../../visual-basic/reference/command-line-compiler/nostdlib.md)|Bewirkt, dass der Compiler nicht auf die Standardbibliotheken verweist.|  
|[-nowin32manifest](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)|Weist den Compiler an, kein Anwendungsmanifest in die ausführbare Datei einzubetten.|  
|[-platform](../../../visual-basic/reference/command-line-compiler/platform.md)|Gibt die Prozessorplattform an, auf die der Compiler für die Ausgabedatei verweist.|  
|[-recurse](../../../visual-basic/reference/command-line-compiler/recurse.md)|Durchsucht Unterverzeichnisse nach zu kompilierenden Quelldateien.|  
|[-rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)|Gibt einen Namespace für alle Typdeklarationen an.|  
|[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)|Gibt den Speicherort von „mscorlib.dll“ und „microsoft.visualbasic.dll“ an.|  
|[-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)|Gibt an, dass der Compiler ohne einen Verweis auf die Visual Basic Runtime Library oder mit einem Verweis auf eine bestimmte Laufzeitbibliothek kompilieren soll.|  
|[-win32manifest](../../../visual-basic/reference/command-line-compiler/win32manifest.md)|Identifiziert eine benutzerdefinierte Win32-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei (PE) eines Projekts eingebettet werden soll.|  
|`-parallel[+&#124;-]`|Gibt an, ob parallele Builds (+) verwendet werden sollen.|  
|`-checksumalgorithm:<alg>`|Gibt den Algorithmus zur Berechnung der Quelldateiprüfsumme an, der in der PDB-Datei gespeichert ist.  Unterstützte Werte: SHA-1 (Standard) oder SHA-256. <br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256 oder höher.|  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic Compileroptionen in alphabetischer Reihenfolge](../../../visual-basic/reference/command-line-compiler/compiler-options-listed-alphabetically.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
