---
title: Deklarieren und Auslösen von Ereignissen
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 6f4c303604f9cf55b4ecd500636e0d2772b6234c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345089"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen (Visual Basic)
Diese exemplarische Vorgehensweise veranschaulicht, wie Sie Ereignisse für eine Klasse mit dem Namen `Widget`deklarieren und Auswerfen. Nachdem Sie die Schritte ausgeführt haben, können Sie das Begleit Thema Exemplarische Vorgehensweise [: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)lesen, in dem gezeigt wird, wie Ereignisse aus `Widget` Objekten verwendet werden, um Statusinformationen in einer Anwendung bereitzustellen.  
  
## <a name="the-widget-class"></a>Die widgeklasse  
 Angenommen, Sie verfügen über eine `Widget`-Klasse. Die `Widget`-Klasse verfügt über eine-Methode, deren Ausführung viel Zeit in Anspruch nehmen kann, und Sie möchten, dass Ihre Anwendung in der Lage ist, einen beliebigen Abschluss Indikator zu verwenden.  
  
 Natürlich können Sie das `Widget`-Objekt das Dialogfeld "Prozentsatz vervollständigen" anzeigen lassen, aber dann würden Sie in jedem Projekt, in dem Sie die `Widget`-Klasse verwendet haben, an diesem Dialogfeld hängen. Ein gutes Prinzip des Objekt Entwurfs besteht darin, dass die Anwendung, die ein Objekt verwendet, die Benutzeroberfläche verarbeitet – es sei denn, der gesamte Zweck des Objekts besteht darin, ein Formular oder Dialogfeld zu verwalten.  
  
 Der Zweck `Widget` besteht darin, andere Aufgaben auszuführen. es ist daher besser, ein `PercentDone`-Ereignis hinzuzufügen und die Prozedur, die `Widget`Methoden aufruft, dieses Ereignis zu behandeln und Statusaktualisierungen anzuzeigen. Das `PercentDone` Ereignis kann auch einen Mechanismus zum Abbrechen der Aufgabe bereitstellen.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>So erstellen Sie das Codebeispiel für dieses Thema  
  
1. Öffnen Sie ein neues Visual Basic Windows-Anwendungsprojekt, und erstellen Sie ein Formular mit dem Namen `Form1`.  
  
2. Fügen Sie `Form1`zwei Schaltflächen und eine Bezeichnung hinzu.  
  
3. Benennen Sie die Objekte wie in der folgenden Tabelle gezeigt.  
  
    |Object|Eigenschaft|Einstellung|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Startaufgabe|  
    |`Button2`|`Text`|Abbrechen|  
    |`Label`|`(Name)`, `Text`|lblprozentudone, 0|  
  
4. Wählen Sie im Menü **Projekt** die Option **Klasse hinzufügen** aus, um dem Projekt eine Klasse mit dem Namen `Widget.vb` hinzuzufügen.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>So deklarieren Sie ein Ereignis für die Widget-Klasse  
  
- Verwenden Sie das `Event`-Schlüsselwort, um ein Ereignis in der `Widget` Klasse zu deklarieren. Beachten Sie, dass ein Ereignis `ByVal` und `ByRef` Argumente aufweisen kann, wie `Widget`das `PercentDone` Ereignis veranschaulicht:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 Wenn das aufrufenden Objekt ein `PercentDone` Ereignis empfängt, enthält das `Percent`-Argument den Prozentsatz der abgeschlossenen Aufgabe. Das `Cancel`-Argument kann `True` festgelegt werden, um die Methode abzubrechen, die das Ereignis ausgelöst hat.  
  
> [!NOTE]
> Sie können Ereignis Argumente genau wie Argumente von Prozeduren deklarieren, mit den folgenden Ausnahmen: Ereignisse können keine `Optional`-oder `ParamArray` Argumente aufweisen, und Ereignisse haben keine Rückgabewerte.  
  
 Das `PercentDone`-Ereignis wird von der `LongTask`-Methode der `Widget`-Klasse ausgelöst. `LongTask` verwendet zwei Argumente: die Zeitdauer, die die Methode für die Ausführung der Methode voraussetzt, und das minimale Zeitintervall, bevor `LongTask` angehalten wird, um das `PercentDone` Ereignis zu erhöhen.  
  
#### <a name="to-raise-the-percentdone-event"></a>So heben Sie das Ereignis "" vom  
  
1. Um den Zugriff auf die von dieser Klasse verwendete `Timer`-Eigenschaft zu vereinfachen, fügen Sie am Anfang des Deklarations Abschnitts Ihres Class-Moduls oberhalb der `Class Widget`-Anweisung eine `Imports`-Anweisung hinzu.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. Fügen Sie der `Widget` -Klasse folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 Wenn die Anwendung die `LongTask`-Methode aufruft, löst die `Widget`-Klasse alle `MinimumInterval` Sekunden das `PercentDone`-Ereignis aus. Wenn das Ereignis zurückgibt, prüft `LongTask`, ob das `Cancel`-Argument auf `True`festgelegt wurde.  
  
 Hier sind einige Haftungsausschlüsse erforderlich. Der Einfachheit halber wird bei der `LongTask` Prozedur davon ausgegangen, dass Sie im Voraus wissen, wie lange die Aufgabe dauert. Dies ist fast nie der Fall. Das Aufteilen von Aufgaben in Blöcke mit gleichmäßiger Größe kann schwierig sein, und häufig ist das, was für Benutzer am wichtigsten ist, einfach die Zeitspanne, die verstrichen ist, bevor Sie einen Hinweis darauf erhalten, dass etwas passiert.  
  
 Möglicherweise haben Sie in diesem Beispiel einen weiteren Fehler erkannt. Die `Timer`-Eigenschaft gibt die Anzahl der Sekunden zurück, die seit Mitternacht vergangen sind. Daher bleibt die Anwendung hängen, wenn Sie unmittelbar vor Mitternacht gestartet wird. Ein sorgfältiger Ansatz zum Messen der Zeit würde Grenzbedingungen wie diese berücksichtigen oder die Verwendung von Eigenschaften wie `Now`vermeiden.  
  
 Nun, da die `Widget` Klasse Ereignisse hervorrufen kann, können Sie zur nächsten exemplarischen Vorgehensweise wechseln. Exemplarische Vorgehensweise [: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) veranschaulicht, wie `WithEvents` verwendet wird, um dem `PercentDone` Ereignis einen Ereignishandler zuzuordnen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
