---
title: Erstellen und Implementieren von Schnittstellen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: faed4d3c9498938e022daf821dd0aefbcbcf2e8d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053768"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Exemplarische Vorgehensweise: Erstellen und Implementieren von Schnittstellen (Visual Basic)

Schnittstellen werden die Merkmale der Eigenschaften, Methoden und Ereignisse beschrieben, aber die Einzelheiten der Implementierung in Strukturen oder Klassen.  
  
 Diese exemplarische Vorgehensweise veranschaulicht, wie Sie deklarieren und Implementieren einer Schnittstelle.  
  
> [!NOTE]
>  In dieser exemplarischen Vorgehensweise stellt Informationen zum Erstellen einer Benutzeroberfläche bereit.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a>Um eine Schnittstelle zu definieren.
  
1. Öffnen Sie ein neues Visual Basic-Windows-Anwendungsprojekt.  
  
2. Fügen Sie ein neues Modul für das Projekt, indem Sie auf **Modul hinzufügen** auf die **Projekt** Menü.  
  
3. Nennen Sie das neue Modul `Module1.vb` , und klicken Sie auf **hinzufügen**. Der Code für das neue Modul wird angezeigt.  
  
4. Definieren Sie eine Schnittstelle, die mit dem Namen `TestInterface` in `Module1` durch Eingabe `Interface TestInterface` zwischen der `Module` und `End Module` Anweisungen und dann die EINGABETASTE drücken. Die **Code-Editor** Einzüge der `Interface` Schlüsselwort und fügt eine `End Interface` Anweisung, um einen Codeblock zu bilden.  
  
5. Definieren Sie eine Eigenschaft, Methode und Ereignis für die Schnittstelle, platzieren Sie den folgenden Code zwischen den `Interface` und `End Interface` Anweisungen:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>Implementierung

 Sie können feststellen, dass die Syntax zum Deklarieren der Schnittstellenmember verwendet verschiedene, von der Syntax verwendet, um Klassenmember zu deklarieren. Dieser Unterschied gibt die Tatsache, dass Schnittstellen Implementierungscode enthalten können.  
  
### <a name="to-implement-the-interface"></a>Implementieren die Schnittstelle
  
1. Fügen Sie eine Klasse, die mit dem Namen `ImplementationClass` durch Hinzufügen der folgenden Anweisung auf `Module1`, nachdem die `End Interface` Anweisung aber vor der `End Module` -Anweisung und drücken Sie die EINGABETASTE:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     Wenn Sie in der integrierten Entwicklungsumgebung, arbeiten die **Code-Editor** stellt ein entsprechendes `End Class` -Anweisung, wenn Sie die EINGABETASTE drücken.  
  
2. Fügen Sie die folgenden `Implements` Anweisung `ImplementationClass`, die Namen der Schnittstelle an, der Klasse implementiert:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     Wenn separat von anderen Elementen am Anfang einer Klasse oder Struktur, steht die `Implements` Anweisung gibt an, dass die Klasse oder Struktur eine Schnittstelle implementiert.  
  
     Wenn Sie in der integrierten Entwicklungsumgebung, arbeiten die **Code-Editor** implementiert die erforderlichen Member `TestInterface` Wenn Sie die EINGABETASTE drücken, und Sie können den nächsten Schritt überspringen.  
  
3. Wenn Sie nicht innerhalb der integrierten Entwicklungsumgebung arbeiten, müssen Sie alle Member der Schnittstelle implementieren `MyInterface`. Fügen Sie den folgenden Code `ImplementationClass` implementieren `Event1`, `Method1`, und `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     Die `Implements` Anweisung benennt die Schnittstelle und Schnittstellenmember implementiert wird.  
  
4. Führen Sie die Definition der `Prop1` durch Hinzufügen eines privaten Felds auf die Klasse, die den Wert der Eigenschaft gespeichert:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     Der Rückgabewert von der `pval` aus der Eigenschaft get-Accessor.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     Legen Sie den Wert der `pval` set-Accessor der Eigenschaft.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. Führen Sie die Definition der `Method1` durch den folgenden Code hinzufügen.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>So testen Sie die Implementierung der Schnittstelle
  
1. Mit der rechten Maustaste in des Startformulars für Ihr Projekt in der **Projektmappen-Explorer**, und klicken Sie auf **Ansichtscode**. Der Editor zeigt die Klasse des Startformulars. Standardmäßig heißt das Startformular `Form1`.  
  
2. Fügen Sie die folgenden `testInstance` Feld der `Form1` Klasse:  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     Durch Deklarieren `testInstance` als `WithEvents`, `Form1` Klasse die Ereignisse behandeln kann.  
  
3. Fügen Sie den folgenden Ereignishandler, um die `Form1` -Klasse, von ausgelösten Ereignisse behandeln `testInstance`:  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. Fügen Sie eine Unterroutine namens `Test` auf die `Form1` Klasse, um die Implementierungsklasse zu testen:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     Die `Test` Prozedur erstellt eine Instanz der Klasse, die implementiert `MyInterface`, weist diese Instanz die `testInstance` Feld legt eine Eigenschaft fest, und führt eine Methode über die Schnittstelle.  
  
5. Fügen Sie Code zum Aufrufen der `Test` Prozedur aus der `Form1 Load` Verfahren des Startformulars:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. Führen Sie die `Test` Prozedur durch Drücken von F5. Die Meldung "Prop1 set bis 9" wird angezeigt. Nachdem Sie OK, der Nachricht klicken Sie auf "Parameters" X "für Method1 ist 5" werden angezeigt. Klicken Sie auf OK, und die Meldung "der Ereignishandler das Ereignis erkannt" angezeigt wird.  
  
## <a name="see-also"></a>Siehe auch

- [Implements-Anweisung](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [Schnittstellen](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Interface-Anweisung](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [Event-Anweisung](../../../../visual-basic/language-reference/statements/event-statement.md)
