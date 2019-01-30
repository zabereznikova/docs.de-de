---
title: Auswirkungen beim Ändern der Darstellung von Basisformularen
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: fc0edaa8ca115a09eb6d8382a12d9a7c0c0db7f6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260163"
---
# <a name="effects-of-modifying-a-base-forms-appearance"></a>Auswirkungen beim Ändern der Darstellung von Basisformularen
Während der Anwendungsentwicklung müssen Sie möglicherweise häufig die Darstellung des Basisformulars ändern, dessen Merkmale an andere Formulare im Projekt (oder in anderen Projekten) vererbt werden.  
  
 Zur Entwurfszeit werden Änderungen an der Darstellung des Basisformulars (z.B. das Festlegen von Eigenschaften oder die Addition und Subtraktion von Steuerelementen) in geerbten Formularen reflektiert, wenn das Projekt mit dem Basisformular erstellt wird. Es genügt nicht, wenn Sie die am Basisformular vorgenommenen Änderungen einfach speichern. Wählen Sie aus dem Menü **Erstellen** die Option **Erstellen** aus, um ein Projekt zu erstellen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
 Änderungen, die zur Laufzeit am Basisformular vorgenommen werden, haben keine Auswirkungen auf geerbte Formulare, die bereits instanziiert werden.  
  
## <a name="see-also"></a>Siehe auch
- [base](~/docs/csharp/language-reference/keywords/base.md)
- [Vorgehensweise: Erben von Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)
- [Visuelle Vererbung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
