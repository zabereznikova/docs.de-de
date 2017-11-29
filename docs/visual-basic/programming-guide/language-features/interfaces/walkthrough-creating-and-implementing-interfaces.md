---
title: Erstellen und Implementieren von Schnittstellen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 08bf6dc7344d4f83c8ab1908fdeb29eb4a53e142
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Exemplarische Vorgehensweise: Erstellen und Implementieren von Schnittstellen (Visual Basic)
Schnittstellen beschreiben die Merkmale von Eigenschaften, Methoden und Ereignisse, sondern die Einzelheiten der Implementierung in Strukturen oder Klassen.  
  
 Diese exemplarische Vorgehensweise veranschaulicht das Deklarieren und Implementieren einer Schnittstelle.  
  
> [!NOTE]
>  In dieser exemplarischen Vorgehensweise stellt keine Informationen zum Erstellen einer Benutzeroberfläche bereit.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-define-an-interface"></a>Um eine Schnittstelle zu definieren.  
  
1.  Öffnen Sie ein neues [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Windows-Anwendungsprojekt.  
  
2.  Fügen Sie ein neues Modul für das Projekt, indem Sie auf **Modul hinzufügen** auf die **Projekt** Menü.  
  
3.  Geben Sie dem neue Modul `Module1.vb` , und klicken Sie auf **hinzufügen**. Der Code für das neue Modul wird angezeigt.  
  
4.  Definieren Sie eine Schnittstelle mit dem Namen `TestInterface` in `Module1` dazu `Interface TestInterface` zwischen der `Module` und `End Module` -Anweisungen, und drücken Sie die EINGABETASTE. Die **Code-Editor** Einzüge der `Interface` Schlüsselwort und fügt eine `End Interface` Anweisung um einen Codeblock zu bilden.  
  
5.  Definieren Sie eine Eigenschaft, Methode und Ereignis für die Schnittstelle durch Platzieren den folgenden Code zwischen den `Interface` und `End Interface` Anweisungen:  
  
     [!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]  
  
## <a name="implementation"></a>Implementierung  
 Sie können feststellen, dass die Syntax zum Deklarieren von Schnittstellenmembern Syntax zum Deklarieren von Klassenmembern unterscheiden. Dieser Unterschied Deaktivierung, dass Schnittstellen Implementierungscode enthalten können.  
  
#### <a name="to-implement-the-interface"></a>Implementieren die Schnittstelle  
  
1.  Fügen Sie eine Klasse mit dem Namen `ImplementationClass` durch Hinzufügen folgender Anweisung zu `Module1`nach der `End Interface` Anweisung aber vor der `End Module` -Anweisung, und drücken Sie die EINGABETASTE:  
  
     [!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]  
  
     Wenn Sie in der integrierten Entwicklungsumgebung arbeiten die **Code-Editor** bereitstellt, einen übereinstimmenden `End Class` -Anweisung, wenn Sie die EINGABETASTE drücken.  
  
2.  Fügen Sie die folgenden `Implements` -Anweisung `ImplementationClass`, die die Schnittstelle der Klassennamen implementiert:  
  
     [!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]  
  
     Wenn separat von anderen Elementen am Anfang einer Klasse oder Struktur, aufgeführt. die `Implements` Anweisung gibt an, dass die Klasse oder Struktur eine Schnittstelle implementiert.  
  
     Wenn Sie in der integrierten Entwicklungsumgebung arbeiten die **Code-Editor** implementiert die erforderlichen Klassenmember `TestInterface` Wenn Sie die EINGABETASTE drücken und Sie können den nächsten Schritt überspringen.  
  
3.  Wenn Sie nicht innerhalb der integrierten Entwicklungsumgebung arbeiten, müssen Sie alle Member der Schnittstelle implementieren `MyInterface`. Fügen Sie folgenden Code zum `ImplementationClass` implementieren `Event1`, `Method1`, und `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]  
  
     Die `Implements` Anweisung benennt die Schnittstelle und Schnittstellenmember implementiert wird.  
  
4.  Beenden Sie die Definition der `Prop1` durch Hinzufügen eines privaten Felds auf die Klasse, die den Wert der Eigenschaft gespeichert:  
  
     [!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]  
  
     Der Rückgabewert von der `pval` aus der Eigenschaft get-Zugriffsmethode.  
  
     [!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]  
  
     Legen Sie den Wert des `pval` im Eigenschaftensatz-Zugriffsmethode.  
  
     [!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]  
  
5.  Beenden Sie die Definition der `Method1` durch den folgenden Code hinzufügen.  
  
     [!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]  
  
#### <a name="to-test-the-implementation-of-the-interface"></a>So testen Sie die Implementierung der Schnittstelle  
  
1.  Mit der rechten Maustaste des Startformulars für das Projekt in der **Projektmappen-Explorer**, und klicken Sie auf **Code anzeigen**. Der Editor zeigt die Klasse für Ihr Startformular. Standardmäßig heißt die Startformular `Form1`.  
  
2.  Fügen Sie die folgenden `testInstance` -Feld der `Form1` Klasse:  
  
     [!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]  
  
     Durch das Deklarieren von `testInstance` als `WithEvents`, die `Form1` Klasse seine Ereignisse behandeln kann.  
  
3.  Fügen Sie den folgenden Ereignishandler auf der `Form1` Klasse ausgelöste Ereignisse behandeln `testInstance`:  
  
     [!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]  
  
4.  Hinzufügen eine Unterroutine namens `Test` auf die `Form1` Klasse, um die Implementierungsklasse zu testen:  
  
     [!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]  
  
     Die `Test` Prozedur erstellt eine Instanz der Klasse, die implementiert `MyInterface`, weist diese Instanz die `testInstance` Feld Festlegen einer Eigenschaft, und führt eine Methode über die Schnittstelle.  
  
5.  Fügen Sie Code zum Aufrufen der `Test` Prozedur aus der `Form1 Load` Prozedur mit dem Startformular:  
  
     [!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]  
  
6.  Führen Sie die `Test` Prozedur durch Drücken von F5. Die Meldung "Prop1 festlegen und 9" wird angezeigt. Nachdem Sie nun der Nachricht klicken Sie auf "Parameters" X "für Method1 is 5" werden angezeigt. Klicken Sie auf OK, und die Meldung "der Ereignishandler das Ereignis abgefangen" angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Implements-Anweisung](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Schnittstellen](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Interface-Anweisung](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Event-Anweisung](../../../../visual-basic/language-reference/statements/event-statement.md)
