---
title: Lokalisieren einer APP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: dc7d8f4f56b26fffbd883e1e1d6e420026e1f94f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209681"
---
# <a name="how-to-localize-an-application"></a>Gewusst wie: Lokalisieren einer Anwendung

In diesem Lernprogramm wird erläutert, wie eine lokalisierte Anwendung mit dem LocBaml-Tool erstellt wird.  
  
> [!NOTE]
> Das LocBaml-Tool ist keine einsatzfertige Anwendung. Es wird als Beispiel präsentiert, das einen Teil der Lokalisierungs-APIs verwendet und veranschaulicht, wie Sie ein Lokalisierungstool schreiben können.  
  
## <a name="overview"></a>Übersicht

In diesem Artikel erhalten Sie einen Schritt-für-Schritt-Ansatz zum Lokalisieren einer Anwendung. Zuerst bereiten Sie Ihre Anwendung so vor, dass der zu über setzende Text extrahiert werden kann. Nachdem der Text übersetzt wurde, führen Sie den übersetzten Text mit einer neuen Kopie der ursprünglichen Anwendung zusammen.
  
## <a name="create-a-sample-application"></a>Erstellen einer Beispielanwendung

In diesem Schritt bereiten Sie Ihre APP auf die Lokalisierung vor. In den Windows Presentation Foundation-Beispielen (WPF) wird ein HelloApp-Beispiel bereitgestellt, das für die Codebeispiele in dieser Diskussion verwendet wird. Wenn Sie dieses Beispiel verwenden möchten, laden Sie die Extensible Application Markup Language Dateien (XAML) vom [LocBaml-Tool Beispiel](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)herunter.  
  
1. Entwickeln Sie Ihre Anwendung bis zu dem Punkt, an dem Sie die Lokalisierung starten möchten.  
  
2. Geben Sie die Entwicklungssprache in der Projektdatei an, damit MSBuild eine Hauptassembly und eine Satellitenassembly (eine Datei mit der Erweiterung ". resources. dll") generiert, die die neutralen Sprachressourcen enthält. Die Projektdatei im HelloApp-Beispiel ist "HelloApp.csproj". In dieser Datei finden Sie die Entwicklungssprache wie folgt gekennzeichnet:  
  
   `<UICulture>en-US</UICulture>`  
  
3. Fügen Sie den XAML-Dateien UIDs hinzu. UIDs werden verwendet, um Änderungen an Dateien nachzuverfolgen und die Elemente zu identifizieren, die übersetzt werden müssen. Um den Dateien UIDs hinzuzufügen, führen Sie `updateuid` in der Projektdatei aus:  

   `msbuild -t:updateuid helloapp.csproj`

   Führen Sie Folgendes aus, um zu überprüfen, ob Sie über fehlende oder doppelte UIDs verfügen `checkuid` :  

   `msbuild -t:checkuid helloapp.csproj`

   Nach dem Ausführen von `updateuid` sollten Ihre Dateien UIDs enthalten. In der *"Pane1. XAML* -Datei von HelloApp sollten Sie z. b. Folgendes finden:  

   ```xaml
   <StackPanel x:Uid="StackPanel_1">
     <TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>
     <TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>
   </StackPanel>
   ```

## <a name="create-the-neutral-language-resources-satellite-assembly"></a>Erstellen der Satellitenassembly für neutrale Sprachressourcen

Nachdem die Anwendung so konfiguriert wurde, dass Sie eine Satellitenassembly mit neutralen Sprachressourcen generiert, erstellen Sie die Anwendung. Dadurch wird die Hauptanwendungsassembly und die Satellitenassembly für die neutrale Sprache generiert, die von LocBaml für die Lokalisierung benötigt wird.

So erstellen Sie die Anwendung:  
  
1. Kompilieren Sie HelloApp, um eine Dynamic Link Library (dll) zu erstellen:  
  
   `msbuild helloapp.csproj`
  
2. Die neu erstellte Hauptanwendungsassembly "HelloApp. exe" wird im folgenden Ordner erstellt: *c:\helloapp\bin\debug*
  
3. Die neu erstellte-Satellitenassembly "HelloApp. resources. dll" wird im folgenden Ordner erstellt: *c:\helloapp\bin\debug\de-US*
  
## <a name="build-the-locbaml-tool"></a>Erstellen des LocBaml-Tools  
  
1. Alle Dateien, die zum Erstellen von LocBaml erforderlich sind, befinden sich in den WPF-Beispielen. Laden Sie die c#-Dateien aus dem [LocBaml-Tool Beispiel](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)herunter.  
  
2. Führen Sie über die Befehlszeile die Projektdatei (locbaml.csproj) aus, um das Tool zu erstellen:  

   `msbuild locbaml.csproj`
  
