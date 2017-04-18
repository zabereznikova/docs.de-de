---
title: Implementieren von IEnumerable in Visual Basic | Microsoft-Dokumentation
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
- control flow [Visual Basic]
- enumerable interfaces
- loop structures, optimizing performance
- control flow
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
caps.latest.revision: 15
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
ms.openlocfilehash: 68c37c46cbceb1056d50972cdc58ddb7c7577447
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Exemplarische Vorgehensweise: Implementieren von IEnumerable(Of T) in Visual Basic
Die <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle wird implementiert von Klassen, die eine Sequenz von Werten ein Element zu einem Zeitpunkt zurückgeben können.</xref:System.Collections.Generic.IEnumerable%601> Der Vorteil der Rückgabe von Daten, die jeweils ein Element ist, dass Sie nicht den vollständigen Satz von Daten in den Speicher derzeit geladen. Sie müssen nur genügend Arbeitsspeicher verwenden, um ein einzelnes Element aus den Daten zu laden. Klassen, in denen die `IEnumerable(T)` Schnittstelle kann verwendet werden, mit `For Each` Schleifen oder LINQ-Abfragen.  
  
 Betrachten Sie z. B. eine Anwendung, die eine große Textdatei lesen muss, und jede Zeile aus der Datei, die bestimmten Suchkriterien entspricht zurückzugeben. Die Anwendung verwendet eine LINQ-Abfrage zurückzugebenden Zeilen aus der Datei, die den angegebenen Kriterien entsprechen. Um den Inhalt der Datei werden mithilfe einer LINQ-Abfrage abzufragen, konnte die Anwendung den Inhalt der Datei in ein Array oder eine Auflistung laden. Laden die gesamte Datei in ein Array oder eine Auflistung würde jedoch weitaus mehr Arbeitsspeicher als erforderlich nutzen. Die LINQ-Abfrage konnte stattdessen den Inhalt der Datei mit Abfragen eine enumerable-Klasse, nur Werte zurückgeben, die den Suchkriterien entsprechen. Abfragen, die nur wenige zurückgeben übereinstimmende Werte würden deutlich weniger Arbeitsspeicher belegen.  
  
 Sie können eine Klasse erstellen, implementiert die <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle, um Quelldaten als aufzählbare Daten verfügbar zu machen.</xref:System.Collections.Generic.IEnumerable%601> Die Klasse, die implementiert die `IEnumerable(T)` Schnittstelle benötigt eine andere Klasse, die implementiert die <xref:System.Collections.Generic.IEnumerator%601>Schnittstelle zum Durchlaufen der Quelldaten.</xref:System.Collections.Generic.IEnumerator%601> Diese beiden Klassen können Sie Elemente der Daten sequenziell als bestimmten Typ zurückgibt.  
  
 In dieser exemplarischen Vorgehensweise erstellen Sie eine Klasse, implementiert der `IEnumerable(Of String)` Schnittstelle und die Klasse, die implementiert die `IEnumerator(Of String)` Schnittstelle, um eine Textdatei zeilenweise zu lesen.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Erstellen der Enumerable-Klasse  
  
|Zum Erstellen des Projekts enumerable-Klasse|  
|---|  
|1.  In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]auf der **Datei** auf **neu** , und klicken Sie dann auf **Projekt**.<br />2.  In der **neues Projekt** im Feld der **Projekttypen** Bereich, stellen Sie sicher, dass **Windows** ausgewählt ist. Wählen Sie **-Klassenbibliothek** in der **Vorlagen** Bereich. In der **Namen** geben `StreamReaderEnumerable`, und klicken Sie dann auf **OK**. Das neue Projekt wird angezeigt.<br />3.  In **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei "Class1.vb" um, und klicken Sie auf **umbenennen**. Benennen Sie die Datei `StreamReaderEnumerable.vb` , und drücken Sie die EINGABETASTE. Umbenennen der Datei wird auch die Klasse umbenennen `StreamReaderEnumerable`. Diese Klasse implementiert die `IEnumerable(Of String)` Schnittstelle.<br />4.  Mit der rechten Maustaste des Projekts StreamReaderEnumerable, zeigen Sie auf **hinzufügen**, und klicken Sie dann auf **neues Element**. Wählen Sie die **Klasse** Vorlage. In der **Namen** geben `StreamReaderEnumerator.vb` , und klicken Sie auf **OK**.|  
  
 Die erste Klasse in diesem Projekt ist die enumerable-Klasse und Implementieren der `IEnumerable(Of String)` Schnittstelle. Diese generische Schnittstelle implementiert die <xref:System.Collections.IEnumerable>-Schnittstelle und gewährleistet, dass Consumer dieser Klasse auf Werte vom Typ zugreifen können `String`.</xref:System.Collections.IEnumerable>  
  
