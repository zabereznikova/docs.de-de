---
title: Definieren von Klassen (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: c41d3b2c8d905395f1249b15709da8dbdf5d4632
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640432"
---
# <a name="walkthrough-defining-classes-visual-basic"></a>Exemplarische Vorgehensweise: Definieren von Klassen (Visual Basic)

Diese exemplarische Vorgehensweise veranschaulicht, wie Sie Klassen definieren, die Sie zum Erstellen von Objekten verwenden können. Außerdem erfahren Sie, wie die neue Klasse Eigenschaften und Methoden hinzugefügt, und zeigt, wie ein Objekt zu initialisieren.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a>So definieren Sie eine Klasse
  
1.  Erstellen Sie ein Projekt, indem Sie auf **neues Projekt** auf die **Datei** Menü. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2.  Wählen Sie Windows-Anwendung, aus der Liste der Visual Basic-Projektvorlagen, die das neue Projekt anzuzeigen.  
  
3.  Fügen Sie eine neue Klasse für das Projekt, indem Sie auf **Klasse hinzufügen** auf die **Projekt** Menü. Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
4.  Wählen Sie die **Klasse** Vorlage.  
  
5.  Nennen Sie die neue Klasse `UserNameInfo.vb`, und klicken Sie dann auf **hinzufügen** um den Code für die neue Klasse anzuzeigen.  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    >  Können Sie die Visual Basic **Code-Editor** Startformulars eine Klasse hinzu, durch Eingabe der `Class` Schlüsselwort, gefolgt vom Namen der neuen Klasse. Die **Code-Editor** bietet ein entsprechendes `End Class` -Anweisung für Sie.  
  
6.  Definieren Sie ein privates Feld für die Klasse, indem Sie den folgenden Code zwischen Hinzufügen der `Class` und `End Class` Anweisungen:  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     Deklarieren das Feld als `Private` bedeutet, sie kann nur innerhalb der Klasse verwendet werden. Können Sie Felder verfügbar machen von außerhalb einer Klasse mit Zugriffsmodifizierern wie z. B. `Public` , umfassenderen Zugriff bereitstellen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7.  Definieren Sie eine Eigenschaft für die Klasse, indem Sie den folgenden Code hinzufügen:  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8.  Definieren Sie eine Methode für die Klasse, indem Sie den folgenden Code hinzufügen:  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. Definieren Sie einen parametrisierten Konstruktor für die neue Klasse, durch das Hinzufügen einer Prozedur, die mit dem Namen `Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     Die `Sub New` Konstruktor wird automatisch aufgerufen, wenn ein Objekt auf Grundlage dieser Klasse erstellt wird. Dieser Konstruktor legt den Wert des Felds, das den Benutzernamen enthält.  
  
## <a name="to-create-a-button-to-test-the-class"></a>Zum Erstellen einer Schaltfläche, um die Klasse zu testen.
  
1.  Ändern des Startformulars in den Entwurfsmodus durch Rechtsklick auf seinen Namen im **Projektmappen-Explorer** , und klicken Sie dann auf **Ansicht-Designer**. Standardmäßig heißt das Startformular für Windows-Anwendungsprojekte "Form1.vb". Das Hauptformular wird angezeigt.  
  
2.  Das Hauptformular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um den Code für die Anzeige der `Button1_Click` -Ereignishandler. Fügen Sie den folgenden Code zum Aufrufen der Testprozedur hinzu:  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a>So führen Sie Ihre Anwendung aus
  
1.  Führen Sie Ihre Anwendung durch Drücken von F5. Klicken Sie auf die Schaltfläche im Formular die Testprozedur aufrufen. Es wird die Meldung besagt, dass die ursprüngliche `UserName` "MOORE, BOBBY", ist, da die Prozedur aufgerufen der `Capitalize` -Methode des Objekts.  
  
2.  Klicken Sie auf **OK**, um das Meldungsfeld zu schließen. Die `Button1 Click` Prozedur ändert den Wert für die `UserName` Eigenschaft und zeigt einer Meldung, die besagt, dass den neuen Wert des `UserName` "Worden, Joe" ist.  
  
## <a name="see-also"></a>Siehe auch

- [Objektorientierte Programmierung (Visual Basic)](../../concepts/object-oriented-programming.md)
- [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
