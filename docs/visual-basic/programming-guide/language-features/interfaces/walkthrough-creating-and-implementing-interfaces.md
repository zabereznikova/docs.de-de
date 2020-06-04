---
title: Erstellen und Implementieren von Schnittstellen
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 89e8f91a04b25b84bc783d5c4f4b91cf12426f72
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405066"
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
  
3. Benennen Sie das neue Modul, `Module1.vb` und klicken Sie auf **Hinzufügen** Der Code für das neue Modul wird angezeigt.  
  
4. Definieren Sie eine Schnitt `TestInterface` Stelle `Module1` mit dem Namen in `Interface TestInterface` , indem Sie zwischen der `Module` -Anweisung und der- `End Module` Anweisung eingeben Im **Code-Editor** wird das `Interface` Schlüsselwort eingerückt und eine-Anweisung hinzugefügt `End Interface` , um einen Codeblock zu bilden.  
  
5. Definieren Sie eine Eigenschaft, eine Methode und ein Ereignis für die Schnittstelle, indem Sie den folgenden Code zwischen den `Interface` Anweisungen und platzieren `End Interface` :  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>Implementierung

 Sie werden feststellen, dass sich die Syntax zum Deklarieren von Schnittstellenmembern von der Syntax unterscheidet, mit der Klassenmember deklariert werden Dieser Unterschied spiegelt die Tatsache wider, dass Schnittstellen keinen Implementierungs Code enthalten können.  
  
### <a name="to-implement-the-interface"></a>So implementieren Sie die-Schnittstelle
  
1. Fügen Sie eine Klasse mit dem Namen hinzu, indem Sie nach `ImplementationClass` `Module1` der `End Interface` Anweisung, aber vor der Anweisung die folgende Anweisung hinzufügen `End Module` , und drücken Sie dann die EINGABETASTE:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     Wenn Sie innerhalb der integrierten Entwicklungsumgebung arbeiten, liefert der **Code-Editor** eine entsprechende `End Class` Anweisung, wenn Sie die EINGABETASTE drücken.  
  
2. Fügen Sie die folgende- `Implements` Anweisung hinzu `ImplementationClass` , die die von der Klasse implementierte Schnittstelle benennt:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     Wenn Sie getrennt von anderen Elementen oben in einer Klasse oder Struktur aufgeführt werden, gibt die Anweisung an, `Implements` dass die Klasse oder Struktur eine Schnittstelle implementiert.  
  
     Wenn Sie innerhalb der integrierten Entwicklungsumgebung arbeiten, implementiert der **Code-Editor** die Klassenmember, die für erforderlich sind `TestInterface` , wenn Sie die EINGABETASTE drücken, und Sie können den nächsten Schritt überspringen.  
  
3. Wenn Sie nicht innerhalb der integrierten Entwicklungsumgebung arbeiten, müssen Sie alle Member der-Schnittstelle implementieren `MyInterface` . Fügen Sie den folgenden Code hinzu, um `ImplementationClass` `Event1` , und zu implementieren `Method1` `Prop1` :  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     Die `Implements` -Anweisung benennt die implementierte Schnittstelle und den Schnittstellenmember.  
  
4. Vervollständigen Sie die Definition von `Prop1` , indem Sie der Klasse, die den Eigenschafts Wert gespeichert hat, ein privates Feld hinzufügen:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     Gibt den Wert von `pval` aus dem Get-Accessor der Eigenschaft zurück.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     Legen Sie den Wert von `pval` im Eigenschaften Satz-Accessor fest.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. Vervollständigen Sie die Definition von, `Method1` indem Sie den folgenden Code hinzufügen.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>So testen Sie die Implementierung der Schnittstelle
  
1. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf das Start Formular für das Projekt, und klicken Sie dann auf **Code anzeigen**. Im Editor wird die Klasse für das Start Formular angezeigt. Standardmäßig wird das Start Formular aufgerufen `Form1` .  
  
2. Fügen Sie der-Klasse das folgende `testInstance` Feld hinzu `Form1` :  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     Durch Deklarieren von `testInstance` als `WithEvents` kann die-Klasse die- `Form1` Ereignisse verarbeiten.  
  
3. Fügen Sie der-Klasse den folgenden Ereignishandler hinzu `Form1` , um von aufgebene Ereignisse zu behandeln `testInstance` :  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. Fügen Sie der-Klasse eine Unterroutine mit dem Namen hinzu `Test` `Form1` , um die Implementierungs Klasse zu testen:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     Die `Test` Prozedur erstellt eine Instanz der-Klasse, die implementiert `MyInterface` , diese Instanz dem `testInstance` Feld zuweist, eine Eigenschaft festlegt und eine Methode über die-Schnittstelle ausführt.  
  
5. Fügen Sie Code hinzu, um die `Test` Prozedur aus der `Form1 Load` Prozedur Ihres Start Formulars aufzurufen:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. Führen Sie die `Test` Prozedur aus, indem Sie F5 drücken. Die Meldung "Eigenschaft PROP1 wurde auf 9 festgelegt" wird angezeigt. Nachdem Sie auf OK geklickt haben, wird die Meldung "der X-Parameter für Methode1 ist 5" angezeigt. Klicken Sie auf OK, und die Meldung "der Ereignishandler hat das Ereignis abgefangen" wird angezeigt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Implements-Anweisung](../../../language-reference/statements/implements-statement.md)
- [Schnittstellen](index.md)
- [Interface-Anweisung](../../../language-reference/statements/interface-statement.md)
- [Event-Anweisung](../../../language-reference/statements/event-statement.md)
