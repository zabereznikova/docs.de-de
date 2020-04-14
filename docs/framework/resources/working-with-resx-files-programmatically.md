---
title: Programmgesteuertes Arbeiten mit RESX-Dateien
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resource files, .resx files
- .resx files
ms.assetid: 168f941a-2b84-43f8-933f-cf4a8548d824
ms.openlocfilehash: 3b84d77e4ac9b9889d1bc2f08e5ead6b81deecb0
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243036"
---
# <a name="work-with-resx-files-programmatically"></a>Programmgesteuertes Arbeiten mit RESX-Dateien

Da XML-Ressourcendateien (RESX) aus ordnungsgemäß definiertem XML-Code bestehen müssen, einschließlich eines Headers, der einem bestimmten Schema entsprechen muss, und auf den Daten in Name/Wert-Paaren folgen, werden Sie vermutlich feststellen, dass das manuelle Erstellen dieser Dateien ziemlich fehlerträchtig ist. Alternativ können Sie RESX-Dateien programmgesteuert mithilfe von Typen und Elementen aus der .NET-Klassenbibliothek erstellen. Sie können die .NET-Klassenbibliothek auch zum Abrufen der in RESX-Dateien gespeicherten Ressourcen verwenden. In diesem Artikel wird erläutert, wie <xref:System.Resources> Sie die Typen und Member im Namespace verwenden können, um mit .resx-Dateien zu arbeiten.

In diesem Artikel wird das Arbeiten mit XML-Dateien (.resx) erläutert, die Ressourcen enthalten. Informationen zum Arbeiten mit binären Ressourcendateien, die <xref:System.Resources.ResourceManager>in Assemblys eingebettet wurden, finden Sie unter .

> [!WARNING]
> Es gibt nicht programmgesteuerte Verfahren zum Arbeiten mit RESX-Dateien. Wenn Sie einem Visual [Studio-Projekt](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) eine Ressourcendatei hinzufügen, stellt Visual Studio eine Schnittstelle zum Erstellen und Verwalten einer .resx-Datei bereit und konvertiert die .resx-Datei automatisch zur Kompilierungszeit in eine .resources-Datei. Ferner können Sie RESX-Dateien in einem Texteditor direkt bearbeiten. Um eine Beschädigung der Datei zu vermeiden, müssen Sie allerdings sorgfältig darauf achten, keine der in der Datei gespeicherten binären Informationen zu verändern.

## <a name="create-a-resx-file"></a>Erstellen einer RESX-Datei

Sie können die Klasse <xref:System.Resources.ResXResourceWriter?displayProperty=nameWithType> verwenden, um eine RESX-Datei programmgesteuert zu erstellen, indem Sie folgende Schritte ausführen:

1. Instanziieren Sie ein <xref:System.Resources.ResXResourceWriter> -Objekt, indem Sie die <xref:System.Resources.ResXResourceWriter.%23ctor%28System.String%29> -Methode aufrufen und den Namen der RESX-Datei angeben. Der Dateiname muss die Erweiterung „.resx“ enthalten. Wenn Sie das <xref:System.Resources.ResXResourceWriter> -Objekt in einem `using` -Block instanziieren, müssen Sie die Methode <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> in Schritt 3 nicht explizit aufrufen.

2. Rufen Sie die <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> -Methode für jede Ressource auf, die Sie der Datei hinzufügen möchten. Verwenden Sie die Überladungen dieser Methode, um Zeichenfolgen-, Objekt- und binäre Daten (Bytearray) hinzuzufügen. Wenn es sich bei der Ressource um ein Objekt handelt, muss es serialisierbar sein.

3. Rufen Sie die <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> -Methode auf, um die Ressourcendatei zu generieren und alle Ressourcen freizugeben. Wenn das <xref:System.Resources.ResXResourceWriter> -Objekt innerhalb eines `using` -Blocks erstellt wurde, werden Ressourcen in die RESX-Datei geschrieben, und die vom <xref:System.Resources.ResXResourceWriter> -Objekt verwendeten Ressourcen werden am Ende des `using` -Blocks freigegeben.

