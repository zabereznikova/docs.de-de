---
title: Internationale Schriftarten in Windows Forms und Steuerelementen
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
ms.openlocfilehash: 1f9afd575e2de04e0b11556ad34436839e13d968
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693239"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Internationale Schriftarten in Windows Forms und Steuerelementen

Die empfohlene Methode für das Auswählen von Schriftarten werden in internationale Anwendungen Schriftart-Fallback transaktionsanweisungen verwendet werden. Schriftart-fallback-bedeutet, dass das System bestimmt, was das Zeichen Skript gehört.

## <a name="using-font-fallback"></a>Verwenden Schriftart-fallback

Um dieses Feature nutzen zu können, legen Sie nicht die <xref:System.Drawing.Font> -Eigenschaft für das Formular oder ein anderes Element. Die Anwendung verwendet automatisch die Standardschriftart des Systems, die von einer lokalisierten Sprache des Betriebssystems zur anderen unterscheidet. Wenn die Anwendung ausgeführt wird, wird das System automatisch die richtige Schriftart für die Kultur, die im Betriebssystem aktiviert bereitstellen.

Es gibt eine Ausnahme von der Regel der Schriftart an, die zum Ändern der Schriftart wird nicht festgelegt. Dies kann für eine Anwendung wichtig sein in dem der Benutzer eine Schaltfläche, um Text in einem Textfeld angezeigt werden in Fettdruck stellen klickt. Dazu würden Sie eine Funktion zum Ändern der Textfeld-Schriftart fett formatiert ist, schreiben, basierend auf den der Schriftart des Formulars ist. Es ist wichtig, diese Funktion aufrufen, an zwei Orten: in der Schaltfläche <xref:System.Windows.Forms.Control.Click> -Ereignishandler und klicken Sie in der <xref:System.Windows.Forms.Control.FontChanged> -Ereignishandler. Wenn die Funktion, nur in aufgerufen wird der <xref:System.Windows.Forms.Control.Click> -Ereignishandler und einen anderen Teil des Codes ändert die Schriftfamilie für das gesamte Formular, mit dem Rest des Formulars ändert sich nicht im Textfeld.

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

Jedoch wenn Sie die Anwendung zu lokalisieren, möglicherweise die fettformatierung schlecht für bestimmte Sprachen angezeigt. Wenn dies relevant ist, möchten Sie den Lokalisierungsexperten die Schrift in Fettdruck in normalen Text benötigen. Da Lokalisierer in der Regel keine Entwickler sind und keinen Zugriff auf den Quellcode haben, muss diese Option nur für Ressourcendateien, in den Ressourcendateien festgelegt werden. Zu diesem Zweck legen Sie die <xref:System.Drawing.Font.Bold%2A> Eigenschaft `true`. Dies führt in die schriftarteinstellung, die in die Ressourcendateien, in dem Lokalisierungsexperten diese bearbeiten können geschrieben werden. Sie klicken Sie dann Code schreiben, nachdem die `InitializeComponent` Methode, die Schriftart auf beliebige der Schriftart des Formulars ist, jedoch mit den Schriftschnitt in der Ressourcendatei angegeben.

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a>Siehe auch

- [Globalisieren von Windows Forms-Anwendungen](globalizing-windows-forms.md)
- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
