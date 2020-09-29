---
title: Compileroptionen alphabetisch sortiert
ms.date: 04/12/2018
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: e67febba-bacf-4e1f-a143-c141e063f90e
ms.openlocfilehash: d0dbe785edf7a9aa029d4be08a9b854cf1fb2b79
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085294"
---
# <a name="visual-basic-compiler-options-listed-alphabetically"></a>Visual Basic-Compileroptionen in alphabetischer Reihenfolge

Der Visual Basic-Befehlszeilencompiler bietet eine Alternative zum Kompilieren von Programmen in der integrierten Entwicklungsumgebung (IDE) von Visual Studio. Es folgt eine Liste der Befehlszeilen-Compileroptionen von Visual Basic (alphabetisch sortiert).  

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]
  
|Option|Zweck|  
|------------|-------------|  
|[@ (Antwortdatei festlegen)](specify-response-file.md)|Legt eine Antwortdatei fest.|  
|[-?](help.md)|Zeigt Compileroptionen an Dieser Befehl entspricht der Angabe der `-help`-Option. Es findet keine Kompilierung statt.|  
|`-additionalfile`|Benennt zusätzliche Dateien, die möglicherweise vom Analyzer verwendet werden, um Fehler oder Warnungen zu erzeugen, sich aber nicht direkt auf die Codegenerierung auswirken.|  
|[-addmodule](addmodule.md)|Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.|  
|`-analyzer`|Führt die Analysetools aus dieser Assembly aus (Kurzform: -a)|  
|[-baseaddress](baseaddress.md)|Gibt die Basisadresse einer DLL an.|  
|[-bugreport](bugreport.md)|Erstellt eine Datei mit Informationen, die das Melden eines Bugs erleichtern.|  
|`-checksumalgorithm:<alg>`|Gibt den Algorithmus zur Berechnung der Quelldateiprüfsumme an, der in der PDB-Datei gespeichert ist.  Unterstützte Werte: SHA-1 (Standard) oder SHA-256. <br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256 oder höher.|  
|[-codepage](codepage.md)|Gibt die für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.|  
|[-debug](debug.md)|Erzeugt Debuginformationen.|  
|[-define](define.md)|Definiert Symbole für bedingte Kompilierung.|  
|[-delaysign](delaysign.md)|Gibt an, ob die Assembly vollständig oder teilweise signiert wird.|  
|[-deterministic](deterministic.md)|Bewirkt, dass der Compiler eine Assembly ausgibt, deren Inhalt im Binärformat über Kompilierungen identisch ist, wenn die Eingaben identisch sind.|
|[-doc](doc.md)|Verarbeitet Dokumentationskommentare zu einer XML-Datei.|  
|[-errorreport](errorreport.md)|Gibt an, wie interne Compilerfehler vom Visual Basic-Compiler gemeldet werden sollen.|  
|[-filealign](filealign.md)|Gibt die Ausrichtung der Abschnitte der Ausgabedatei an.|  
|[-help](help.md)|Zeigt Compileroptionen an Dieser Befehl entspricht der Angabe der `-?`-Option. Es findet keine Kompilierung statt.|  
|[-highentropyva](highentropyva.md)|Gibt an, ob eine bestimmte ausführbare Datei ASLR mit hoher Entropie (Address Space Layout Randomization, Zufällige Anordnung des Layouts des Adressraums) unterstützt.|  
|[-imports](imports.md)|Importiert einen Namespace aus einer angegebenen Assembly.|  
|[-keycontainer](keycontainer.md)|Gibt einen Schlüsselcontainernamen für ein Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.|  
|[-keyfile](keyfile.md)|Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.|  
|[-langversion](langversion.md)|Sprachversion angeben: 9&#124;9.0&#124;10&#124;10.0&#124;11&#124;11.0.|  
|[-libpath](libpath.md)|Gibt den Speicherort der Assemblys an, auf die durch die [-reference](reference.md)-Option verwiesen wird.|  
|[-linkresource](linkresource.md)|Erstellt einen Link zu einer verwalteten Ressource.|  
|[-main](main.md)|Gibt die Klasse an, die die `Sub Main`-Prozedur enthält, die beim Start verwendet werden soll.|  
|[-moduleassemblyname](moduleassemblyname.md)|Gibt den Namen der Assembly an, zu der dieses Modul gehört.|  
|`-modulename:<string>`|Geben Sie den Namen des Quellmoduls an|  
|[-netcf](netcf.md)|Legt den Compiler als Ziel für .NET Compact Framework fest.|  
|[-noconfig](noconfig.md)|Führen Sie die Kompilierung nicht mit Vbc.rsp durch.|  
|[-nologo](nologo.md)|Unterdrückt Compilerbannerinformationen.|  
|[-nostdlib](nostdlib.md)|Bewirkt, dass der Compiler nicht auf die Standardbibliotheken verweist.|  
|[-nowarn](nowarn.md)|Unterdrückt die Compilerfunktion zum Generieren von Warnungen.|  
|[-nowin32manifest](nowin32manifest.md)|Weist den Compiler an, kein Anwendungsmanifest in die ausführbare Datei einzubetten.|  
|[-optimize](optimize.md)|Aktiviert/deaktiviert Codeoptimierungen.|  
|[-optioncompare](optioncompare.md)|Gibt an, ob Zeichenfolgenvergleiche binär sein oder gebietsschemaspezifische Textsemantik verwenden sollen.|  
|[-optionexplicit](optionexplicit.md)|Erzwingt explizite Variablendeklaration.|  
|[-optioninfer](optioninfer.md)|Ermöglicht die Verwendung von lokalem Typrückschluss in Variablendeklarationen.|  
|[-optionstrict](optionstrict.md)|Erzwingt strenge Sprachsemantik.|  
|[-out](out.md)|Gibt eine Ausgabedatei an.|  
|<code>-parallel[+&#124;-]</code>|Gibt an, ob parallele Builds (+) verwendet werden sollen.|  
|[-platform](platform.md)|Gibt die Prozessorplattform an, auf die der Compiler für die Ausgabedatei verweist.|  
|`-preferreduilang`|Geben Sie den Namen der bevorzugten Ausgabesprache an.|  
|[-quiet](quiet.md)|Verhindert, dass der Compiler Code für syntaxbezogene Fehler und Warnungen anzeigt.|  
|[-recurse](recurse.md)|Durchsucht Unterverzeichnisse nach zu kompilierenden Quelldateien.|  
|[-reference](reference.md)|Importiert Metadaten aus einer Assembly.|  
|[/refonly](refonly-compiler-option.md)|Gibt nur eine Referenzassembly aus.|
|[/refout](refout-compiler-option.md)|Gibt den Ausgabepfad einer Referenzassembly an.|
|[-removeintchecks](removeintchecks.md)|Deaktiviert Überprüfungen auf Ganzzahlüberlauf|  
|[-resource](resource.md)|Bettet eine verwaltete Ressource in eine Assembly ein.|  
|[-rootnamespace](rootnamespace.md)|Gibt einen Namespace für alle Typdeklarationen an.|  
|`-ruleset:<file>`|Geben Sie eine Regelsatzdatei an, die bestimmte Diagnosefunktionen deaktiviert.|  
|[-sdkpath](sdkpath.md)|Gibt den Speicherort von „mscorlib.dll“ und „microsoft.visualbasic.dll“ an.|  
|[-subsystemversion](subsystemversion.md)|Gibt die mindestens erforderliche Version des Subsystems an, die die generierte ausführbare Datei verwenden kann.|  
|[-target](target.md)|Gibt das Format der Ausgabedatei an.|  
|[-utf8output](utf8output.md)|Zeigt die Compilerausgabe mit UTF-8-Codierung an.|  
|[-vbruntime](vbruntime.md)|Gibt an, dass der Compiler ohne einen Verweis auf die Visual Basic Runtime Library oder mit einem Verweis auf eine bestimmte Laufzeitbibliothek kompilieren soll.|  
|[-verbose](verbose.md)|Gibt Zusatzinformationen während der Kompilierung aus.|  
|[-warnaserror](warnaserror.md)|Stuft Warnungen zu Fehlern hoch.|  
|[-win32icon](win32icon.md)|Fügt eine ICO-Datei in die Ausgabedatei ein.|  
|[-win32manifest](win32manifest.md)|Identifiziert eine benutzerdefinierte Win32-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei (PE) eines Projekts eingebettet werden soll.|  
|[-win32resource](win32resource.md)|Fügt eine Win32-Ressource in die Ausgabedatei ein.|  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Compileroptionen nach Kategorien sortiert](compiler-options-listed-by-category.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
