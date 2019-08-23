---
title: Erstellen und Implementieren von Schnittstellen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 62e301e9eb366d14b58088d3e2cda3b567d17f5b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923309"
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
  
3. Benennen Sie das neue `Module1.vb` Modul, und klicken Sie auf **Hinzufügen** Der Code für das neue Modul wird angezeigt.  
  
4. Definieren Sie eine Schnitt `TestInterface` Stelle `Module1` mit dem Namen in `Module` , `End Module` indem Sie zwischen der-Anweisung und der-Anweisung eingeben `Interface TestInterface` Im **Code-Editor** wird das `Interface` Schlüsselwort eingerückt `End Interface` und eine-Anweisung hinzugefügt, um einen Codeblock zu bilden.  
  
5. Definieren Sie eine Eigenschaft, eine Methode und ein Ereignis für die Schnittstelle, indem Sie den `Interface` folgenden `End Interface` Code zwischen den Anweisungen und platzieren:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>Implementierung

 Sie werden feststellen, dass sich die Syntax zum Deklarieren von Schnittstellenmembern von der Syntax unterscheidet, mit der Klassenmember deklariert werden Dieser Unterschied spiegelt die Tatsache wider, dass Schnittstellen keinen Implementierungs Code enthalten können.  
  
### <a name="to-implement-the-interface"></a>So implementieren Sie die-Schnittstelle
  
1. Fügen Sie eine Klasse `ImplementationClass` mit dem Namen hinzu, indem `Module1`Sie nach der `End Interface` Anweisung, aber vor `End Module` der Anweisung die folgende Anweisung hinzufügen, und drücken Sie dann die EINGABETASTE:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     Wenn Sie innerhalb der integrierten Entwicklungsumgebung arbeiten, liefert der **Code-Editor** eine entsprechende `End Class` Anweisung, wenn Sie die EINGABETASTE drücken.  
  
2. Fügen Sie die `Implements` folgende- `ImplementationClass`Anweisung hinzu, die die von der Klasse implementierte Schnittstelle benennt:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     Wenn Sie getrennt von anderen Elementen oben in einer Klasse oder Struktur aufgeführt werden, gibt `Implements` die Anweisung an, dass die Klasse oder Struktur eine Schnittstelle implementiert.  
  
     Wenn Sie innerhalb der integrierten Entwicklungsumgebung arbeiten, implementiert der **Code-Editor** die Klassenmember, `TestInterface` die für erforderlich sind, wenn Sie die EINGABETASTE drücken, und Sie können den nächsten Schritt überspringen.  
  
3. Wenn Sie nicht innerhalb der integrierten Entwicklungsumgebung arbeiten, müssen Sie alle Member der-Schnittstelle `MyInterface`implementieren. Fügen Sie den folgenden Code `ImplementationClass` hinzu, `Event1`um `Method1`, und `Prop1`zu implementieren:  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     Die `Implements` -Anweisung benennt die implementierte Schnittstelle und den Schnittstellenmember.  
  
4. Vervollständigen Sie die Definition `Prop1` von, indem Sie der Klasse, die den Eigenschafts Wert gespeichert hat, ein privates Feld hinzufügen:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     Gibt den Wert von `pval` aus dem Get-Accessor der Eigenschaft zurück.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     Legen Sie den Wert `pval` von im Eigenschaften Satz-Accessor fest.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. Vervollständigen Sie die Definition `Method1` von, indem Sie den folgenden Code hinzufügen.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>So testen Sie die Implementierung der Schnittstelle
  
1. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf das Start Formular für das Projekt, und klicken Sie dann auf **Code anzeigen**. Im Editor wird die Klasse für das Start Formular angezeigt. Standardmäßig wird das Start Formular aufgerufen `Form1`.  
  
2. Fügen Sie der `testInstance` - `Form1` Klasse das folgende Feld hinzu:  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     Durch `testInstance` deklarieren `WithEvents`von als `Form1` kann die-Klasse die-Ereignisse verarbeiten.  
  
3. Fügen Sie der- `Form1` Klasse den folgenden Ereignishandler hinzu, um von `testInstance`aufgebene Ereignisse zu behandeln:  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. Fügen Sie der `Form1` -Klasse `Test` eine Unterroutine mit dem Namen hinzu, um die Implementierungs Klasse zu testen:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     Die `Test` Prozedur erstellt eine Instanz der-Klasse, die `MyInterface`implementiert, diese Instanz dem `testInstance` Feld zuweist, eine Eigenschaft festlegt und eine Methode über die-Schnittstelle ausführt.  
  
5. Fügen Sie Code hinzu, `Test` um die Prozedur `Form1 Load` aus der Prozedur Ihres Start Formulars aufzurufen:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. Führen Sie `Test` die Prozedur aus, indem Sie F5 drücken. Die Meldung "Eigenschaft PROP1 wurde auf 9 festgelegt" wird angezeigt. Nachdem Sie auf OK geklickt haben, wird die Meldung "der X-Parameter für Methode1 ist 5" angezeigt. Klicken Sie auf OK, und die Meldung "der Ereignishandler hat das Ereignis abgefangen" wird angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- [Implements-Anweisung](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [Schnittstellen](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Interface-Anweisung](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [Event-Anweisung](../../../../visual-basic/language-reference/statements/event-statement.md)
