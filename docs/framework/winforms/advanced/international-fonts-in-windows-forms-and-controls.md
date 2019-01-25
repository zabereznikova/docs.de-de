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
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="7f099-102">Internationale Schriftarten in Windows Forms und Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="7f099-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="7f099-103">Die empfohlene Methode für das Auswählen von Schriftarten werden in internationale Anwendungen Schriftart-Fallback transaktionsanweisungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f099-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="7f099-104">Schriftart-fallback-bedeutet, dass das System bestimmt, was das Zeichen Skript gehört.</span><span class="sxs-lookup"><span data-stu-id="7f099-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="7f099-105">Verwenden Schriftart-fallback</span><span class="sxs-lookup"><span data-stu-id="7f099-105">Using font fallback</span></span>

<span data-ttu-id="7f099-106">Um dieses Feature nutzen zu können, legen Sie nicht die <xref:System.Drawing.Font> -Eigenschaft für das Formular oder ein anderes Element.</span><span class="sxs-lookup"><span data-stu-id="7f099-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="7f099-107">Die Anwendung verwendet automatisch die Standardschriftart des Systems, die von einer lokalisierten Sprache des Betriebssystems zur anderen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="7f099-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="7f099-108">Wenn die Anwendung ausgeführt wird, wird das System automatisch die richtige Schriftart für die Kultur, die im Betriebssystem aktiviert bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7f099-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="7f099-109">Es gibt eine Ausnahme von der Regel der Schriftart an, die zum Ändern der Schriftart wird nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7f099-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="7f099-110">Dies kann für eine Anwendung wichtig sein in dem der Benutzer eine Schaltfläche, um Text in einem Textfeld angezeigt werden in Fettdruck stellen klickt.</span><span class="sxs-lookup"><span data-stu-id="7f099-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="7f099-111">Dazu würden Sie eine Funktion zum Ändern der Textfeld-Schriftart fett formatiert ist, schreiben, basierend auf den der Schriftart des Formulars ist.</span><span class="sxs-lookup"><span data-stu-id="7f099-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="7f099-112">Es ist wichtig, diese Funktion aufrufen, an zwei Orten: in der Schaltfläche <xref:System.Windows.Forms.Control.Click> -Ereignishandler und klicken Sie in der <xref:System.Windows.Forms.Control.FontChanged> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="7f099-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="7f099-113">Wenn die Funktion, nur in aufgerufen wird der <xref:System.Windows.Forms.Control.Click> -Ereignishandler und einen anderen Teil des Codes ändert die Schriftfamilie für das gesamte Formular, mit dem Rest des Formulars ändert sich nicht im Textfeld.</span><span class="sxs-lookup"><span data-stu-id="7f099-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

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

<span data-ttu-id="7f099-114">Jedoch wenn Sie die Anwendung zu lokalisieren, möglicherweise die fettformatierung schlecht für bestimmte Sprachen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f099-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="7f099-115">Wenn dies relevant ist, möchten Sie den Lokalisierungsexperten die Schrift in Fettdruck in normalen Text benötigen.</span><span class="sxs-lookup"><span data-stu-id="7f099-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="7f099-116">Da Lokalisierer in der Regel keine Entwickler sind und keinen Zugriff auf den Quellcode haben, muss diese Option nur für Ressourcendateien, in den Ressourcendateien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7f099-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="7f099-117">Zu diesem Zweck legen Sie die <xref:System.Drawing.Font.Bold%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="7f099-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="7f099-118">Dies führt in die schriftarteinstellung, die in die Ressourcendateien, in dem Lokalisierungsexperten diese bearbeiten können geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7f099-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="7f099-119">Sie klicken Sie dann Code schreiben, nachdem die `InitializeComponent` Methode, die Schriftart auf beliebige der Schriftart des Formulars ist, jedoch mit den Schriftschnitt in der Ressourcendatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="7f099-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="7f099-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f099-120">See also</span></span>

- [<span data-ttu-id="7f099-121">Globalisieren von Windows Forms-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="7f099-121">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)
- [<span data-ttu-id="7f099-122">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="7f099-122">Using Fonts and Text</span></span>](using-fonts-and-text.md)