3. Wechseln Sie zum Verzeichnis " *bin\Release* ", um die neu erstellte ausführbare Datei (LocBaml. exe) zu finden. Beispiel: *c:\LocBaml\Bin\Release\locbaml.exe*
  
4. Die Optionen, die Sie beim Ausführen von LocBaml angeben können, sind wie folgt.

   | Option | Beschreibung|
   | - | - |
   | `parse` oder `-p` | Analysiert BAML-, Ressourcen-oder DLL-Dateien, um eine CSV-oder txt-Datei zu generieren. |
   | `generate` oder `-g` | Generiert eine lokalisierte Binärdatei, indem eine übersetzte Datei verwendet wird. |
   | `out`oder `-o` {*File Directory*] | Der Name der Ausgabedatei. |
   | `culture`oder `-cul` {*Culture*] | Locale der Ausgabeassemblys |
   | `translation`oder `-trans` {*Translation. CSV*] | Übersetzte oder lokalisierte Datei. |
   | `asmpath`oder `-asmpath` {*File Directory*] | Wenn Ihr XAML-Code benutzerdefinierte Steuerelemente enthält, müssen Sie `asmpath` für die benutzerdefinierte Steuerelement-Assembly bereitstellen. |
   | `nologo` |  Bewirkt, dass weder ein Logo noch Copyrightinformationen angezeigt werden. |
   | `verbose` |  Bewirkt, dass Informationen im ausführlichen Modus angezeigt werden. |
  
   > [!NOTE]
   > Wenn Sie beim Ausführen des Tools eine Liste der Optionen benötigen, geben Sie ein, `LocBaml.exe` und drücken Sie dann die **Eingabe**Taste.
  
## <a name="use-locbaml-to-parse-a-file"></a>Verwenden von LocBaml zum Analysieren einer Datei

Nachdem Sie das LocBaml-Tool erstellt haben, können Sie es verwenden, um "HelloApp.resources.dll" zu analysieren, um den Textinhalt zu extrahieren, der lokalisiert wird.  
  
1. Kopieren Sie "LocBaml.exe" in den "bin\debug"-Ordner Ihrer Anwendung, in dem die Hauptanwendungsassembly erstellt wurde.  
  
2. Um die Satellitenassemblydatei zu analysieren und die Ausgabe als CSV-Datei zu speichern, verwenden Sie den folgenden Befehl ein:  
  
   `LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv`
  
   > [!NOTE]
   > Wenn sich die Eingabedatei "HelloApp.resources.dll" nicht im selben Ordner wie "LocBaml.exe" befindet, verschieben Sie eine der Dateien, damit sich beide Dateien im selben Verzeichnis befinden.  
  
3. Wenn Sie LocBaml ausführen, um Dateien zu analysieren, besteht die Ausgabe aus sieben Feldern, die jeweils durch Kommas (CSV-Dateien) oder Tabulatoren (TXT-Dateien) getrennt sind. Nachstehend ist die bei der Analyse erstellte CSV-Datei für "HelloApp.Resources.dll" gezeigt:

   | |
   |-|
   |HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;|
   |HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World|
   |HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World|

   Die sieben Felder sind:  
  
   - **BAML-Name**. Der Name der BAML-Ressource bezogen auf die Satellitenassembly für die Ausgangssprache.  
  
   - **Ressourcen Schlüssel**. Der lokalisierte Ressourcenbezeichner.  
  
   - **Kategorie** Der Werttyp. Siehe [Lokalisierungs Attribute und-Kommentare](localization-attributes-and-comments.md).  
  
   - **Lesbarkeit**. Gibt an, ob der Wert von einem Lokalisierungstool gelesen werden kann. Siehe [Lokalisierungs Attribute und-Kommentare](localization-attributes-and-comments.md).  
  
   - **Änderbarkeit**. Gibt an, ob der Wert von einem Lokalisierungstool geändert werden kann. Siehe [Lokalisierungs Attribute und-Kommentare](localization-attributes-and-comments.md).  
  
   - **Kommentare**. Zusätzliche Beschreibung des Werts, um zu ermitteln, wie ein Wert lokalisiert wird. Siehe [Lokalisierungs Attribute und-Kommentare](localization-attributes-and-comments.md).  
  
   - **Wert**. Der Textwert, der in die gewünschte Sprache übersetzt werden soll.  
  
   Die folgende Tabelle zeigt, wie diese Felder den durch Trennzeichen getrennten Werten der CSV-Datei zugeordnet sind:  
  
   |BAML-Name|Ressourcenschlüssel|Kategorie|Lesbarkeit|Änderbarkeit|Kommentare|Wert|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |HelloApp.g.en-US.resources:window1.baml|Stack1:System.Windows.Controls.StackPanel.$Content|Ignorieren|FALSE|FALSE||#Text1;#Text2|
   |HelloApp.g.en-US.resources:window1.baml|Text1:System.Windows.Controls.TextBlock.$Content|Keine|TRUE|TRUE||Hello World|
   |HelloApp.g.en-US.resources:window1.baml|Text2:System.Windows.Controls.TextBlock.$Content|Keine|TRUE|TRUE||Goodbye World|
  
   Beachten Sie, dass alle Werte für das Feld **Kommentare** keine Werte enthalten. Wenn ein Feld keinen Wert hat, ist es leer. Beachten Sie auch, dass das Element in der ersten Zeile weder lesbar noch änderbar ist und "Ignore" als **Kategoriewert** aufweist. Dies bedeutet, dass der Wert nicht lokalisierbar ist.  
  
