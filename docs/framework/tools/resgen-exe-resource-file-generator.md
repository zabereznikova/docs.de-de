---
title: "Resgen.exe (Resource File Generator) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "resource files, .resources files"
  - "resource files, .resx files"
  - "resx files (resource files)"
  - ".resources files"
  - "files, converting"
  - "Resource File Generator"
  - ".resx files"
  - "Resgen.exe"
  - "resource files, converting"
  - "converting files, Resource File Generator"
  - "binary resources files"
  - "embedding files in runtime binary executable"
ms.assetid: 8ef159de-b660-4bec-9213-c3fbc4d1c6f4
caps.latest.revision: 46
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 46
---
# Resgen.exe (Resource File Generator)
Der Resource File Generator \(Resgen.exe\) konvertiert Textdateien \(TXT\- oder RESTEXT\-Dateien\) und Dateien im XML\-basierten Ressourcenformat \(RESX\-Dateien\) in binäre Common Language Runtime\-Dateien \(RESOURCES\-Dateien\), die in ausführbare Laufzeit\-Binärdateien oder Satellitenassemblys eingebettet werden können. \(Siehe [Erstellen von Ressourcendateien](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md).\)  
  
 Resgen.exe ist ein universelles Hilfsprogramm zur Ressourcenkonvertierung, mit dem folgende Aufgaben ausgeführt werden können:  
  
-   Konvertieren von TXT\- oder RESTEXT\-Dateien in RESOURCES\- oder RESX\-Dateien \(RESTEXT\- und TXT\-Dateien weisen das gleiche Format auf.  Durch die Erweiterung ".restext" können jedoch Textdateien mit Ressourcendefinitionen einfacher identifiziert werden.\)  
  
-   Konvertieren von RESOURCES\-Dateien in Text\- oder RESX\-Dateien  
  
-   Konvertieren von RESX\-Dateien in Text\- oder RESOURCES\-Dateien  
  
-   Extrahieren der Zeichenfolgenressourcen aus einer Assembly in eine RESW\-Datei, die von einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-App verwendet werden kann  
  
-   Erstellen einer stark typisierten Klasse, die Zugriff auf einzelne benannte Ressourcen und die <xref:System.Resources.ResourceManager>\-Instanz bietet  
  
 Für alle Fehler in Resgen.exe lautet der Rückgabewert "‑1".  
  
 Verwenden Sie folgenden Befehl ohne Angabe von Optionen, um die Hilfe, Befehlssyntax und Optionen von Resgen.exe anzuzeigen:  
  
```  
resgen  
```  
  
 Außerdem können Sie den `/?`\-Schalter verwenden:  
  
```  
resgen /?  
```  
  
 Wenn Sie Resgen.exe zum Erstellen binärer RESOURCES\-Dateien nutzen, können Sie einen Sprachcompiler verwenden, um die Binärdateien in ausführbare Assemblys einzubetten. Wahlweise können Sie die Binärdateien mithilfe von [Assembly Linker \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md) in Satellitenassemblys kompilieren.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert.  Zum Ausführen des Tools verwenden Sie die Developer\-Eingabeaufforderung \(oder die Visual Studio\-Eingabeaufforderung in Windows 7\).  Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## Syntax  
  
```  
  
      resgen  [/define:symbol1[,symbol2,...]] [/useSourcePath] filename.extension  | /compile filename.extension... [outputFilename.extension]   
[/r:assembly]   
[/str:lang[,namespace[,class[,file]]] [/publicclass]]   
```  
  
```  
  
resgen filename.extension [outputDirectory]  
```  
  
#### Parameter  
  
