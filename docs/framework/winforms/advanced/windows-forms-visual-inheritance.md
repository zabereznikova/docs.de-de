---
title: "Visuelle Vererbung in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inheritance
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 857eb737-3602-4d49-bd8b-f70d33ace345
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 177b3034e9afc71a8ecc899364cc4911ef42a1a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-visual-inheritance"></a>Visuelle Vererbung in Windows Forms
Gelegentlich können Sie entscheiden, dass in einem Projekt ein Formular aufgerufen wird, das einem in einem früheren Projekt erstellten Formular ähnelt. Möglicherweise möchten Sie aber auch ein Basisformular mit Einstellungen wie z.B. Wasserzeichen oder einem bestimmten Steuerelementlayout erstellen, das Sie anschließend erneut in einem Projekt verwenden, wobei jede Iteration Änderungen an der ursprünglichen Formularvorlage umfasst. Bei der Vererbung von Formularen können Sie ein Basisformular erstellen und anschließend von diesem Formular erben und Änderungen vornehmen, während alle ursprünglichen Einstellungen, die Sie benötigen, beibehalten werden.  
  
 Sie können Formulare mit abgeleiteten Klassen programmgesteuert oder mithilfe der Vererbungsauswahl von Visual erstellen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Erben von Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 Gibt Anweisungen zum Erstellen geerbter Formulare in Code.  
  
 [Vorgehensweise: Erben von Formularen mithilfe des Dialogfelds „Vererbungsauswahl“](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)  
 Gibt Anweisungen zum Erstellen geerbter Formulare mithilfe der Vererbungsauswahl.  
  
 [Auswirkungen beim Ändern der Darstellung von Basisformularen](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)  
 Gibt Anweisungen zum Ändern der Steuerelemente eines Basisformulars und der zugehörigen Eigenschaften.  
  
 [Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 Beschreibt, wie ein einfaches Windows Form erstellt und in eine Klassenbibliothek kompiliert wird. Sie importieren diese Klassenbibliothek in ein anderes Projekt und erstellen ein neues Formular, das vom Basisformular erbt.  
  
 [Vorgehensweise: Verwenden von Modifizierern und GenerateMember-Eigenschaften](../../../../docs/framework/winforms/advanced/how-to-use-the-modifiers-and-generatemember-properties.md)  
 Gibt Anweisungen zur Verwendung der Eigenschaften `GenerateMember` und `Modifiers`, die relevant sind, wenn der Windows Forms-Designer eine Membervariable für eine Komponente generiert.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Grundlagen der Vererbung (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 Beschreibt, wie Visual Basic-Klassen definiert werden, die als Grundlage für andere Klassen dienen.  
  
 [class](~/docs/csharp/language-reference/keywords/class.md)  
 Beschreibt den C#-Ansatz von Klassen, in denen die einfache Vererbung zulässig ist.  
  
 [Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 Führt häufige Probleme auf, die bei Ereignishandlern in geerbten Komponenten auftreten.
