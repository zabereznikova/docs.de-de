---
title: 'Vorgehensweise: Entwickeln eines einfachen Windows Forms-Steuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
ms.openlocfilehash: 4afa4b9e2c92569df4c8023d7dbfdfb025bf94b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527626"
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a>Vorgehensweise: Entwickeln eines einfachen Windows Forms-Steuerelements
Dieser Abschnitt führt Sie durch die wichtigsten Schritte zum Erstellen von benutzerdefinierten Windows Forms-Steuerelementen. Ein einfache Steuerelement in dieser exemplarischen Vorgehensweise entwickelt ermöglicht die Ausrichtung der <xref:System.Windows.Forms.Control.Text%2A> zu ändernden Eigenschaft. Es löst keine Ereignisse aus oder behandelt sie.  
  
### <a name="to-create-a-simple-custom-control"></a>So erstellen Sie ein einfaches benutzerdefiniertes Steuerelement  
  
1.  Definieren Sie eine Klasse, die sich von <xref:System.Windows.Forms.Control?displayProperty=nameWithType> ableitet.  
  
    ```vb  
    Public Class FirstControl  
       Inherits Control  
  
    End Class  
    ```  
  
    ```csharp  
    public class FirstControl:Control {}  
    ```  
  
2.  Definieren Sie Eigenschaften. (Sie müssen keine Eigenschaften definieren, da ein Steuerelement viele Eigenschaften erbt die <xref:System.Windows.Forms.Control> -Klasse, aber die meisten benutzerdefinierten Steuerelemente definieren zusätzliche Eigenschaften.) Das folgende Codefragment definiert eine Eigenschaft namens `TextAlignment` , `FirstControl` verwendet, um die Anzeige formatieren der <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft vererbt <xref:System.Windows.Forms.Control>. Weitere Informationen zum Definieren von Eigenschaften finden Sie in der [Übersicht über Eigenschaften](https://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52).  
  
     [!code-csharp[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]  
  
     Wenn Sie eine Eigenschaft, die die visuelle Darstellung des Steuerelements ändert festlegen, müssen Sie Aufrufen der <xref:System.Windows.Forms.Control.Invalidate%2A> Methode, um das Steuerelement neu gezeichnet werden. <xref:System.Windows.Forms.Control.Invalidate%2A> wird in der Basisklasse definiert <xref:System.Windows.Forms.Control>.  
  
3.  Überschreiben Sie die geschützte <xref:System.Windows.Forms.Control.OnPaint%2A> Methode geerbt von <xref:System.Windows.Forms.Control> Renderinglogik auf das Steuerelement angeben. Wenn Sie nicht außer Kraft setzen <xref:System.Windows.Forms.Control.OnPaint%2A>, das Steuerelement wird nicht in der Lage, sich selbst zu zeichnen. Im folgenden Codefragment der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode zeigt die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft vererbt <xref:System.Windows.Forms.Control> mit die Ausrichtung anhand der `alignmentValue` Feld.  
  
     [!code-csharp[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]  
  
4.  Stellen Sie Attribute für das Steuerelement bereit. Attribute ermöglichen es einem visuellen Designer, Ihr Steuerelement und dessen Eigenschaften und Ereignisse entsprechend zur Entwurfszeit anzuzeigen. Das folgende Codefragment wendet die Attribute auf die Eigenschaft `TextAlignment` an. In einem Designer wie Visual Studio die <xref:System.ComponentModel.CategoryAttribute.Category%2A> Attribut (Siehe Codefragment) bewirkt, dass die Eigenschaft in einer logischen Kategorie angezeigt werden. Die <xref:System.ComponentModel.DescriptionAttribute.Description%2A> Attribut bewirkt, dass eine beschreibende Zeichenfolge, die am unteren Rand angezeigt werden die **Eigenschaften** Fenster bei der `TextAlignment` Eigenschaft ausgewählt ist. Weitere Informationen zu Attributen finden Sie unter [Entwurfszeitattribute für Komponenten](https://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3).  
  
     [!code-csharp[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]  
  
5.  (optional) Stellen Sie Ressourcen für Ihr Steuerelement zur Verfügung. Sie können eine Ressource, z.B. eine Bitmap für das Steuerelement mit einer Compileroption bereitstellen (`/res` für C#), um Ressourcen mit dem Steuerelement zu verpacken. Zur Laufzeit kann die Ressource mithilfe der Methoden der abgerufen werden die <xref:System.Resources.ResourceManager> Klasse. Weitere Informationen zum Erstellen und Verwenden von Ressourcen finden Sie unter [Ressourcen in Desktop-Apps](../../../../docs/framework/resources/index.md).  
  
6.  Kompilieren Sie das Steuerelement, und stellen Sie es bereit. Führen Sie die folgenden Schritte aus, um `FirstControl,` zu kompilieren und bereitzustellen:  
  
    1.  Speichern Sie den Code im folgenden Beispiel als Quelldatei (z.B. als „FirstControl.cs“ oder „FirstControl.vb“).  
  
    2.  Kompilieren Sie den Quellcode in eine Assembly, und speichern Sie sie im Verzeichnis der Anwendung. Führen Sie hierfür den folgenden Befehl in dem Verzeichnis aus, das die Quelldatei enthält.  
  
        ```console  
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb  
        ```  
  
        ```console 
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs  
        ```  
  
         Die Compileroption `/t:library` benachrichtigt den Compiler, dass es sich bei der erstellten Assembly um eine Bibliothek handelt (nicht um eine ausführbare Assembly). Die Option `/out` gibt den Pfad und den Namen der Assembly an. Die Option `/r` gibt den Namen der Assembly an, auf die durch Ihren Code verwiesen wird. In diesem Beispiel erstellen Sie eine private Assembly, die ausschließlich von Ihren Anwendungen verwendet werden kann. Daher müssen Sie sie im Verzeichnis der Anwendung speichern. Weitere Informationen über das Packen und Bereitstellen eines Steuerelements für die Verteilung finden Sie unter [Bereitstellung](../../../../docs/framework/deployment/index.md).  
  
 Das folgende Beispiel zeigt den Code für `FirstControl`. Das Steuerelement ist im Namespace `CustomWinControls` enthalten. Ein Namespace bietet eine logische Gruppierung von verwandten Typen. Sie können das Steuerelement in einem neuen oder vorhandenen Namespace erstellen. In C# ermöglicht die Deklaration `using` (`Imports` in Visual Basic), dass auf Typen von einem Namespace zugegriffen wird, ohne dass der vollqualifizierte Name des Typs verwendet wird. Im folgenden Beispiel die `using` Deklaration kann Code, den Zugriff auf die Klasse <xref:System.Windows.Forms.Control> aus <xref:System.Windows.Forms?displayProperty=nameWithType> einfach als <xref:System.Windows.Forms.Control> statt verwenden Sie den voll gekennzeichneten Namen <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
 [!code-csharp[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
 [!code-vb[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]  
  
## <a name="using-the-custom-control-on-a-form"></a>Verwenden des benutzerdefinierten Steuerelements in einem Formular  
 Im folgenden Beispiel wird ein einfaches Formular dargestellt, dass `FirstControl` verwendet. Es erstellt drei Instanzen von `FirstControl`, jede mit einem anderen Wert für die Eigenschaft `TextAlignment`.  
  
#### <a name="to-compile-and-run-this-sample"></a>So kompilieren Sie dieses Beispiel und führen es aus  
  
1.  Speichern Sie den Code im folgenden Beispiel als Quelldatei („SimpleForm.cs“ oder „SimpleForms.vb“).  
  
2.  Kompilieren Sie den Quellcode in eine ausführbare Assembly, indem Sie den folgenden Befehl im Verzeichnis ausführen, das die Quelldatei enthält.  
  
    ```console  
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb  
    ```  
  
    ```console 
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs  
    ```  
  
     "CustomWinControls.dll" ist die Assembly, die die Klasse enthält `FirstControl`. Diese Assembly muss sich im gleichen Verzeichnis befinden wie die Quelldatei für das Formular, das auf sie zugreift („SimpleForm.cs“ oder „SimpleForms.vb“).  
  
3.  Führen Sie „SimpleForm.exe“ mit dem folgenden Befehl aus.  
  
    ```console
    SimpleForm  
    ```  
  
 [!code-csharp[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
 [!code-vb[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]  
  
## <a name="see-also"></a>Siehe auch
- [Eigenschaften in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
- [Ereignisse in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)
