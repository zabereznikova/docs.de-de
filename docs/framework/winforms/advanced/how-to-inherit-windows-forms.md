---
title: "Gewusst wie: Erben von Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Vererbung, Formulare"
  - "Geerbte Formulare, Erstellen zur Laufzeit"
  - "Windows Forms, Vererbung"
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Erben von Windows&#160;Forms
Das Erstellen neuer Windows Forms durch Vererbung der Eigenschaften der Basisformulare ist eine praktische Möglichkeit zum Duplizieren Ihrer Bemühungen, ohne ein Formular jedes Mal von Grund auf neu erstellen zu müssen, wenn Sie es benötigen.  
  
 Weitere Informationen zum Erben von Formularen zur Entwurfszeit mit dem Dialogfeld **Vererbungsauswahl** und zur visuellen Unterscheidung zwischen den Sicherheitsebenen der vererbten Steuerelemente finden Sie unter [Gewusst wie: Erben von Formularen mithilfe des Dialogfelds "Vererbungsauswahl"](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).  
  
 **Hinweis** Damit die Formularvererbung unterstützt wird, müssen die Datei oder der Namespace mit dem jeweiligen Formular in eine ausführbare Datei oder DLL integriert werden.  Zum Erstellen des Projekts wählen Sie **Erstellen** im Menü **Erstellen** aus.  Darüber hinaus muss der Klasse, die das Formular erbt, auch ein Verweis auf den Namespace hinzugefügt werden.  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erfolgt die Vererbung eines Formulars programmgesteuert  
  
1.  Fügen Sie in der Klasse einen Verweis zu dem Namespace hinzu, der das Formular enthält, das vererbt werden soll.  
  
2.  Fügen Sie in der Klassendefinition einen Verweis auf das Formular hinzu, das vererbt werden soll.  Der Verweis sollte den Namespace enthalten, in dem sich das Formular befindet, gefolgt von einem Punkt und dem Namen des eigentlichen Formulars.  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
  
    ```  
  
 Denken Sie beim Erben von Formularen daran, dass Probleme mit Ereignishandlern auftreten können, die zwei Mal aufgerufen werden, da jedes Ereignis sowohl von der Basisklasse als auch von der geerbten Klasse behandelt wird.  Weitere Informationen dazu, wie Sie dieses Problem vermeiden können, finden Sie unter [Problembehandlung für geerbte Ereignishandler in Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md).  
  
## Siehe auch  
 [Inherits Statement](../../../../ocs/visual-basic/language-reference/statements/inherits-statement.md)   
 [Imports Statement \(.NET Namespace and Type\)](../../../../ocs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Verwenden](../Topic/using%20\(C%23%20Reference\).md)   
 [Auswirkungen beim Ändern der Darstellung von Basisformularen](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)   
 [Visuelle Vererbung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)