---
title: Internationale Schriftarten in Formularen und Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 59dde6bb384d644321a8ff5674d735f8e6d36fd0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743520"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Internationale Schriftarten in Windows Forms und Steuerelementen

In internationalen Anwendungen ist die empfohlene Methode zum Auswählen von Schriftarten die Verwendung eines Schriftart Fallbacks, wenn dies möglich ist. Der Schriftart Fall Back bedeutet, dass das System bestimmt, zu welchem Skript das Zeichen gehört.

## <a name="using-font-fallback"></a>Verwenden eines Schriftart-Fallbacks

Um dieses Feature nutzen zu können, legen Sie die <xref:System.Drawing.Font>-Eigenschaft für das Formular oder ein anderes Element nicht fest. Die Anwendung verwendet automatisch die Standard Schriftart des Systems, die sich von einer lokalisierten Sprache des Betriebssystems zu einer anderen unterscheidet. Wenn die Anwendung ausgeführt wird, stellt das System automatisch die richtige Schriftart für die im Betriebssystem ausgewählte Kultur bereit.

Es gibt eine Ausnahme von der Regel, bei der die Schriftart nicht festgelegt wird. Dies dient zum Ändern des Schrift Grads. Dies ist möglicherweise wichtig für eine Anwendung, in der der Benutzer auf eine Schaltfläche klickt, damit Text in einem Textfeld in Fett Schrift angezeigt wird. Dazu würden Sie eine Funktion schreiben, die den Schrift Schnitt des Textfelds in fett formatiert, je nachdem, was die Schriftart des Formulars ist. Es ist wichtig, diese Funktion an zwei Stellen aufzurufen: im <xref:System.Windows.Forms.Control.Click> Ereignishandler der Schaltfläche und im <xref:System.Windows.Forms.Control.FontChanged>-Ereignishandler. Wenn die Funktion nur im <xref:System.Windows.Forms.Control.Click> Ereignishandler aufgerufen wird und ein anderer Teil des Codes die Schriftfamilie des gesamten Formulars ändert, ändert sich das Textfeld nicht mit dem Rest des Formulars.

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

Wenn Sie die Anwendung jedoch lokalisieren, kann die Fett Schrift für bestimmte Sprachen schlecht angezeigt werden. Wenn dies ein Problem ist, sollten die Lokalisierer die Möglichkeit haben, die Schriftart von Fett zu regulärem Text zu wechseln. Da Lokalisierungen in der Regel keine Entwickler sind und keinen Zugriff auf den Quellcode haben, sondern nur auf Ressourcen Dateien, muss diese Option in den Ressourcen Dateien festgelegt werden. Hierzu legen Sie die <xref:System.Drawing.Font.Bold%2A>-Eigenschaft auf `true`fest. Dies führt dazu, dass die Schriftart Einstellung in die Ressourcen Dateien geschrieben wird, wo Sie von Lokalisierern bearbeitet werden können. Anschließend schreiben Sie den Code nach der `InitializeComponent`-Methode, um die Schriftart basierend auf der Schriftart des Formulars zurückzusetzen, aber mit dem Schrift Schnitt, der in der Ressourcen Datei angegeben ist.

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
