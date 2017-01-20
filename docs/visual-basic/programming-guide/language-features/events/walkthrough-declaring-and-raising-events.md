---
title: "Walkthrough: Declaring and Raising Events (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declarations, events"
  - "events [Visual Basic], walkthroughs"
  - "declaring events, walkthroughs"
  - "events [Visual Basic], declaring"
  - "events [Visual Basic], raising"
  - "raising events, walkthroughs"
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Walkthrough: Declaring and Raising Events (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Ereignisse für eine Klasse mit der Bezeichnung `Widget` deklariert und ausgelöst werden.  Nachdem Sie die einzelnen Schritte ausgeführt haben, können Sie bei Interesse auch das an diese Thematik anknüpfende Thema \([Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)\) lesen. Dort wird gezeigt, wie Ereignisse aus `Widget`\-Objekten verwendet werden, um in einer Anwendung Statusinformationen zur Verfügung zu stellen.  
  
## Die Widget\-Klasse  
 Nehmen wir für den Moment einfach an, Sie verfügen über eine `Widget`\-Klasse.  Diese `Widget`\-Klasse enthält eine Methode, für deren Ausführung einige Zeit beansprucht wird, und Sie möchten nun, dass die Anwendung in der Lage ist, einen Ausführungsindikator zu erstellen.  
  
 Sie können das `Widget`\-Objekt natürlich so deklarieren, dass ein Dialogfeld mit einer Statusanzeige angezeigt wird. In diesem Fall ist jedoch in jedem Projekt, in dem die `Widget`\-Klasse verwendet wurde, dieses Dialogfeld vorhanden.  Eine nützliche Regel beim Objektentwurf stellt die Festlegung dar, dass die Benutzeroberfläche von der Anwendung, die ein Objekt verwendet, behandelt wird. Dies gilt nicht, wenn der alleinige Zweck des Objekts darin besteht, ein Formular oder Dialogfeld zu verwalten.  
  
 Da `Widget` auch andere Aufgaben ausführt, sollte ein `PercentDone`\-Ereignis hinzugefügt und für die Behandlung dieses Ereignisses und die Statusanzeige die Prozedur verwendet werden, die die Methoden der `Widget`\-Klasse aufruft.  Das `PercentDone`\-Ereignis kann auch einen Mechanismus zum Abbrechen der Aufgabe bereitstellen.  
  
#### So erstellen Sie das Codebeispiel für dieses Thema  
  
1.  Öffnen Sie ein neues [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Windows\-Anwendungsprojekt, und erstellen Sie ein Formular mit dem Namen `Form1`.  
  
2.  Fügen Sie `Form1` zwei Schaltflächen und eine Bezeichnung hinzu.  
  
3.  Benennen Sie die Objekte wie in der folgenden Tabelle:  
  
    |Objekt|Property|Einstellung|  
    |------------|--------------|-----------------|  
    |`Button1`|`Text`|Start Task|  
    |`Button2`|`Text`|Abbrechen|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4.  Klicken Sie im Menü **Projekt** auf **Klasse hinzufügen**, um dem Projekt die Klasse `Widget.vb` hinzuzufügen.  
  
#### So deklarieren Sie ein Ereignis für die Widget\-Klasse  
  
-   Verwenden Sie das `Event`\-Schlüsselwort, um in der `Widget`\-Klasse ein Ereignis zu deklarieren.  Ereignisse können über das `ByVal`\-Argument und das `ByRef`\-Argument verfügen. Dies wird im `PercentDone`\-Ereignis von `Widget` veranschaulicht:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/VbEventWalkthrough/Widget.vb#1)]  
  
 Wenn das aufrufende Objekt ein `PercentDone`\-Ereignis erhält, enthält das `Percent`\-Argument den Prozentsatz der Aufgabe, die abgeschlossen wurde.  Um die Methode abzubrechen, die das Ereignis ausgelöst hat, kann für das `Cancel`\-Argument der Wert `True` festgelegt werden.  
  
> [!NOTE]
>  Sie können Ereignisargumente auf dieselbe Weise wie Argumente von Prozeduren deklarieren, mit den folgenden Ausnahmen: Ereignisse dürfen keine `Optional`\-Argumente oder `ParamArray`\-Argumente haben und haben keine Rückgabewerte.  
  
 Das `PercentDone`\-Ereignis wird von der `LongTask`\-Methode der `Widget`\-Klasse ausgelöst.  `LongTask` erfordert zwei Argumente: die Zeitspanne, die für die Ausführung der Methode vorgegeben wird, und das minimale Zeitintervall, bevor `LongTask` angehalten wird, um das `PercentDone`\-Ereignis auszulösen.  
  
#### So lösen Sie das PercentDone\-Ereignis aus  
  
1.  Um den Zugriff auf die von dieser Klasse verwendete `Timer`\-Eigenschaft zu vereinfachen, fügen Sie im oberen Bereich des Deklarationsabschnitts des Klassenmoduls über der `Class Widget`\-Anweisung eine `Imports`\-Anweisung ein.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/VbEventWalkthrough/Widget.vb#2)]  
  
2.  Fügen Sie der `Widget`\-Klasse folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/VbEventWalkthrough/Widget.vb#3)]  
  
 Wenn die Anwendung die `LongTask`\-Methode aufruft, löst die `Widget`\-Klasse in einem Intervall, das mit `MinimumInterval` Sekunden angegeben wird, das `PercentDone`\-Ereignis aus.  Wenn das Ereignis beendet wird, überprüft `LongTask`, ob das `Cancel`\-Argument auf `True` festgelegt wurde.  
  
 An diesem Punkt müssen einige Einschränkungen gemacht werden.  Bei der `LongTask`\-Prozedur wird der Einfachheit halber davon ausgegangen, dass Sie bereits im Voraus wissen, wie lange die Ausführung der Aufgabe dauert.  Dies ist unter normalen Umständen nur sehr selten der Fall.  Die Aufteilung von Aufgaben in Segmente gleicher Größe kann sich als schwierig erweisen. In den meisten Fällen möchten die Benutzer vor allem wissen, wie viel Zeit vergeht, bis sie darauf hingewiesen werden, dass etwas geschieht.  
  
 Möglicherweise haben Sie einen weiteren Schwachpunkt in diesem Beispiel entdeckt.  Die `Timer`\-Eigenschaft gibt die Anzahl der seit Mitternacht vergangenen Sekunden zurück. Aus diesem Grund bleibt die Anwendung hängen, wenn sie kurz vor Mitternacht gestartet wurde.  Bei einem exakteren Ansatz werden derartige Grenzbedingungen in der Zeitmessung in Betracht gezogen oder durch Verwendung einer Eigenschaft, z. B. `Now`, vollständig vermieden.  
  
 Die `Widget`\-Klasse kann jetzt Ereignisse auslösen, und Sie können mit der nächsten exemplarischen Vorgehensweise fortfahren.  [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) veranschaulicht, wie `WithEvents` verwendet wird, um dem `PercentDone`\-Ereignis einen Ereignishandler zuzuordnen.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>   
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>   
 [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)   
 [Events](../../../../visual-basic/programming-guide/language-features/events/events.md)