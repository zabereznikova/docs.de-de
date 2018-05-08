---
title: Erstellen und Implementieren von Schnittstellen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: af9305deb60637b642d091501e743f2c7a57ccad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Exemplarische Vorgehensweise: Erstellen und Implementieren von Schnittstellen (Visual Basic)

Schnittstellen beschreiben die Merkmale von Eigenschaften, Methoden und Ereignisse, sondern die Einzelheiten der Implementierung in Strukturen oder Klassen.  
  
 Diese exemplarische Vorgehensweise veranschaulicht das Deklarieren und Implementieren einer Schnittstelle.  
  
> [!NOTE]
>  In dieser exemplarischen Vorgehensweise stellt keine Informationen zum Erstellen einer Benutzeroberfläche bereit.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a>Um eine Schnittstelle zu definieren.
  
1.  Öffnen Sie ein neues Visual Basic-Windows-Anwendungsprojekt.  
  
2.  Fügen Sie ein neues Modul für das Projekt, indem Sie auf **Modul hinzufügen** auf die **Projekt** Menü.  
  
3.  Geben Sie dem neue Modul `Module1.vb` , und klicken Sie auf **hinzufügen**. Der Code für das neue Modul wird angezeigt.  
  
4.  Definieren Sie eine Schnittstelle mit dem Namen `TestInterface` in `Module1` dazu `Interface TestInterface` zwischen der `Module` und `End Module` -Anweisungen, und drücken Sie die EINGABETASTE. Die **Code-Editor** Einzüge der `Interface` Schlüsselwort und fügt eine `End Interface` Anweisung um einen Codeblock zu bilden.  
  
5.  Definieren Sie eine Eigenschaft, Methode und Ereignis für die Schnittstelle durch Platzieren den folgenden Code zwischen den `Interface` und `End Interface` Anweisungen:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>Implementierung

 Sie können feststellen, dass die Syntax zum Deklarieren von Schnittstellenmembern Syntax zum Deklarieren von Klassenmembern unterscheiden. Dieser Unterschied Deaktivierung, dass Schnittstellen Implementierungscode enthalten können.  
  
### <a name="to-implement-the-interface"></a>Implementieren die Schnittstelle
  
1.  Fügen Sie eine Klasse mit dem Namen `ImplementationClass` durch Hinzufügen folgender Anweisung zu `Module1`nach der `End Interface` Anweisung aber vor der `End Module` -Anweisung, und drücken Sie die EINGABETASTE:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     Wenn Sie in der integrierten Entwicklungsumgebung arbeiten die **Code-Editor** bereitstellt, einen übereinstimmenden `End Class` -Anweisung, wenn Sie die EINGABETASTE drücken.  
  
2.  Fügen Sie die folgenden `Implements` -Anweisung `ImplementationClass`, die die Schnittstelle der Klassennamen implementiert:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     Wenn separat von anderen Elementen am Anfang einer Klasse oder Struktur, aufgeführt. die `Implements` Anweisung gibt an, dass die Klasse oder Struktur eine Schnittstelle implementiert.  
  
     Wenn Sie in der integrierten Entwicklungsumgebung arbeiten die **Code-Editor** implementiert die erforderlichen Klassenmember `TestInterface` Wenn Sie die EINGABETASTE drücken und Sie können den nächsten Schritt überspringen.  
  
3.  Wenn Sie nicht innerhalb der integrierten Entwicklungsumgebung arbeiten, müssen Sie alle Member der Schnittstelle implementieren `MyInterface`. Fügen Sie folgenden Code zum `ImplementationClass` implementieren `Event1`, `Method1`, und `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     Die `Implements` Anweisung benennt die Schnittstelle und Schnittstellenmember implementiert wird.  
  
4.  Beenden Sie die Definition der `Prop1` durch Hinzufügen eines privaten Felds auf die Klasse, die den Wert der Eigenschaft gespeichert:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     Der Rückgabewert von der `pval` aus der Eigenschaft get-Zugriffsmethode.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     Legen Sie den Wert des `pval` im Eigenschaftensatz-Zugriffsmethode.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5.  Beenden Sie die Definition der `Method1` durch den folgenden Code hinzufügen.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>So testen Sie die Implementierung der Schnittstelle
  
1.  Mit der rechten Maustaste des Startformulars für das Projekt in der **Projektmappen-Explorer**, und klicken Sie auf **Code anzeigen**. Der Editor zeigt die Klasse für Ihr Startformular. Standardmäßig heißt die Startformular `Form1`.  
  
2.  Fügen Sie die folgenden `testInstance` -Feld der `Form1` Klasse:  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     Durch das Deklarieren von `testInstance` als `WithEvents`, die `Form1` Klasse seine Ereignisse behandeln kann.  
  
3.  Fügen Sie den folgenden Ereignishandler auf der `Form1` Klasse ausgelöste Ereignisse behandeln `testInstance`:  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4.  Hinzufügen eine Unterroutine namens `Test` auf die `Form1` Klasse, um die Implementierungsklasse zu testen:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     Die `Test` Prozedur erstellt eine Instanz der Klasse, die implementiert `MyInterface`, weist diese Instanz die `testInstance` Feld Festlegen einer Eigenschaft, und führt eine Methode über die Schnittstelle.  
  
5.  Fügen Sie Code zum Aufrufen der `Test` Prozedur aus der `Form1 Load` Prozedur mit dem Startformular:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6.  Führen Sie die `Test` Prozedur durch Drücken von F5. Die Meldung "Prop1 festlegen und 9" wird angezeigt. Nachdem Sie nun der Nachricht klicken Sie auf "Parameters" X "für Method1 is 5" werden angezeigt. Klicken Sie auf OK, und die Meldung "der Ereignishandler das Ereignis abgefangen" angezeigt.  
  
## <a name="see-also"></a>Siehe auch

 [Implements-Anweisung](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Schnittstellen](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Interface-Anweisung](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Event-Anweisung](../../../../visual-basic/language-reference/statements/event-statement.md)  