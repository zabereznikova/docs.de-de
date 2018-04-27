---
title: Definieren von Klassen (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
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
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9fc173ad853755c4b02a13abc0a80229bebffe64
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-defining-classes-visual-basic"></a>Exemplarische Vorgehensweise: Definieren von Klassen (Visual Basic)

Diese exemplarische Vorgehensweise veranschaulicht das Definieren von Klassen, die Sie dann zum Erstellen von Objekten verwenden können. Außerdem wird gezeigt, wie die neue Klasse Eigenschaften und Methoden hinzugefügt, und veranschaulicht, wie ein Objekt initialisiert werden.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a>So definieren Sie eine Klasse
  
1.  Erstellen Sie ein Projekt, indem Sie auf **neues Projekt** auf die **Datei** Menü. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2.  Wählen Sie Windows-Anwendung aus der Liste der Visual Basic-Projektvorlagen, die das neue Projekt anzuzeigen.  
  
3.  Fügen Sie eine neue Klasse für das Projekt, indem Sie auf **Klasse hinzufügen** auf die **Projekt** Menü. Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
4.  Wählen Sie die **Klasse** Vorlage.  
  
5.  Benennen Sie die neue Klasse `UserNameInfo.vb`, und klicken Sie dann auf **hinzufügen** um den Code für die neue Klasse anzuzeigen.  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    >  Können Sie die Visual Basic **Code-Editor** hinzufügen eine Klasse zu Ihrem Startformular durch Eingabe der `Class` Schlüsselwort, gefolgt von den Namen der neuen Klasse. Die **Code-Editor** bietet ein entsprechendes `End Class` -Anweisung für Sie.  
  
6.  Definieren Sie ein privates Feld für die Klasse durch Hinzufügen von den folgenden Code zwischen den `Class` und `End Class` Anweisungen:  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     Deklarieren das Feld als `Private` bedeutet, dass es nur innerhalb der Klasse verwendet werden kann. Können Sie Felder verfügbar machen von außerhalb einer Klasse mit Zugriffsmodifizierern wie z. B. `Public` , umfassenderen Zugriff bereitstellen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7.  Definieren Sie eine Eigenschaft für die Klasse, indem Sie den folgenden Code hinzufügen:  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8.  Definieren Sie eine Methode für die Klasse, indem Sie den folgenden Code hinzufügen:  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. Definieren Sie einen parametrisierten Konstruktor für die neue Klasse, indem Sie eine Prozedur mit dem Namen hinzufügen `Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     Die `Sub New` Konstruktor wird automatisch aufgerufen, wenn ein Objekt auf Grundlage dieser Klasse erstellt wird. Dieser Konstruktor legt den Wert des Felds, das den Benutzernamen enthält.  
  
## <a name="to-create-a-button-to-test-the-class"></a>So erstellen eine Schaltfläche, um die Klasse zu testen
  
1.  Ändern der Startformular in den Entwurfsmodus durch Rechtsklicken auf seinen Namen im **Projektmappen-Explorer** und dann auf **Sicht-Designer**. Standardmäßig heißt die Startformular für Windows-Anwendungsprojekten "Form1.vb". Das Hauptformular wird angezeigt.  
  
2.  Das Hauptformular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um den Code für die Anzeige der `Button1_Click` -Ereignishandler. Fügen Sie den folgenden Code zum Aufrufen der Testprozedur hinzu:  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a>So führen Sie Ihre Anwendung aus
  
1.  Drücken Sie F5, um führen Sie die Anwendung aus. Klicken Sie auf die Schaltfläche im Formular an die Testprozedur aufrufen. Zeigt einer Meldung, die besagt, dass die ursprüngliche `UserName` ist "MOORE, BOBBY", da Prozeduraufruf der `Capitalize` -Methode des Objekts.  
  
2.  Klicken Sie auf **OK** auf das Meldungsfeld zu schließen. Die `Button1 Click` Prozedur ändert den Wert für die `UserName` Eigenschaft und zeigt eine Meldung, die besagt, dass den neuen Wert des `UserName` "Worden, Joe" ist.  
  
## <a name="see-also"></a>Siehe auch

[Objektorientierte Programmierung (Visual Basic)](../../concepts/object-oriented-programming.md)  
[Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)