---
title: „Winres.exe“ (Windows-Ressourcenlokalisierungs-Editor)
description: Verwenden Sie „Winres.exe“, den Windows-Editor für die Ressourcenlokalisierung. Dieses visuelle Layouttool hilft Lokalisierungsexperten dabei, Windows Forms-Benutzeroberflächenressourcen zu lokalisieren, die von Formularen verwendet werden.
ms.date: 08/15/2018
helpviewer_keywords:
- Winres.exe
- Windows Forms Resource Editor
- Windows Resource Localization Editor
- localization
- Windows Forms, localization
- forms, localizing
- resx files
- .resx files
ms.assetid: cb8bc835-9221-4888-af53-1a4f5fad6c48
ms.openlocfilehash: 8393eb44246ed1bbc0e4e6acc84ad7bd57041ec0
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "87516904"
---
# <a name="winresexe-windows-resource-localization-editor"></a>„Winres.exe“ (Windows-Ressourcenlokalisierungs-Editor)

Der Windows-Ressourcenlokalisierungs-Editor, „Winres.exe“, ist ein visuelles Layouttool, das Lokalisierungsexperten beim Lokalisieren von Ressourcen der Windows Forms-Benutzeroberfläche unterstützt, die von Formularen verwendet werden. Die als Eingabe für "Winres.exe" verwendeten RESX- oder RESOURCES-Dateien können unter Verwendung einer visuellen Entwurfsumgebung, wie Microsoft Visual Studio, erstellt werden. Informationen zum Bereitstellen von Ressourcen in .NET Framework-Anwendungen finden Sie unter [Ressourcen in Desktop-Apps](../resources/index.md).

„Winres.exe“ wird mit Visual Studio installiert. Verwenden Sie zum Ausführen des Tools die Developer-Eingabeaufforderung für Visual Studio. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).

## <a name="syntax"></a>Syntax

```console
winres resourceFile
winres /?
```

## <a name="arguments"></a>Argumente

|Argument|BESCHREIBUNG|
|--------------|-----------------|
|`resourceFile`|Die zu lokalisierende Ressourcendatei. Diese Datei muss ein als RESX- oder RESOURCES-Datei durch den Visual Studio-Designer generiertes Windows Forms-Formular sein. "Winres.exe" kann generische RESX- bzw. RESOURCES-Dateien nicht öffnen.|

|Option|BESCHREIBUNG|
|------------|-----------------|
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|

## <a name="remarks"></a>Hinweise

Der Zustand von Elementen der Benutzeroberfläche aus einem Formular in einem Windows Forms-Projekt wird in der Regel in Ressourcendateien gespeichert, bei denen es sich entweder um XML-basierte Dateien mit der Erweiterung ".resx" oder die entsprechenden kompilierten binären Versionen mit der Erweiterung ".resources" handelt. "Winres.exe" ist ein Tool, das eine begrenzte Bearbeitung beider Dateitypen außerhalb der Visual Studio-Entwurfsumgebung ermöglicht. Insbesondere können die folgenden Bearbeitungsvorgänge durchgeführt werden:

- Eine neutrale oder spezifische Kulturressourcendatei kann bearbeitet werden, um die Eigenschaften der Benutzeroberfläche des Formulars oder dessen Steuerelemente zu ändern, z. B. Text, Größe und Position.

- Neutrale oder spezifische Kulturressourcendateien können aus der Standardressourcendatei generiert werden.

- Eine Kulturressourcendatei kann als eine andere Kulturressourcendatei gespeichert werden. So kann z. B. eine Ressourcendatei für Englisch (USA) als Ressourcendatei für Polnisch gespeichert werden. In der Regel wird die neue Datei anschließend bearbeitet, damit sie mit der neuen Kultur kompatibel ist.

Weitere Informationen finden Sie unter [Hierarchical Organization of Resources for Localization (Hierarchische Organisation der Ressourcen für die Lokalisierung)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/756hydy4(v=vs.110)) und [Hierarchical Organization of Resources for Localization (Hierarchische Organisation der Ressourcen für die Lokalisierung)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/756hydy4(v=vs.120)).

"Winres.exe" kann eine RESX-Datei nicht in die zugehörige RESOURCES-Datei konvertieren. Verwenden Sie dazu das Tool "Resgen.exe". Weitere Informationen zu „resgen.exe“ finden Sie unter [Resource File Generator (Resgen.exe)](resgen-exe-resource-file-generator.md).

„Winres.exe“ ist eine grafische Anwendung, die eine Entwurfszeitversion eines Windows Forms-Formulars aus der Ressourcendatei ohne Zugriff auf den Quellcode neu erstellt. „Winres.exe“ hostet den **Windows Forms-Formular-Designer** und das **Eigenschaftenfenster** von Visual Studio. Mithilfe dieser Funktionen ist die visuelle Bearbeitung einer RESOURCES- oder RESX-Datei möglich, die ein Windows Forms-Formular enthält. Lokalisierungsexperten verwenden „Winres.exe“ normalerweise, um Steuerelementbeschriftungen zu bearbeiten und die Position und Größe der einzelnen Steuerelemente so anzupassen, dass die Beschriftungen in der Zielsprache ordnungsgemäß angezeigt werden.