|Der Code zum Implementieren von IEnumerable hinzu|  
|---|  
|1.  Öffnen Sie die Datei StreamReaderEnumerable.vb.<br />2.  In der Zeile nach `Public Class StreamReaderEnumerable`, geben Sie Folgendes ein, und drücken Sie die EINGABETASTE.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#1;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]füllt automatisch die Klasse mit den Elementen, die erforderlich sind die `IEnumerable(Of String)` Schnittstelle.<br />3.  Diese enumerable-Klasse werden Zeilen aus einer Textdatei zeilenweise zu lesen. Fügen Sie den folgenden Code der Klasse einen öffentlichen Konstruktor verfügbar machen, der einen Dateipfad als Eingabeparameter akzeptiert.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#2;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]<br />4.  Die Implementierung von der <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>Methode der `IEnumerable(Of String)` -Schnittstelle zurückgeben, wird eine neue Instanz der der `StreamReaderEnumerator` Klasse</xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> Die Implementierung der `GetEnumerator` Methode der `IEnumerable` Schnittstelle erfolgen `Private`, da Sie nur Member verfügbar machen müssen die `IEnumerable(Of String)` Schnittstelle. Ersetzen Sie den Code, der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] für generiert die `GetEnumerator` Methoden mit den folgenden Code.<br />     [!code-vb[VbVbalrIteratorWalkthrough&3;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]|  
  
|Der Code zum Implementieren von IEnumerator hinzu|  
|---|  
|1.  Öffnen Sie die Datei StreamReaderEnumerator.vb.<br />2.  In der Zeile nach `Public Class StreamReaderEnumerator`, geben Sie Folgendes ein, und drücken Sie die EINGABETASTE.<br />     [!code-vb[VbVbalrIteratorWalkthrough&4;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]füllt automatisch die Klasse mit den Elementen, die erforderlich sind die `IEnumerator(Of String)` Schnittstelle.<br />3.  Die Enumeratorklasse öffnet die Textdatei und führt die Datei-e/a auf die Zeilen aus der Datei gelesen. Fügen Sie folgenden Code der Klasse einen öffentlichen Konstruktor, der einen Dateipfad als Eingabeparameter akzeptiert verfügbar machen, und öffnen die Textdatei zum Lesen.<br />     [!code-vb[VbVbalrIteratorWalkthrough&5;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]<br />4.  Die `Current` für beide Eigenschaften die `IEnumerator(Of String)` und `IEnumerator` Schnittstellen zurückgeben des aktuellen Elements aus der Textdatei als ein `String`. Die Implementierung von der `Current` Eigenschaft der `IEnumerator` Schnittstelle erfolgen `Private`, da Sie nur Member verfügbar machen müssen die `IEnumerator(Of String)` Schnittstelle. Ersetzen Sie den Code, der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] für generiert die `Current` Eigenschaften mit den folgenden Code.<br />     [!code-vb[VbVbalrIteratorWalkthrough&6;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]<br />5.  Die `MoveNext` Methode der `IEnumerator` Benutzeroberfläche wechselt zum nächsten Element in der Textdatei und aktualisiert den Wert der von zurückgegebene die `Current` Eigenschaft. Es sind keine Elemente mehr zu lesen, die `MoveNext` -Methode gibt `False`andernfalls die `MoveNext` -Methode gibt `True`. Fügen Sie der `MoveNext`-Methode folgenden Code hinzu.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#7;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]<br />6.  Die `Reset` Methode der `IEnumerator` Schnittstelle weist den Iterator auf den Anfang der Datei und löscht den aktuellen Elementwert. Fügen Sie der `Reset`-Methode folgenden Code hinzu.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#8;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]<br />7.  Die `Dispose` Methode der `IEnumerator` Schnittstelle garantiert, dass alle nicht verwaltete Ressourcen freigegeben werden, bevor der Iterator zerstört wird. Das Dateihandle, mit dem die `StreamReader` -Objekt ist eine nicht verwaltete Ressource und muss geschlossen werden, bevor die Iteratorinstanz zerstört wird. Ersetzen Sie den Code, der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] für generiert die `Dispose` -Methode durch den folgenden Code.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#9;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)]|  
  
## <a name="using-the-sample-iterator"></a>Mithilfe des Beispieliterators  
 Können Sie eine enumerable-Klasse im Code zusammen mit Steuerungsstrukturen, die ein Objekt erfordern, die implementiert `IEnumerable`, wie z. B. eine `For Next` -Schleife oder eine LINQ-Abfrage. Das folgende Beispiel zeigt die `StreamReaderEnumerable` in einer LINQ-Abfrage.  
  
 [!code-vb[VbVbalrIteratorWalkthrough&#10;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [For Each...Next-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)

