---
title: Definieren von Klassen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- execution, ending
- objects [Visual Basic], initializing
- Initialize event
- files, closing
- programs, quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event
- execution, stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: aeaa5c2bb85c1a642da15c6a29546cf065380e27
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-defining-classes-visual-basic"></a>Exemplarische Vorgehensweise: Definieren von Klassen (Visual Basic)
Diese exemplarische Vorgehensweise veranschaulicht das Definieren von Klassen, die Sie verwenden können, um Objekte zu erstellen. Außerdem erfahren Sie, wie die neue Klasse Eigenschaften und Methoden hinzugefügt, und veranschaulicht, wie ein Objekt zu initialisieren.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-a-class"></a>So definieren Sie eine Klasse  
  
1.  Erstellen Sie ein Projekt, indem Sie auf **neues Projekt** auf der **Datei** Menü. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2.  Wählen Sie aus der Liste der Windows-Anwendung [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Projektvorlagen, um das neue Projekt anzuzeigen.  
  
3.  Fügen Sie eine neue Klasse zum Projekt, indem Sie auf **Klasse hinzufügen** auf der **Projekt** Menü. Die **neues Element hinzufügen** das Dialogfeld wird angezeigt.  
  
4.  Wählen Sie die **Klasse** Vorlage.  
  
5.  Nennen Sie die neue Klasse `UserNameInfo.vb`, und klicken Sie dann auf **hinzufügen** um den Code für die neue Klasse anzuzeigen.  
  
     [!code-vb[VbVbalrOOP&5;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]  
  
    > [!NOTE]
    >  Können Sie die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **Code-Editor** so dem Startformular eine Klasse hinzu, durch Eingabe der `Class` -Schlüsselwort, gefolgt vom Namen der neuen Klasse. Die **Code-Editor** bietet eine entsprechende `End Class` -Anweisung für Sie.  
  
6.  Definieren Sie ein privates Feld für die Klasse, indem Sie den folgenden Code zwischen die `Class` und `End Class` Anweisungen:  
  
     [!code-vb[VbVbalrOOP&#7;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]  
  
     Deklaration des Felds als `Private` bedeutet, dass es nur innerhalb der Klasse verwendet werden kann. Sie können Felder mit verfügbar machen von außerhalb einer Klasse Zugriffsmodifizierer `Public` , die mehr Zugriff bieten. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7.  Definieren Sie eine Eigenschaft für die Klasse, indem Sie den folgenden Code hinzufügen:  
  
     [!code-vb[VbVbalrOOP&#8;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]  
  
8.  Definieren Sie eine Methode für die Klasse, indem Sie den folgenden Code hinzufügen:  
  
     [!code-vb[VbVbalrOOP&#9;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]  
  
9. Definieren Sie einen parametrisierten Konstruktor für die neue Klasse durch Hinzufügen einer Prozedur namens `Sub New`:  
  
     [!code-vb[VbVbalrOOP&#10;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]  
  
     Die `Sub New` Konstruktor wird automatisch aufgerufen, wenn ein Objekt auf Grundlage dieser Klasse erstellt wird. Dieser Konstruktor legt den Wert des Felds, das den Benutzernamen enthält.  
  
### <a name="to-create-a-button-to-test-the-class"></a>Zum Erstellen einer Schaltfläche, um die Klasse zu testen.  
  
1.  Ändern des Startformulars in den Entwurfsmodus per Rechtsklick auf seinen Namen im **Projektmappen-Explorer** , und klicken Sie dann auf **Ansicht-Designer**. Standardmäßig ist das Startformular für Windows-Anwendungsprojekte Form1.vb benannt. Das Hauptformular wird angezeigt.  
  
2.  Das Hauptformular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um den Code anzuzeigen der `Button1_Click` -Ereignishandler. Fügen Sie den folgenden Code zum Aufrufen der Testprozedur:  
  
     [!code-vb[VbVbalrOOP&#12;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]  
  
### <a name="to-run-your-application"></a>So führen Sie Ihre Anwendung aus  
  
1.  Führen Sie die Anwendung durch Drücken von F5. Klicken Sie auf die Schaltfläche im Formular an die Testprozedur aufrufen. Es wird eine Meldung, die besagt, dass die ursprüngliche `UserName` "MOORE, BOBBY" ist, da die Prozedur aufgerufen der `Capitalize` -Methode des Objekts.  
  
2.  Klicken Sie auf **OK** um das Meldungsfeld zu schließen. Die `Button1 Click` Prozedur ändert den Wert der `UserName` -Eigenschaft und zeigt eine Meldung, die besagt, dass den neuen Wert des `UserName` "Worden, Joe" ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Objektorientierte Programmierung](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)   
 [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)

