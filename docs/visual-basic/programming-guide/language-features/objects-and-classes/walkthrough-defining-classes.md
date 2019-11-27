---
title: Definieren von Klassen
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
ms.openlocfilehash: bd3f6e5cff41551240d9904ab93af8758eb104d2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346074"
---
# <a name="walkthrough-defining-classes-visual-basic"></a>Exemplarische Vorgehensweise: Definieren von Klassen (Visual Basic)

In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Klassen definiert werden, die Sie dann zum Erstellen von-Objekten verwenden können. Außerdem wird gezeigt, wie Sie der neuen Klasse Eigenschaften und Methoden hinzufügen und wie ein Objekt initialisiert wird.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a>So definieren Sie eine Klasse
  
1. Erstellen Sie ein Projekt, indem Sie im Menü **Datei** auf **Neues Projekt** klicken. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2. Wählen Sie in der Liste der Visual Basic Projektvorlagen die Option Windows-Anwendung aus, um das neue Projekt anzuzeigen.  
  
3. Fügen Sie dem Projekt eine neue Klasse hinzu, indem Sie im Menü **Projekt** auf **Klasse hinzufügen** klicken. Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
4. Wählen Sie die **Klassen** Vorlage aus.  
  
5. Benennen Sie die neue Klasse `UserNameInfo.vb`, und klicken Sie dann auf **Hinzufügen** , um den Code für die neue Klasse anzuzeigen.  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    > Sie können den Visual Basic **Code-Editor** verwenden, um dem Start Formular eine Klasse hinzuzufügen, indem Sie das Schlüsselwort `Class` eingeben, gefolgt vom Namen der neuen Klasse. Der **Code-Editor** stellt eine entsprechende `End Class`-Anweisung für Sie bereit.  
  
6. Definieren Sie ein privates Feld für die Klasse, indem Sie den folgenden Code zwischen den Anweisungen `Class` und `End Class` hinzufügen:  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     Das Deklarieren des Felds als `Private` bedeutet, dass es nur innerhalb der Klasse verwendet werden kann. Sie können Felder außerhalb einer Klasse verfügbar machen, indem Sie Zugriffsmodifizierer wie `Public` verwenden, die mehr Zugriff bereitstellen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7. Definieren Sie eine Eigenschaft für die Klasse, indem Sie den folgenden Code hinzufügen:  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8. Definieren Sie eine Methode für die Klasse, indem Sie den folgenden Code hinzufügen:  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. Definieren Sie einen parametrisierten Konstruktor für die neue Klasse, indem Sie eine Prozedur mit dem Namen `Sub New`hinzufügen:  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     Der `Sub New`-Konstruktor wird automatisch aufgerufen, wenn ein Objekt erstellt wird, das auf dieser Klasse basiert. Dieser Konstruktor legt den Wert des Felds fest, das den Benutzernamen enthält.  
  
## <a name="to-create-a-button-to-test-the-class"></a>So erstellen Sie eine Schaltfläche zum Testen der Klasse
  
1. Ändern Sie das Start Formular in den Entwurfs Modus, indem Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Namen klicken und dann **auf Designer anzeigen**klicken. Standardmäßig hat das Start Formular für Windows-Anwendungsprojekte den Namen Form1. vb. Das Hauptformular wird dann angezeigt.  
  
2. Fügen Sie dem Hauptformular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um den Code für den `Button1_Click` Ereignishandler anzuzeigen. Fügen Sie den folgenden Code hinzu, um die Testprozedur aufzurufen:  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a>So führen Sie die Anwendung aus
  
1. Führen Sie die Anwendung aus, indem Sie F5 drücken. Klicken Sie auf die Schaltfläche im Formular, um die Testprozedur aufzurufen. Es wird eine Meldung angezeigt, die besagt, dass der ursprüngliche `UserName` "Moore, Bobby" ist, weil die Prozedur die `Capitalize`-Methode des Objekts aufgerufen hat.  
  
2. Klicken Sie auf **OK**, um das Meldungsfeld zu schließen. Die Prozedur `Button1 Click` ändert den Wert der Eigenschaft `UserName` und zeigt eine Meldung an, die besagt, dass der neue Wert von `UserName` "hat, Joe" lautet.  
  
## <a name="see-also"></a>Siehe auch

- [Objektorientierte Programmierung (Visual Basic)](../../concepts/object-oriented-programming.md)
- [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
