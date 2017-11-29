---
title: Definieren von Klassen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ec002e1709fa5fe31dfe7744fb91a230c32337a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-defining-classes-visual-basic"></a>Exemplarische Vorgehensweise: Definieren von Klassen (Visual Basic)
Diese exemplarische Vorgehensweise veranschaulicht das Definieren von Klassen, die Sie dann zum Erstellen von Objekten verwenden können. Außerdem wird gezeigt, wie die neue Klasse Eigenschaften und Methoden hinzugefügt, und veranschaulicht, wie ein Objekt initialisiert werden.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-define-a-class"></a>So definieren Sie eine Klasse  
  
1.  Erstellen Sie ein Projekt, indem Sie auf **neues Projekt** auf die **Datei** Menü. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2.  Wählen Sie aus der Liste der Windows-Anwendung [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Projektvorlagen, um das neue Projekt anzuzeigen.  
  
3.  Fügen Sie eine neue Klasse für das Projekt, indem Sie auf **Klasse hinzufügen** auf die **Projekt** Menü. Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
4.  Wählen Sie die **Klasse** Vorlage.  
  
5.  Benennen Sie die neue Klasse `UserNameInfo.vb`, und klicken Sie dann auf **hinzufügen** um den Code für die neue Klasse anzuzeigen.  
  
     [!code-vb[VbVbalrOOP#5](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]  
  
    > [!NOTE]
    >  Können Sie die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] **Code-Editor** hinzufügen eine Klasse zu Ihrem Startformular durch Eingabe der `Class` Schlüsselwort, gefolgt von den Namen der neuen Klasse. Die **Code-Editor** bietet ein entsprechendes `End Class` -Anweisung für Sie.  
  
6.  Definieren Sie ein privates Feld für die Klasse durch Hinzufügen von den folgenden Code zwischen den `Class` und `End Class` Anweisungen:  
  
     [!code-vb[VbVbalrOOP#7](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]  
  
     Deklarieren das Feld als `Private` bedeutet, dass es nur innerhalb der Klasse verwendet werden kann. Können Sie Felder verfügbar machen von außerhalb einer Klasse mit Zugriffsmodifizierern wie z. B. `Public` , umfassenderen Zugriff bereitstellen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7.  Definieren Sie eine Eigenschaft für die Klasse, indem Sie den folgenden Code hinzufügen:  
  
     [!code-vb[VbVbalrOOP#8](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]  
  
8.  Definieren Sie eine Methode für die Klasse, indem Sie den folgenden Code hinzufügen:  
  
     [!code-vb[VbVbalrOOP#9](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]  
  
9. Definieren Sie einen parametrisierten Konstruktor für die neue Klasse, indem Sie eine Prozedur mit dem Namen hinzufügen `Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]  
  
     Die `Sub New` Konstruktor wird automatisch aufgerufen, wenn ein Objekt auf Grundlage dieser Klasse erstellt wird. Dieser Konstruktor legt den Wert des Felds, das den Benutzernamen enthält.  
  
### <a name="to-create-a-button-to-test-the-class"></a>So erstellen eine Schaltfläche, um die Klasse zu testen  
  
1.  Ändern der Startformular in den Entwurfsmodus durch Rechtsklicken auf seinen Namen im **Projektmappen-Explorer** und dann auf **Sicht-Designer**. Standardmäßig heißt die Startformular für Windows-Anwendungsprojekten "Form1.vb". Das Hauptformular wird angezeigt.  
  
2.  Das Hauptformular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um den Code für die Anzeige der `Button1_Click` -Ereignishandler. Fügen Sie den folgenden Code zum Aufrufen der Testprozedur hinzu:  
  
     [!code-vb[VbVbalrOOP#12](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]  
  
### <a name="to-run-your-application"></a>So führen Sie Ihre Anwendung aus  
  
1.  Drücken Sie F5, um führen Sie die Anwendung aus. Klicken Sie auf die Schaltfläche im Formular an die Testprozedur aufrufen. Zeigt einer Meldung, die besagt, dass die ursprüngliche `UserName` ist "MOORE, BOBBY", da Prozeduraufruf der `Capitalize` -Methode des Objekts.  
  
2.  Klicken Sie auf **OK** auf das Meldungsfeld zu schließen. Die `Button1 Click` Prozedur ändert den Wert für die `UserName` Eigenschaft und zeigt eine Meldung, die besagt, dass den neuen Wert des `UserName` "Worden, Joe" ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Objektorientierte Programmierung](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)  
 [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