Wenn "Winres.exe" einen bestimmten Steuerelementtyp nicht auflösen kann, wird ein Platzhaltersteuerelement in der lokalisierten RESX- bzw. RESOURCES-Datei erstellt. Das Platzhaltersteuerelement wird im Windows Forms-Formular als schraffiertes Fenster angezeigt. Größe und Position des schraffierten Fensters entsprechen der Größe und Position des Steuerelements selbst. Alle verfügbaren lokalisierbaren Eigenschaften für das Platzhaltersteuerelement werden im **Eigenschaftenfenster** angezeigt. Am Platzhaltersteuerelement vorgenommene Änderungen werden im Steuerelement selbst gespeichert.

## <a name="winresexe-versus-visual-studio"></a>"Winres.exe" im Vergleich zu Visual Studio

Bevor Sie mit dem Lokalisieren der Windows Forms-Formulare einer Anwendung beginnen, sollten Sie sich entscheiden, ob Sie Visual Studio oder "Winres.exe" als Lokalisierungstool verwenden. Aus Gründen der Versionskompatibilität, wie später beschrieben, können Sie möglicherweise nicht zwischen den beiden Tools wechseln.

Der Vorteil von Visual Studio besteht darin, dass Sie es sowohl zum Entwickeln als auch zum Lokalisieren einer Anwendung verwenden können. Wenn Sie nach Abschluss der Entwicklung ein Formular lokalisieren möchten, legen Sie <xref:System.ComponentModel.LocalizableAttribute> des Formulars (die Eigenschaft **Lokalisierbar** im **Eigenschaften**-Editor) auf `true` fest und ändern die Eigenschaft **Sprache** in die gewünschte Zielkultur. Bearbeiten Sie dann die Zeichenfolgen, und passen Sie die Position und Größe der Steuerelemente an, damit die Zeichenfolgen der Zielkultur ordnungsgemäß angezeigt werden. Wenn Sie die lokalisierte RESX-Datei speichern, schreibt Visual Studio nur die lokalisierbaren Eigenschaften (d. h. diejenigen Eigenschaften, die sich in der Zielkultur geändert haben) in die Datei. Visual Studio erstellt automatisch eine Satellitenassembly für die lokalisierte RESX-Datei im richtigen Verzeichnis.

Obwohl in Visual Studio eine integrierte Entwicklungs- und Lokalisierungsumgebung zur Verfügung steht, wird für die Lokalisierung durch Lokalisierungsexperten von Drittanbietern die Verwendung von „Winres.exe“ empfohlen. "Winres.exe" ist ein reines Lokalisierungstool und ermöglicht daher eine sauberere Trennung des Anwendungscodes von den zu lokalisierenden Formularen. Deshalb ist es für die Verwaltung umfangreicher Projekte besser geeignet.

## <a name="using-winresexe"></a>Verwenden von "Winres.exe"

Für die Lokalisierung mithilfe von „Winres.exe“ müssen Sie zunächst unter Verwendung eines visuellen Designers wie dem **Windows Forms-Designer** in Visual Studio eine Anwendung entwickeln. Wenn die Entwicklung beendet ist, legen Sie <xref:System.ComponentModel.LocalizableAttribute> des Formulars (die Eigenschaft **Lokalisierbar** im **Eigenschaften**-Editor) auf `true` fest und leiten dann die RESX-Datei für die Standardkultur an den Lokalisierungsexperten eines Drittanbieters weiter. Diese RESX-Datei enthält zusätzliche Informationen, mit deren Hilfe „Winres.exe“ eine Entwurfszeitversion des Originalformulars erstellt.

> [!NOTE]
> "Winres.exe" kann nicht zum Bearbeiten der Standardressourcendatei verwendet werden. "Winres.exe" interpretiert alle geänderten Eigenschaften als lokalisierte Eigenschaften und speichert diese in der Ressourcendatei für die Zielkultur.

Mithilfe der endgültigen Versionen der Kulturressourcendateien können lokalisierte Versionen der Anwendung erstellt werden. Weitere Informationen finden Sie unter [Ressourcen in Desktop-Apps](../resources/index.md).

„Winres.exe“ weist die folgenden Funktionen und Möglichkeiten auf:

- Winres kann im Einzeldateimodus oder im Visual Studio-Dateimodus ausgeführt werden. Der Einzeldateimodus ist der Legacymodus, in dem umfassende Informationen zu dem Formular und dem zugehörigen Inhalt in der Ressourcendatei gespeichert werden. Im Visual Studio-Modus werden nur kulturelle Änderungen in der Ressourcendatei gespeichert.

- An die linke untere Ecke des Hauptfensters wurde ein Fehlerberichtsfenster angedockt.

- Hotkeys können auf Duplikate überprüft werden: Klicken Sie im Menü **Format** auf den Befehl **HotKeys überprüfen**.

