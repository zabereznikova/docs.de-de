---
title: Entwickeln Sie ein einfaches Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
ms.openlocfilehash: 5383cee5358dbd260fc6c023d3db607da6b10ea4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742251"
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a>Gewusst wie: Entwickeln eines einfachen Windows Forms-Steuerelements

Dieser Abschnitt führt Sie durch die wichtigsten Schritte zum Erstellen von benutzerdefinierten Windows Forms-Steuerelementen. Das in dieser exemplarischen Vorgehensweise entwickelte einfache Steuerelement ermöglicht die Änderung der Ausrichtung der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft. Es löst keine Ereignisse aus oder behandelt sie.

### <a name="to-create-a-simple-custom-control"></a>So erstellen Sie ein einfaches benutzerdefiniertes Steuerelement

1. Definieren Sie eine Klasse, die sich von <xref:System.Windows.Forms.Control?displayProperty=nameWithType> ableitet.

    ```vb
    Public Class FirstControl
       Inherits Control

    End Class
    ```

    ```csharp
    public class FirstControl:Control {}
    ```

2. Definieren Sie Eigenschaften. (Sie müssen keine Eigenschaften definieren, da ein Steuerelement viele Eigenschaften von der <xref:System.Windows.Forms.Control> Klasse erbt, aber die meisten benutzerdefinierten Steuerelemente definieren in der Regel zusätzliche Eigenschaften.) Das folgende Code Fragment definiert eine Eigenschaft mit dem Namen `TextAlignment`, die `FirstControl` verwendet, um die Anzeige der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft zu formatieren, die von <xref:System.Windows.Forms.Control>geerbt wird. Weitere Informationen zum Definieren von Eigenschaften finden Sie in der [Übersicht über Eigenschaften](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120)).

     [!code-csharp[System.Windows.Forms.FirstControl#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]

     Wenn Sie eine Eigenschaft festlegen, die die visuelle Darstellung des Steuer Elements ändert, müssen Sie die <xref:System.Windows.Forms.Control.Invalidate%2A>-Methode aufrufen, um das Steuerelement neu zu zeichnen. <xref:System.Windows.Forms.Control.Invalidate%2A> ist in der Basisklasse <xref:System.Windows.Forms.Control>definiert.

3. Überschreiben Sie die von <xref:System.Windows.Forms.Control> geerbte geschützte <xref:System.Windows.Forms.Control.OnPaint%2A> Methode, um Renderinglogik für das Steuerelement bereitzustellen Wenn Sie <xref:System.Windows.Forms.Control.OnPaint%2A>nicht überschreiben, kann das Steuerelement nicht selbst gezeichnet werden. Im folgenden Code Fragment zeigt die <xref:System.Windows.Forms.Control.OnPaint%2A>-Methode die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft, die von <xref:System.Windows.Forms.Control> geerbt wurde, mit der Ausrichtung an, die vom `alignmentValue` Feld angegeben wird.

     [!code-csharp[System.Windows.Forms.FirstControl#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]

4. Stellen Sie Attribute für das Steuerelement bereit. Attribute ermöglichen es einem visuellen Designer, Ihr Steuerelement und dessen Eigenschaften und Ereignisse entsprechend zur Entwurfszeit anzuzeigen. Das folgende Codefragment wendet die Attribute auf die Eigenschaft `TextAlignment` an. In einem Designer, wie z. b. Visual Studio, bewirkt das <xref:System.ComponentModel.CategoryAttribute.Category%2A>-Attribut (im Code Fragment gezeigt), dass die Eigenschaft unter einer logischen Kategorie angezeigt wird. Das <xref:System.ComponentModel.DescriptionAttribute.Description%2A>-Attribut bewirkt, dass eine beschreibende Zeichenfolge im unteren Bereich des **Eigenschaften** Fensters angezeigt wird, wenn die `TextAlignment`-Eigenschaft ausgewählt ist. Weitere Informationen zu Attributen finden Sie unter [Entwurfszeitattribute für Komponenten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).

     [!code-csharp[System.Windows.Forms.FirstControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]

5. (optional) Stellen Sie Ressourcen für Ihr Steuerelement zur Verfügung. Sie können eine Ressource, z.B. eine Bitmap für das Steuerelement mit einer Compileroption bereitstellen (`/res` für C#), um Ressourcen mit dem Steuerelement zu verpacken. Zur Laufzeit kann die Ressource mithilfe der Methoden der <xref:System.Resources.ResourceManager>-Klasse abgerufen werden. Weitere Informationen zum Erstellen und Verwenden von Ressourcen finden Sie unter [Ressourcen in Desktop-Apps](../../resources/index.md).

6. Kompilieren Sie das Steuerelement, und stellen Sie es bereit. Führen Sie die folgenden Schritte aus, um `FirstControl,` zu kompilieren und bereitzustellen:

    1. Speichern Sie den Code im folgenden Beispiel als Quelldatei (z.B. als „FirstControl.cs“ oder „FirstControl.vb“).

    2. Kompilieren Sie den Quellcode in eine Assembly, und speichern Sie sie im Verzeichnis der Anwendung. Führen Sie hierfür den folgenden Befehl in dem Verzeichnis aus, das die Quelldatei enthält.

        ```console
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb
        ```

        ```console
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs
        ```

         Die Compileroption `/t:library` benachrichtigt den Compiler, dass es sich bei der erstellten Assembly um eine Bibliothek handelt (nicht um eine ausführbare Assembly). Die Option `/out` gibt den Pfad und den Namen der Assembly an. Die Option `/r` gibt den Namen der Assembly an, auf die durch Ihren Code verwiesen wird. In diesem Beispiel erstellen Sie eine private Assembly, die ausschließlich von Ihren Anwendungen verwendet werden kann. Daher müssen Sie sie im Verzeichnis der Anwendung speichern. Weitere Informationen über das Packen und Bereitstellen eines Steuerelements für die Verteilung finden Sie unter [Bereitstellung](../../deployment/index.md).

Das folgende Beispiel zeigt den Code für `FirstControl`. Das Steuerelement ist im Namespace `CustomWinControls` enthalten. Ein Namespace bietet eine logische Gruppierung von verwandten Typen. Sie können das Steuerelement in einem neuen oder vorhandenen Namespace erstellen. In C# ermöglicht die Deklaration `using` (`Imports` in Visual Basic), dass auf Typen von einem Namespace zugegriffen wird, ohne dass der vollqualifizierte Name des Typs verwendet wird. Im folgenden Beispiel ermöglicht die `using` Deklaration Code den Zugriff auf die-Klasse <xref:System.Windows.Forms.Control> von <xref:System.Windows.Forms?displayProperty=nameWithType> <xref:System.Windows.Forms.Control>, anstatt den voll qualifizierten Namen <xref:System.Windows.Forms.Control?displayProperty=nameWithType>zu verwenden.

[!code-csharp[System.Windows.Forms.FirstControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
[!code-vb[System.Windows.Forms.FirstControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]

## <a name="using-the-custom-control-on-a-form"></a>Verwenden des benutzerdefinierten Steuerelements in einem Formular

Im folgenden Beispiel wird ein einfaches Formular dargestellt, dass `FirstControl` verwendet. Es erstellt drei Instanzen von `FirstControl`, jede mit einem anderen Wert für die Eigenschaft `TextAlignment`.

#### <a name="to-compile-and-run-this-sample"></a>So kompilieren Sie dieses Beispiel und führen es aus

1. Speichern Sie den Code im folgenden Beispiel als Quelldatei („SimpleForm.cs“ oder „SimpleForms.vb“).

2. Kompilieren Sie den Quellcode in eine ausführbare Assembly, indem Sie den folgenden Befehl im Verzeichnis ausführen, das die Quelldatei enthält.

    ```console
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb
    ```

    ```console
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs
    ```

     CustomWinControls. dll ist die Assembly, die die Klasse `FirstControl`enthält. Diese Assembly muss sich im gleichen Verzeichnis befinden wie die Quelldatei für das Formular, das auf sie zugreift („SimpleForm.cs“ oder „SimpleForms.vb“).

3. Führen Sie „SimpleForm.exe“ mit dem folgenden Befehl aus.

    ```console
    SimpleForm
    ```

[!code-csharp[System.Windows.Forms.FirstControl#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
[!code-vb[System.Windows.Forms.FirstControl#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]

## <a name="see-also"></a>Weitere Informationen

- [Eigenschaften in Windows Forms-Steuerelementen](properties-in-windows-forms-controls.md)
- [Ereignisse in Windows Forms-Steuerelementen](events-in-windows-forms-controls.md)
