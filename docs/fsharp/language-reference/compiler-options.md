---
title: Compileroptionen (F#)
description: Verwenden Sie F#-Compilerbefehlszeilenoptionen, um die Kompilierung von der F#-apps und Bibliotheken zu steuern.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c797cf0b-5953-4053-8626-0558e9eaf10f
ms.openlocfilehash: 4bc9861f489eb068ca58656ab4ee9d43e8d212d5
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2017
---
# <a name="compiler-options"></a>Compileroptionen

In diesem Thema werden Compilerbefehlszeilenoptionen für den F#-Compiler fsc.exe beschrieben. Die Kompilierungsumgebung kann auch durch Festlegen der Projekteigenschaften gesteuert werden.


## <a name="compiler-options-listed-alphabetically"></a>Compileroptionen alphabetisch sortiert
In der folgenden Tabelle werden Compileroptionen alphabetisch aufgeführt. Einige der F#-Compileroptionen ähneln den C#-Compileroptionen. Wenn dies der Fall ist, wird ein Link zum Thema für die C#-Compileroptionen zur Verfügung gestellt.



|Compileroptionen|Beschreibung|
|---------------|-----------|
|**– ein ***&lt;Ausgabedateiname&gt;**|Generiert eine Bibliothek und gibt ihren Dateinamen an. Diese Option ist die Kurzform der **--Target: Library ***&lt;Filename&gt;**.|
|**--Baseaddress:&lt;Zeichenfolge&gt;**|Gibt die Basisadresse der zu erstellenden Bibliothek an.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; BaseAddress-Element &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/2fdbz5xd.aspx).|
|**--Codepage:&lt;Int&gt;**|Gibt die zum Lesen von Quelldateien verwendete Codepage an.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; Codepage &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/w0kyekyh.aspx).|
|**--consolecolors**|Gibt an, dass Fehler und Warnungen farbkodierten Text in der Konsole verwenden.|
|**--Crossoptimize**[**+**&#124; **-**]|Aktiviert oder deaktiviert modulübergreifende Optimierungen.|
|**-Delaysign**[**+**&#124; **-**]|Signiert das Assembly verzögert nur mit dem öffentlichen Teil des Schlüssels für einen starken Namen.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; Delaysign &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/ta1sxwy8.aspx).|
|**--überprüft**[**+**&#124; **-**]|Aktiviert oder deaktiviert die Generierung von Überlaufprüfungen.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; überprüft &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/h25wtyxf.aspx).|
|**--Debuggen**[**+**&#124; **-**]<br /><br />**-g**[**+**&#124; **-**]<br /><br />**--Debuggen**: [**vollständige**&#124; **"pdbonly"**]<br /><br />**-g:** [**vollständige**&#124; **"pdbonly"**]|Aktiviert oder deaktiviert die Generierung der Debuginformationen, oder gibt den Typ der zu generierenden Debuginformationen an. Der Standardwert ist full. Dieser lässt das Anhängen an ein in Ausführung befindliches Programm zu. Wählen Sie **"pdbonly"** abzurufenden beschränkte Debuginformationen in einer Pdb (Program Database-)-Datei gespeichert.<br /><br />Entsprechung der C#-Compileroption mit demselben Namen. Weitere Informationen finden Sie unter<br /><br />[&#47; Debug &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/8cw0bt21.aspx).|
|**--definieren:&lt;Zeichenfolge&gt;**<br /><br />**-d:&lt;Zeichenfolge&gt;**|Definiert ein bei der bedingten Kompilierung zu verwendendes Symbol.|
|**--deterministisch**[**+**&#124; **-**]|Erzeugen Sie eine deterministische Assembly (einschließlich Modul Versions-GUID und Timestamp).  Dies kann mit Versionsnummern Platzhalter verwendet werden und unterstützt nur eingebettete und portable debugging-Typen|
|**– Doc:&lt;Xmldoc-Dateiname&gt;**|Weist den Compiler an, in der angegebenen Datei XML-Dokumentationskommentare zu generieren. Weitere Informationen finden Sie unter [XML-Dokumentation](xml-documentation.md).<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; Doc &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/3260k4x7.aspx).|
|**--fullpaths**|Weist den Compiler an, vollqualifizierte Pfade zu generieren.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; Fullpaths &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/d315xc66.aspx).|
|**– Hilfe**<br /><br />**-?**|Zeigt Verwendungsinformationen an, einschließlich einer kurzen Beschreibung aller Compileroptionen.|
|**-Highentropyva**[**+**&#124; **-**]|Aktivieren oder deaktivieren Sie Address Space Layout Randomization (ASLR) mit hoher Entropie, eine verbesserte Sicherheitsfunktion. Das Betriebssystem legt die Speicherorte im Speicher, in denen Infrastruktur für Anwendungen (wie dem Stapel und den Heap) geladen wird, zufällig fest. Wenn Sie diese Option aktivieren, können die Betriebssysteme diese Zufallszuteilung verwenden, um den vollständigen 64-Bit-Adressbereich auf einem 64-Bit-Computer zu verwenden.|
|**-Keycontainer:&lt;Zeichenfolge&gt;**|Gibt einen Schlüsselcontainer mit starkem Namen an.|
|**--Keyfile:&lt;Dateiname&gt;**|Gibt den Namen einer Datei mit öffentlichem Schlüssel zum Signieren der generierten Assembly an.|
|**--Lib:&lt;Ordner-Name&gt;**<br /><br />**-I:&lt;Ordner-Name&gt;**|Gibt ein Verzeichnis an, in dem Assemblys gesucht werden sollen, auf die verwiesen wird.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; Lib &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/s5bac5fx.aspx).|
|**--Linkresource**:**&lt;Resource-Info&gt;**|Verknüpft eine angegebene Ressource mit der Assembly. Das Format von Resource-Info ist *Filename*[,*Namen*[,*öffentlichen*&#124; *private*]]<br /><br />Verknüpfen einer einzelnen Ressource mit dieser Option ist eine Alternative zum Einbetten einer gesamten Ressourcendatei mit der **--Ressource** Option.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; Linkresource &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/xawyf94k.aspx).|
|**--mlcompatibility**|Ignoriert Warnungen, die bei der Verwendung von Funktionen angezeigt werden, die für Kompatibilität mit anderen ML-Versionen konzipiert sind.|
|**--noframework**|Deaktiviert den Standardverweis auf die .NET Framework-Assembly.|
|**--nointerfacedata**|Weist den Compiler an, die Ressource wegzulassen, die normalerweise einer Assembly hinzugefügt wird, die F#-spezifische Metadaten enthält.|
|**-nologo**|Zeigt beim Starten des Compilers nicht den Bannertext an.|
|**--nooptimizationdata**|Weist den Compiler an, nur grundlegende Optimierungsoptionen zum Implementieren von Inlinekonstrukten einzuschließen. Dies verhindert zwar modulübergreifende Inlinekonstrukte, verbessert aber die Binärkompatibilität.|
|**--nowin32manifest**|Weist den Compiler an, das Standard-Win32-Manifest auszulassen.|
|**--Nowarn:&lt;Int-Liste&gt;**|Deaktiviert bestimmte, nach Nummern aufgeführte Warnungen. Trennen Sie die einzelnen Warnungsnummern durch ein Komma. Sie können die Warnungsnummer für eine Warnung aus der Kompilierungsausgabe ermitteln.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; Nowarn &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/7f28x9z3.aspx).|
|**– Optimieren**[**+**&#124; **-** ]**[&lt;Zeichenfolgenliste&gt;]**<br /><br />**-O [+ &#124;-] [&lt;Zeichenfolgenliste&gt;]**|Aktiviert oder deaktiviert Optimierungen. Einige Optimierungsoptionen können selektiv aktiviert oder deaktiviert werden, indem sie aufgeführt werden. Dies sind: **Nojitoptimize**, **Nojittracking**, **Nolocaloptimize**, **Nocrossoptimize**, **Notailcalls**.|
|**--out:&lt;Ausgabedateiname&gt;**<br /><br />**-o:&lt;Ausgabedateiname&gt;**|Gibt den Namen der kompilierten Assembly oder des kompilierten Moduls an.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; Out &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/bw3t50f3.aspx).|
|**--Pdb:&lt;Pdb-Dateinamen&gt;**|Benennt die PDB-(Program Database-)Ausgabedebugdatei. Diese Option ist nur gültig, wenn **--Debuggen** ebenfalls aktiviert.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; Pdb &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/ms228625.aspx).|
|**--Plattform:&lt;Plattformname&gt;**|Gibt an, dass der generierte Code nur auf den angegebenen Plattformen laufen (**X86**, **Itanium**, oder **X64**), oder wenn der Plattformname **"anycpu"**ausgewählt wird, gibt an, dass der generierte Code auf jeder Plattform ausgeführt werden kann.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; Plattform &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/zekwfyz4.aspx).|
|**--Angebote-Debug**|Gibt an, dass zusätzliche Debuginformationen für Ausdrücke ausgegeben werden, die von F#-Quotation-Literalen und reflektierten Definitionen abgeleitet werden. Die Debuginformationen werden zu den benutzerdefinierten Attributen eines F#-Ausdrucksbaumstrukturknotens hinzugefügt. Finden Sie unter [Codezitate](code-quotations.md) und [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**– Referenz:&lt;Assembly-Dateiname&gt;**<br /><br />**R -** &lt; **Assembly-Dateiname&gt;**|Macht Code aus einer F#- oder .NET Framework-Assembly für den Code verfügbar, der kompiliert wird.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; Referenz &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/yabyz3h4.aspx).|
|**--Ressource:&lt;Ressourcen-Dateiname&gt;**|Bettet eine verwaltete Ressourcendatei in die generierte Assembly ein.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; &#40; Ressource C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/c0tyye07.aspx).|
|**--Sig**:&lt;**Signatur-Dateiname&gt;**|Generiert eine Signaturdatei auf Grundlage der generierten Assembly. Weitere Informationen zu Signaturdateien, finden Sie unter [Signaturen](signatures.md).|
|**--simpleresolution**|Gibt an, dass Assemblyverweise mit verzeichnisbasierten Mono-Regeln aufgelöst werden sollen, und nicht mit der MSBuild-Auflösung. Sofern nicht Mono verwendet wird, wird standardmäßig die MSBuild-Auflösung verwendet.|
|**– eigenständige**|Gibt an, dass eine Assembly erstellt wird, die alle ihre Abhängigkeiten enthält, damit sie eigenständig ausgeführt wird, ohne dass Bedarf für zusätzliche Assemblys, wie die F#-Bibliothek, besteht.|
|**--Staticlink:&lt;Assemblyname**&gt;|Verknüpft statistisch die angegebene Assembly und alle DLLs, auf die verwiesen wird und die von dieser Assembly abhängen. Verwenden Sie den Assemblynamen, nicht den DLL-Namen.|
|**--subsystemversion**|Gibt die Version des Subsystems des Betriebssystems an, das von der generierten ausführbaren Datei verwendet wird. Verwenden Sie 6.02 für Windows 8.1, 6.01 für Windows 7 und 6.00 für Windows Vista. Diese Option gilt nur für ausführbare Dateien, nicht für DLLs, und kann nur dann verwendet werden, wenn die Anwendung von bestimmten Sicherheitsfunktionen abhängt, die nur in bestimmten Betriebssystemversionen verfügbar sind. Wenn diese Option verwendet wird und ein Benutzer versucht, die Anwendung auf einer niedrigeren Version des Betriebssystems auszuführen, wird eine Fehlermeldung angezeigt.|
|**--Tailcalls**[**+**&#124; **-**]|Aktiviert oder deaktiviert die Verwendung der Tail-IL-Anweisung, die die Wiederverwendung des Stapelrahmens für endrekursive Funktionen verursacht. Diese Option ist standardmäßig aktiviert.|
|**--Ziel**: [**Exe** &#124; **Winexe** &#124; **Bibliothek** &#124; **Modul** ]  **&lt;Ausgabedateiname&gt;**|Gibt den Typ und Dateinamen des generierten kompilierten Codes an.<ul><li>**EXE-Datei** bedeutet, dass eine Konsolenanwendung.<br /></li><li>**Winexe** bedeutet, dass eine Windows-Anwendung von der Konsolenanwendung unterscheidet sich insofern, dass keine standardmäßigen Eingabe-/Ausgabestreams (Stdin, Stdout und Stderr) definiert sind.<br /></li><li>**Bibliothek** ist eine Assembly ohne Einstiegspunkt.<br /></li><li>**Modul** ist ein .NET Framework-Modul (NETMODULE-Dateien), die später in eine Assembly mit anderen Modulen kombiniert werden können.<br /></li><ul/>Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; Ziel &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/6h25dztx.aspx).|
|**--Zeiten**|Zeigt Zeitinformationen für die Kompilierung an.|
|**--utf8output**|Aktiviert das Drucken der Compilerausgabe mit UTF-8-Codierung.|
|**– Warnung:&lt;Warnstufe&gt;**|Legt eine Warnstufe (0 bis 5) fest. Der Standardwert ist 3. Jeder Warnung wird auf Grundlage ihres Schweregrads eine Stufe zugewiesen. Bei Stufe 5 werden mehr Warnungen (jedoch mit geringerem Schweregrad) als bei Stufe 1 angezeigt.<br /><br />Warnungen der Stufe 5 sind: 21 (rekursive Verwendung zur Laufzeit aktiviert), 22 (**können Rec** außerhalb der Reihenfolge ausgewertet), 45 (vollständige Abstraktion) und 52 (tiefe Kopie). Alle anderen Warnungen sind Stufe 2.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; warn &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/13b90fz7.aspx).|
|**--Warnon:&lt;Int-Liste&gt;**|Aktivieren Sie bestimmte Warnungen, die standardmäßig oder durch eine andere Befehlszeilenoption deaktiviert sind. In F# 3.0 ist nur die Warnung 1182 (nicht verwendete Variablen) standardmäßig deaktiviert.|
|**--Warnaserror**[**+**&#124; **-** ] [**&lt;Int-List&gt;**]|Aktiviert oder deaktiviert die Option zum Ausgeben von Warnungen als Fehler. Sie können bestimmte Warnungsnummern angeben, die deaktiviert oder aktiviert werden sollen. Optionen, die später in der Befehlszeile stehen, überschreiben Optionen, die früher in der Befehlszeile stehen. Geben Sie beispielsweise Warnungen angeben möchten, die nicht als Fehler gemeldet werden sollen, **--Warnaserror +--Warnaserror-:&lt;Int-List&gt;**.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; Warnaserror &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/406xhdz3.aspx).|
|**--Win32manifest:manifest-Dateiname**|Fügt eine Win32-Manifestdatei zur Kompilierung hinzu. Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; win32manifest &#40; C &#35; Compileroptionen &#41; ](https://msdn.microsoft.com/library/bb545961.aspx).|
|**--Win32res:resource-Dateiname**|Fügt eine Win32-Ressourcendatei zur Kompilierung hinzu.<br /><br />Diese Compileroption entspricht der C#-Compileroption gleichen Namens. Weitere Informationen finden Sie unter [&#47; win32res (&#40; C & #35); Compileroptionen &#41; ](https://msdn.microsoft.com/library/8f2f5x2e.aspx).|

## <a name="related-topics"></a>Verwandte Themen


|Titel|Beschreibung|
|-----|-----------|
|[F# Interactive-Optionen](../tutorials/fsharp-interactive/fsharp-interactive-options.md)|Beschreibt vom F#-Interpreter fsi.exe unterstützte Befehlszeilenoptionen.|
|[Projekteigenschaftenverweise](/visualstudio/ide/reference/project-properties-reference)|Beschreibt die Benutzeroberfläche für Projekte, einschließlich Projekteigenschaftenseiten, die Buildoptionen bereitstellen.|
