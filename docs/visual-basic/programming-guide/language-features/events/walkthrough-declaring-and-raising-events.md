---
title: "Deklarieren und Auslösen von Ereignissen (Visual Basic) | Microsoft-Dokumentation"
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
- declarations, events
- events [Visual Basic], walkthroughs
- declaring events, walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events, walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: 16
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
ms.openlocfilehash: 233673c1d42684b7caa9042d18fb341a1043a31b
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen (Visual Basic)
Diese exemplarische Vorgehensweise veranschaulicht das Deklarieren und Auslösen von Ereignissen für eine Klasse mit dem Namen `Widget`. Nachdem Sie die Schritte abgeschlossen haben, empfiehlt begleitthema, lesen [Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), die zeigt, wie Ereignisse aus `Widget` Objekte zum Bereitstellen von Statusinformationen in einer Anwendung.  
  
## <a name="the-widget-class"></a>Die Widget-Klasse  
 Nehmen Sie für den Moment, die Sie an einer `Widget` Klasse. Die `Widget` -Klasse verfügt über eine Methode, die zum Ausführen einer lange dauern kann, und Sie möchten die Anwendung einige Abschluss Indikator erstellen können.  
  
 Natürlich, Sie können die `Widget` Objekt ein Statusanzeige-Dialogfeld anzeigen, jedoch hängen mit diesem Dialogfeld in jedem Projekt, in dem Sie verwendet, die `Widget` Klasse. Verhaltensweise des Objektdesign stellt die Anwendung, die ein Objekthandle der Benutzeroberfläche verwendet, es sei denn, die gesamte des Objekts dient zum Verwalten von einem Formular oder das Dialogfeld.  
  
 Der Zweck der `Widget` werden weitere Aufgaben erledigen, daher ist es besser, Hinzufügen einer `PercentDone` Ereignis und die Prozedur, die aufgerufen `Widget`Methoden des behandelt werden, dass Ereignis und die Statusanzeige. Die `PercentDone` -Ereignis kann auch einen Mechanismus zum Abbrechen der Aufgabe bereitstellen.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Das Codebeispiel in diesem Thema erstellen  
  
1.  Öffnen Sie eine neue [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows-Anwendung und erstellen Sie ein Formular mit dem Namen `Form1`.  
  
2.  Fügen Sie zwei Schaltflächen und eine Bezeichnung, die `Form1`.  
  
3.  Benennen Sie die Objekte, wie in der folgenden Tabelle dargestellt.  
  
    |Objekt|Eigenschaft|Einstellung|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Startaufgabe|  
    |`Button2`|`Text`|Abbrechen|  
    |`Label`|`(Name)`, `Text`|LblPercentDone, 0|  
  
4.  Auf der **Projekt** Menü wählen **Klasse hinzufügen** eine Klasse mit dem Namen `Widget.vb` zum Projekt.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Deklariert ein Ereignis für die Widget-Klasse  
  
-   Verwenden der `Event` -Schlüsselwort zu deklarieren, ein Ereignis in der `Widget` Klasse. Beachten Sie, dass ein Ereignis kann `ByVal` und `ByRef` Argumente als `Widget`des `PercentDone` Ereignis veranschaulicht wird:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#1;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 Erhält das aufrufende Objekt ein `PercentDone` -Ereignis, das `Percent` -Argument enthält den Anteil der Vorgang abgeschlossen ist. Die `Cancel` Argument festgelegt werden kann, um `True` zum Abbrechen der Methode, die das Ereignis ausgelöst hat.  
  
> [!NOTE]
>  Sie können Ereignisargumente deklarieren, wie Argumente von Prozeduren mit den folgenden Ausnahmen: Ereignisse dürfen keine `Optional` oder `ParamArray` -Argumente haben und keine Werte zurückgeben.  
  
 Die `PercentDone` -Ereignis wird ausgelöst, indem die `LongTask` Methode der `Widget` Klasse. `LongTask`akzeptiert zwei Argumente: die Zeitspanne zu arbeiten, und das minimale Zeitintervall vor dem Ausführen der Methode vorgegeben `LongTask` Pausen zum Auslösen der `PercentDone` Ereignis.  
  
#### <a name="to-raise-the-percentdone-event"></a>Zum Auslösen des Ereignisses PercentDone  
  
1.  Um Zugriff auf die `Timer` Eigenschaft, die von dieser Klasse verwendete hinzufügen ein `Imports` Anweisung am Anfang der Deklarationsabschnitt des Klassenmoduls, über die `Class Widget` Anweisung.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#2;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  Fügen Sie der `Widget` -Klasse folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&3;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 Bei einem Aufruf der `LongTask` -Methode, die `Widget` -Klasse löst die `PercentDone` Ereignis jedes `MinimumInterval` Sekunden. Gibt das Ereignis `LongTask` überprüft, ob die `Cancel` Argument festgelegt wurde, um `True`.  
  
 Hier sind einige Haftungsausschlüsse erforderlich. Der Einfachheit halber die `LongTask` Verfahren wird vorausgesetzt, Sie wissen im voraus, wie lange der Vorgang dauert. Dies ist fast nie der Fall. Unterteilen Aufgaben in Segmente gleicher Größe kann schwierig sein, und häufig an Benutzer verpassen wird einfach die Zeitspanne, die vergeht, bevor man ein Hinweis darauf, dass etwas geschieht.  
  
 Sie können einen anderen Fehler in diesem Beispiel erkannt haben. Die `Timer` Eigenschaft gibt die Anzahl der seit Mitternacht vergangenen Sekunden zurück; aus diesem Grund bleibt die Anwendung hängen, wenn sie kurz vor Mitternacht gestartet wird. Ein sorgfältiger Ansatz zum Messen der Zeit begrenzungsbedingungen wie diesem berücksichtigt werden würde, oder vermeiden Sie sie, wie mithilfe von Eigenschaften `Now`.  
  
 Nachdem die `Widget` -Klasse kann Ereignisse auslösen, können Sie in der nächsten exemplarischen Vorgehensweise verschieben. [Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) veranschaulicht, wie `WithEvents` verknüpfen Sie einen Ereignishandler mit der `PercentDone` Ereignis.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>   
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A></xref:Microsoft.VisualBasic.DateAndTime.Now%2A>   
 [Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)   
 [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
