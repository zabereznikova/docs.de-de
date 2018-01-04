---
title: "Internationale Schriftarten in Windows Forms und Steuerelementen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e7b6574e452faf4f0396f7633ba7f21519948262
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="7ffd5-102">Internationale Schriftarten in Windows Forms und Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="7ffd5-102">International Fonts in Windows Forms and Controls</span></span>
<span data-ttu-id="7ffd5-103">Die empfohlene Methode zum Auswählen von Schriftarten werden in internationalen Anwendungen Schriftartauswahl transaktionsanweisungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-103">In International applications the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="7ffd5-104">Automatische Schriftartauswahl bedeutet, dass das System bestimmt, was das Zeichen Skript gehört.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-104">Font fallback means that the system determines what script the character belongs to.</span></span>  
  
## <a name="using-font-fallback"></a><span data-ttu-id="7ffd5-105">Verwenden Schriftart-Fallback</span><span class="sxs-lookup"><span data-stu-id="7ffd5-105">Using Font Fallback</span></span>  
 <span data-ttu-id="7ffd5-106">Um dieses Feature nutzen zu können, stellen Sie keine der <xref:System.Drawing.Font> -Eigenschaft für das Formular oder ein anderes Element.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-106">To take advantage of this feature, do not set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="7ffd5-107">Die Anwendung wird automatisch der Standardsystemschriftart verwenden, die von einer lokalisierten Sprache des Betriebssystems auf einen anderen abweicht.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="7ffd5-108">Wenn die Anwendung ausgeführt wird, wird das System automatisch die richtige Schriftart für die Kultur, die im Betriebssystem aktiviert bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>  
  
 <span data-ttu-id="7ffd5-109">Es wird eine Ausnahme von der Regel der Schriftart an, die zum Ändern der Schriftart wird nicht festlegen.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-109">There is an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="7ffd5-110">Dies könnte wichtig für eine Anwendung sein in dem der Benutzer eine Schaltfläche, um Text in einem Textfeld angezeigt werden in Fettschrift klickt.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="7ffd5-111">Dazu würden Sie eine Funktion zum Ändern der Schriftart fett formatiert, das Textfeld schreiben, basierend auf den des Formulars Schriftart ist.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="7ffd5-112">Es ist wichtig, diesen Funktionsaufruf an zwei Orten: in der Schaltfläche <xref:System.Windows.Forms.Control.Click> Ereignishandler und klicken Sie in der <xref:System.Windows.Forms.Control.FontChanged> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-112">It is important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="7ffd5-113">Wenn die Funktion, nur in aufgerufen wird der <xref:System.Windows.Forms.Control.Click> -Ereignishandler und einigen anderen Codeabschnitt ändert die Schriftfamilie des gesamten Formulars, im Textfeld wird nicht mit dem Rest des Formulars ändern.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box will not change with the rest of the form.</span></span>  
  
```  
' Visual Basic  
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
  
// C#  
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
  
 <span data-ttu-id="7ffd5-114">Jedoch, wenn Sie die Anwendung zu lokalisieren, möglicherweise die fettformatierung Verschlechterung der Leistung für bestimmte Sprachen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="7ffd5-115">Wenn dies eine wichtige Überlegung ist, sollen die Lokalisierungsexperten haben die Möglichkeit, wechseln die Schriftart von fetter zu normaler Text.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="7ffd5-116">Da Lokalisierungsexperten nicht in der Regel Entwickler sind und haben keinen Zugriff auf den Quellcode, muss diese Option nur für Ressourcendateien, in den Ressourcendateien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-116">Since localizers are typically not developers and do not have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="7ffd5-117">Zu diesem Zweck legen Sie die <xref:System.Drawing.Font.Bold%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="7ffd5-118">Dadurch wird der Einstellung "Schriftart" in die Ressourcendateien, in dem Sie Lokalisierungsexperten bearbeiten können geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="7ffd5-119">Anschließend schreiben Sie Code nach der `InitializeComponent` Methode, um die Schriftart basierend auf beliebigen des Formulars Schriftart ist, jedoch mit den Schriftschnitt in der Ressourcendatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="7ffd5-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>  
  
```  
' Visual Basic  
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)  
  
// C#  
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ffd5-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ffd5-120">See Also</span></span>  
 [<span data-ttu-id="7ffd5-121">Globalisieren von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ffd5-121">Globalizing Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)  
 [<span data-ttu-id="7ffd5-122">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="7ffd5-122">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
