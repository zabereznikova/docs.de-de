---
title: Winres.exe (Windows Forms Resource Editor-Tool)
ms.date: 05/21/2018
helpviewer_keywords:
- Winres.exe
- Windows Forms Resource Editor
- localization
- Windows Forms, localization
- forms, localizing
- resx files
- .resx files
ms.assetid: cb8bc835-9221-4888-af53-1a4f5fad6c48
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14e90916261250452c1f07e66a46bee400da0428
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2018
---
# <a name="winresexe-windows-forms-resource-editor"></a>Winres.exe (Windows Forms Resource Editor-Tool)
Der Windows Forms Resource Editor, "Winres.exe", ist ein visuelles Layouttool, das Lokalisierungsexperten beim Lokalisieren von Ressourcen der Windows Forms-Benutzeroberfläche unterstützt, die von Formularen verwendet werden. Die als Eingabe für "Winres.exe" verwendeten RESX- oder RESOURCES-Dateien können unter Verwendung einer visuellen Entwurfsumgebung, wie Microsoft Visual Studio, erstellt werden. Informationen zum Bereitstellen von Ressourcen in .NET Framework-Anwendungen finden Sie unter [Ressourcen in Desktop-Apps](../../../docs/framework/resources/index.md).  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Zum Ausführen des Tools verwenden Sie die Developer-Eingabeaufforderung (oder die Visual Studio-Eingabeaufforderung in Windows 7). Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  

> [!IMPORTANT]
> Sie sollten RESX-Dateien nur dann laden und verwenden, wenn die Quelle vertrauenswürdig ist. RESX-Dateien können ausführbaren Code enthalten und sollten bei der Sicherheit wie ausführbare Dateien (.exe) behandelt werden.

 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```  
winres resourceFile   
winres /?   
```  
  
## <a name="remarks"></a>Hinweise  
  
|Argument|description|  
|--------------|-----------------|  
|`resourceFile`|Die zu lokalisierende Ressourcendatei. Diese Datei muss ein als RESX- oder RESOURCES-Datei durch den Visual Studio-Designer generiertes Windows Forms-Formular sein. "Winres.exe" kann generische RESX- bzw. RESOURCES-Dateien nicht öffnen.|  
  
|Option|description|  
|------------|-----------------|  
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
 Der Zustand von Elementen der Benutzeroberfläche aus einem Formular in einem Windows Forms-Projekt wird in der Regel in Ressourcendateien gespeichert, bei denen es sich entweder um XML-basierte Dateien mit der Erweiterung ".resx" oder die entsprechenden kompilierten binären Versionen mit der Erweiterung ".resources" handelt. "Winres.exe" ist ein Tool, das eine begrenzte Bearbeitung beider Dateitypen außerhalb der Visual Studio-Entwurfsumgebung ermöglicht. Insbesondere können die folgenden Bearbeitungsvorgänge durchgeführt werden:  
  
-   Eine neutrale oder spezifische Kulturressourcendatei kann bearbeitet werden, um die Eigenschaften der Benutzeroberfläche des Formulars oder dessen Steuerelemente zu ändern, z. B. Text, Größe und Position.  
  
-   Neutrale oder spezifische Kulturressourcendateien können aus der Standardressourcendatei generiert werden.  
  
