---
title: "Walkthrough: Creating and Implementing Interfaces (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interfaces, walkthroughs"
  - "interfaces, testing"
  - "interface implementation, walkthrough"
  - "interfaces, creating"
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Walkthrough: Creating and Implementing Interfaces (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Schnittstellen beschreiben die Merkmale von Feldern, Eigenschaften, Methoden und Ereignissen, wobei die Einzelheiten der Implementierung in Strukturen oder Klassen definiert sind.  
  
 Diese exemplarische Vorgehensweise veranschaulicht das Deklarieren und Implementieren einer Schnittstelle.  
  
> [!NOTE]
>  Diese exemplarische Vorgehensweise bietet keine Informationen dazu, wie eine Benutzeroberfläche erstellt wird.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### So definieren Sie eine Schnittstelle  
  
1.  Öffnen Sie ein neues [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Windows\-Anwendungsprojekt.  
  
2.  Fügen Sie dem Projekt ein neues Modul hinzu, indem Sie im Menü **Projekt** auf **Modul hinzufügen** klicken.  
  
3.  Benennen Sie das neue Modul `Module1.vb`, und klicken Sie auf **Hinzufügen**.  Der Code für das neue Modul wird angezeigt.  
  
4.  Definieren Sie in `Module1` die `TestInterface`\-Schnittstelle, indem Sie `Interface TestInterface` zwischen der `Module`\-Anweisung und der `End Module`\-Anweisung eingeben und dann die EINGABETASTE drücken.  Der **Code\-Editor** rückt das `Interface`\-Schlüsselwort ein und fügt eine `End Interface`\-Anweisung hinzu, um einen Codeblock zu bilden.  
  
5.  Definieren Sie eine Eigenschaft, eine Methode und ein Ereignis für die Schnittstelle, indem Sie zwischen der `Interface`\-Anweisung und der `End Interface`\-Anweisung folgenden Code einfügen:  
  
     [!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]  
  
## Implementierung  
 Die Syntax für das Deklarieren von Schnittstellenmembern unterscheidet sich von der Syntax für das Deklarieren von Klassenmembern.  Die Ursache für diesen Unterschied ist, dass Schnittstellen keinen Implementierungscode enthalten können.  
  
#### So implementieren Sie die Schnittstelle  
  
1.  Fügen Sie eine Klasse mit dem Namen `ImplementationClass` hinzu, indem Sie in `Module1` nach der `End Interface`\-Anweisung und vor der `End Module`\-Anweisung die folgende Anweisung einfügen und dann die EINGABETASTE drücken:  
  
     [!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]  
  
     Wenn Sie in der IDE \(Integrated Development Environment\) arbeiten, stellt der **Code\-Editor** eine entsprechende `End Class`\-Anweisung bereit, sobald Sie die EINGABETASTE drücken.  
  
2.  Fügen Sie `ImplementationClass` die folgende `Implements`\-Anweisung hinzu, die die von der Klasse implementierte Schnittstelle benennt:  
  
     [!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]  
  
     Wenn die `Implements`\-Anweisung getrennt von anderen Elementen am Anfang einer Klasse oder Struktur steht, gibt sie an, dass die Klasse bzw. Struktur eine Schnittstelle implementiert.  
  
     Wenn Sie in der IDE \(Integrated Development Environment\) arbeiten, implementiert der **Code\-Editor** die für `TestInterface` erforderlichen Klassenmember, sobald Sie die EINGABETASTE drücken. Der nächste Schritt wird dadurch übersprungen.  
  
3.  Wenn Sie nicht innerhalb der integrierten Entwicklungsumgebung arbeiten, müssen Sie alle Member der `MyInterface`\-Schnittstelle implementieren.  Fügen Sie `ImplementationClass` folgenden Code hinzu, um `Event1`, `Method1` und `Prop1` zu implementieren.  
  
     [!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]  
  
     Die `Implements`\-Anweisung benennt die Schnittstelle und den Schnittstellenmember, der implementiert wird.  
  
4.  Vervollständigen Sie die Definition von `Prop1`, indem Sie der Klasse, in der der Eigenschaftswert gespeichert wurde, ein privates Feld hinzufügen:  
  
     [!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]  
  
     Geben Sie den Wert von `pval` aus dem get\-Accessor der Eigenschaft zurück.  
  
     [!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]  
  
     Legen Sie den Wert von `pval` im set\-Accessor der Eigenschaft fest.  
  
     [!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]  
  
5.  Vervollständigen Sie die Definition von `Method1`, indem Sie folgenden Code hinzufügen.  
  
     [!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]  
  
#### So testen Sie die Implementierung der Schnittstelle  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Startformular des Projekts, und klicken Sie dann auf **Code anzeigen**.  Im Editor wird die Klasse des Startformulars angezeigt.  In der Standardeinstellung wird das Startformular mit `Form1` bezeichnet.  
  
2.  Fügen Sie der `Form1`\-Klasse das folgende `testInstance`\-Feld hinzu:  
  
     [!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]  
  
     Wenn `testInstance` als `WithEvents` deklariert wird, kann die `Form1`\-Klasse seine Ereignisse behandeln.  
  
3.  Fügen Sie der `Form1`\-Klasse folgenden Ereignishandler hinzu, um durch `testInstance` ausgelöste Ereignisse zu behandeln:  
  
     [!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]  
  
4.  Fügen Sie der `Form1`\-Klasse eine Unterroutine mit dem Namen `Test` hinzu, um die Implementierungsklasse zu testen:  
  
     [!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]  
  
     Die `Test`\-Prozedur erstellt eine Instanz der Klasse, die `MyInterface` implementiert, weist diese Instanz dem `testInstance`\-Feld zu, legt eine Eigenschaft fest und führt eine Methode über die Schnittstelle aus.  
  
5.  Fügen Sie Code ein, um die `Test`\-Prozedur aus der `Form1 Load`\-Prozedur des Startformulars heraus aufzurufen:  
  
     [!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]  
  
6.  Führen Sie die `Test`\-Prozedur aus, indem Sie F5 drücken.  Die Meldung "Prop1 was set to 9" wird angezeigt.  Nachdem Sie auf OK geklickt haben, wird die Meldung "The X parameter for Method1 is 5" angezeigt.  Klicken Sie auf OK. Daraufhin wird die Meldung "The event handler caught the event" angezeigt.  
  
## Siehe auch  
 [Implements Statement](../../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Interfaces](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)   
 [Interface Statement](../../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md)