|Parameter oder Schalter|Beschreibung|  
|-----------------------------|------------------|  
|`/define:` *symbol1*\[, *symbol2*,...\]|Ab [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] wird bedingte Kompilierung in textbasierten Ressourcendateien \(TXT\- oder RESTEXT\-Dateien\) unterstützt.  Wenn *symbol* einem Symbol entspricht, das innerhalb eines `#ifdef`\-Konstrukts in der Eingabetextdatei enthalten ist, wird die zugehörige Zeichenfolgenressource in die RESOURCES\-Datei einbezogen.  Wenn die Eingabetextdatei eine `#if !`\-Anweisung mit einem Symbol enthält, das nicht durch den `/define`\-Schalter definiert ist, wird die zugehörige Zeichenfolgenressource in die RESOURCES\-Datei einbezogen.<br /><br /> Bei Verwendung mit Nicht\-Textdateien wird `/define` ignoriert.  Bei Symbolen wird die Groß\-\/Kleinschreibung berücksichtigt.<br /><br /> Weitere Informationen zu dieser Option finden Sie weiter unten in diesem Thema unter [Bedingte Kompilierung von Ressourcen](#Conditional).|  
|`useSourcePath`|Gibt an, dass das aktuelle Verzeichnis der Eingabedatei zum Auflösen relativer Dateipfade verwendet werden soll.|  
|`/compile`|Ermöglicht Ihnen die Angabe mehrerer RESX\- oder Textdateien, die von einem einzelnen Massenvorgang in RESOURCES\-Dateien konvertiert werden sollen.  Wenn Sie diese Option nicht festlegen, kann für die Eingabedatei nur ein Argument angegeben werden.  Ausgabedateien werden als "*filename*.resources" benannt.<br /><br /> Diese Option kann nicht mit der `/str:`\-Option verwendet werden.<br /><br /> Weitere Informationen zu dieser Option finden Sie weiter unten in diesem Thema unter [Kompilieren oder Konvertieren mehrerer Dateien](#Multiple).|  
|`/r:` `assembly`|Verweist auf Metadaten aus der angegebenen Assembly.  Wird beim Konvertieren von RESX\-Dateien verwendet und ermöglicht Resgen.exe das Serialisieren oder Deserialisieren von Objektressourcen.  Ähnelt der `/reference:`\-Option oder `/r:`\-Option für den C\#\- und den Visual Basic\-Compiler.|  
|`filename.extension`|Gibt den Namen der zu konvertierenden Eingabedatei an.  Wenn Sie die vor dieser Tabelle aufgeführte erste, längere Befehlszeilensyntax verwenden, muss `extension` einen der folgenden Werte aufweisen:<br /><br /> ".txt" oder ".restext"<br /> Eine Textdatei, die in eine RESOURCES\-Datei oder RESX\-Datei konvertiert werden soll.  Textdateien dürfen nur Zeichenfolgenressourcen enthalten.  Weitere Informationen zum Dateiformat finden Sie im Abschnitt "Ressourcen in Textdateien" unter [Erstellen von Ressourcendateien](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md).<br /><br /> .resx<br /> Eine XML\-basierte Ressourcendatei, die in eine RESOURCES\- oder Textdatei \(TXT\- oder RESTEXT\-Datei\) konvertiert werden soll.<br /><br /> .resources<br /> Eine binäre Ressourcendatei, die in eine RESX\- oder Textdatei \(TXT\- oder RESTEXT\-Datei\) konvertiert werden soll.<br /><br /> Wenn Sie die vor dieser Tabelle aufgeführte zweite, kürzere Befehlszeilensyntax verwenden, muss `extension` einen der folgenden Werte aufweisen:<br /><br /> ".exe" oder ".dll"<br /> Eine .NET Framework\-Assembly \(ausführbare Datei oder Bibliothek\), deren Zeichenfolgenressourcen zwecks Verwendung beim Entwickeln von [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-Apps in eine RESW\-Datei extrahiert werden sollen.|  
|`outputFilename.extension`|Gibt den Namen und den Typ der zu erstellenden Ressourcendatei an.<br /><br /> Dieses Argument ist optional, wenn Sie eine TXT\-, RESTEXT\- oder RESX\-Datei in eine RESOURCES\-Datei konvertieren.  Wenn Sie `outputFilename` nicht angeben, fügt Resgen.exe die Erweiterung ".resources" an den eingegebenen `filename` an und schreibt die Datei in das Verzeichnis, das `filename,extension` enthält.<br /><br /> Das `outputFilename.extension`\-Argument ist erforderlich, wenn eine RESOURCES\-Datei konvertiert werden soll.  Geben Sie einen Dateinamen mit der Erweiterung ".resx" an, wenn Sie eine RESOURCES\-Datei in eine XML\-basierte Ressourcendatei konvertieren.  Geben Sie einen Namen mit der Erweiterung ".txt" oder ".restext" an, wenn Sie eine RESOURCES\-Datei in eine Textdatei konvertieren.  Sie sollten eine RESOURCES\-Datei nur dann in eine TXT\-Datei konvertieren, wenn die RESOURCES\-Datei ausschließlich Zeichenfolgenwerte enthält.|  
|`outputDirectory`|Gibt für [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-Apps das Verzeichnis an, in das eine RESW\-Datei mit den Zeichenfolgenressourcen in `filename.extension` geschrieben werden soll.  `outputDirectory` muss bereits vorhanden sein.|  
|`/str:` `language[,namespace[,classname[,filename]]]`|Erstellt eine stark typisierte Ressourcenklassendatei in der durch die `language` Option angegebenen Programmiersprache.  `language` kann aus einem der folgenden Literale bestehen:<br /><br /> -   Für C\#: `c#`, `cs` oder `csharp`.<br />-   Für Visual Basic: `vb` oder `visualbasic`.<br />-   Für VBScript: `vbs` oder `vbscript`.<br />-   Für C\+\+: `c++`, `mc` oder `cpp`.<br />-   Für JavaScript: `js`, `jscript` oder `javascript`.<br /><br /> Die `namespace`\-Option gibt den Standardnamespace des Projekts an, die `classname`\-Option den Namen der generierten Klasse und die `filename`\-Option den Namen der Klassendatei.<br /><br /> Die `/str:`\-Option lässt nur eine Eingabedatei zu und kann daher nicht mit der `/compile`\-Option verwendet werden.<br /><br /> Wenn `namespace` angegeben wird, `classname` jedoch nicht, wird der Klassenname vom Namen der Ausgabedatei abgeleitet \(zum Beispiel werden Punkte durch Unterstriche ersetzt\).  Daher ist es möglich, dass die stark typisierten Ressourcen nicht ordnungsgemäß funktionieren.  Um dies zu vermeiden, geben Sie sowohl den Klassennamen als auch den Ausgabedateinamen an.<br /><br /> Weitere Informationen zu dieser Option finden Sie weiter unten in diesem Thema unter [Generieren einer stark typisierten Ressourcenklasse](#Strong).|  
|`/publicClass`|Erstellt eine stark typisierte Ressourcenklasse als öffentliche Klasse.  Standardmäßig ist die Ressourcenklasse `internal` in C\# und `Friend` in Visual Basic.<br /><br /> Diese Option wird ignoriert, wenn die Option `/str:` nicht verwendet wird.|  
  
## Resgen.exe und Ressourcendateitypen  
 Für eine erfolgreiche Ressourcenkonvertierung mit Resgen.exe müssen Text\- und RESX\-Dateien das richtige Format aufweisen.  
  
### Textdateien \(".txt" und ".restext"\)  
 Textdateien \(".txt" oder ".restext"\) dürfen ausschließlich Zeichenfolgenressourcen enthalten.  Zeichenfolgenressourcen sind nützlich, wenn Sie eine Anwendung schreiben, für die Zeichenfolgen in mehrere Sprachen übersetzt werden müssen.  Beispielsweise können Menüzeichenfolgen leicht anhand der entsprechenden Zeichenfolgenressource lokalisiert werden.  Resgen.exe liest Textdateien mit Name\-Wert\-Paaren, wobei es sich beim Namen um eine die Ressource beschreibende Zeichenfolge handelt und der Wert die Ressourcenzeichenfolge selbst darstellt.  
  
> [!NOTE]
>  Weitere Informationen zum Format von TXT\- und RESTEXT\-Dateien finden Sie im Abschnitt" Ressourcen in Textdateien" unter [Erstellen von Ressourcendateien](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md).  
  
 Eine Textdatei mit Ressourcen muss in UTF\-8\- oder Unicode \(UTF\-16\)\-Codierung gespeichert werden, es sei denn, sie enthält nur Zeichen aus dem lateinischen Standardalphabet \(U\+007F\).  Beim Verarbeiten einer in ANSI\-Codierung gespeicherten Textdatei werden erweiterte ANSI\-Zeichen von Resgen.exe entfernt.  
  
 Die Textdatei wird von Resgen.exe auf doppelte Ressourcennamen überprüft.  Wenn die Textdatei doppelte Ressourcennamen aufweist, gibt Resgen.exe eine Warnung aus und ignoriert den zweiten Wert.  
  
### RESX\-Dateien  
 Das Format von RESX\-Ressourcendateien besteht aus XML\-Einträgen.  Innerhalb dieser XML\-Einträge können wie in Textdateien Zeichenfolgenressourcen angegeben werden.  Ein wichtiger Vorteil von RESX\-Dateien gegenüber Textdateien ist, dass auch Objekte angegeben oder eingebettet werden können.  Wenn Sie eine RESX\-Datei anzeigen, wird die binäre Form eines eingebetteten Objekts \(z. B. eines Bilds\) dargestellt, sofern diese binären Informationen Teil des Ressourcenmanifests sind.  Wie Textdateien können RESX\-Dateien mit einem Text\-Editor \(z. B. Editor oder Microsoft Word\) geöffnet und der Inhalt eingefügt, analysiert und bearbeitet werden.  Beachten Sie, dass hierfür fundierte Kenntnisse über XML\-Tags und die RESX\-Dateistruktur erforderlich sind.  Weitere Informationen zum RESX\-Dateiformat Sie im Abschnitt "Ressourcen in RESX\-Dateien" unter [Erstellen von Ressourcendateien](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md).  
  
 Zum Erstellen einer RESOURCES\-Datei mit eingebetteten Objekten, die keine Zeichenfolgen darstellen, verwenden Sie entweder Resgen.exe zum Konvertieren einer RESX\-Datei mit enthaltenen Objekten oder fügen die Objektressourcen der Datei direkt über den Code hinzu, indem Sie die Methoden der <xref:System.Resources.ResourceWriter>\-Klasse aufrufen.  
  
 Wenn eine RESX\- oder RESOURCES\-Datei Objekte enthält und mit Resgen.exe in eine Textdatei konvertiert wird, werden alle Zeichenfolgenressourcen ordnungsgemäß konvertiert. Die Datentypen der Objekte, die keine Zeichenfolgen darstellen, werden jedoch ebenfalls als Zeichenfolgen in die Datei geschrieben.  Die eingebetteten Objekte gehen bei der Konvertierung verloren, und von Resgen.exe wird ein Fehler beim Abrufen der Ressourcen gemeldet.  
  
### Konvertieren zwischen Ressourcendateitypen  
 Die Konvertierung zwischen verschiedenen Ressourcendateitypen kann möglicherweise nicht mit Resgen.exe durchgeführt werden, oder bestimmte Ressourceninformationen können, je nach den Quell\- und Zieldateitypen, verloren gehen.  In der folgenden Tabelle finden Sie die Konvertierungstypen, die beim Konvertieren eines Ressourcendateityps in einen anderen erfolgreich ausgeführt werden.  
  
|Konvertieren von|In Textdatei|In RESX\-Datei|In RESW\-Datei|In RESOURCES\-Datei|  
|----------------------|------------------|--------------------|--------------------|-------------------------|  
|Textdatei \(".txt" oder ".restext"\)|\-\-|Keine Probleme|Nicht unterstützt|Keine Probleme|  
|RESX\-Datei|Konvertierungsfehler, wenn die Datei Ressourcen aufweist, die keine Zeichenfolgen sind \(einschließlich Dateilinks\)|\-\-|Nicht unterstützt|Keine Probleme|  
|RESOURCES\-Datei|Konvertierungsfehler, wenn die Datei Ressourcen aufweist, die keine Zeichenfolgen sind \(einschließlich Dateilinks\)|Keine Probleme|Nicht unterstützt|\-\-|  
|EXE\- oder DLL\-Assembly|Nicht unterstützt|Nicht unterstützt|Nur Zeichenfolgenressourcen \(einschließlich Pfadnamen\) werden als Ressourcen erkannt|Nicht unterstützt|  
  
## Ausführen bestimmter Aufgaben mit Resgen.exe  
 Resgen.exe bietet vielfältige Verwendungsmöglichkeiten, z. B. Kompilieren einer text\- oder XML\-basierten Ressourcendatei in eine Binärdatei, Konvertieren zwischen Ressourcendateiformaten und Generieren einer Klasse, die <xref:System.Resources.ResourceManager>\-Funktionen umschließt und Zugriff auf Ressourcen bereitstellt.  In diesem Abschnitt werden die einzelnen Aufgaben ausführlich beschrieben:  
  
-   [Kompilieren von Ressourcen in eine Binärdatei](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Compiling)  
  
-   [Konvertieren zwischen Ressourcendateitypen](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Convert)  
  
-   [Kompilieren oder Konvertieren mehrerer Dateien](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Multiple)  
  
-   [Exportieren von Ressourcen in eine RESW\-Datei](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Exporting)  
  
-   [Bedingte Kompilierung von Ressourcen](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Conditional)  
  
-   [Generieren einer stark typisierten Ressourcenklasse](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Strong)  
  
<a name="Compiling"></a>   
### Kompilieren von Ressourcen in eine Binärdatei  
 Resgen.exe wird am häufigsten zum Kompilieren einer textbasierten Ressourcendatei \(TXT\- oder RESTEXT\-Datei\) oder einer XML\-basierten Ressourcendatei \(RESX\-Datei\) in eine binäre RESOURCES\-Datei verwendet.  Die Ausgabedatei kann dann mit einem Sprachcompiler in eine Hauptassembly oder mit [Assembly Linker \(AL.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md) in eine Satellitenassembly eingebettet werden.  
  
 Die Syntax zum Kompilieren einer Ressourcendatei lautet wie folgt:  
  
```  
resgen inputFilename [outputFilename]   
```  
  
 mit folgenden Parametern:  
  
 `inputFilename`  
 Der Dateiname der zu kompilierenden Ressourcendatei, einschließlich der Erweiterung.  Von Resgen.exe werden nur Dateien mit den Erweiterungen ".txt", ".restext" oder ".resx" kompiliert.  
  
 `outputFilename`  
 Der Name der Ausgabedatei.  Wenn Sie `outputFilename` weglassen, wird von Resgen.exe eine RESOURCES\-Datei mit dem Stammdateinamen von `inputFilename` im gleichen Verzeichnis wie `inputFilename` erstellt.  Wenn `outputFilename` einen Verzeichnispfad aufweist, muss das Verzeichnis vorhanden sein.  
  
 Sie geben einen vollqualifizierten Namespace für die RESOURCES\-Datei an, indem Sie diesen in den Dateinamen einbeziehen und durch einen Punkt vom Stammdateinamen trennen.  Wenn `outputFilename` z. B. `MyCompany.Libraries.Strings.resources` lautet, handelt es sich bei "MyCompany.Libraries" um den Namespace.  
  
 Durch den folgenden Befehl werden die Name\-Wert\-Paare der Datei "Resources.txt" gelesen und eine binäre RESOURCES\-Datei mit dem Namen "Resources.resources" geschrieben.  Da der Name der Ausgabedatei nicht explizit angegeben wird, erhält diese standardmäßig den gleichen Namen wie die Eingabedatei.  
  
```  
resgen Resources.txt   
```  
  
 Durch den folgenden Befehl werden die Name\-Wert\-Paare der Datei "Resources.restext" gelesen und eine binäre Ressourcendatei mit dem Namen "StringResources.resources" geschrieben.  
  
```  
resgen Resources.restext StringResources.resources  
```  
  
 Durch den folgenden Befehl wird die XML\-basierte Eingabedatei "Resources.resx" gelesen und eine binäre RESOURCES\-Datei mit dem Namen "Resources.resources" geschrieben.  
  
```  
resgen Resources.resx Resources.resources  
```  
  
<a name="Convert"></a>   
### Konvertieren zwischen Ressourcendateitypen  
 Neben dem Kompilieren von text\- oder XML\-basierten Ressourcendateien in binäre RESOURCES\-Dateien kann mit Resgen.exe jeder unterstützte Dateityp in einen anderen unterstützten Dateityp konvertiert werden.  Dies ermöglicht das Ausführen folgender Konvertierungen:  
  
-   TXT\- und RESTEXT\-Dateien in RESX\-Dateien.  
  
-   RESX\-Dateien in TXT\- und RESTEXT\-Dateien  
  
-   RESOURCES\-Dateien in TXT\- und RESTEXT\-Dateien  
  
-   RESOURCES\-Dateien in RESX\-Dateien  
  
 Die Syntax ist mit der im vorherigen Abschnitt erläuterten identisch.  
  
 Darüber hinaus können Sie Resgen.exe verwenden, um in eine .NET Framework\-Assembly eingebettete Ressourcen in eine RESW\-Datei für [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-Anwendungen zu konvertieren.  
  
 Durch den folgenden Befehl wird die binäre Ressourcendatei "Resources.resources" gelesen und eine XML\-basierte Ausgabedatei mit dem Namen "Resources.resx" geschrieben.  
  
```  
resgen Resources.resources Resources.resx  
```  
  
 Durch den folgenden Befehl wird die textbasierte Ressourcendatei "StringResources.txt" gelesen und eine XML\-basierte Ressourcendatei mit dem Namen "LibraryResources.resx" geschrieben.  Eine RESX\-Datei kann nicht nur Zeichenfolgenressourcen enthalten, sondern auch zum Speichern anderer Ressourcentypen verwendet werden.  
  
```  
resgen StringResources.txt LibraryResources.resx  
```  
  
 Durch die folgenden beiden Befehle werden nach dem Lesen der XML\-basierten Ressourcendatei "Resources.resx" binäre Textdateien mit den Namen "Resources.txt" und "Resources.restext" geschrieben.  Hinweis: Wenn die RESX\-Datei eingebettete Objekte aufweist, werden diese nicht fehlerfrei in die Textdateien konvertiert.  
  
```  
resgen Resources.resx Resources.txt  
resgen Resources.resx Resources.restext  
```  
  
<a name="Multiple"></a>   
### Kompilieren oder Konvertieren mehrerer Dateien  
 Sie können den `/compile`\-Schalter verwenden, um eine Liste mit Ressourcendateien in einem einzelnen Vorgang von einem Format in ein anderes zu konvertieren.  Die Syntax lautet:  
  
```  
resgen /compile filename.extension [filename.extension...]  
```  
  
 Durch den folgenden Befehl werden drei Dateien, "StringResources.txt", "TableResources.resw" und "ImageResources.resw", in getrennte RESOURCES\-Dateien mit den Namen "StringResources.resources", "TableResources.resources" und "ImageResources.resources" kompiliert.  
  
```  
resgen /compile StringResources.txt TableResources.resx ImageResources.resx  
```  
  
<a name="Exporting"></a>   
### Exportieren von Ressourcen in eine RESW\-Datei  
 Wenn Sie eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-App entwickeln, können Sie Ressourcen aus einer vorhandenen Desktop\-App verwenden.  Von den beiden Anwendungsarten werden jedoch unterschiedliche Dateiformate unterstützt.  Bei Desktop\-Anwendungen werden Ressourcen in Textdaten \(".txt" oder ".restext"\) oder RESX\-Dateien in binäre RESOURCES\-Dateien kompiliert.  Bei [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-Apps werden RESW\-Dateien in binäre Indexdateien der Paketressource \(PRI\-Dateien\) kompiliert.  Mithilfe von Resgen.exe können Sie diese Schwierigkeit umgehen, indem Sie Ressourcen aus einer ausführbaren Datei oder einer Satellitenassembly extrahieren und diese in RESW\-Dateien schreiben, die beim Entwickeln einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-App verwendet werden können.  
  
> [!IMPORTANT]
>  Sämtliche zum Einbinden von Ressourcen aus einer portablen Bibliothek in eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-App erforderliche Konvertierungen werden von Visual Studio automatisch ausgeführt.  Die Verwendung von Resgen.exe zum direkten Konvertieren der Ressourcen einer Assembly in das RESW\-Dateiformat ist nur für Entwickler von Interesse, die eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-App außerhalb von Visual Studio erstellen möchten.  
  
 Die Syntax zum Generieren von RESW\-Dateien aus einer Assembly lautet:  
  
```  
resgen filename.extension  [outputDirectory]  
```  
  
 mit folgenden Parametern:  
  
 `filename.extension`  
 Der Name einer .NET Framework\-Assembly \(eine ausführbare Datei oder DLL\-Datei\).  Bei einer Datei ohne Ressourcen werden von Resgen.exe keine Dateien erstellt.  
  
 `outputDirectory`  
 Das vorhandene Verzeichnis zum Schreiben der RESW\-Dateien.  Wenn `outputDirectory` weggelassen wird, werden RESW\-Dateien in das aktuelle Verzeichnis geschrieben.  Für jede RESOURCES\-Datei in der Assembly wird von Resgen.exe eine RESW\-Datei erstellt.  Der Stammdateiname der RESW\-Datei stimmt mit dem Stammnamen der RESOURCES\-Datei überein.  
  
 Durch den folgenden Befehl wird für jede in MyApp.exe eingebettete RESOURCES\-Datei im Verzeichnis "Win8Resources" eine RESW\-Datei erstellt:  
  
```  
resgen MyApp.exe Win8Resources  
```  
  
<a name="Conditional"></a>   
### Bedingte Kompilierung von Ressourcen  
 Ab [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] wird von Resgen.exe die bedingte Kompilierung von Zeichenfolgenressourcen in Textdateien \(".txt" und ".restext"\) unterstütz.  Hierdurch kann eine einzige textbasierte Ressourcendatei in mehreren Buildkonfigurationen verwendet werden.  
  
 Wenn ein Symbol definiert ist, verwenden Sie in einer TXT\- oder RESTEXT\-Datei das `#ifdef`…`#endif`\-Konstrukt, um eine Ressource in die binäre RESOURCES\-Datei einzubeziehen. Verwenden Sie das `#if !`...  `#endif`\-Konstrukt, um eine Ressource ohne Definition eines Symbols einzubeziehen.  Zur Kompilierzeit definieren Sie anschließend Symbole mithilfe der `/define:`\-Option, gefolgt von einer durch Kommas getrennten Liste von Symbolen.  Beim Vergleich wird die Klein\-\/Großschreibung berücksichtigt. Die Groß\-\/Kleinschreibung der durch `/define` definierten Symbole muss derjenigen in den zu kompilierenden Textdateien entsprechen.  
  
 Beispielsweise enthält die folgende Datei "UIResources.restext" eine Zeichenfolgenressource mit dem Namen `AppTitle`, die abhängig von der Definition der Attribute `PRODUCTION`, `CONSULT` oder `RETAIL` einen von drei Werten annehmen kann.  
  
```  
  
#ifdef PRODUCTION  
AppTitle=My Software Company Project Manager   
#endif  
#ifdef CONSULT  
AppTitle=My Consulting Company Project Manager  
#endif  
#ifdef RETAIL  
AppTitle=My Retail Store Project Manager  
#endif  
FileMenuName=File  
  
```  
  
 Anschließend kann die Datei mit folgendem Befehl in eine binäre RESOURCES\-Datei kompiliert werden:  
  
```  
resgen /define:CONSULT UIResources.restext  
```  
  
 Hierdurch wird eine RESOURCES\-Datei mit zwei Zeichenfolgenressourcen erstellt.  Der Wert der `AppTitle`\-Ressource lautet "My Consulting Company Project Manager".  
  
<a name="Strong"></a>   
### Generieren einer stark typisierten Ressourcenklasse  
 Von Resgen.exe werden stark typisierte Ressourcen unterstützt, die durch das Erstellen von Klassen mit einer Reihe statischer schreibgeschützter Eigenschaften den Zugriff auf Ressourcen kapseln.  Dies stellt eine Alternative zum direkten Aufrufen der Methoden der <xref:System.Resources.ResourceManager>\-Klasse zwecks Ressourcenabruf dar.  Die Unterstützung von stark typisierten Ressourcen kann in Resgen.exe über die `/str`\-Option aktiviert werden, die die Funktionalität der <xref:System.Resources.Tools.StronglyTypedResourceBuilder>\-Klasse umschließt.  Wenn Sie die `/str`\-Option angeben, wird von Resgen.exe eine Klasse mit stark typisierten Eigenschaften ausgegeben, die mit den Ressourcen übereinstimmen, auf die der Eingabeparameter verweist.  Diese Klasse ermöglicht den stark typisierten, schreibgeschützten Zugriff auf die in der verarbeiteten Datei verfügbaren Ressourcen.  
  
 Die Syntax zum Erstellen einer stark typisierten Ressource lautet:  
  
```  
resgen inputFilename [outputFilename] /str:language[,namespace,[classname[,filename]]] [/publicClass]  
```  
  
 Parameter und Schalter:  
  
 `inputFilename`  
 Der Dateiname der Ressourcendatei, einschließlich der Erweiterung, für die eine Ressourcenklasse mit starker Typisierung generiert werden soll.  Bei der Datei kann es sich um eine textbasierte, XML\-basierte oder binäre RESOURCES\-Datei handeln, die eine der Erweiterungen ".txt", ".restext", ".resw "oder" .resources" aufweisen kann.  
  
 `outputFilename`  
 Der Name der Ausgabedatei.  Wenn `outputFilename` einen Verzeichnispfad aufweist, muss das Verzeichnis vorhanden sein.  Wenn Sie `outputFilename` weglassen, wird von Resgen.exe eine RESOURCES\-Datei mit dem Stammdateinamen von `inputFilename` im gleichen Verzeichnis wie `inputFilename` erstellt.  
  
 `outputFilename` kann eine textbasierte, XML\-basierte oder binäre RESOURCES\-Datei sein.  Wenn sich die Dateierweiterungen von `outputFilename` und `inputFilename` unterscheiden, werden die Dateien von Resgen.exe konvertiert.  
  
 Wenn es sich bei der `inputFilename` um eine RESOURCES\-Datei handelt, wird diese von Resgen.exe kopiert, sofern die `outputFilename` ebenfalls eine RESOURCES\-Datei ist.  Wenn `outputFilename` weggelassen wird, überschreibt Resgen.exe `inputFilename` mit einer identischen RESOURCES\-Datei.  
  
 *language*  
 Die Sprache, die beim Generieren von Quellcode für die Ressourcenklasse mit starker Typisierung verwendet werden soll.  Mögliche Werte sind `cs`, `C#` und `csharp` für C\#\-Code, `vb` und `visualbasic` für Visual Basic\-Code, `vbs` und `vbscript` für VBScript\-Code sowie `c++`, `mc` und `cpp` für C\+\+\-Code.  
  
 *namespace*  
 Der Namespace der Ressourcenklasse mit starker Typisierung.  Die RESOURCES\-Datei und die Ressourcenklasse sollten denselben Namespace aufweisen.  Informationen zum Angeben des Namespace in `outputFilename` finden Sie unter [Kompilieren von Ressourcen in eine Binärdatei](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Compiling).  Wenn *namespace* weggelassen wird, befindet die Ressourcenklasse sich nicht in einem Namespace.  
  
 *classname*  
 Der Name der stark typisierten Ressourcenklasse.  Dieser sollte dem Stammnamen der RESOURCES\-Datei entsprechen.  Wenn von Resgen.exe z. B. eine RESOURCES\-Datei mit dem Namen "MyCompany.Libraries.Strings.resources" generiert wird, lautet der Name der Ressourcenklasse mit starker Typisierung "Strings".  Wenn der *classname* weggelassen wird, wird die generierte Klasse vom Stammnamen der `outputFilename` abgeleitet.  Wenn der `outputFilename` weggelassen wird, wird die generierte Klasse vom Stammnamen der `inputFilename` abgeleitet.  
  
 Ein *classname* darf keine ungültigen Zeichen aufweisen, z. B. eingebettete Leerzeichen.  Wenn in *classname* Leerzeichen eingebettet sind oder *classname* standardmäßig aus *inputFilename* generiert wird, und *inputFilename* eingebettete Leerzeichen aufweist, ersetzt Resgen.exe alle ungültigen Zeichen durch Unterstriche \(\_\).  
  
 *filename*  
 Der Name der Klassendatei.  
  
 `/publicclass`  
 Macht die Ressourcenklasse mit starker Typisierung anstatt `internal` \(in C\#\) oder `Friend` \(in Visual Basic\) öffentlich.  Dies ermöglicht den Zugriff auf die Ressourcen von außerhalb der Assembly, in der sie eingebettet sind.  
  
> [!IMPORTANT]
>  Beim Erstellen einer Ressourcenklasse mit starker Typisierung muss der Name der RESOURCES\-Datei mit dem Namespace\- und Klassennamen des generierten Codes übereinstimmen.  In Resgen.exe können jedoch Optionen angegeben werden, durch die eine RESOURCES\-Datei mit inkompatiblem Namen erstellt wird.  Um dieses Verhalten zu umgehen, benennen Sie die Ausgabedatei um, nachdem sie generiert wurde.  
  
 Die Ressourcenklasse mit starker Typisierung verfügt über die folgenden Member:  
  
-   Ein parameterloser Konstruktor zum Instanziieren der Ressourcenklasse mit starker Typisierung.  
  
-   Eine `static`\-Eigenschaft \(C\#\) oder `Shared`\-Eigenschaft \(Visual Basic\) und eine schreibgeschützte `ResourceManager`\-Eigenschaft, von der die <xref:System.Resources.ResourceManager>\-Instanz zum Verwalten der Ressource mit starker Typisierung zurückgegeben wird.  
  
-   Eine statische `Culture`\-Eigenschaft zum Festlegen der Kultur für das Abrufen von Ressourcen.  In der Standardeinstellung lautet deren Wert `null`, sodass die aktuelle Benutzeroberflächenkultur verwendet wird.  
  
-   Ein `static`\-Eigenschaft \(C\#\) oder `Shared`\-Eigenschaft \(Visual Basic\) und eine schreibgeschützte Eigenschaft für jede Ressource in der RESOURCES\-Datei.  Der Eigenschaftsname stellt den Namen der Ressource dar.  
  
 Durch den folgenden Befehl wird beispielsweise eine Ressourcendatei mit dem Namen "StringResources.txt" in "StringResources.resources" kompiliert und eine `StringResources`\-Klasse in der Visual Basic\-Quellcodedatei "StringResources.vb" generiert, die für den Zugriff auf den Ressourcen\-Manager verwendet werden kann.  
  
```  
resgen StringResources.txt /str:vb,,StringResources   
```  
  
## Siehe auch  
 [Tools](../../../docs/framework/tools/index.md)   
 [Ressourcen in Desktop\-Apps](../../../docs/framework/resources/index.md)   
 [Erstellen von Ressourcendateien](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)   
 [Al.exe \(Assembly Linker\-Tool\)](../../../docs/framework/tools/al-exe-assembly-linker.md)   
 [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md)