-   Eine Kulturressourcendatei kann als eine andere Kulturressourcendatei gespeichert werden. So kann z. B. eine Ressourcendatei für Englisch (USA) als Ressourcendatei für Polnisch gespeichert werden. In der Regel wird die neue Datei anschließend bearbeitet, damit sie mit der neuen Kultur kompatibel ist.  
  
 Weitere Informationen finden Sie unter [Hierarchical Organization of Resources for Localization (Hierarchische Organisation der Ressourcen für die Lokalisierung)](http://msdn.microsoft.com/library/756hydy4\(v=vs.110\)) und [Hierarchical Organization of Resources for Localization (Hierarchische Organisation der Ressourcen für die Lokalisierung)](http://msdn.microsoft.com/library/756hydy4\(v=vs.120\)).  
  
 "Winres.exe" kann eine RESX-Datei nicht in die zugehörige RESOURCES-Datei konvertieren. Verwenden Sie dazu das Tool "Resgen.exe". Weitere Informationen zu „resgen.exe“ finden Sie unter [Resource File Generator (Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md).  
  
 „Winres.exe“ ist eine grafische Anwendung, die eine Entwurfszeitversion eines Windows Forms-Formulars aus der Ressourcendatei ohne Zugriff auf den Quellcode neu erstellt. "Winres.exe" hostet den Windows Forms-Designer und das Eigenschaftenfenster von Visual Studio. Mithilfe dieser Funktionen ist die visuelle Bearbeitung einer RESOURCES- oder RESX-Datei möglich, die ein Windows Forms-Formular enthält. Lokalisierungsexperten verwenden "Winres.exe" normalerweise, um Steuerelementbeschriftungen zu bearbeiten und die Position und Größe der einzelnen Steuerelemente so anzupassen, dass die Beschriftungen in der Zielsprache ordnungsgemäß angezeigt werden.  
  
 Wenn "Winres.exe" einen bestimmten Steuerelementtyp nicht auflösen kann, wird ein Platzhaltersteuerelement in der lokalisierten RESX- bzw. RESOURCES-Datei erstellt. Das Platzhaltersteuerelement wird im Windows Forms-Formular als schraffiertes Fenster angezeigt. Größe und Position des schraffierten Fensters entsprechen der Größe und Position des Steuerelements selbst. Alle verfügbaren lokalisierbaren Eigenschaften für das Platzhaltersteuerelement werden im Eigenschaftenfenster angezeigt. Am Platzhaltersteuerelement vorgenommene Änderungen werden im Steuerelement selbst gespeichert.  
  
## <a name="winresexe-versus-visual-studio"></a>"Winres.exe" im Vergleich zu Visual Studio  
 Bevor Sie mit dem Lokalisieren der Windows Forms-Formulare einer Anwendung beginnen, sollten Sie sich entscheiden, ob Sie Visual Studio oder "Winres.exe" als Lokalisierungstool verwenden. Aus Gründen der Versionskompatibilität, wie später beschrieben, können Sie möglicherweise nicht zwischen den beiden Tools wechseln.  
  
 Der Vorteil von Visual Studio besteht darin, dass Sie es sowohl zum Entwickeln als auch zum Lokalisieren einer Anwendung verwenden können. Um ein Formular nach Abschluss der Entwicklung zu lokalisieren, legen Sie <xref:System.ComponentModel.LocalizableAttribute> des Formulars (die **Localizable**-Eigenschaft im Eigenschaften-Editor) auf `true` fest und ändern die Eigenschaft **Language** in die gewünschte Zielkultur. Bearbeiten Sie dann die Zeichenfolgen, und passen Sie die Position und Größe der Steuerelemente an, damit die Zeichenfolgen der Zielkultur ordnungsgemäß angezeigt werden. Wenn Sie die lokalisierte RESX-Datei speichern, schreibt Visual Studio nur die lokalisierbaren Eigenschaften (d. h. diejenigen Eigenschaften, die sich in der Zielkultur geändert haben) in die Datei. Visual Studio erstellt automatisch eine Satellitenassembly für die lokalisierte RESX-Datei im richtigen Verzeichnis.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](http://msdn.microsoft.com/library/y99d1cd3\(v=vs.110\)).  
  
 Obwohl in Visual Studio eine integrierte Entwicklungs- und Lokalisierungsumgebung zur Verfügung steht, wird für die Lokalisierung durch Lokalisierungsexperten von Drittanbietern die Verwendung von "Winres.exe" empfohlen. "Winres.exe" ist ein reines Lokalisierungstool und ermöglicht daher eine sauberere Trennung des Anwendungscodes von den zu lokalisierenden Formularen. Deshalb ist es für die Verwaltung umfangreicher Projekte besser geeignet.  
  
## <a name="using-winresexe"></a>Verwenden von "Winres.exe"  
 Um mithilfe von "Winres.exe" zu lokalisieren, müssen Sie zunächst unter Verwendung eines visuellen Designers, wie dem Forms-Designer in Visual Studio, eine Anwendung entwickeln. Wenn die Entwicklung beendet ist, legen Sie <xref:System.ComponentModel.LocalizableAttribute> des Formulars (die **Localizable**-Eigenschaft im Eigenschaften-Editor) auf `true` fest und leiten dann die RESX-Datei für die Standardkultur an den Lokalisierungsexperten eines Drittanbieters weiter. Diese RESX-Datei enthält zusätzliche Informationen, mit deren Hilfe „Winres.exe“ eine Entwurfszeitversion des Originalformulars erstellt.  
  
> [!CAUTION]
>  "Winres.exe" kann nicht zum Bearbeiten der Standardressourcendatei verwendet werden. "Winres.exe" interpretiert alle geänderten Eigenschaften als lokalisierte Eigenschaften und speichert diese in der Ressourcendatei für die Zielkultur.  
  
 Mithilfe der endgültigen Versionen der Kulturressourcendateien können lokalisierte Versionen der Anwendung erstellt werden. Weitere Informationen finden Sie unter [Ressourcen in Desktop-Apps](../../../docs/framework/resources/index.md).  
  
 Version 2.0 von „Winres.exe“ weist die folgenden Funktionen und Möglichkeiten auf:  
  
-   Winres kann im Einzeldateimodus oder im Visual Studio-Dateimodus ausgeführt werden. Der Einzeldateimodus ist der Legacymodus, in dem umfassende Informationen zu dem Formular und dem zugehörigen Inhalt in der Ressourcendatei gespeichert werden. Im Visual Studio-Modus werden nur kulturelle Änderungen in der Ressourcendatei gespeichert.  
  
-   Der Oberfläche wurde in der linken unteren Ecke des Hauptfensters ein Fehlerberichtsfenster hinzugefügt.  
  
-   HotKeys können auf Duplikate überprüft werden: Klicken Sie im Menü „Format“ auf den Befehl **HotKeys überprüfen**.  
  
## <a name="version-compatibility"></a>Versionskompatibilität  
 Da das Format der Ressourcendateien zwischen Visual Studio .NET 2002 und Visual Studio 2005 geändert wurde, wurde auch "Winres.exe" aus Kompatibilitätsgründen geändert. Sie sollten daher stets die Version von "Winres.exe" verwenden, die mit der Version von .NET Framework veröffentlicht wurde, mit der Sie die Anwendung erstellen. Die kompatiblen Versionen sind in der folgenden Tabelle aufgelistet.  
  
|Visual Studio|.NET Framework|Winres.exe|  
|-------------------|--------------------|----------------|  
|Visual Studio .NET 2002|1.0|1.0|  
|Visual Studio .NET 2003|1.1|1.1|  
|Visual Studio 2005|2.0|2.0|  
|Visual Studio 2008|3.0 und 3.5|3.0 und 3.5|  
|Visual Studio 2010|4.0|4.0|  
  
 Wenn Sie versuchen, eine ältere Ressourcendatei mit Version 2.0 von "Winres.exe" zu öffnen, werden Sie aufgefordert, das Format der Datei zu aktualisieren, damit diese mit Version 2.0 von .NET Framework kompatibel ist.  
  
 In Versionen von .NET Framework vor Version 2.0 haben "Winres.exe" und der Forms-Designer in Visual Studio nicht kompatible kulturneutrale und kulturspezifische Ressourcendateien erstellt. Daher konnten Sie nach Beginn des Lokalisierungsprozesses nur noch ein Tool verwenden. Mit Version 2.0 von "Winres.exe" wurde jedoch der Visual Studio-Dateimodus hinzugefügt. Wie der Name impliziert, kann eine in diesem Kompatibilitätsmodus gespeicherte Ressourcendatei mit beiden dieser Tools bearbeitet werden.  
  
> [!NOTE]
>  Obwohl der Visual Studio-Dateimodus den Vorteil der Kompatibilität mit Visual Studio bietet, da in ihm nur geänderte Werte in der Ressourcendatei gespeichert werden, müssen sich für "Winres.exe" die übergeordneten Elemente der aktuellen Ressourcendatei in demselben Verzeichnis befinden. Wenn Sie beispielsweise `TestApp.de-DE.resources`, eine Ressourcendatei für Deutsch (Deutschland) bearbeiten möchten, muss die Standardressourcendatei, `TestApp.resx` und möglicherweise auch die kulturneutrale Ressourcendatei, `TestApp.de.resources`, vorliegen.  
  
## <a name="examples"></a>Beispiele  
  
#### <a name="to-localize-a-resx-or-resources-file-associated-with-a-form"></a>Lokalisieren einer mit einem Formular verknüpfte RESX- oder RESOURCES-Datei  
  
1.  Geben Sie `winres` in der Developer-Eingabeaufforderung ein, um "Winres.exe" auszuführen.  
  
2.  Um die Standardressourcen für ein zu lokalisierendes Formular zu öffnen, klicken Sie im Menü **Datei** auf den Befehl **Öffnen**, und navigieren Sie zu der zu öffnenden Datei.  
  
     - oder -   
  
     Geben Sie die zu öffnende Datei beim Starten von "Winres.exe" in der Befehlszeile an.  
  
     Der folgende Befehl startet "Winres.exe" und lädt das mit `TestApp.resx` verknüpfte Formular in den Formular-Designer.  
  
    ```  
    winres TestApp.resx  
    ```  
  
     Der folgende Befehl startet "Winres.exe" und lädt das mit `TestApp.resources` verknüpfte Formular in den Formular-Designer.  
  
    ```  
    winres TestApp.resources  
    ```  
  
    > [!NOTE]
    >  Wenn das Formular, dessen Ressourcen Sie bearbeiten, ein geerbtes Formular ist, muss sowohl die im geerbten Formular enthaltene Assembly als auch die Assembly, die das erbende (abgeleitete) Formular enthält, im globalen Assemblycache (GAC) registriert sein oder sich in demselben Verzeichnis wie "WinRes.exe" befinden. Weitere Informationen zur Installation von .NET Framework-Komponenten in GAC finden Sie unter [Globaler Assemblycache](../../../docs/framework/app-domains/gac.md).  
  
3.  Wählen Sie Steuerelemente in dem Formular aus, und ändern Sie ihre <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft und andere Eigenschaften in die lokalisierte Kultur und die entsprechende Sprache. Damit der lokalisierte Text ordnungsgemäß angezeigt wird, verschieben Sie die Steuerelemente bei Bedarf bzw. ändern ihre Größe.  
  
4.  Um die lokalisierte Version der RESX- bzw. RESOURCES-Datei zu speichern, klicken Sie auf das Symbol **Speichern** oder auf den entsprechenden Befehl im Menü **Datei**. Das Fenster **Kultur auswählen** wird angezeigt.  
  
5.  Wählen Sie die entsprechende Kultur und den entsprechenden Dateimodus aus, und klicken Sie dann auf **OK**. Die Datei wird gespeichert, wobei die Benennungskonvention verwendet wird, die die Laufzeit für lokalisierte Ressourcendateien erwartet. Wenn Sie beispielsweise `TestApp.resources` für Deutsch (Deutschland) lokalisieren, speichert das Tool die Datei als `TestApp.de-DE.resources`. Wenn Sie `TestApp.resx` für Deutsch (Deutschland) lokalisieren, speichert das Tool die Datei als `TestApp.de-DE.resx`. Weitere Informationen zu Benennungskonventionen für Ressourcen finden Sie unter [Verpacken und Bereitstellen von Ressourcen](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md). Eine Liste der von der Runtime verwendeten vordefinierten Kulturnamen finden Sie unter der Klasse <xref:System.Globalization.CultureInfo>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ComponentModel.LocalizableAttribute>  
 <xref:System.Globalization.CultureInfo>  
 <xref:System.Resources.ResourceManager>  
 <xref:System.Resources.ResourceReader>  
 <xref:System.Resources.ResourceWriter>  
 [Extras](../../../docs/framework/tools/index.md)  
 [Ressourcen in Desktop-Apps](../../../docs/framework/resources/index.md)  
 [Globalisierung und Lokalisierung](../../../docs/standard/globalization-localization/index.md)
