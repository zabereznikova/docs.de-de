---
title: Compileroptionen alphabetisch sortiert
ms.date: 04/12/2018
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: e67febba-bacf-4e1f-a143-c141e063f90e
ms.openlocfilehash: c529c03fd3856bbd3d3b26371415907c94ca8d30
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343519"
---
# <a name="visual-basic-compiler-options-listed-alphabetically"></a>Visual Basic in alphabetischer Reihenfolge aufgeführten Compileroptionen
Der Visual Basic-Befehlszeilen Compiler wird als Alternative zum Kompilieren von Programmen in der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) von Visual Studio bereitgestellt. Im folgenden finden Sie eine Liste der Visual Basic Befehlszeilen-Compileroptionen, die alphabetisch sortiert sind.  

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]
  
|Option|Zweck|  
|------------|-------------|  
|[@ (Antwortdatei festlegen)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)|Legt eine Antwortdatei fest.|  
|[-?](../../../visual-basic/reference/command-line-compiler/help.md)|Zeigt Compileroptionen an Dieser Befehl entspricht der Angabe der `-help`-Option. Es findet keine Kompilierung statt.|  
|`-additionalfile`|Benennt zusätzliche Dateien, die möglicherweise vom Analyzer verwendet werden, um Fehler oder Warnungen zu erzeugen, sich aber nicht direkt auf die Codegenerierung auswirken.|  
|[-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)|Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.|  
|`-analyzer`|Führt die Analysetools aus dieser Assembly aus (Kurzform: -a)|  
|[-baseaddress](../../../visual-basic/reference/command-line-compiler/baseaddress.md)|Gibt die Basisadresse einer DLL an.|  
|[-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)|Erstellt eine Datei mit Informationen, die das Melden eines Bugs erleichtern.|  
|`-checksumalgorithm:<alg>`|Gibt den Algorithmus zur Berechnung der Quelldateiprüfsumme an, der in der PDB-Datei gespeichert ist.  Unterstützte Werte sind: SHA1 (Standard) oder SHA256. <br>Aufgrund von Konnektivitätsproblemen mit SHA1 empfiehlt Microsoft SHA256 oder eine bessere.|  
|[-codepage](../../../visual-basic/reference/command-line-compiler/codepage.md)|Gibt die für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.|  
|[-debug](../../../visual-basic/reference/command-line-compiler/debug.md)|Erzeugt Debuginformationen.|  
|[-define](../../../visual-basic/reference/command-line-compiler/define.md)|Definiert Symbole für bedingte Kompilierung.|  
|[-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)|Gibt an, ob die Assembly vollständig oder teilweise signiert wird.|  
|[-deterministic](../../../visual-basic/reference/command-line-compiler/deterministic.md)|Bewirkt, dass der Compiler eine Assembly ausgibt, deren Inhalt im Binärformat über Kompilierungen identisch ist, wenn die Eingaben identisch sind.|
|[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)|Verarbeitet Dokumentationskommentare zu einer XML-Datei.|  
|[-errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)|Gibt an, wie der Visual Basic Compiler interne Compilerfehler melden soll.|  
|[-filealign](../../../visual-basic/reference/command-line-compiler/filealign.md)|Gibt die Ausrichtung der Abschnitte der Ausgabedatei an.|  
|[-help](../../../visual-basic/reference/command-line-compiler/help.md)|Zeigt Compileroptionen an Dieser Befehl entspricht der Angabe der `-?`-Option. Es findet keine Kompilierung statt.|  
|[-highentropyva](../../../visual-basic/reference/command-line-compiler/highentropyva.md)|Gibt an, ob eine bestimmte ausführbare Datei ASLR mit hoher Entropie (Address Space Layout Randomization, Zufällige Anordnung des Layouts des Adressraums) unterstützt.|  
|[-imports](../../../visual-basic/reference/command-line-compiler/imports.md)|Importiert einen Namespace aus einer angegebenen Assembly.|  
|[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)|Gibt einen Schlüsselcontainernamen für ein Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.|  
|[-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)|Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.|  
|[-langversion](../../../visual-basic/reference/command-line-compiler/langversion.md)|Sprachversion angeben: 9&#124;9,0&#124;10&#124;10,0&#124;11&#124;11,0.|  
|[-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)|Gibt den Speicherort der Assemblys an, auf die die Option [-Reference verweist](../../../visual-basic/reference/command-line-compiler/reference.md) .|  
|[-linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)|Erstellt einen Link zu einer verwalteten Ressource.|  
|[-main](../../../visual-basic/reference/command-line-compiler/main.md)|Gibt die Klasse an, die die `Sub Main` Prozedur enthält, die beim Start verwendet werden soll.|  
|[-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)|Gibt den Namen der Assembly an, zu der dieses Modul gehört.|  
|`-modulename:<string>`|Geben Sie den Namen des Quellmoduls an|  
|[-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)|Legt den Compiler als Ziel für den .NET Compact Framework fest.|  
|[-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)|Führen Sie die Kompilierung nicht mit Vbc.rsp durch.|  
|[-nologo](../../../visual-basic/reference/command-line-compiler/nologo.md)|Unterdrückt Compilerbannerinformationen.|  
|[-nostdlib](../../../visual-basic/reference/command-line-compiler/nostdlib.md)|Bewirkt, dass der Compiler nicht auf die Standardbibliotheken verweist.|  
|[-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)|Unterdrückt die Compilerfunktion zum Generieren von Warnungen.|  
|[-nowin32manifest](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)|Weist den Compiler an, kein Anwendungsmanifest in die ausführbare Datei einzubetten.|  
|[-optimize](../../../visual-basic/reference/command-line-compiler/optimize.md)|Aktiviert/deaktiviert Codeoptimierungen.|  
|[-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)|Gibt an, ob Zeichenfolgenvergleiche binär sein oder gebietsschemaspezifische Textsemantik verwenden sollen.|  
|[-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)|Erzwingt explizite Variablendeklaration.|  
|[-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)|Ermöglicht die Verwendung von lokalem Typrückschluss in Variablendeklarationen.|  
|[-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)|Erzwingt strenge Sprachsemantik.|  
|[-out](../../../visual-basic/reference/command-line-compiler/out.md)|Gibt eine Ausgabedatei an.|  
|`-parallel[+&#124;-]`|Gibt an, ob parallele Builds (+) verwendet werden sollen.|  
|[-platform](../../../visual-basic/reference/command-line-compiler/platform.md)|Gibt die Prozessorplattform an, auf die der Compiler für die Ausgabedatei verweist.|  
|`-preferreduilang`|Geben Sie den Namen der bevorzugten Ausgabesprache an.|  
|[-quiet](../../../visual-basic/reference/command-line-compiler/quiet.md)|Verhindert, dass der Compiler Code für syntaxbezogene Fehler und Warnungen anzeigt.|  
|[-recurse](../../../visual-basic/reference/command-line-compiler/recurse.md)|Durchsucht Unterverzeichnisse nach zu kompilierenden Quelldateien.|  
|[-reference](../../../visual-basic/reference/command-line-compiler/reference.md)|Importiert Metadaten aus einer Assembly.|  
|[/refonly](refonly-compiler-option.md)|Gibt nur eine Verweisassembly aus.|
|[/refout](refout-compiler-option.md)|Gibt den Ausgabepfad einer Verweisassembly an.|
|[-removeintchecks](../../../visual-basic/reference/command-line-compiler/removeintchecks.md)|Deaktiviert Überprüfungen auf Ganzzahlüberlauf|  
|[-resource](../../../visual-basic/reference/command-line-compiler/resource.md)|Bettet eine verwaltete Ressource in eine Assembly ein.|  
|[-rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)|Gibt einen Namespace für alle Typdeklarationen an.|  
|`-ruleset:<file>`|Geben Sie eine Regelsatzdatei an, die bestimmte Diagnosefunktionen deaktiviert.|  
|[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)|Gibt den Speicherort von „mscorlib.dll“ und „microsoft.visualbasic.dll“ an.|  
|[-subsystemversion](../../../visual-basic/reference/command-line-compiler/subsystemversion.md)|Gibt die mindestens erforderliche Version des Subsystems an, die die generierte ausführbare Datei verwenden kann.|  
|[-target](../../../visual-basic/reference/command-line-compiler/target.md)|Gibt das Format der Ausgabedatei an.|  
|[-utf8output](../../../visual-basic/reference/command-line-compiler/utf8output.md)|Zeigt die Compilerausgabe mit UTF-8-Codierung an.|  
|[-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)|Gibt an, dass der Compiler ohne einen Verweis auf die Visual Basic Runtime Library oder mit einem Verweis auf eine bestimmte Laufzeitbibliothek kompilieren soll.|  
|[-verbose](../../../visual-basic/reference/command-line-compiler/verbose.md)|Gibt Zusatzinformationen während der Kompilierung aus.|  
|[-warnaserror](../../../visual-basic/reference/command-line-compiler/warnaserror.md)|Stuft Warnungen zu Fehlern hoch.|  
|[-win32icon](../../../visual-basic/reference/command-line-compiler/win32icon.md)|Fügt eine ICO-Datei in die Ausgabedatei ein.|  
|[-win32manifest](../../../visual-basic/reference/command-line-compiler/win32manifest.md)|Identifiziert eine benutzerdefinierte Win32-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei (PE) eines Projekts eingebettet werden soll.|  
|[-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)|Fügt eine Win32-Ressource in die Ausgabedatei ein.|  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Compileroptionen nach Kategorien sortiert](../../../visual-basic/reference/command-line-compiler/compiler-options-listed-by-category.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