4. Um die Ermittlung Lokalisier barer Elemente in analysierten Dateien, insbesondere in großen Dateien, zu vereinfachen, können Sie die Elemente nach **Kategorie**, **Lesbarkeit**und **Änderbarkeit**sortieren oder filtern. Beispielsweise können Sie nicht lesbare und nicht änderbare Werte herausfiltern.  
  
## <a name="translate-the-localizable-content"></a>Übersetzen des lokalisierbaren Inhalts

Verwenden Sie ein beliebiges Tool, das Ihnen zur Verfügung steht, um den extrahierten Inhalt zu übersetzen. Eine gute Möglichkeit hierfür besteht darin, die Ressourcen in eine CSV-Datei zu schreiben und Sie in Microsoft Excel anzuzeigen, sodass Übersetzungsänderungen an der letzten Spalte (Wert) vorgenommen werden.  
  
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a>Verwenden von LocBaml zum Generieren einer neuen. resources. dll-Datei

Die Inhalte, die durch das Analysieren von "HelloApp.resources.dll" mit LocBaml erkannt wurden, sind nun übersetzt und müssen wieder mit der ursprünglichen Anwendung zusammengeführt werden. Verwenden `generate` Sie die `-g` Option oder, um eine neue resources. dll-Datei zu generieren.  
  
1. Verwenden Sie die folgende Syntax, um eine neue "HelloApp.resources.dll"-Datei zu generieren. Kennzeichnen Sie die Kultur als "en-US" (/cul:en-US).  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US`  

   > [!NOTE]
   > Wenn sich die Eingabedatei, "HelloApp.resources.dll", nicht im selben Ordner wie die ausführbare Datei, "LocBaml.exe", befindet, verschieben Sie eine der Dateien, damit sich beide Dateien im selben Verzeichnis befinden.  
  
2. Ersetzen Sie die alte Datei " *HelloApp. resources. dll* " im Verzeichnis " *C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll* " durch die neu erstellte Datei " *HelloApp. resources. dll* ".  
  
3. "Hello World" und "Goodbye World" sollten jetzt in Ihrer Anwendung übersetzt sein.  
  
4. Um in eine andere Kultur zu übersetzen, verwenden Sie die Kultur der Sprache, in die Sie übersetzen. Das folgende Beispiel zeigt, wie in kanadisches Französisch übersetzt wird:  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA`  
  
5. Erstellen Sie in dem Ordner, in dem sich die Hauptanwendungsassembly befindet, einen neuen kulturspezifischen Ordner, der die neue Satellitenassembly aufnehmen soll. Für kanadisches Französisch ist dies der Ordner "fr-CA".  
  
6. Kopieren Sie die generierte Satellitenassembly in den neuen Ordner.  
  
7. Um die neue Satellitenassembly zu testen, müssen Sie die Kultur ändern, unter der Ihre Anwendung ausgeführt wird. Dazu haben Sie zwei Möglichkeiten:  
  
   - Ändern Sie die regionalen Einstellungen des Betriebssystems.
  
   - Fügen Sie in Ihrer Anwendung den folgenden Code in "App.xaml.cs" hinzu:  
  
     [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
     [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
     [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
## <a name="tips-for-using-locbaml"></a>Tipps für die Verwendung von LocBaml  
  
- Alle abhängigen Assemblys, die benutzerdefinierte Steuerelemente definieren, müssen in das lokale Verzeichnis von LocBaml kopiert oder im globalen Assemblycache (GAC) installiert werden. Dies ist erforderlich, da die Lokalisierungs-API Zugriff auf die abhängigen Assemblys haben muss, wenn Sie das binäre XAML (BAML) liest.  
  
- Wenn die Hauptassembly signiert ist, muss auch die generierte Ressourcen-DLL signiert sein, damit sie geladen werden kann.  
  
- Die Version der lokalisierten Ressourcen-DLL muss mit der Hauptassembly synchronisiert werden.
  
## <a name="see-also"></a>Siehe auch

- [Globalisierung für WPF](globalization-for-wpf.md)
- [Übersicht über die Verwendung eines automatischen Layouts](use-automatic-layout-overview.md)
