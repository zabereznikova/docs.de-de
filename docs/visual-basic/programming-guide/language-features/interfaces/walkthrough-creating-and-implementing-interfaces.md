---
title: Erstellen und Implementieren von Schnittstellen (Visual Basic) | Microsoft-Dokumentation
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
- interfaces, walkthroughs
- interfaces, testing
- interface implementation, walkthrough
- interfaces, creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 076bc8d33e97286c31f27a2016e39a25e9cec22c
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Exemplarische Vorgehensweise: Erstellen und Implementieren von Schnittstellen (Visual Basic)
Schnittstellen beschreiben die Merkmale von Eigenschaften, Methoden und Ereignisse, aber die Einzelheiten der Implementierung in Strukturen oder Klassen.  
  
 Diese exemplarische Vorgehensweise veranschaulicht das Deklarieren und Implementieren einer Schnittstelle.  
  
> [!NOTE]
>  Diese exemplarische Vorgehensweise stellt Informationen zum Erstellen einer Benutzeroberfläche bereit.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-an-interface"></a>So definieren Sie eine Schnittstelle  
  
1.  Öffnen Sie eine neue [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows-Anwendungsprojekt.  
  
2.  Fügen Sie ein neues Modul in das Projekt, indem Sie auf **Modul hinzufügen** auf der **Projekt** Menü.  
  
3.  Nennen Sie das neue Modul `Module1.vb` , und klicken Sie auf **hinzufügen**. Der Code für das neue Modul wird angezeigt.  
  
4.  Definieren Sie eine Schnittstelle mit dem Namen `TestInterface` in `Module1` durch Eingabe `Interface TestInterface` zwischen der `Module` und `End Module` -Anweisungen, und drücken Sie die EINGABETASTE. Die **Code-Editor** Einzüge der `Interface` Schlüsselwort und fügt eine `End Interface` Anweisung um einen Codeblock zu bilden.  
  
5.  Definieren Sie eine Eigenschaft, eine Methode und ein Ereignis für die Schnittstelle durch Platzieren den folgenden Code zwischen die `Interface` und `End Interface` Anweisungen:  
  
     [!code-vb[VbVbalrOOP&#98;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]  
  
## <a name="implementation"></a>Implementierung  
 Sie können feststellen, dass die Syntax zum Deklarieren von Schnittstellenmembern unterscheidet die Syntax zum Deklarieren von Klassenmembern. Ursache für diesen Unterschied die Tatsache, dass Schnittstellen Implementierungscode enthalten können.  
  
#### <a name="to-implement-the-interface"></a>Implementieren die Schnittstelle  
  
1.  Fügen Sie eine Klasse mit dem Namen `ImplementationClass` durch Hinzufügen folgender Anweisung zu `Module1`nach dem `End Interface` Anweisung aber vor der `End Module` -Anweisung, und drücken Sie die EINGABETASTE:  
  
     [!code-vb[VbVbalrOOP&#99;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]  
  
     Wenn Sie in der IDE arbeiten die **Code-Editor** stellt eine entsprechende `End Class` -Anweisung, wenn Sie die EINGABETASTE drücken.  
  
2.  Fügen Sie die folgenden `Implements` -Anweisung `ImplementationClass`, implementiert die Schnittstelle der Klasse Namen:  
  
     [!code-vb[VbVbalrOOP&#100;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]  
  
     Wenn getrennt von anderen Elementen am Anfang einer Klasse oder Struktur steht die `Implements` Anweisung gibt an, dass die Klasse oder Struktur eine Schnittstelle implementiert.  
  
     Wenn Sie in der IDE arbeiten die **Code-Editor** implementiert die erforderlichen Klassenmember `TestInterface` Wenn Sie die EINGABETASTE, und können Sie den nächsten Schritt überspringen.  
  
3.  Wenn Sie nicht innerhalb der IDE arbeiten, müssen Sie alle Member der Schnittstelle implementieren `MyInterface`. Fügen Sie den folgenden Code `ImplementationClass` implementieren `Event1`, `Method1`, und `Prop1`:  
  
     [!code-vb[VbVbalrOOP&#101;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]  
  
     Die `Implements` -Anweisung benennt die Schnittstelle und die Member der Schnittstelle implementiert wird.  
  
4.  Vervollständigen Sie die Definition des `Prop1` durch Hinzufügen eines privaten Felds auf die Klasse, die den Wert der Eigenschaft gespeichert:  
  
     [!code-vb[VbVbalrOOP&#102;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]  
  
     Der Rückgabewert von der `pval` aus der Eigenschaft get-Accessor.  
  
     [!code-vb[VbVbalrOOP&#103;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]  
  
     Legen Sie den Wert von `pval` in der Eigenschaft set-Accessor.  
  
     [!code-vb[VbVbalrOOP&#104;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]  
  
5.  Vervollständigen Sie die Definition der `Method1` durch den folgenden Code hinzufügen.  
  
     [!code-vb[VbVbalrOOP&#105;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]  
  
#### <a name="to-test-the-implementation-of-the-interface"></a>So testen Sie die Implementierung der Schnittstelle  
  
1.  Mit der rechten Maustaste des Startformulars für das Projekt in der **Projektmappen-Explorer**, und klicken Sie auf **Anzeigecode**. Der Editor zeigt die Klasse des Startformulars. Standardmäßig ist das Startformular bezeichnet `Form1`.  
  
2.  Fügen Sie die folgenden `testInstance` Feld der `Form1` Klasse:  
  
     [!code-vb[VbVbalrOOP&#120;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]  
  
     Durch Deklarieren `testInstance` als `WithEvents`die `Form1` Klasse, die Ereignisse behandeln kann.  
  
3.  Fügen Sie den folgenden Ereignishandler, um die `Form1` Klasse ausgelöste Ereignisse behandeln `testInstance`:  
  
     [!code-vb[VbVbalrOOP&#106;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]  
  
4.  Fügen Sie eine Unterroutine namens `Test` an die `Form1` Klasse, um die Implementierungsklasse zu testen:  
  
     [!code-vb[VbVbalrOOP&#107;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]  
  
     Die `Test` Prozedur erstellt eine Instanz der Klasse, die implementiert `MyInterface`, weist diese Instanz dem `testInstance` Feld legt eine Eigenschaft fest und führt eine Methode über die Schnittstelle.  
  
5.  Fügen Sie Code zum Aufrufen der `Test` Prozedur aus der `Form1 Load` Verfahren des Startformulars:  
  
     [!code-vb[VbVbalrOOP&#108;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]  
  
6.  Führen Sie die `Test` Prozedur durch Drücken von F5. Die Meldung "Prop1 was set to 9" wird angezeigt. Nachdem Sie OK, klicken Sie auf die Meldung "The X Parameter for Method1 is 5" wird angezeigt. Klicken Sie auf OK, und die Meldung "der Ereignishandler das Ereignis erfasst" angezeigt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Implements-Anweisung](../../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Schnittstellen](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)   
 [Interface-Anweisung](../../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Event-Anweisung](../../../../visual-basic/language-reference/statements/event-statement.md)

