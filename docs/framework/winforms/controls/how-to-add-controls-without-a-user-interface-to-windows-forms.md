---
title: 'Vorgehensweise: Hinzufügen von Steuerelementen ohne Benutzeroberfläche zu Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: 49bf927085d29b60c1d9cf5d61df3894495349db
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210409"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>Vorgehensweise: Hinzufügen von Steuerelementen ohne Benutzeroberfläche zu Windows Forms

Ein nicht visuelles Steuerelement (oder Komponente) bietet Funktionen für Ihre Anwendung. Im Gegensatz zu anderen Steuerelementen Komponenten bieten eine Benutzeroberfläche für dem Benutzer nicht und müssen somit auch nicht auf der Windows Forms-Designer-Oberfläche angezeigt werden. Wenn eine Komponente zu einem Formular hinzugefügt wird, zeigt der Windows Forms-Designer ein veränderbarer am unteren Rand der Form, in dem alle Komponenten angezeigt werden. Nach einem Steuerelement der Komponentenleiste hinzugefügt wurde, können Sie wählen die Komponente aus und legen Sie seine Eigenschaften fest, wie jedes andere Steuerelement im Formular.

## <a name="add-a-component-to-a-windows-form"></a>Hinzufügen einer Komponente zu einem Windows Form

1. Öffnen Sie das Formular in Visual Studio. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Windows Forms im Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).

2. In der **Toolbox**, klicken Sie auf eine Komponente, und ziehen Sie es in Ihrem Formular.

     Die Komponente wird auf der Komponentenleiste angezeigt.

Darüber hinaus können Komponenten zu einem Formular zur Laufzeit hinzugefügt werden. Dies ist ein häufiges Szenario, insbesondere deshalb, weil Komponenten keine visuellen Ausdruck im Gegensatz zu Steuerelementen haben, die eine Benutzeroberfläche verfügen. Im folgenden Beispiel wird eine <xref:System.Windows.Forms.Timer> Komponente wird zur Laufzeit hinzugefügt. (Beachten Sie, dass Visual Studio eine Reihe von verschiedenen Zeitgeber enthält; in diesem Fall verwenden Sie ein Windows Forms <xref:System.Windows.Forms.Timer> Komponente. Weitere Informationen zu den verschiedenen Zeitgeber in Visual Studio, finden Sie unter [Einführung in serverbasierte Timer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)

> [!CAUTION]
> Komponenten haben häufig steuerelementspezifischen Eigenschaften, die für die Komponente effektive Funktionsweise festgelegt werden müssen. Im Fall von der <xref:System.Windows.Forms.Timer> folgenden Komponenten, Sie legen die `Interval` Eigenschaft. Achten Sie darauf, wenn Komponenten zu Ihrem Projekt hinzufügen, die die Eigenschaften für die jeweilige Komponente erforderlich.

## <a name="add-a-component-to-a-windows-form-programmatically"></a>Eine Komponente programmgesteuert zu einem Windows Form hinzufügen

1. Erstellen Sie eine Instanz von der <xref:System.Windows.Forms.Timer> Klasse im Code.

2. Legen Sie die `Interval` Eigenschaft, um die Zeit zwischen den Ticks des Zeitgebers zu bestimmen.

3. Konfigurieren Sie alle anderen erforderlichen Eigenschaften für die Komponente an.

     Der folgende Code zeigt die Erstellung einer <xref:System.Windows.Forms.Timer> mit seiner `Interval` Eigenschaftensatz.

    ```vb
    Public Sub CreateTimer()
       Dim timerKeepTrack As New System.Windows.Forms.Timer
       timerKeepTrack.Interval = 1000
    End Sub
    ```

    ```csharp
    public void createTimer()
    {
       System.Windows.Forms.Timer timerKeepTrack = new
           System.Windows.Forms.Timer();
       timerKeepTrack.Interval = 1000;
    }
    ```

    ```cpp
    public:
       void createTimer()
       {
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew
             System::Windows::Forms::Timer();
          timerKeepTrack->Interval = 1000;
       }
    ```

    > [!IMPORTANT]
    > Sie können Ihrem lokalen Computer über das Netzwerk ein Sicherheitsrisiko durch Verweisen auf eine böswillige UserControl verfügbar machen. Dies wäre nur ein Problem, wenn ein böswilliger Benutzer erstellt ein schädliches benutzerdefiniertes Steuerelement, indem Sie versehentlich zu Ihrem Projekt hinzufügen.

## <a name="see-also"></a>Siehe auch

- [Windows Forms-Steuerelemente](index.md)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Vorgehensweise: Hinzufügen von ActiveX-Steuerelemente zu Windows Forms](how-to-add-activex-controls-to-windows-forms.md)
- [Vorgehensweise: Kopieren von Steuerelementen zwischen Windows Forms](how-to-copy-controls-between-windows-forms.md)
- [Einfügen von Steuerelementen in Windows Forms](putting-controls-on-windows-forms.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
- [Windows Forms-Steuerelemente nach Funktion](windows-forms-controls-by-function.md)