## <a name="version-compatibility"></a>Versionskompatibilität

Sie sollten die Version von „Winres.exe“ verwenden, die mit der von Ihnen verwendeten Version von .NET Framework veröffentlicht wurde. In der folgenden Tabelle werden die kompatiblen Versionen aufgeführt:

|Visual Studio|.NET Framework|Winres.exe|
|-------------------|--------------------|----------------|
|Visual Studio .NET 2002|1.0|1.0|
|Visual Studio .NET 2003|1.1|1.1|
|Visual Studio 2005|2.0|2.0|
|Visual Studio 2008|3.0 und 3.5|3.0 und 3.5|
|Visual Studio 2010|4,0|4,0|
|Visual Studio 2017|4.6|4.6|

> [!NOTE]
> Obwohl der Visual Studio-Dateimodus den Vorteil der Kompatibilität mit Visual Studio bietet, da in ihm nur geänderte Werte in der Ressourcendatei gespeichert werden, müssen sich für "Winres.exe" die übergeordneten Elemente der aktuellen Ressourcendatei in demselben Verzeichnis befinden. Wenn Sie beispielsweise `TestApp.de-DE.resources`, eine Ressourcendatei für Deutsch (Deutschland) bearbeiten möchten, muss die Standardressourcendatei, `TestApp.resx` und möglicherweise auch die kulturneutrale Ressourcendatei, `TestApp.de.resources`, vorliegen.

## <a name="examples"></a>Beispiele

### <a name="to-localize-a-resx-or-resources-file-associated-with-a-form"></a>Lokalisieren einer mit einem Formular verknüpfte RESX- oder RESOURCES-Datei

1. Geben Sie `winres` in der Developer-Eingabeaufforderung ein, um "Winres.exe" auszuführen.

2. Um die Standardressourcen für ein zu lokalisierendes Formular zu öffnen, klicken Sie im Menü **Datei** auf den Befehl **Öffnen**, und navigieren Sie zu der zu öffnenden Datei.

     - oder -

     Geben Sie die zu öffnende Datei beim Starten von "Winres.exe" in der Befehlszeile an.

     Der folgende Befehl startet "Winres.exe" und lädt das mit `TestApp.resx` verknüpfte Formular in den Formular-Designer.

    ```console
    winres TestApp.resx
    ```

     Der folgende Befehl startet "Winres.exe" und lädt das mit `TestApp.resources` verknüpfte Formular in den Formular-Designer.

    ```console
    winres TestApp.resources
    ```

    > [!NOTE]
    > Wenn das Formular, dessen Ressourcen Sie bearbeiten, ein geerbtes Formular ist, muss sowohl die im geerbten Formular enthaltene Assembly als auch die Assembly, die das erbende (abgeleitete) Formular enthält, im globalen Assemblycache (GAC) registriert sein oder sich in demselben Verzeichnis wie "WinRes.exe" befinden. Weitere Informationen zur Installation von .NET Framework-Komponenten in GAC finden Sie unter [Globaler Assemblycache](../app-domains/gac.md).

3. Wählen Sie Steuerelemente in dem Formular aus, und ändern Sie ihre <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft und andere Eigenschaften in die lokalisierte Kultur und die entsprechende Sprache. Damit der lokalisierte Text ordnungsgemäß angezeigt wird, verschieben Sie die Steuerelemente bei Bedarf bzw. ändern ihre Größe.

4. Um die lokalisierte Version der RESX- bzw. RESOURCES-Datei zu speichern, klicken Sie auf das Symbol **Speichern** oder auf den entsprechenden Befehl im Menü **Datei**. Das Fenster **Kultur auswählen** wird angezeigt.

5. Wählen Sie die entsprechende Kultur und den entsprechenden Dateimodus aus, und klicken Sie dann auf **OK**.

   Die Datei wird gespeichert, wobei die Benennungskonvention verwendet wird, die die Laufzeit für lokalisierte Ressourcendateien erwartet. Wenn Sie beispielsweise `TestApp.resources` für Deutsch (Deutschland) lokalisieren, speichert das Tool die Datei als `TestApp.de-DE.resources`. Wenn Sie `TestApp.resx` für Deutsch (Deutschland) lokalisieren, speichert das Tool die Datei als `TestApp.de-DE.resx`. Weitere Informationen zu Benennungskonventionen für Ressourcen finden Sie unter [Verpacken und Bereitstellen von Ressourcen](../resources/packaging-and-deploying-resources-in-desktop-apps.md). Eine Liste der von der Runtime verwendeten vordefinierten Kulturnamen finden Sie unter der Klasse <xref:System.Globalization.CultureInfo>.

## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.LocalizableAttribute>
- <xref:System.Globalization.CultureInfo>
- <xref:System.Resources.ResourceManager>
- <xref:System.Resources.ResourceReader>
- <xref:System.Resources.ResourceWriter>
- [Extras](index.md)
- [Ressourcen in Desktop-Apps](../resources/index.md)
- [Globalisierung und Lokalisierung](../../standard/globalization-localization/index.md)
