---
title: Compileroptionen nach Kategorien sortiert
ms.date: 04/12/2018
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: fbe36f7a-7cfa-4f77-a8d4-2be5958568e3
ms.openlocfilehash: 533d3da2f76854d311262ce97b43f240acab5f7d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408750"
---
# <a name="visual-basic-compiler-options-listed-by-category"></a>Visual Basic-Compileroptionen nach Kategorien sortiert
Die Visual Basic-Befehlszeilencompiler bietet eine Alternative zum Kompilieren von Programmen in der integrierten Entwicklungsumgebung (IDE) von Visual Studio. Es folgt eine Liste der Befehlszeilen-Compileroptionen von Visual Basic (nach Funktionskategorie sortiert).  

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]
  
## <a name="compiler-output"></a>Compilerausgabe  
  
|Option|Zweck|  
|---|---|  
|[-nologo](nologo.md)|Unterdrückt Compilerbannerinformationen.|  
|[-utf8output](utf8output.md)|Zeigt die Compilerausgabe mit UTF-8-Codierung an.|  
|[-verbose](verbose.md)|Gibt Zusatzinformationen während der Kompilierung aus.|  
|`-modulename:<string>`|Geben Sie den Namen des Quellmoduls an|  
|[/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Geben Sie eine Sprache für die Kompilierungsausgabe an.|
  
## <a name="optimization"></a>Optimierung  
  
|Option|Zweck|  
|---|---|  
|[-filealign](filealign.md)|Gibt die Ausrichtung der Abschnitte der Ausgabedatei an.|  
|[-optimize](optimize.md)|Aktiviert/deaktiviert Optimierungen.|  
  
## <a name="output-files"></a>Ausgabedateien  
  
|Option|Zweck|  
|---|---|  
|[-doc](doc.md)|Verarbeitet Dokumentationskommentare zu einer XML-Datei.|  
|[-deterministic](deterministic.md)|Bewirkt, dass der Compiler eine Assembly ausgibt, deren Inhalt im Binärformat über Kompilierungen identisch ist, wenn die Eingaben identisch sind.|
|[-netcf](netcf.md)|Legt den Compiler als Ziel für .NET Compact Framework fest|  
|[-out](out.md)|Gibt eine Ausgabedatei an.|  
|[/refonly](refonly-compiler-option.md)|Gibt nur eine Referenzassembly aus|
|[/refout](refout-compiler-option.md)|Gibt den Namen des Ausgabepfads einer Referenzassembly an|
|[-target](target.md)|Gibt das Format der Ausgabe an.|  
  
## <a name="net-assemblies"></a>.NET-Assemblys  
  
|Option|Zweck|  
|---|---|  
|[-addmodule](addmodule.md)|Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.|  
|[-delaysign](delaysign.md)|Gibt an, ob die Assembly vollständig oder teilweise signiert wird.|  
|[-imports](imports.md)|Importiert einen Namespace aus einer angegebenen Assembly.|  
|[-keycontainer](keycontainer.md)|Gibt einen Schlüsselcontainernamen für ein Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.|  
|[-keyfile](keyfile.md)|Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.|  
|[-libpath](libpath.md)|Gibt den Speicherort der Assemblys an, auf die durch die [-reference](reference.md)-Option verwiesen wird.|  
|[-reference](reference.md)|Importiert Metadaten aus einer Assembly.|  
|[-moduleassemblyname](moduleassemblyname.md)|Gibt den Namen der Assembly an, zu der dieses Modul gehört.|  
|`-analyzer`|Führt die Analysetools aus dieser Assembly aus (Kurzform: -a)|  
|`-additionalfile`|Benennt zusätzliche Dateien, die möglicherweise vom Analyzer verwendet werden, um Fehler oder Warnungen zu erzeugen, sich aber nicht direkt auf die Codegenerierung auswirken.|  
  
## <a name="debuggingerror-checking"></a>Debuggen/Fehlerüberprüfung  
  
|Option|Zweck|  
|---|---|  
|[-bugreport](bugreport.md)|Erstellt eine Datei mit Informationen, die das Melden eines Bugs erleichtern.|  
|[-debug](debug.md)|Erzeugt Debuginformationen.|  
|[-nowarn](nowarn.md)|Unterdrückt die Compilerfunktion zum Generieren von Warnungen.|  
|[-quiet](quiet.md)|Verhindert, dass der Compiler Code für syntaxbezogene Fehler und Warnungen anzeigt.|  
|[-removeintchecks](removeintchecks.md)|Deaktiviert Überprüfungen auf Ganzzahlüberlauf|  
|[-warnaserror](warnaserror.md)|Stuft Warnungen zu Fehlern hoch.|  
|`-ruleset:<file>`|Geben Sie eine Regelsatzdatei an, die bestimmte Diagnosefunktionen deaktiviert.|  
  
## <a name="help"></a>Hilfe  
  
|Option|Zweck|  
|---|---|  
|[-?](help.md)|Zeigt die Compileroptionen an. Dieser Befehl entspricht der Angabe der `-help`-Option. Es findet keine Kompilierung statt.|  
|[-help](help.md)|Zeigt die Compileroptionen an. Dieser Befehl entspricht der Angabe der `-?`-Option. Es findet keine Kompilierung statt.|  
  
## <a name="language"></a>Sprache  
  
|Option|Zweck|  
|---|---|  
|[-langversion](langversion.md)|Sprachversion angeben: 9&#124;9.0&#124;10&#124;10.0&#124;11&#124;11.0.|  
|[-optionexplicit](optionexplicit.md)|Erzwingt explizite Variablendeklaration.|  
|[-optionstrict](optionstrict.md)|Erzwingt strenge Typsemantik.|  
|[-optioncompare](optioncompare.md)|Gibt an, ob Zeichenfolgenvergleiche binär sein oder gebietsschemaspezifische Textsemantik verwenden sollen.|  
|[-optioninfer](optioninfer.md)|Ermöglicht die Verwendung von lokalem Typrückschluss in Variablendeklarationen.|  
  
## <a name="preprocessor"></a>Präprozessor  
  
|Option|Zweck|  
|---|---|  
|[-define](define.md)|Definiert Symbole für bedingte Kompilierung.|  
  
## <a name="resources"></a>Ressourcen  
  
|Option|Zweck|  
|---|---|  
|[-linkresource](linkresource.md)|Erstellt einen Link zu einer verwalteten Ressource.|  
|[-resource](resource.md)|Bettet eine verwaltete Ressource in eine Assembly ein.|  
|[-win32icon](win32icon.md)|Fügt eine ICO-Datei in die Ausgabedatei ein.|  
|[-win32resource](win32resource.md)|Fügt eine Win32-Ressource in die Ausgabedatei ein.|  
  
## <a name="miscellaneous"></a>Verschiedenes  
  
|Option|Zweck|  
|---|---|  
|[@ (Antwortdatei festlegen)](specify-response-file.md)|Legt eine Antwortdatei fest.|  
|[-baseaddress](baseaddress.md)|Gibt die Basisadresse einer DLL an.|  
|[-codepage](codepage.md)|Gibt die für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.|  
|[-errorreport](errorreport.md)|Gibt an, wie interne Compilerfehler vom Visual Basic-Compiler gemeldet werden sollen|  
|[-highentropyva](highentropyva.md)|Informiert den Windows-Kernel, ob eine bestimmte ausführbare Datei ASLR mit hoher Entropie (Address Space Layout Randomization, Zufällige Anordnung des Layouts des Adressraums) unterstützt.|  
|[-main](main.md)|Gibt die Klasse an, die die `Sub Main`-Prozedur enthält, die beim Start verwendet werden soll|  
|[-noconfig](noconfig.md)|Führen Sie die Kompilierung nicht mit Vbc.rsp durch.|  
|[-nostdlib](nostdlib.md)|Bewirkt, dass der Compiler nicht auf die Standardbibliotheken verweist.|  
|[-nowin32manifest](nowin32manifest.md)|Weist den Compiler an, kein Anwendungsmanifest in die ausführbare Datei einzubetten.|  
|[-platform](platform.md)|Gibt die Prozessorplattform an, auf die der Compiler für die Ausgabedatei verweist.|  
|[-recurse](recurse.md)|Durchsucht Unterverzeichnisse nach zu kompilierenden Quelldateien.|  
|[-rootnamespace](rootnamespace.md)|Gibt einen Namespace für alle Typdeklarationen an.|  
|[-sdkpath](sdkpath.md)|Gibt den Speicherort von „mscorlib.dll“ und „microsoft.visualbasic.dll“ an.|  
|[-vbruntime](vbruntime.md)|Gibt an, dass der Compiler ohne einen Verweis auf die Visual Basic Runtime Library oder mit einem Verweis auf eine bestimmte Laufzeitbibliothek kompilieren soll.|  
|[-win32manifest](win32manifest.md)|Identifiziert eine benutzerdefinierte Win32-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei (PE) eines Projekts eingebettet werden soll.|  
|`-parallel[+&#124;-]`|Gibt an, ob parallele Builds (+) verwendet werden sollen.|  
|`-checksumalgorithm:<alg>`|Gibt den Algorithmus zur Berechnung der Quelldateiprüfsumme an, der in der PDB-Datei gespeichert ist.  Unterstützte Werte: SHA-1 (Standard) oder SHA-256. <br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256 oder höher.|  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic Compileroptionen in alphabetischer Reihenfolge](compiler-options-listed-alphabetically.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
