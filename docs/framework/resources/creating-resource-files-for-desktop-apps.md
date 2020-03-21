---
title: Erstellen von Ressourcendateien für .NET-Apps
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resource files, .resources files
- .resources files
- application resources, creating files
- resource files, creating
ms.assetid: 6c5ad891-66a0-4e7a-adcf-f41863ba6d8d
ms.openlocfilehash: b679539be1aeb593124eb35a235bcc578decb4c0
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111776"
---
# <a name="create-resource-files-for-net-apps"></a>Erstellen von Ressourcendateien für .NET-Apps

Sie können Ressourcen (z. B. Zeichenfolgen, Bilder oder Objektdaten) in Ressourcendateien einschließen, um sie für die Anwendung leicht verfügbar zu machen. .NET Framework bietet fünf Möglichkeiten, Ressourcendateien zu erstellen:

- Erstellen Sie eine Textdatei, die Zeichenfolgenressourcen enthält. Sie können die Textdatei mithilfe des [Resource File Generator (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) in eine binäre Ressourcendatei (.resources) konvertieren. Sie können die binäre Ressourcendatei dann mithilfe eines Sprachcompilers in eine ausführbare Anwendungsdatei oder eine Anwendungsbibliothek einbetten oder sie mithilfe von [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md)in eine Satellitenassembly einbetten. Weitere Informationen finden Sie im Abschnitt [Ressourcen in Textdateien](creating-resource-files-for-desktop-apps.md#TextFiles).

- Erstellen Sie eine XML-Ressourcendatei (.resx), die Zeichenfolgen-, Bild- oder Objektdaten enthält. Sie können die RESX-Datei mithilfe des [Resource File Generator (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) in eine binäre Ressourcendatei (.resources) konvertieren. Anschließend können Sie die binäre Ressourcendatei mit einem Sprachcompiler in eine ausführbare Datei der Anwendung oder eine Anwendungsbibliothek einbetten, oder Sie können sie mithilfe des [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) in eine Satellitenassembly einbetten. Weitere Informationen finden Sie im Abschnitt [Ressourcen in RESX-Dateien](creating-resource-files-for-desktop-apps.md#ResxFiles).

- Erstellen Sie programmgesteuert mithilfe von Typen im <xref:System.Resources>-Namespace eine XML-Ressourcendatei (.resx). Sie können eine RESX-Datei erstellen, ihre Ressourcen auflisten und bestimmte Ressourcen nach dem Namen abrufen. Weitere Informationen finden Sie unter [Programmgesteuertes Arbeiten mit RESX-Dateien](working-with-resx-files-programmatically.md).

- Erstellen Sie programmgesteuert eine binäre Ressourcendatei (.resources). Anschließend können Sie die Datei mit einem Sprachcompiler in eine ausführbare Datei der Anwendung oder eine Anwendungsbibliothek einbetten, oder Sie können sie mithilfe des [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) in eine Satellitenassembly einbetten. Weitere Informationen finden Sie im Abschnitt [Ressourcen in RESOURCES-Dateien](creating-resource-files-for-desktop-apps.md#ResourcesFiles).

- Verwenden Sie [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), um eine Ressourcendatei zu erstellen und in das Projekt einzuschließen. Visual Studio stellt einen Ressourcen-Editor bereit, mit dem Sie Ressourcen hinzufügen, löschen und ändern können. Zur Kompilierzeit wird die Ressourcendatei automatisch in eine binäre RESOURCES-Datei konvertiert und in eine Anwendungsassembly oder eine Satellitenassembly eingebettet. Weitere Informationen finden Sie im Abschnitt [Ressourcendateien in Visual Studio](creating-resource-files-for-desktop-apps.md#VSResFiles).

<a name="TextFiles"></a>
## <a name="resources-in-text-files"></a>Ressourcen in Textdateien

Sie können Textdateien (TXT oder RESTEXT) verwenden, um nur Zeichenfolgenressourcen zu speichern. Verwenden Sie für Nicht-Zeichenfolgenressourcen RESX-Dateien, oder erstellen Sie sie programmgesteuert. Textdateien, die Zeichenfolgenressourcen enthalten, haben das folgende Format:

```text
# This is an optional comment.
name = value

; This is another optional comment.
name = value

; The following supports conditional compilation if X is defined.
#ifdef X
name1=value1
name2=value2
#endif

# The following supports conditional compilation if Y is undefined.
#if !Y
name1=value1
name2=value2
#endif
```

 Das Ressourcendateiformat von .txt und von .restext-Dateien ist identisch. Die .restext-Dateierweiterung dient lediglich dazu, Textdateien direkt als textbasierte Ressourcendateien identifizierbar zu machen.

 Zeichenfolgenressourcen werden als Name/Wert-Paare (*name/value* pairs) angezeigt, wobei *name* eine Zeichenfolge ist, die die Ressource identifiziert, und *value* die Ressourcenzeichenfolge, die zurückgegeben wird, wenn Sie *name* an eine Ressourcenabrufmethode wie <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> übergeben. *name* und *value* müssen durch ein Gleichheitszeichen (=) getrennt werden. Beispiel:

```text
FileMenuName=File
EditMenuName=Edit
ViewMenuName=View
HelpMenuName=Help
```

> [!CAUTION]
> Verwenden Sie Ressourcendateien nicht, um Kennwörter, sicherheitsrelevante Informationen oder private Daten zu speichern.

 Leere Zeichenfolgen (eine Ressource, deren Wert <xref:System.String.Empty?displayProperty=nameWithType> ist) sind in Textdateien zulässig. Beispiel:

```text
EmptyString=
```

 Ab .NET Framework 4.5 und in allen Versionen von .NET `#ifdef`Core unterstützen Textdateien die bedingte Kompilierung mit dem *Symbol*... `#endif` und `#if !` *Symbol*... `#endif` Konstrukte. Sie können dann den `/define`-Schalter mit dem [Resource File Generator (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) verwenden, um Symbole zu definieren. Jede Ressource benötigt `#ifdef`ein eigenes *Symbol*... `#endif` oder `#if !` *Symbol*... `#endif` Konstrukt. Wenn Sie eine `#ifdef`-Anweisung verwenden und *Symbol* definiert ist, wird die zugeordnete Ressource in die RESOURCES-Datei einbezogen; andernfalls wird sie nicht eingeschlossen. Wenn Sie eine `#if !`-Anweisung verwenden und *Symbol* nicht definiert ist, wird die zugeordnete Ressource in die RESOURCES-Datei einbezogen; andernfalls wird sie nicht eingeschlossen.

 Kommentare sind in Textdateien optional, und am Anfang einer Zeile wird entweder ein Semikolon (;) vorangestellt oder ein Nummernzeichen (#). Zeilen, die Kommentare enthalten sind, können an beliebiger Stelle in der Datei eingefügt werden. Kommentare sind nicht in einer mit dem [Resource File Generator (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) erstellten kompilierten RESOURCES-Datei enthalten.

 Alle leeren Zeilen in den Textdateien werden als Leerzeichen angesehen ignoriert.

 Im folgenden Beispiel werden zwei Zeichenfolgenressourcen mit dem Namen `OKButton` und `CancelButton` definiert.

```text
#Define resources for buttons in the user interface.
OKButton=OK
CancelButton=Cancel
```

 Wenn die Textdatei doppelte Vorkommen von *name* enthält, zeigt der [Resource File Generator (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) eine Warnung an und ignoriert den zweiten Namen.

 *Wert* darf keine neuen Zeilenzeichen enthalten, aber Sie können `\n` Escape-Zeichen im `\t` C-Sprachstil verwenden, z. B. um eine neue Zeile darzustellen und eine Registerkarte darzustellen. Sie können auch ein umgekehrtes Schrägstrichzeichen einschließen,\\\\wenn es mit einem Escapezeichen versehen wird (z. B. " "). Darüber hinaus ist eine leere Zeichenfolge zulässig.

 Speichern Sie Ressourcen im Textdateiformat, indem Sie die UTF-8-Codierung oder die UTF-16-Codierung in Little-Endian- oder Big-Endian-Bytereihenfolge verwenden. Obwohl der [Resource File Generator (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) TXT-Dateien in RESOURCES-Dateien konvertiert, behandelt er Dateien standardmäßig als UTF-8. Wenn "Resgen.exe" eine als UTF-16 codierte Datei erkennen soll, müssen Sie am Anfang der Datei eine Unicode-Bytereihenfolgemarkierung (U+FEFF) angeben.

 Um eine Ressourcendatei im Textformat in eine .NET-Assembly einzubetten, müssen Sie die Datei mit dem [Resource File Generator (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) in eine binäre Ressourcendatei (.resources) konvertieren. Sie können die RESOURCES-Datei dann mit einem Sprachcompiler in eine .NET-Assembly oder mit dem [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) in eine Satellitenassembly einbetten.

 Im folgenden Beispiel wird eine Ressourcendatei im Textformat mit dem Namen "GreetingResources.txt" für eine einfache Konsolenanwendung "Hello World" verwendet. Die Textdatei definiert zwei `prompt` `greeting`Zeichenfolgen und , die den Benutzer auffordern, seinen Namen einzugeben und eine Begrüßung anzuzeigen.

```text
# GreetingResources.txt
# A resource file in text format for a "Hello World" application.
#
# Initial prompt to the user.
prompt=Enter your name:
# Format string to display the result.
greeting=Hello, {0}!
```

Die Textdatei wird mit dem folgenden Befehl in eine RESOURCES-Datei konvertiert:

```console
resgen GreetingResources.txt
```

 Im folgenden Beispiel wird der Quellcode für eine Konsolenanwendung veranschaulicht, die dem Benutzer mithilfe der RESOURCES-Datei Nachrichten anzeigt.

 [!code-csharp[Conceptual.Resources.TextFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.textfiles/cs/greeting.cs#1)]
 [!code-vb[Conceptual.Resources.TextFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.textfiles/vb/greeting.vb#1)]

 Wenn Sie Visual Basic verwenden und die Quellcodedatei "Greeting.vb" genannt wird, erstellt der folgende Befehl eine ausführbare Datei, die die eingebettete RESOURCES-Datei einschließt:

```console
vbc greeting.vb -resource:GreetingResources.resources
```

 Wenn Sie C# verwenden und die Quellcodedatei "Greeting.cs" genannt wird, erstellt der folgende Befehl eine ausführbare Datei, die die eingebettete RESOURCES-Datei einschließt:

```console
csc greeting.cs -resource:GreetingResources.resources
```

<a name="ResxFiles"></a>
## <a name="resources-in-resx-files"></a>Ressourcen in RESX-Dateien
 Im Gegensatz zu Textdateien, in denen nur Zeichenfolgenressourcen gespeichert werden können, können in XML-Ressourcendateien (.resx) Zeichenfolgen, Binärdaten wie Bilder, Symbole und Audioclips sowie programmgesteuerte Objekte gespeichert werden. Eine RESX-Datei enthält einen Standardheader, der das Format der Ressourceneinträge beschreibt und die XML-Versioninginformationen zum Interpretieren der Daten angibt. Die Ressourcendateidaten folgen auf den XML-Header. Jedes Datenelement besteht aus einem Name-Wert-Paar, das in einem `data`-Tag enthalten ist. Sein `name`-Attribut definiert den Ressourcennamen, und das geschachtelte `value`-Tag enthält den Ressourcenwert. Bei Zeichenfolgendaten enthält das `value`-Tag die Zeichenfolge.

 Das folgende `data`-Tag definiert z. B. eine Zeichenfolgenressource mit dem Namen von `prompt`, deren Wert "Enter your name:" lautet.

```xml
<data name="prompt" xml:space="preserve">
  <value>Enter your name:</value>
</data>
```

> [!WARNING]
> Verwenden Sie Ressourcendateien nicht, um Kennwörter, sicherheitsrelevante Informationen oder private Daten zu speichern.

 Bei Ressourcenobjekten enthält das Tag **data** ein `type`-Attribut, das den Datentyp der Ressource angibt. Bei Objekten, die aus Binärdaten bestehen, schließt das `data`-Tag auch ein `mimetype`-Attribut ein, das den `base64`-Typ der Binärdaten angibt.

> [!NOTE]
> Alle RESX-Dateien verwenden ein Programm für die binäre Serialisierung, um die Binärdaten für einen bestimmten Typ zu generieren und zu analysieren. Daher kann eine RESX-Datei ungültig werden, wenn das Format für die binäre Serialisierung für ein Objekt auf nicht kompatible Weise geändert wird.

 Im folgenden Beispiel wird ein Teil einer RESX-Datei veranschaulicht, die eine <xref:System.Int32>-Ressource und ein Bitmapbild enthält.

```xml
<data name="i1" type="System.Int32, mscorlib">
  <value>20</value>
</data>

<data name="flag" type="System.Drawing.Bitmap, System.Drawing,
    Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
    mimetype="application/x-microsoft.net.object.bytearray.base64">
  <value>
    AAEAAAD/////AQAAAAAAAAAMAgAAADtTeX…
  </value>
</data>
```

> [!IMPORTANT]
> Da RESX-Dateien aus wohlgeformtem XML in einem vordefinierten Format bestehen müssen, empfiehlt es sich nicht, mit RESX-Dateien manuell zu arbeiten, insbesondere, wenn die RESX-Dateien andere Ressourcen als Zeichenfolgen enthalten. Stattdessen bietet [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) eine transparente Schnittstelle zum Erstellen und Bearbeiten von RESX-Dateien. Weitere Informationen finden Sie im Abschnitt [Ressourcendateien in Visual Studio](creating-resource-files-for-desktop-apps.md#VSResFiles). Sie können RESX-Dateien auch programmgesteuert erstellen und bearbeiten. Weitere Informationen finden Sie unter [Programmgesteuertes Arbeiten mit RESX-Dateien](working-with-resx-files-programmatically.md).

<a name="ResourcesFiles"></a>
## <a name="resources-in-resources-files"></a>Ressourcen in RESOURCES-Dateien

Mit der <xref:System.Resources.ResourceWriter?displayProperty=nameWithType>-Klasse können Sie eine binäre Ressourcendatei (.resources) direkt aus Code programmgesteuert erstellen. Sie können auch mithilfe des [Resource File Generator (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) eine RESOURCES-Datei aus einer Textdatei oder einer RESX-Datei erstellen. Die RESOURCES-Datei kann neben Zeichenfolgendaten Binärdaten (Bytearrays) und Objektdaten enthalten. Das programmgesteuerte Erstellen einer RESOURCES-Datei erfordert die folgenden Schritte:

1. Erstellen Sie ein <xref:System.Resources.ResourceWriter>-Objekt mit einem eindeutigen Dateinamen. Geben Sie dazu entweder einen Dateinamen oder einen Dateistream zu einem <xref:System.Resources.ResourceWriter>-Klassenkonstruktor an.

2. Rufen Sie eine der Überladungen der <xref:System.Resources.ResourceWriter.AddResource%2A?displayProperty=nameWithType>-Methode für jede benannte Ressource an, die der Datei hinzugefügt werden soll. Die Ressource kann eine Zeichenfolge, ein Objekt oder eine Auflistung der Binärdaten (ein Bytearray) sein.

3. Rufen Sie die <xref:System.Resources.ResourceWriter.Close%2A?displayProperty=nameWithType>-Methode auf, um die Ressourcen in die Datei zu schreiben und das <xref:System.Resources.ResourceWriter>-Objekt zu schließen.

> [!NOTE]
> Verwenden Sie Ressourcendateien nicht, um Kennwörter, sicherheitsrelevante Informationen oder private Daten zu speichern.

 Im folgenden Beispiel wird programmgesteuert eine RESOURCES-Datei mit dem Namen "CarResources.resources" erstellt, mit der sechs Zeichenfolgen, ein Symbol und zwei anwendungsdefinierte Objekte (zwei `Automobile`-Objekte) gespeichert werden. Die `Automobile` Klasse, die im Beispiel definiert und instanziiert wird, wird mit dem <xref:System.SerializableAttribute> Attribut markiert, wodurch sie vom binären Serialisierungsformatar beibehalten werden kann.

 [!code-csharp[Conceptual.Resources.Resources#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resources/cs/resources1.cs#1)]
 [!code-vb[Conceptual.Resources.Resources#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resources/vb/resources1.vb#1)]

 Nachdem Sie die RESOURCES-Datei erstellt haben, können Sie die RESOURCES-Datei in eine ausführbare Datei oder Runtimebibliothek einbetten, indem Sie den `/resource`-Schalter des Sprachcompilers einschließen, oder Sie betten sie mit dem [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) in eine Satellitenassembly ein.

<a name="VSResFiles"></a>
## <a name="resource-files-in-visual-studio"></a>Ressourcendateien in Visual Studio

Wenn Sie dem [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)-Projekt eine Ressourcendatei hinzufügen, wird von Visual Studio im Projektverzeichnis eine RESX-Datei erstellt. Visual Studio stellt Ressourcen-Editoren bereit, die es Ihnen ermöglichen, Zeichenfolgen, Bilder und binäre Objekte hinzuzufügen. Da die Editoren nur dazu dienen, statische Daten zu behandeln, können sie nicht zum Speichern programmgesteuerter Objekte verwendet werden. Sie müssen Objektdaten programmgesteuert in eine RESX-Datei oder in eine RESOURCES-Datei schreiben. Weitere Informationen finden Sie in den Abschnitten [Programmgesteuertes Arbeiten mit RESX-Dateien](working-with-resx-files-programmatically.md) und [Ressourcen in RESOURCES-Dateien](creating-resource-files-for-desktop-apps.md#ResourcesFiles).

Wenn Sie lokalisierte Ressourcen hinzufügen, geben Sie ihnen den gleichen Stammdateinamen wie der Hauptressourcendatei. Sie sollten auch ihre Kultur im Dateinamen festlegen. Wenn Sie z. B. eine Ressourcendatei mit dem Namen "Ressourcen.resx" hinzufügen, können Sie auch Ressourcendateien mit dem Namen "Ressourcen.en-US.resx" und "Ressourcen.fr-FR.resx" erstellen, um lokalisierte Ressourcen für die englischen (USA) und französischen (Frankreich) Kulturen zu halten. Sie sollten auch die Standardkultur der Anwendung festlegen. Die Ressourcen dieser Kultur werden verwendet, wenn keine lokalisierten Ressourcen für eine bestimmte Kultur gefunden werden. Zum Angeben der Standardkultur klicken Sie in Visual Studio im Projektmappen-Explorer mit der rechten Maustaste auf den Projektnamen, zeigen Sie auf "Anwendung", klicken Sie auf **Assemblyinformationen**, und wählen Sie die entsprechende Sprache/Kultur in der Liste **Neutrale Sprache** aus.

Zur Kompilierzeit werden von Visual Studio zuerst die RESX-Dateien in einem Projekt in binäre Ressourcendateien (.resources) konvertiert und im Verzeichnis *obj* des Projekts in einem Unterverzeichnis gespeichert. Visual Studio bettet alle Ressourcendateien ein, die keine lokalisierten Ressourcen in der vom Projekt generierten Hauptassembly enthalten. Wenn Ressourcendateien lokalisierte Ressourcen enthalten, werden diese von Visual Studio für jede lokalisierte Kultur in separate Satellitenassemblys eingebettet. Anschließend wird jede Satellitenassembly in einem Verzeichnis gespeichert, dessen Name der lokalisierten Kultur entspricht. Lokalisierte englische Ressourcen (USA) werden z. B. in einer Satellitenassembly im Unterverzeichnis "en-US" gespeichert.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Resources>
- [Ressourcen in Desktop-Apps](index.md)
- [Packaging and Deploying Resources](packaging-and-deploying-resources-in-desktop-apps.md)
