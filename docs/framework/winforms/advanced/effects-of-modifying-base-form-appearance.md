---
title: "Auswirkungen beim Ändern der Darstellung von Basisformularen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5121238341afac46ad1c999710d51b5c203a1b6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="effects-of-modifying-a-base-form39s-appearance"></a>Auswirkungen beim Ändern der Darstellung von Basisformularen
Während der Anwendungsentwicklung müssen Sie möglicherweise häufig die Darstellung des Basisformulars ändern, dessen Merkmale an andere Formulare im Projekt (oder in anderen Projekten) vererbt werden.  
  
 Zur Entwurfszeit werden Änderungen an der Darstellung des Basisformulars (z.B. das Festlegen von Eigenschaften oder die Addition und Subtraktion von Steuerelementen) in geerbten Formularen reflektiert, wenn das Projekt mit dem Basisformular erstellt wird. Es genügt nicht, wenn Sie die am Basisformular vorgenommenen Änderungen einfach speichern. Wählen Sie aus dem Menü **Erstellen** die Option **Erstellen** aus, um ein Projekt zu erstellen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 Änderungen, die zur Laufzeit am Basisformular vorgenommen werden, haben keine Auswirkungen auf geerbte Formulare, die bereits instanziiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [base](~/docs/csharp/language-reference/keywords/base.md)  
 [Vorgehensweise: Erben von Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [Visuelle Vererbung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
