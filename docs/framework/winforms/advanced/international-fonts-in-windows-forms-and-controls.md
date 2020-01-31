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
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="89327-102">Internationale Schriftarten in Windows Forms und Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="89327-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="89327-103">In internationalen Anwendungen ist die empfohlene Methode zum Auswählen von Schriftarten die Verwendung eines Schriftart Fallbacks, wenn dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="89327-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="89327-104">Der Schriftart Fall Back bedeutet, dass das System bestimmt, zu welchem Skript das Zeichen gehört.</span><span class="sxs-lookup"><span data-stu-id="89327-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="89327-105">Verwenden eines Schriftart-Fallbacks</span><span class="sxs-lookup"><span data-stu-id="89327-105">Using font fallback</span></span>

<span data-ttu-id="89327-106">Um dieses Feature nutzen zu können, legen Sie die <xref:System.Drawing.Font>-Eigenschaft für das Formular oder ein anderes Element nicht fest.</span><span class="sxs-lookup"><span data-stu-id="89327-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="89327-107">Die Anwendung verwendet automatisch die Standard Schriftart des Systems, die sich von einer lokalisierten Sprache des Betriebssystems zu einer anderen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="89327-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="89327-108">Wenn die Anwendung ausgeführt wird, stellt das System automatisch die richtige Schriftart für die im Betriebssystem ausgewählte Kultur bereit.</span><span class="sxs-lookup"><span data-stu-id="89327-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="89327-109">Es gibt eine Ausnahme von der Regel, bei der die Schriftart nicht festgelegt wird. Dies dient zum Ändern des Schrift Grads.</span><span class="sxs-lookup"><span data-stu-id="89327-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="89327-110">Dies ist möglicherweise wichtig für eine Anwendung, in der der Benutzer auf eine Schaltfläche klickt, damit Text in einem Textfeld in Fett Schrift angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="89327-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="89327-111">Dazu würden Sie eine Funktion schreiben, die den Schrift Schnitt des Textfelds in fett formatiert, je nachdem, was die Schriftart des Formulars ist.</span><span class="sxs-lookup"><span data-stu-id="89327-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="89327-112">Es ist wichtig, diese Funktion an zwei Stellen aufzurufen: im <xref:System.Windows.Forms.Control.Click> Ereignishandler der Schaltfläche und im <xref:System.Windows.Forms.Control.FontChanged>-Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="89327-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="89327-113">Wenn die Funktion nur im <xref:System.Windows.Forms.Control.Click> Ereignishandler aufgerufen wird und ein anderer Teil des Codes die Schriftfamilie des gesamten Formulars ändert, ändert sich das Textfeld nicht mit dem Rest des Formulars.</span><span class="sxs-lookup"><span data-stu-id="89327-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

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

<span data-ttu-id="89327-114">Wenn Sie die Anwendung jedoch lokalisieren, kann die Fett Schrift für bestimmte Sprachen schlecht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="89327-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="89327-115">Wenn dies ein Problem ist, sollten die Lokalisierer die Möglichkeit haben, die Schriftart von Fett zu regulärem Text zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="89327-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="89327-116">Da Lokalisierungen in der Regel keine Entwickler sind und keinen Zugriff auf den Quellcode haben, sondern nur auf Ressourcen Dateien, muss diese Option in den Ressourcen Dateien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="89327-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="89327-117">Hierzu legen Sie die <xref:System.Drawing.Font.Bold%2A>-Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="89327-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="89327-118">Dies führt dazu, dass die Schriftart Einstellung in die Ressourcen Dateien geschrieben wird, wo Sie von Lokalisierern bearbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="89327-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="89327-119">Anschließend schreiben Sie den Code nach der `InitializeComponent`-Methode, um die Schriftart basierend auf der Schriftart des Formulars zurückzusetzen, aber mit dem Schrift Schnitt, der in der Ressourcen Datei angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="89327-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="89327-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89327-120">See also</span></span>

- [<span data-ttu-id="89327-121">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="89327-121">Using Fonts and Text</span></span>](using-fonts-and-text.md)
