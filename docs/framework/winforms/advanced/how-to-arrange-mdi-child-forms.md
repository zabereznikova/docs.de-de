---
title: 'Gewusst wie: Anordnen von untergeordneten MDI-Formularen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms [Windows Forms], arranging
- MDI [Windows Forms], arranging child forms
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
ms.openlocfilehash: d5c0d24ff8a7188a669c218ce8b0dc66ffa56c47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521026"
---
# <a name="how-to-arrange-mdi-child-forms"></a><span data-ttu-id="7e89d-102">Gewusst wie: Anordnen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="7e89d-102">How to: Arrange MDI Child Forms</span></span>
<span data-ttu-id="7e89d-103">Anwendungen verfügen häufig über Menübefehle für Aktionen wie z. B. Nebeneinander anordnen, Überlappend anordnen und Anordnen, über die das Layout des geöffneten untergeordneten MDI-Formulars gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="7e89d-103">Often, applications will have menu commands for actions such as Tile, Cascade, and Arrange, which control the layout of the open MDI child forms.</span></span> <span data-ttu-id="7e89d-104">Sie können die <xref:System.Windows.Forms.Form.LayoutMdi%2A> -Methode mit einem der <xref:System.Windows.Forms.MdiLayout>-Enumerationswerte anwenden, um die untergeordneten Formulare in einem übergeordneten MDI-Enumerationswerteformular neu anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="7e89d-104">You can use the <xref:System.Windows.Forms.Form.LayoutMdi%2A> method with one of the <xref:System.Windows.Forms.MdiLayout> enumeration values to rearrange the child forms in an MDI parent form.</span></span>  
  
 <span data-ttu-id="7e89d-105">Mit <xref:System.Windows.Forms.MdiLayout>-Enumerationswerten werden untergeordnete Formulare als überlappend, nebeneinander oder untereinander bzw. in Form von untergeordneten Formularsymbolen im unteren Bereich des MDI-Formulars angeordnet.</span><span class="sxs-lookup"><span data-stu-id="7e89d-105">The <xref:System.Windows.Forms.MdiLayout> enumeration values display child forms as cascading, as horizontally or vertically tiled, or as child form icons arranged along the lower portion of the MDI form.</span></span> <span data-ttu-id="7e89d-106">Diese Werte haben denselben Effekt wie die Windows-Befehle **überlappend**, **Fenster nebeneinander anzeigen**, **Fenster gestapelt anzeigen**, und **Desktop anzeigen** bzw.</span><span class="sxs-lookup"><span data-stu-id="7e89d-106">These values have the same effect as the Windows commands **Cascade windows**, **Show windows side by side**, **Show windows stacked**, and **Show the desktop**, respectively.</span></span>  
  
 <span data-ttu-id="7e89d-107">Diese Methoden werden häufig als Ereignishandler aufgerufen, die vom <xref:System.Windows.Forms.Control.Click>-Ereignis eines Menüelements abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7e89d-107">Often, these methods are used as the event handlers called by a menu item's <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="7e89d-108">Auf diese Weise kann ein Menüelement mit dem Text "Fenster überlappend anzeigen" den gewünschten Effekt auf untergeordnete MDI-Fenster haben.</span><span class="sxs-lookup"><span data-stu-id="7e89d-108">In this way, a menu item with the text "Cascade Windows" can have the desired effect on the MDI child windows.</span></span>  
  
### <a name="to-arrange-child-forms"></a><span data-ttu-id="7e89d-109">So ordnen Sie untergeordnete Formulare an</span><span class="sxs-lookup"><span data-stu-id="7e89d-109">To arrange child forms</span></span>  
  
1.  <span data-ttu-id="7e89d-110">Verwenden Sie in einer Methode die <xref:System.Windows.Forms.Form.LayoutMdi%2A> -Methode zum Festlegen der <xref:System.Windows.Forms.MdiLayout> -Enumeration für das übergeordnete MDI-Formular.</span><span class="sxs-lookup"><span data-stu-id="7e89d-110">In a method, use the <xref:System.Windows.Forms.Form.LayoutMdi%2A> method to set the <xref:System.Windows.Forms.MdiLayout> enumeration for the MDI parent form.</span></span> <span data-ttu-id="7e89d-111">Im folgenden Beispiel wird der <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> -Enumerationswert für die untergeordneten Fenster des übergeordneten MDI-Formulars (`Form1`) verwendet.</span><span class="sxs-lookup"><span data-stu-id="7e89d-111">The following example uses the <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> enumeration value for the child windows of the MDI parent form (`Form1`).</span></span> <span data-ttu-id="7e89d-112">Die Enumeration wird im Code verwendet, während der Ereignishandler für das <xref:System.Windows.Forms.Control.Click> -Ereignis für die **überlappend** Menüelement.</span><span class="sxs-lookup"><span data-stu-id="7e89d-112">The enumeration is used in code during the event handler for the <xref:System.Windows.Forms.Control.Click> event of the **Cascade Windows** menu item.</span></span>  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="7e89d-113">Sie könne Fenster auch nebeneinander oder als Symbole anordnen, indem Sie den verwendeten <xref:System.Windows.Forms.MdiLayout> -Enumerationswert ändern.</span><span class="sxs-lookup"><span data-stu-id="7e89d-113">You can also tile windows and arranging windows as icons by changing the <xref:System.Windows.Forms.MdiLayout> enumeration value used.</span></span>  
  
2.  <span data-ttu-id="7e89d-114">Wenn Sie Visual C# verwenden, fügen Sie folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="7e89d-114">If you’re using Visual C#, place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7e89d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e89d-115">See Also</span></span>  
 [<span data-ttu-id="7e89d-116">MDI-Anwendungen (Multiple Document Interface)</span><span class="sxs-lookup"><span data-stu-id="7e89d-116">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [<span data-ttu-id="7e89d-117">Gewusst wie: Erstellen von übergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="7e89d-117">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="7e89d-118">Gewusst wie: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="7e89d-118">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="7e89d-119">Gewusst wie: Bestimmen des aktiven untergeordneten MDI-Elements</span><span class="sxs-lookup"><span data-stu-id="7e89d-119">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [<span data-ttu-id="7e89d-120">Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element</span><span class="sxs-lookup"><span data-stu-id="7e89d-120">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)