Die resultierende RESX-Datei weist den entsprechenden Header und ein `data` -Kennzeichen für jede Ressource auf, die von der <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> -Methode hinzugefügt wurde.

> [!WARNING]
> Verwenden Sie Ressourcendateien nicht, um Kennwörter, sicherheitsrelevante Informationen oder private Daten zu speichern.

Im folgenden Beispiel wird eine RESX-Datei mit dem Namen "CarResources.resx" erstellt, mit der sechs Zeichenfolgen, ein Symbol und zwei anwendungsdefinierte Objekte (zwei `Automobile` -Objekte) gespeichert werden. Die `Automobile` Klasse, die im Beispiel definiert und instanziiert wird, wird mit dem <xref:System.SerializableAttribute> Attribut markiert.

[!code-csharp[Conceptual.Resources.ResX#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resx/cs/create1.cs#1)]
[!code-vb[Conceptual.Resources.ResX#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resx/vb/create1.vb#1)]

> [!TIP]
> Sie können [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) auch verwenden, um .resx-Dateien zu erstellen. Zum Zeitpunkt der Kompilierung verwendet Visual Studio den [Resource File Generator (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) , um die RESX-Datei in eine binäre Ressourcendatei (RESOURCES) zu konvertieren, und bettet sie entweder in eine Anwendungsassembly oder in eine Satellitenassembly ein.

Eine RESX-Datei kann nicht in eine von der Laufzeitumgebung ausführbare Datei eingebettet oder in eine Satellitenassembly kompiliert werden. Sie müssen die RESX-Datei mithilfe des [Resource File Generator (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md)in eine binäre Ressourcendatei (RESOURCES) konvertieren. Die resultierende RESOURCES-Datei kann dann in eine Anwendungsassembly oder eine Satellitenassembly eingebettet werden. Weitere Informationen finden Sie unter [Creating Resource Files](creating-resource-files-for-desktop-apps.md).

## <a name="enumerate-resources"></a>Aufzählen der Ressourcen
 In bestimmten Fällen müssen anstelle einer bestimmten alle Ressourcen aus einer RESX-Datei abgerufen werden. Zu diesem Zweck können Sie die Klasse <xref:System.Resources.ResXResourceReader?displayProperty=nameWithType> verwenden, die einen Enumerator für alle in der RESX-Datei enthaltenen Ressourcen enthält. Die <xref:System.Resources.ResXResourceReader?displayProperty=nameWithType> -Klasse implementiert <xref:System.Collections.IDictionaryEnumerator>, der ein <xref:System.Collections.DictionaryEntry> -Objekt zurückgibt, das für jede Iteration der Schleife eine bestimmte Ressource darstellt. Seine <xref:System.Collections.DictionaryEntry.Key%2A?displayProperty=nameWithType> -Eigenschaft gibt den Schlüssel der Ressource und seine <xref:System.Collections.DictionaryEntry.Value%2A?displayProperty=nameWithType> -Eigenschaft den Wert der Ressource zurück.

 Im folgenden Beispiel wird ein <xref:System.Resources.ResXResourceReader> -Objekt für die im vorhergehenden Beispiel erstellte Datei „CarResources.resx“ erstellt, das durch die Ressourcendatei iteriert. Es fügt die zwei in der Ressourcendatei definierten `Automobile` -Objekte einem <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> und fünf der sechs Zeichenfolgen einem <xref:System.Collections.SortedList> -Objekt hinzu. Die Werte in dem <xref:System.Collections.SortedList> -Objekt werden in ein Parameterarray konvertiert, das zum Anzeigen von Spaltenüberschriften in der Konsole verwendet wird. Die Werte der Eigenschaft `Automobile` werden ebenfalls in der Konsole angezeigt.

 [!code-csharp[Conceptual.Resources.ResX#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resx/cs/enumerate1.cs#2)]
 [!code-vb[Conceptual.Resources.ResX#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resx/vb/enumerate1.vb#2)]

## <a name="retrieve-a-specific-resource"></a>Abrufen einer bestimmten Ressource
 Über das Aufzählen der Elemente in einer RESX-Datei hinaus können Sie mithilfe der <xref:System.Resources.ResXResourceSet?displayProperty=nameWithType> -Klasse eine bestimmte Ressource anhand des Namens abrufen. Die <xref:System.Resources.ResourceSet.GetString%28System.String%29?displayProperty=nameWithType> -Methode ruft den Wert einer benannten Zeichenfolgenressource ab. Die <xref:System.Resources.ResourceSet.GetObject%28System.String%29?displayProperty=nameWithType> -Methode ruft den Wert eines benannten Objekts oder Binärdaten ab. Die Methode gibt ein Objekt zurück, für das anschließend eine Umwandlung (in C#) oder Konvertierung (in Visual Basic) in ein Objekt des geeigneten Typs erfolgen muss.

 Im folgenden Beispiel wird die Überschriftenzeichenfolge eines Formulars und dessen Symbol anhand des Ressourcennamens abgerufen. Außerdem werden die von der Anwendung definierten `Automobile`-Objekte abgerufen, die im vorherigen Beispiel verwendet wurden, und in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement angezeigt.

 [!code-csharp[Conceptual.Resources.ResX#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resx/cs/retrieve1.cs#3)]
 [!code-vb[Conceptual.Resources.ResX#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resx/vb/retrieve1.vb#3)]

## <a name="convert-resx-files-to-binary-resources-files"></a>Konvertieren von RESX-Dateien in binäre RESOURCES-Dateien
 Das Konvertieren von RESX-Dateien in eingebettete binäre Ressourcendateien (RESOURCES) bietet erhebliche Vorteile. Obwohl RESX-Dateien in der Entwicklungsphase einer Anwendung leicht zu lesen und zu verwalten sind, sind sie nur selten in den fertigen Anwendungen enthalten. Wenn sie als Teil einer Anwendung verteilt werden, liegen sie als separate Dateien vor, getrennt von der ausführbaren Programmdatei und ihren begleitenden Bibliotheken. Im Unterschied dazu sind RESOURCES-Dateien in die ausführbare Programmdatei oder ihre begleitenden Assemblys eingebettet. Außerdem wird beim Einsatz von RESX-Dateien zur Laufzeit bei lokalisierten Anwendungen der Entwickler für die Behandlung des Ressourcenfallbacks in die Pflicht genommen. Wenn demgegenüber eine Sammlung von Satellitenassemblys erstellt wurde, die eingebettete RESOURCES-Dateien enthalten, übernimmt die Common Language Runtime die Zuständigkeit für den Ressourcenfallbackvorgang.

 Zum Konvertieren einer RESX-Datei in eine RESOURCES-Datei wird der [Resource File Generator (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md)verwendet, der die folgende grundlegende Syntax aufweist:

 **Resgen.exe** *.resxDateiname*

 Das Ergebnis ist eine binäre Ressourcendatei, die den gleichen Stammdateinamen wie die RESX-Datei und darüber hinaus eine RESOURCES-Dateierweiterung aufweist. Diese Datei kann dann zum Zeitpunkt der Kompilierung in eine ausführbare Datei oder eine Bibliothek kompiliert werden. Wenn Sie den Visual Basic-Compiler verwenden, verwenden Sie die folgende Syntax, um eine RESOURCES-Datei in die ausführbare Programmdatei einer Anwendung einzubetten:

 **vbc** *Dateiname* **.vb /resource:** *.Name_der_Ressourcendatei*

 Wenn Sie C# verwenden, lautet die Syntax wie folgt:

 **csc** *Dateiname* **.cs /resource:** *.Name_der_Ressourcendatei*

 Die RESOURCES-Datei kann mithilfe von [Assembly Linker (AL.exe)](../tools/al-exe-assembly-linker.md)auch in eine Satellitenassembly eingebettet werden. Dafür gilt diese Syntax:

 **al** *Name_der_Ressourcendatei* **/out:** *Name_der_Assemblydatei*

## <a name="see-also"></a>Siehe auch

- [Creating Resource Files](creating-resource-files-for-desktop-apps.md)
- [Resgen.exe (Ressourcendateigenerator)](../tools/resgen-exe-resource-file-generator.md)
- [Al.exe (Assembly Linker)](../tools/al-exe-assembly-linker.md)
