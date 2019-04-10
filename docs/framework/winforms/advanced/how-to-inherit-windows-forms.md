---
title: 'Vorgehensweise: Erben von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: 0d8799359a12b9bb64331d83df2500bede8c0ff2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314541"
---
# <a name="how-to-inherit-windows-forms"></a>Vorgehensweise: Erben von Windows Forms
Das Erstellen neuer Windows Forms durch Vererbung der Eigenschaften der Basisformulare ist eine praktische Möglichkeit zum Duplizieren Ihrer Bemühungen, ohne ein Formular jedes Mal von Grund auf neu erstellen zu müssen, wenn Sie es benötigen.  
  
 Weitere Informationen zum erben von Formularen zur Entwurfszeit mit der **Vererbungsauswahl** und das Dialogfeld zur visuellen Unterscheidung zwischen den Sicherheitsebenen der vererbten Steuerelemente, finden Sie unter [Vorgehensweise: Erben von Formularen mithilfe des Dialogfelds Auswahl](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).  
  
 **Hinweis** Damit die Formularvererbung vom Dialogfeld unterstützt wird, muss die Datei oder der Namespace mit dem jeweiligen Formular in eine ausführbare Datei oder DLL integriert werden. Wählen Sie zum Erstellen des Projekts aus dem Menü **Erstellen** die Option **Erstellen** aus. Darüber hinaus muss der Klasse, die das Formular erbt, auch ein Verweis auf den Namespace hinzugefügt werden. Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-inherit-a-form-programmatically"></a>So erfolgt die Vererbung eines Formulars programmgesteuert  
  
1. Fügen Sie in der Klasse einen Verweis zu dem Namespace hinzu, der das Formular enthält, das vererbt werden soll.  
  
2. Fügen Sie in der Klassendefinition einen Verweis auf das Formular hinzu, das vererbt werden soll. Der Verweis sollte den Namespace enthalten, in dem sich das Formular befindet, gefolgt von einem Punkt und dem Namen des eigentlichen Formulars.  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 Denken Sie beim Erben von Formularen daran, dass Probleme mit Ereignishandlern auftreten können, die zwei Mal aufgerufen werden, da jedes Ereignis sowohl von der Basisklasse als auch von der geerbten Klasse behandelt wird. Weitere Informationen dazu, wie Sie dieses Problem vermeiden können, finden Sie unter [Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).  
  
## <a name="see-also"></a>Siehe auch

- [Inherits Statement](~/docs/visual-basic/language-reference/statements/inherits-statement.md)
- [Imports-Anweisung (.NET-Namespace und Typ)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [using](~/docs/csharp/language-reference/keywords/using.md)
- [Auswirkungen beim Ändern der Darstellung von Basisformularen](effects-of-modifying-base-form-appearance.md)
- [Visuelle Vererbung in Windows Forms](windows-forms-visual-inheritance.md)
