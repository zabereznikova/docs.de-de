---
title: Erstellen und Implementieren von Schnittstellen
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 47176d2e7a512d8e8c27a90ac04d2a2a2af274b5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345037"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Exemplarische Vorgehensweise: Erstellen und Implementieren von Schnittstellen (Visual Basic)

Schnittstellen beschreiben die Merkmale von Eigenschaften, Methoden und Ereignissen, belassen aber die Implementierungsdetails in Strukturen oder Klassen.  
  
 In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie eine Schnittstelle deklariert und implementiert wird.  
  
> [!NOTE]
> Diese exemplarische Vorgehensweise bietet keine Informationen zum Erstellen einer Benutzeroberfläche.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a>So definieren Sie eine Schnittstelle
  
1. Öffnen Sie ein neues Visual Basic-Windows-Anwendungsprojekt.  
  
2. Fügen Sie dem Projekt ein neues Modul hinzu, indem Sie im Menü **Projekt** auf **Modul hinzufügen** klicken.  
  
3. Benennen Sie das neue Modul `Module1.vb` und klicken Sie dann auf **Hinzufügen**. Der Code für das neue Modul wird angezeigt.  
  
4. Definieren Sie eine Schnittstelle mit dem Namen `TestInterface` in `Module1`, indem Sie `Interface TestInterface` zwischen den Anweisungen `Module` und `End Module` eingeben und dann die EINGABETASTE drücken. Der **Code-Editor** zieht das `Interface`-Schlüsselwort ein und fügt eine `End Interface`-Anweisung hinzu, um einen Codeblock zu bilden.  
  
5. Definieren Sie eine Eigenschaft, eine Methode und ein Ereignis für die Schnittstelle, indem Sie den folgenden Code zwischen den `Interface`-und `End Interface`-Anweisungen platzieren:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>Implementierung

 Sie werden feststellen, dass sich die Syntax zum Deklarieren von Schnittstellenmembern von der Syntax unterscheidet, mit der Klassenmember deklariert werden Dieser Unterschied spiegelt die Tatsache wider, dass Schnittstellen keinen Implementierungs Code enthalten können.  
  
### <a name="to-implement-the-interface"></a>So implementieren Sie die-Schnittstelle
  
1. Fügen Sie eine Klasse mit dem Namen `ImplementationClass` hinzu, indem Sie die folgende Anweisung zu `Module1`hinzufügen, nachdem Sie die Anweisung `End Interface`, aber vor der `End Module`-Anweisung eingegeben haben, und drücken Sie  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     Wenn Sie innerhalb der integrierten Entwicklungsumgebung arbeiten, liefert der **Code-Editor** eine entsprechende `End Class`-Anweisung, wenn Sie die EINGABETASTE drücken.  
  
2. Fügen Sie der `ImplementationClass`die folgende `Implements`-Anweisung hinzu, die die von der Klasse implementierte Schnittstelle benennt:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     Wenn Sie getrennt von anderen Elementen oben in einer Klasse oder Struktur aufgeführt werden, gibt die `Implements`-Anweisung an, dass die Klasse oder Struktur eine Schnittstelle implementiert.  
  
     Wenn Sie innerhalb der integrierten Entwicklungsumgebung arbeiten, implementiert der **Code-Editor** die von `TestInterface` benötigten Klassenmember, wenn Sie die EINGABETASTE drücken, und Sie können den nächsten Schritt überspringen.  
  
3. Wenn Sie nicht innerhalb der integrierten Entwicklungsumgebung arbeiten, müssen Sie alle Member der Schnittstelle `MyInterface`implementieren. Fügen Sie den folgenden Code hinzu, um zu `ImplementationClass`, `Event1`, `Method1`und `Prop1`zu implementieren:  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     Die `Implements`-Anweisung benennt die Schnittstelle und den Schnittstellenmember, der implementiert wird.  
  
4. Vervollständigen Sie die Definition von `Prop1`, indem Sie der Klasse, die den Eigenschafts Wert gespeichert hat, ein privates Feld hinzufügen:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     Gibt den Wert des `pval` aus dem Get-Accessor der Eigenschaft zurück.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     Legen Sie den Wert `pval` im Eigenschaften Satz-Accessor fest.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. Vervollständigen Sie die Definition von `Method1`, indem Sie den folgenden Code hinzufügen.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>So testen Sie die Implementierung der Schnittstelle
  
1. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf das Start Formular für das Projekt, und klicken Sie dann auf **Code anzeigen**. Im Editor wird die Klasse für das Start Formular angezeigt. Standardmäßig wird das Start Formular `Form1`aufgerufen.  
  
2. Fügen Sie der `Form1`-Klasse das folgende `testInstance` Feld hinzu:  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     Wenn Sie `testInstance` als `WithEvents`deklarieren, kann die `Form1` Klasse ihre Ereignisse verarbeiten.  
  
3. Fügen Sie der `Form1`-Klasse den folgenden Ereignishandler hinzu, um Ereignisse zu behandeln, die von `testInstance`ausgelöst werden:  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. Fügen Sie der `Form1`-Klasse eine Unterroutine namens `Test` hinzu, um die Implementierungs Klasse zu testen:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     Die Prozedur `Test` erstellt eine Instanz der-Klasse, die `MyInterface`implementiert, diese Instanz dem `testInstance`-Feld zuweist, eine Eigenschaft festlegt und eine Methode über die-Schnittstelle ausführt.  
  
5. Fügen Sie Code hinzu, um die `Test` Prozedur aus der `Form1 Load` Prozedur Ihres Start Formulars aufzurufen:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. Führen Sie die `Test` Prozedur aus, indem Sie F5 drücken. Die Meldung "Eigenschaft PROP1 wurde auf 9 festgelegt" wird angezeigt. Nachdem Sie auf OK geklickt haben, wird die Meldung "der X-Parameter für Methode1 ist 5" angezeigt. Klicken Sie auf OK, und die Meldung "der Ereignishandler hat das Ereignis abgefangen" wird angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- [Implements-Anweisung](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [Schnittstellen](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Interface-Anweisung](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [Event-Anweisung](../../../../visual-basic/language-reference/statements/event-statement.md)
