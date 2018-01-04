---
title: "Gewusst wie: Erstellen von übergeordneten MDI-Formularen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0147bc0777fdf3168ab0bc36ced0943571187d3c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-mdi-parent-forms"></a>Gewusst wie: Erstellen von übergeordneten MDI-Formularen
> [!IMPORTANT]
>  In diesem Thema wird das Steuerelement <xref:System.Windows.Forms.MainMenu> verwendet, welches durch das Steuerelement <xref:System.Windows.Forms.MenuStrip> ersetzt wurde. Das Steuerelement <xref:System.Windows.Forms.MainMenu> kann, falls gewünscht, für die Abwärtskompatibilität und zur künftigen Verwendung beibehalten werden.  Weitere Informationen zum Erstellen einer MDI übergeordnete Formular mithilfe einer <xref:System.Windows.Forms.MenuStrip>, finden Sie unter [Vorgehensweise: Erstellen einer MDI-Fensterliste mithilfe von MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).  
  
 Die Grundlage einer MDI (Multiple Document Interface)-Anwendung ist das übergeordnete MDI-Formular. Dies ist das Formular, das untergeordnete MDI-Fenster enthält. In diesen Unterfenstern interagiert der Benutzer mit der MDI-Anwendung. Ein übergeordnetes MDI-Formular lässt sich sowohl im Windows Forms-Designer als auch programmgesteuert leicht erstellen.  
  
### <a name="to-create-an-mdi-parent-form-at-design-time"></a>So erstellen Sie ein übergeordnetes MDI-Formular zur Entwurfszeit  
  
1.  Erstellen Sie ein Windows-Anwendungsprojekt.  
  
2.  In der **Eigenschaften** legen die <xref:System.Windows.Forms.Form.IsMdiContainer%2A> Eigenschaft **"true"**.  
  
     Dies kennzeichnet das Formular als MDI-Container für untergeordnete Fenster.  
  
    > [!NOTE]
    >  Beim Festlegen der Eigenschaften im Fenster **Eigenschaften** können Sie bei Bedarf auch die `WindowState`-Eigenschaft auf **Maximiert** festlegen, da sich untergeordnete MDI-Fenster am leichtesten bearbeiten lassen, wenn das übergeordnete Formular maximiert ist. Achten Sie außerdem darauf, dass durch den Rand des übergeordneten MDI-Formulars die Systemfarbe (die in der Windows-Systemsteuerung festgelegt wird) und nicht die Hintergrundfarbe, die Sie mithilfe der <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> -Eigenschaft festlegen, übernommen wird.  
  
3.  Ziehen Sie aus der **Toolbox** ein **MenuStrip**-Steuerelement in das Formular. Erstellen Sie ein Menüelement auf der obersten Ebene, wobei die **Text**-Eigenschaft auf **&Datei** festgelegt ist und die Untermenüs **&Neu** und **&Schließen** heißen. Erstellen Sie darüber hinaus ein Menüelement auf der obersten Ebene mit dem Namen **&Fenster**.  
  
     Durch das erste Menü werden Menüelemente zur Laufzeit erstellt und ausgeblendet, während über das zweite Menü die offenen untergeordneten MDI-Fenster nachverfolgt werden. Jetzt haben Sie ein übergeordnetes MDI-Fenster erstellt.  
  
4.  Drücken Sie **F5**, um die Anwendung auszuführen. Informationen zum Erstellen von untergeordneten MDI-Fenstern, die innerhalb der übergeordneten MDI-Formulars verwendet werden, finden Sie unter [Gewusst wie: Erstellen von untergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md).  
  
## <a name="see-also"></a>Siehe auch  
 [MDI-Anwendungen (Multiple Document Interface)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [Gewusst wie: Erstellen von untergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Gewusst wie: Bestimmen des aktiven untergeordneten MDI-Elements](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [Gewusst wie: Anordnen von untergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
