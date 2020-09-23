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
ms.openlocfilehash: 07ef611b50cfa13f77fa168d58dd3b43e97eeec6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91057987"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen (Visual Basic)

Diese exemplarische Vorgehensweise veranschaulicht, wie Sie Ereignisse für eine Klasse mit dem Namen deklarieren und Auswerfen `Widget` . Nachdem Sie die Schritte ausgeführt haben, können Sie das Begleit Thema Exemplarische Vorgehensweise [: Behandeln von Ereignissen](walkthrough-handling-events.md)lesen, in dem gezeigt wird, wie Ereignisse aus Objekten verwendet werden, `Widget` um Statusinformationen in einer Anwendung bereitzustellen.  
  
## <a name="the-widget-class"></a>Die widgeklasse  

 Angenommen, Sie haben eine- `Widget` Klasse. Die `Widget` -Klasse verfügt über eine-Methode, die für die Ausführung viel Zeit in Anspruch nehmen kann, und Sie möchten, dass Ihre Anwendung in der Lage ist, einen beliebigen Abschluss Indikator zu verwenden.  
  
 Natürlich könnten Sie das `Widget` Objekt mit dem Dialogfeld "Prozentsatz vervollständigen" anzeigen lassen, aber dann würden Sie in jedem Projekt, in dem Sie die Klasse verwendet haben, an diesem Dialogfeld hängen bleiben `Widget` . Ein gutes Prinzip des Objekt Entwurfs besteht darin, dass die Anwendung, die ein Objekt verwendet, die Benutzeroberfläche verarbeitet – es sei denn, der gesamte Zweck des Objekts besteht darin, ein Formular oder Dialogfeld zu verwalten.  
  
 Der Zweck von `Widget` ist das Ausführen weiterer Aufgaben, daher ist es besser, ein `PercentDone` -Ereignis hinzuzufügen und die Prozedur, die Methoden aufruft, `Widget` Dieses Ereignis zu behandeln und Statusaktualisierungen anzuzeigen. Das `PercentDone` Ereignis kann auch einen Mechanismus zum Abbrechen der Aufgabe bereitstellen.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>So erstellen Sie das Codebeispiel für dieses Thema  
  
1. Öffnen Sie ein neues Visual Basic Windows-Anwendungsprojekt, und erstellen Sie ein Formular mit dem Namen `Form1` .  
  
2. Fügen Sie zwei Schaltflächen und eine Bezeichnung hinzu `Form1` .  
  
3. Benennen Sie die Objekte wie in der folgenden Tabelle gezeigt.  
  
    |Object|Eigenschaft|Einstellung|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Startaufgabe|  
    |`Button2`|`Text`|Abbrechen|  
    |`Label`|`(Name)`, `Text`|lblprozentudone, 0|  
  
4. Wählen Sie im Menü **Projekt** die Option **Klasse hinzufügen** aus, um `Widget.vb` dem Projekt eine Klasse mit dem Namen hinzuzufügen.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>So deklarieren Sie ein Ereignis für die Widget-Klasse  
  
- Verwenden Sie das- `Event` Schlüsselwort zum Deklarieren eines Ereignisses in der- `Widget` Klasse. Beachten Sie, dass ein Ereignis über `ByVal` -und `ByRef` -Argumente verfügen kann, wie `Widget` das- `PercentDone` Ereignis veranschaulicht:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 Wenn das aufrufenden Objekt ein- `PercentDone` Ereignis empfängt, enthält das- `Percent` Argument den Prozentsatz der abgeschlossenen Aufgabe. Das- `Cancel` Argument kann auf festgelegt werden, `True` um die Methode abzubrechen, die das Ereignis ausgelöst hat.  
  
> [!NOTE]
> Sie können Ereignis Argumente genau wie Argumente von Prozeduren deklarieren, mit den folgenden Ausnahmen: Ereignisse können `Optional` keine `ParamArray` -oder-Argumente aufweisen, und Ereignisse haben keine Rückgabewerte.  
  
 Das- `PercentDone` Ereignis wird von der- `LongTask` Methode der-Klasse ausgelöst `Widget` . `LongTask` erfordert zwei Argumente: die Zeitdauer, die die Methode vor dem Ausführen der Arbeit vornimmt, und das minimale Zeitintervall vor dem Anhalten, `LongTask` um das Ereignis zu erhöhen `PercentDone` .  
  
#### <a name="to-raise-the-percentdone-event"></a>So heben Sie das Ereignis "" vom  
  
1. Wenn Sie den Zugriff auf die `Timer` von dieser Klasse verwendete Eigenschaft vereinfachen möchten, fügen Sie eine- `Imports` Anweisung oberhalb der-Anweisung am Anfang des Deklarations Abschnitts des Klassen Moduls hinzu `Class Widget` .  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. Fügen Sie der `Widget`-Klasse folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 Wenn die Anwendung die- `LongTask` Methode aufruft, löst die- `Widget` Klasse das- `PercentDone` Ereignis alle `MinimumInterval` Sekunden aus. Wenn das Ereignis zurückgibt, `LongTask` prüft, ob das- `Cancel` Argument auf festgelegt wurde `True` .  
  
 Hier sind einige Haftungsausschlüsse erforderlich. Der Einfachheit halber wird `LongTask` bei der Vorgehensweise davon ausgegangen, dass Sie im Voraus wissen, wie lange die Aufgabe dauert. Dies ist fast nie der Fall. Das Aufteilen von Aufgaben in Blöcke mit gleichmäßiger Größe kann schwierig sein, und häufig ist das, was für Benutzer am wichtigsten ist, einfach die Zeitspanne, die verstrichen ist, bevor Sie einen Hinweis darauf erhalten, dass etwas passiert.  
  
 Möglicherweise haben Sie in diesem Beispiel einen weiteren Fehler erkannt. Die- `Timer` Eigenschaft gibt die Anzahl der Sekunden zurück, die seit Mitternacht vergangen sind. Daher bleibt die Anwendung hängen, wenn Sie unmittelbar vor Mitternacht gestartet wird. Ein sorgfältiger Ansatz zum Messen der Zeit würde Grenzbedingungen wie diese berücksichtigen oder die Verwendung von Eigenschaften wie z `Now` . b. vermeiden.  
  
 Nachdem die `Widget` Klasse nun Ereignisse aufhebt, können Sie mit der nächsten exemplarischen Vorgehensweise fortfahren. Exemplarische Vorgehensweise [: Behandeln von Ereignissen](walkthrough-handling-events.md) veranschaulicht, wie verwendet wird, `WithEvents` um dem-Ereignis einen Ereignishandler zuzuordnen `PercentDone` .  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [Exemplarische Vorgehensweise: Behandeln von Ereignissen](walkthrough-handling-events.md)
- [Ereignisse](index.md)
