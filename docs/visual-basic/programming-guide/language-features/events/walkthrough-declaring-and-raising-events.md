---
title: Deklarieren und Auslösen von Ereignissen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: cab6c90947eae8abeb9387535eadb2f89e71454a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973089"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen (Visual Basic)
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie für das Deklarieren und Auslösen von Ereignissen für eine Klasse, die mit dem Namen `Widget`. Nachdem Sie die Schritte abgeschlossen haben, Sie möchten das begleitthema lesen [Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), erfahren, wie Sie Ereignisse aus `Widget` Objekte Statusinformationen in einer Anwendung bereitstellen.  
  
## <a name="the-widget-class"></a>Die Widget-Klasse  
 Davon aus, die Sie derzeit eine `Widget` Klasse. Ihre `Widget` -Klasse verfügt über eine Methode, die eine lange Ausführungszeit benötigt erreichen, und Sie möchten die Anwendung, um eine Art des Indikators für Abschluss erstellen zu können.  
  
 Natürlich könnten Sie machen die `Widget` Objekt anzuzeigen, ein Dialogfeld Fortschritt in Prozent, aber dann deklarieren Sie mit diesem Dialogfeld in jedem Projekt, in dem Sie verwendet, die `Widget` Klasse. Ein gutes Prinzip des objektentwurfs besteht darin, die Anwendung, das ein Objekthandle der Benutzeroberfläche verwendet, es sei denn, die gesamte des Objekts dient zum Verwalten eines Felds zum Formular oder Dialogfeld.  
  
 Der Zweck der `Widget` besteht darin, andere Aufgaben auszuführen, daher ist es besser, hinzuzufügen, eine `PercentDone` Ereignis und die Prozedur verwendet, die aufruft `Widget`Methoden der behandelt werden, dass Ereignis und die Statusanzeige. Die `PercentDone` Ereignis bieten auch einen Mechanismus zum Abbrechen der Aufgabe.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Das Codebeispiel in diesem Thema erstellen  
  
1. Öffnen Sie ein neues Visual Basic Windows-Anwendungsprojekt, und erstellen Sie ein Formular mit dem Namen `Form1`.  
  
2. Fügen Sie zwei Schaltflächen und eine Bezeichnung für die `Form1`.  
  
3. Benennen Sie die Objekte wie in der folgenden Tabelle gezeigt.  
  
    |Objekt|Eigenschaft|Einstellung|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Startaufgabe|  
    |`Button2`|`Text`|Abbrechen|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4. Auf der **Projekt** Menü wählen **Klasse hinzufügen** zum Hinzufügen der Klasse `Widget.vb` zum Projekt.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Um ein Ereignis für das Widget-Klasse zu deklarieren.  
  
- Verwenden der `Event` -Schlüsselwort zu deklarieren, ein Ereignis in der `Widget` Klasse. Beachten Sie, dass ein Ereignis kann `ByVal` und `ByRef` Argumente als `Widget`des `PercentDone` Ereignis veranschaulicht wird:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 Wenn das aufrufende Objekt empfängt ein `PercentDone` -Ereignis, das `Percent` Argument enthält den Prozentsatz der der Vorgang abgeschlossen ist. Die `Cancel` Argument kann festgelegt werden, um `True` zum Abbrechen der Methode, die das Ereignis ausgelöst hat.  
  
> [!NOTE]
>  Sie können Ereignisargumente deklarieren, wie von Prozeduren mit den folgenden Ausnahmen Argumente: Ereignisse dürfen keine `Optional` oder `ParamArray` Argumente und Ereignisse haben keine Rückgabewerte.  
  
 Die `PercentDone` Ereignis wird ausgelöst, durch die `LongTask` Methode der `Widget` Klasse. `LongTask` akzeptiert zwei Argumente: die Zeitdauer zu arbeiten, und das minimale Zeitintervall vor dem Ausführen der Methode vorgegeben `LongTask` angehalten wird, um das Auslösen der `PercentDone` Ereignis.  
  
#### <a name="to-raise-the-percentdone-event"></a>Zum Auslösen des Ereignisses PercentDone  
  
1. Zur Vereinfachung der Zugriff auf die `Timer` hinzufügen Eigenschaft, die von dieser Klasse verwendet eine `Imports` Anweisung am Anfang des Abschnitts Deklarationen Klassenmoduls über die `Class Widget` Anweisung.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. Fügen Sie der `Widget`-Klasse folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 Bei einem Aufruf der `LongTask` -Methode, die `Widget` löst die `PercentDone` Ereignis jedes `MinimumInterval` Sekunden. Gibt das Ereignis `LongTask` überprüft, ob die `Cancel` -Argument wurde auf festgelegt `True`.  
  
 Hier sind einige Haftungsausschlüsse erforderlich. Der Einfachheit halber die `LongTask` Verfahren wird vorausgesetzt, Sie wissen im voraus, wie lange der Vorgang dauert. Dies ist fast nie der Fall. Unterteilen Aufgaben in Blöcke von gleichmäßiger Größe kann schwierig sein, und häufig was für Benutzer am wichtigsten ist einfach die Zeitspanne, die übergeben werden, bevor sie eine Angabe über das erhalten, dass etwas passiert ist.  
  
 Sie können in diesem Beispiel ein weiterer Nachteil entdeckt haben. Die `Timer` Eigenschaft gibt die Anzahl der Sekunden an, die seit Mitternacht vergangenen; die Anwendung ruft daher hängen, wenn sie kurz vor Mitternacht gestartet wird. Ein sorgfältiger Ansatz zum Messen der Zeit begrenzungsbedingungen wie diese berücksichtigt werden würde, oder vermeiden Sie sie, wie z. B. mithilfe von Eigenschaften `Now`.  
  
 Nachdem die `Widget` Klasse Ereignisse auslösen kann, können Sie in der nächsten exemplarischen Vorgehensweise verschieben. [Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) veranschaulicht, wie `WithEvents` , ordnen Sie einen Ereignishandler mit dem `PercentDone` Ereignis.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
