---
title: "Gewusst wie: Lokalisieren einer Anwendung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anwendungen, Lokalisieren"
  - "Lokalisierung, Anwendungen"
  - "LocBaml-Tool"
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
caps.latest.revision: 37
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Gewusst wie: Lokalisieren einer Anwendung
In diesem Lernprogramm wird erläutert, wie eine lokalisierte Anwendung mit dem LocBaml\-Tool erstellt wird.  
  
> [!NOTE]
>  Das LocBaml\-Tool ist keine einsatzfertige Anwendung.  Es wird als Beispiel präsentiert, das einen Teil der Lokalisierungs\-APIs verwendet und veranschaulicht, wie Sie ein Lokalisierungstool schreiben können.  
>   
>    
  
<a name="Introduction"></a>   
## Übersicht  
 Diese Diskussion bietet einen schrittweisen Ansatz zum Lokalisieren einer Anwendung.  Zuerst bereiten Sie Ihre Anwendung so vor, dass der zu übersetzende Text extrahiert werden kann.  Nachdem der Text übersetzt wurde, führen Sie den übersetzten Text mit einer neuen Kopie der ursprünglichen Anwendung zusammen.  
  
<a name="Requirements"></a>   
## Anforderungen  
 Im Verlauf dieser Diskussion verwenden Sie [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)], ein Compiler, der über die Befehlszeile ausgeführt wird.  
  
 Darüber hinaus werden Sie aufgefordert, eine Projektdatei zu verwenden.  Anweisungen zur Verwendung von [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] und Projektdateien finden Sie unter [Erstellen und Bereitstellen](../../../../docs/framework/wpf/app-development/building-and-deploying-wpf-applications.md).  
  
 Alle Beispiele in dieser Diskussion verwenden als Kultur US\-amerikanisches Englisch \(en\-US, Englisch\-US\).  Dies ermöglicht es Ihnen, die Beispielschritte durchzuarbeiten, ohne eine andere Sprache installieren zu müssen.  
  
<a name="create_sample_app"></a>   
## Erstellen einer Beispielanwendung  
 In diesem Schritt bereiten Sie Ihre Anwendung für die Lokalisierung vor.  In den [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Beispielen wird die Beispielanwendung HelloApp bereitgestellt, die für die Codebeispiele in dieser Diskussion verwendet wird.  Wenn Sie dieses Beispiel verwenden möchten, laden Sie die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Dateien aus [Beispiel für LocBaml\-Tool](http://go.microsoft.com/fwlink/?LinkID=160016) herunter.  
  
1.  Entwickeln Sie Ihre Anwendung bis zu dem Punkt, an dem Sie die Lokalisierung starten möchten.  
  
2.  Geben Sie die Entwicklungssprache in der Projektdatei so an, dass [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] eine Hauptassembly und eine Satellitenassembly \(eine Datei mit der Erweiterung ".resources.dll"\) generiert, die die neutralen Sprachressourcen enthält.  Die Projektdatei im HelloApp\-Beispiel ist "HelloApp.csproj".  In dieser Datei finden Sie die Entwicklungssprache wie folgt gekennzeichnet:  
  
     `<UICulture>en-US</UICulture>`  
  
3.  Fügen Sie den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Dateien UIDs hinzu.  UIDs werden verwendet, um Änderungen an Dateien nachzuverfolgen und die Elemente zu identifizieren, die übersetzt werden müssen.  Um den Dateien UIDs hinzuzufügen, führen Sie **updateuid** für die Projektdatei aus:  
  
     **msbuild \/t:updateuid helloapp.csproj**  
  
     Um sicherzustellen, dass keine UIDs fehlen bzw. doppelt vorhanden sind, führen Sie **checkuid** aus:  
  
     **msbuild \/t:checkuid helloapp.csproj**  
  
     Nach dem Ausführen von **updateuid** sollten Ihre Dateien UIDs enthalten.  Beispielsweise sollten Sie in der Datei "Pane1.xaml" von HelloApp Folgendes finden:  
  
     `<StackPanel x:Uid="StackPanel_1">`  
  
     `<TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>`  
  
     `<TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>`  
  
     `</StackPanel>`  
  
<a name="create_dll"></a>   
## Erstellen der Satellitenassembly mit den neutralen Sprachressourcen  
 Nachdem die Anwendung so konfiguriert ist, dass eine Satellitenassembly mit den neutralen Sprachressourcen generiert wird, erstellen Sie die Anwendung.  Auf diese Weise werden die Hauptassembly der Anwendung und die Satellitenassembly mit den neutralen Sprachressourcen generiert, die LocBaml für die Lokalisierung benötigt.  So erstellen Sie die Anwendung:  
  
1.  Kompilieren Sie HelloApp, damit eine [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)] erstellt wird:  
  
     **msbuild helloapp.csproj**  
  
2.  Die neu erstellte Hauptanwendungsassembly, "HelloApp.exe", wird im folgenden Ordner erstellt:  
  
     `C:\HelloApp\Bin\Debug\`  
  
3.  Die neu erstellte Satellitenassembly mit den neutralen Sprachressourcen, "HelloApp.resources.dll", wird im folgenden Ordner erstellt:  
  
     `C:\HelloApp\Bin\Debug\en-US\`  
  
<a name="build_locbaml"></a>   
## Erstellen des LocBaml\-Tools  
  
1.  Alle für das Erstellen von LocBaml notwendigen Dateien befinden sich in den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Beispielen.  Laden Sie die [!INCLUDE[TLA#tla_lhcshrp](../../../../includes/tlasharptla-lhcshrp-md.md)]\-Dateien aus [Beispiel für LocBaml\-Tool](http://go.microsoft.com/fwlink/?LinkID=160016) herunter.  
  
2.  Führen Sie über die Befehlszeile die Projektdatei \(locbaml.csproj\) aus, um das Tool zu erstellen:  
  
     **msbuild locbaml.csproj**  
  
3.  Wechseln Sie zum Verzeichnis "Bin\\Release", um die neu erstellte ausführbare Datei \(locbaml.exe\) zu finden.  Beispiel: C:\\LocBaml\\Bin\\Release\\locbaml.exe.  
  
4.  Für ein Ausführen von LocBaml können Sie folgende Optionen angeben:  
  
    -   **parse** oder **\-p:** Analysiert Baml\-, Ressourcen\- oder [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]\-Dateien, um eine CSV\- oder TXT\-Datei zu generieren.  
  
    -   **generate** oder **\-g:** Generiert eine lokalisierte Binärdatei, indem eine übersetzte Datei verwendet wird.  
  
    -   **out** oder **\-o** \[*Dateiverzeichnis*\]**:**: der Name der Ausgabedatei.  
  
    -   **culture** oder **\-cul** \[*Kultur*\]**:**: das Gebietsschema der Ausgabeassemblys.  
  
    -   **translation** oder **\-trans** \[*translation.csv*\]**:** die übersetzte oder lokalisierte Datei.  
  
    -   **asmpath** oder **\-asmpath:** \[*Dateiverzeichnis*\]**:** Wenn Ihr [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Code benutzerdefinierte Steuerelemente enthält, müssen Sie den **asmpath** für die benutzerdefinierte Steuerelementassembly angeben.  
  
    -   **nologo:** Bewirkt, dass weder ein Logo noch Copyrightinformationen angezeigt werden.  
  
    -   **verbose:** Bewirkt, dass Informationen im ausführlichen Modus angezeigt werden.  
  
    > [!NOTE]
    >  Wenn Sie beim Ausführen des Tools eine Liste der Optionen benötigen, geben Sie **LocBaml.exe** ein, und drücken Sie die EINGABETASTE.  
  
<a name="parse_dll"></a>   
## Verwenden von LocBaml zum Analysieren einer Datei  
 Nachdem Sie das LocBaml\-Tool erstellt haben, können Sie es verwenden, um "HelloApp.resources.dll" zu analysieren, um den Textinhalt zu extrahieren, der lokalisiert wird.  
  
1.  Kopieren Sie "LocBaml.exe" in den "bin\\debug"\-Ordner Ihrer Anwendung, in dem die Hauptanwendungsassembly erstellt wurde.  
  
2.  Um die Satellitenassemblydatei zu analysieren und die Ausgabe als CSV\-Datei zu speichern, verwenden Sie den folgenden Befehl ein:  
  
     **LocBaml.exe \/parse HelloApp.resources.dll \/out:Hello.csv**  
  
    > [!NOTE]
    >  Wenn sich die Eingabedatei "HelloApp.resources.dll" nicht im selben Ordner wie "LocBaml.exe" befindet, verschieben Sie eine der Dateien, damit sich beide Dateien im selben Verzeichnis befinden.  
  
3.  Wenn Sie LocBaml ausführen, um Dateien zu analysieren, besteht die Ausgabe aus sieben Feldern, die jeweils durch Kommas \(CSV\-Dateien\) oder Tabulatoren \(TXT\-Dateien\) getrennt sind.  Nachstehend ist die bei der Analyse erstellte CSV\-Datei für "HelloApp.Resources.dll" gezeigt:  
  
    ||  
    |-|  
    |HelloApp.g.en\-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,\#Text1;\#Text2;|  
    |HelloApp.g.en\-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World|  
    |HelloApp.g.en\-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World|  
  
     Die sieben Felder sind:  
  
    1.  **BAML\-Name**.  Der Name der BAML\-Ressource bezogen auf die Satellitenassembly für die Ausgangssprache.  
  
    2.  **Ressourcenschlüssel**.  Der lokalisierte Ressourcenbezeichner.  
  
    3.  **Kategorie**.  Der Werttyp.  Weitere Informationen finden Sie unter [Lokalisierungsattribute und \-kommentare](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).  
  
    4.  **Lesbarkeit**.  Gibt an, ob der Wert von einem Lokalisierungstool gelesen werden kann.  Weitere Informationen finden Sie unter [Lokalisierungsattribute und \-kommentare](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).  
  
    5.  **Änderbarkeit**.  Gibt an, ob der Wert von einem Lokalisierungstool geändert werden kann.  Weitere Informationen finden Sie unter [Lokalisierungsattribute und \-kommentare](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).  
  
    6.  **Kommentare**.  Zusätzliche Beschreibung des Werts, um zu ermitteln, wie ein Wert lokalisiert wird.  Weitere Informationen finden Sie unter [Lokalisierungsattribute und \-kommentare](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).  
  
    7.  **Wert**.  Der Textwert, der in die gewünschte Sprache übersetzt werden soll.  
  
     Die folgende Tabelle zeigt, wie diese Felder den durch Trennzeichen getrennten Werten der CSV\-Datei zugeordnet sind:  
  
    |BAML\-Name|Ressourcenschlüssel|Kategorie|Lesbarkeit|Änderbarkeit|Kommentare|Wert|  
    |----------------|-------------------------|---------------|----------------|------------------|----------------|----------|  
    |HelloApp.g.en\-US.resources:window1.baml|Stack1:System.Windows.Controls.StackPanel.$Content|Ignorieren|FALSE|FALSE||\#Text1;\#Text2|  
    |HelloApp.g.en\-US.resources:window1.baml|Text1:System.Windows.Controls.TextBlock.$Content|Keine|TRUE|TRUE||Hello World|  
    |HelloApp.g.en\-US.resources:window1.baml|Text2:System.Windows.Controls.TextBlock.$Content|Keine|TRUE|TRUE||Goodbye World|  
  
     Beachten Sie, dass alle Werte für das Feld **Kommentare** keine Werte enthalten. Hat ein Feld keinen Wert, ist es leer.  Beachten Sie auch, dass das Element in der ersten Zeile weder lesbar noch änderbar ist und "Ignorieren" als **Kategorie**\-Wert hat, wodurch angegeben ist, dass der Wert nicht lokalisierbar ist.  
  
4.  Um das Erkennen von lokalisierbaren Elementen in analysierten Dateien, insbesondere in großen Dateien, zu vereinfachen, können Sie die Elemente nach **Kategorie**, **Lesbarkeit** und **Änderbarkeit** sortieren oder filtern.  Beispielsweise können Sie nicht lesbare und nicht änderbare Werte herausfiltern.  
  
<a name="translate_loc_content"></a>   
## Übersetzen des lokalisierbaren Inhalts  
 Verwenden Sie ein beliebiges Tool, das Ihnen zur Verfügung steht, um den extrahierten Inhalt zu übersetzen.  Eine gute Vorgehensweise besteht darin, die Ressourcen in eine CSV\-Datei zu schreiben, diese in [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] anzuzeigen und die Einträge in der letzten Spalte \(Value\) zu übersetzen.  
  
<a name="merge_translations"></a>   
## Verwenden von LocBaml zum Generieren einer neuen .resources.dll\-Datei  
 Die Inhalte, die durch das Analysieren von "HelloApp.resources.dll" mit LocBaml erkannt wurden, sind nun übersetzt und müssen wieder mit der ursprünglichen Anwendung zusammengeführt werden.  Verwenden Sie die Option **generate** oder **\-g**, um eine neue . resources.dll\-Datei zu erstellen.  
  
1.  Verwenden Sie die folgende Syntax, um eine neue "HelloApp.resources.dll"\-Datei zu generieren.  Kennzeichnen Sie die Kultur als "en\-US" \(\/cul:en\-US\).  
  
     **LocBaml.exe \/generate HelloApp.resources.dll \/trans:Hello.csv \/out:c:\\ \/cul:en\-US**  
  
    > [!NOTE]
    >  Wenn sich die Eingabedatei, "HelloApp.resources.dll", nicht im selben Ordner wie die ausführbare Datei, "LocBaml.exe", befindet, verschieben Sie eine der Dateien, damit sich beide Dateien im selben Verzeichnis befinden.  
  
2.  Ersetzen Sie die alte "HelloApp.resources.dll"\-Datei im Verzeichnis "C:\\HelloApp\\Bin\\Debug\\en\-US\\HelloApp.resources.dll" durch die neu erstellte "HelloApp.resources.dll"\-Datei.  
  
3.  "Hello World" und "Goodbye World" sollten jetzt in Ihrer Anwendung übersetzt sein.  
  
4.  Um in eine andere Kultur zu übersetzen, verwenden Sie die Kultur der Sprache, in die Sie übersetzen.  Das folgende Beispiel zeigt, wie in kanadisches Französisch übersetzt wird:  
  
     **LocBaml.exe \/generate HelloApp.resources.dll \/trans:Hellofr\-CA.csv \/out:c:\\ \/cul:fr\-CA**  
  
5.  Erstellen Sie in dem Ordner, in dem sich die Hauptanwendungsassembly befindet, einen neuen kulturspezifischen Ordner, der die neue Satellitenassembly aufnehmen soll.  Für kanadisches Französisch ist dies der Ordner "fr\-CA".  
  
6.  Kopieren Sie die generierte Satellitenassembly in den neuen Ordner.  
  
7.  Um die neue Satellitenassembly zu testen, müssen Sie die Kultur ändern, unter der Ihre Anwendung ausgeführt wird.  Dazu haben Sie zwei Möglichkeiten:  
  
    -   Ändern Sie die Einstellung für das Gebietsschema \(**Start** &#124; **Systemsteuerung** &#124; **Regions\- und Sprachoptionen**\) des Betriebssystems.  
  
    -   Fügen Sie in Ihrer Anwendung den folgenden Code in "App.xaml.cs" hinzu:  
  
         [!code-xml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]  
  
         [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
         [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
<a name="Some_Tips_for_Using_LocBaml"></a>   
## Einige Tipps zum Verwenden von LocBaml  
  
-   Alle abhängigen Assemblys, die benutzerdefinierte Steuerelemente definieren, müssen in das lokale Verzeichnis von LocBaml kopiert oder im globalen Assemblycache \(GAC\) installiert werden.  Dies ist notwendig, da die Lokalisierungs\-API Zugriff auf die abhängigen Assemblys haben muss, wenn sie die [!INCLUDE[TLA#tla_baml](../../../../includes/tlasharptla-baml-md.md)] liest.  
  
-   Wenn die Hauptassembly signiert ist, muss auch die generierte Ressourcen\-DLL signiert sein, damit sie geladen werden kann.  
  
-   Die Version der lokalisierten Ressourcen\-DLL muss mit der Hauptassembly synchronisiert werden.  
  
<a name="Whats_Next"></a>   
## Weitere Informationen  
 Sie wissen nun in Grundzügen, wie das LocBaml\-Tool verwendet werden kann.  Sie sollten in der Lage sein, eine Datei zu erstellen, die UIDs enthält.  Mit dem LocBaml\-Tool sollten Sie in der Lage sein, eine Datei zu analysieren, um den lokalisierbaren Inhalt zu extrahieren, und nach der Übersetzung des Inhalts sollten Sie eine .resources.dll\-Datei generieren können, die den übersetzten Inhalt zusammenführt.  Dieses Thema beinhaltet nicht jedes mögliche Detail, aber Sie verfügen nun über das notwendige Wissen, um LocBaml zur Lokalisierung Ihrer Anwendungen zu verwenden.  
  
## Siehe auch  
 [Globalisierung für WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)   
 [Übersicht über die Verwendung eines automatischen Layouts](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)