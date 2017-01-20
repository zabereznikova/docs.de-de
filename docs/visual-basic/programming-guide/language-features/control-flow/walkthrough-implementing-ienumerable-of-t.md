---
title: "Walkthrough: Implementing IEnumerable(Of T) in Visual Basic | Microsoft Docs"
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
  - "control flow [Visual Basic]"
  - "enumerable interfaces"
  - "loop structures, optimizing performance"
  - "control flow"
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Walkthrough: Implementing IEnumerable(Of T) in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die <xref:System.Collections.Generic.IEnumerable%601>\-Schnittstelle wird von Klassen implementiert, die immer jeweils eine Sequenz von Werten zurückgeben können.  Der Vorteil des einzelnen Zurückgebens von Daten liegt darin, dass Sie nicht den vollständigen Satz von Daten in den Arbeitsspeicher laden müssen, um damit zu arbeiten.  Sie müssen nur genügend Arbeitsspeicher verwenden, um ein einzelnes Element der Daten laden zu können.  Klassen, die die `IEnumerable(T)`\-Schnittstelle implementieren, können mit `For Each`\-Schleifen oder LINQ\-Abfragen verwendet werden.  
  
 Betrachten Sie z. B. eine Anwendung, die eine große Textdatei lesen und jede Zeile der Datei zurückgeben muss, die bestimmten Suchkriterien entspricht.  Die Anwendung verwendet eine LINQ\-Abfrage, um die Zeilen aus der Datei zurückzugeben, die mit den angegebenen Kriterien übereinstimmen.  Um den Inhalt der Datei mit einer LINQ\-Abfrage abzufragen, konnte die Anwendung den Inhalt der Datei in ein Array oder eine Auflistung laden.  Das Laden der gesamten Datei in ein Array oder eine Auflistung würde jedoch weitaus mehr Arbeitsspeicher erfordern als nötig.  Die LINQ\-Abfrage konnte stattdessen den Dateiinhalt mithilfe einer aufzählbaren Klasse abfragen und nur Werte zurückgeben, die den Suchkriterien entsprechen.  Abfragen, die nur einige übereinstimmende Werte zurückgeben, würden deutlich weniger Arbeitsspeicher belegen.  
  
 Sie können eine Klasse erstellen, die die <xref:System.Collections.Generic.IEnumerable%601>\-Schnittstelle implementiert, um Quelldaten als aufzählbare Daten verfügbar zu machen.  Die Klasse, die die `IEnumerable(T)`\-Schnittstelle implementiert, erfordert eine weitere Klasse, die die <xref:System.Collections.Generic.IEnumerator%601>\-Schnittstelle implementiert, um die Quelldaten zu durchlaufen.  Diese zwei Klassen ermöglichen es Ihnen, Elemente der Daten sequenziell als bestimmten Typ zurückzugeben.  
  
 In dieser exemplarischen Vorgehensweise wird das Erstellen einer Klasse veranschaulicht, die die `IEnumerable(Of String)`\-Schnittstelle implementiert, sowie einer Klasse, die die `IEnumerator(Of String)`\-Schnittstelle implementiert, um eine Textdatei zeilenweise zu lesen.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
## Erstellen der aufzählbaren Klasse  
  
||  
|-|  
|So erstellen Sie das aufzählbare Klassenprojekt|  
|1.  Zeigen Sie in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.<br />2.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist.  Wählen Sie im Bereich **Vorlagen** den Eintrag **Klassenbibliothek** aus.  Geben Sie im Feld **Name** die Bezeichnung `StreamReaderEnumerable` ein, und klicken Sie auf **OK**.  Das neue Projekt wird angezeigt.<br />3.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die Datei Class1.vb, und klicken Sie auf **Umbenennen**.  Benennen Sie die Datei in `StreamReaderEnumerable.vb` um, und drücken Sie die EINGABETASTE.  Durch das Umbenennen der Datei wird auch die Klasse in `StreamReaderEnumerable` umbenannt.  Diese Klasse implementiert die `IEnumerable(Of String)`\-Schnittstelle.<br />4.  Klicken Sie mit der rechten Maustaste auf das Projekt StreamReaderEnumerable, zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Neues Element**.  Wählen Sie die Vorlage **Klasse** aus.  Geben Sie im Feld **Name** die Bezeichnung `StreamReaderEnumerator.vb` ein, und klicken Sie auf **OK**.|  
  
 Die erste Klasse in diesem Projekt ist die aufzählbare Klasse, die die `IEnumerable(Of String)`\-Schnittstelle implementiert.  Diese generische Schnittstelle implementiert die <xref:System.Collections.IEnumerable>\-Schnittstelle und gewährleistet, dass Consumer dieser Klasse auf Werte vom Typ `String` zugreifen können.  
  
||  
|-|  
|So fügen Sie den Code zum Implementieren von IEnumerable hinzu|  
|1.  Öffnen Sie die Datei StreamReaderEnumerable.vb.<br />2.  Geben Sie in der Zeile nach `Public Class StreamReaderEnumerable` Folgendes ein, und drücken Sie die EINGABETASTE.<br />     [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#1)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] füllt die Klasse automatisch mit den Membern auf, die für die `IEnumerable(Of String)`\-Schnittstelle erforderlich sind.<br />3.  Diese aufzählbare Klasse liest die Zeilen aus einer Textdatei einzeln.  Fügen Sie der Klasse den folgenden Code hinzu, um einen öffentlichen Konstruktor verfügbar zu machen, der einen Dateipfad als Eingabeparameter akzeptiert.<br />     [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#2)]<br />4.  Die Implementierung der <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>\-Methode der `IEnumerable(Of String)`\-Schnittstelle gibt eine neue Instanz der `StreamReaderEnumerator`\-Klasse zurück.  Die Implementierung der `GetEnumerator`\-Methode der `IEnumerable`\-Schnittstelle kann als `Private` festgelegt werden, da Sie nur Member der `IEnumerable(Of String)`\-Schnittstelle verfügbar machen müssen.  Ersetzen Sie den Code, den [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] für die `GetEnumerator`\-Methoden generiert hat, durch den folgenden Code.<br />     [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#3)]|  
  
||  
|-|  
|So fügen Sie den Code zum Implementieren von IEnumerator hinzu|  
|1.  Öffnen Sie die Datei StreamReaderEnumerator.vb.<br />2.  Geben Sie in der Zeile nach `Public Class StreamReaderEnumerator` Folgendes ein, und drücken Sie die EINGABETASTE.<br />     [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#4)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] füllt die Klasse automatisch mit den Membern auf, die für die `IEnumerator(Of String)`\-Schnittstelle erforderlich sind.<br />3.  Die Enumeratorklasse öffnet die Textdatei und führt die Datei\-E\/A aus, um die Zeilen aus der Datei zu lesen.  Fügen Sie der Klasse den folgenden Code hinzu, um einen öffentlichen Konstruktor verfügbar zu machen, der einen Dateipfad als Eingabeparameter akzeptiert, und öffnen Sie die Textdatei zum Lesen.<br />     [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#5)]<br />4.  Die `Current`\-Eigenschaften für die `IEnumerator(Of String)`\-Schnittstelle und die `IEnumerator`\-Schnittstelle geben das aktuelle Element der Textdatei als `String` zurück.  Die Implementierung der `Current`\-Eigenschaft der `IEnumerator`\-Schnittstelle kann als `Private` festgelegt werden, da Sie nur Member der `IEnumerator(Of String)`\-Schnittstelle verfügbar machen müssen.  Ersetzen Sie den Code, den [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] für die `Current`\-Eigenschaften generiert hat, durch den folgenden Code.<br />     [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#6)]<br />5.  Die `MoveNext`\-Methode der `IEnumerator`\-Schnittstelle navigiert zum nächsten Element in der Textdatei und aktualisiert den Wert, der von der `Current`\-Eigenschaft zurückgegeben wird.  Wenn keine zu lesenden Elemente mehr vorhanden sind, gibt die `MoveNext`\-Methode `False` zurück. Andernfalls gibt die `MoveNext`\-Methode `True` zurück.  Fügen Sie der `MoveNext`\-Methode folgenden Code hinzu.<br />     [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#7)]<br />6.  Die `Reset`\-Methode der `IEnumerator`\-Schnittstelle weist den Iterator an, auf den Start der Textdatei zu zeigen, und löscht den aktuellen Elementwert.  Fügen Sie der `Reset`\-Methode folgenden Code hinzu.<br />     [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#8)]<br />7.  Die `Dispose`\-Methode der `IEnumerator`\-Schnittstelle gewährleistet, dass alle nicht verwalteten Ressourcen freigegeben werden, bevor der Iterator zerstört wird.  Das vom `StreamReader`\-Objekt verwendete Dateihandle ist eine nicht verwaltete Ressource und muss geschlossen werden, bevor die Iteratorinstanz zerstört wird.  Ersetzen Sie den Code, den [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] für die `Dispose`\-Methode generiert hat, durch den folgenden Code.<br />     [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#9)]|  
  
## Verwenden des Beispieliterators  
 Sie können eine aufzählbare Klasse im Code zusammen mit Steuerstrukturen verwenden, die ein Objekt erfordern, das `IEnumerable` implementiert, z. B. eine `For Next`\-Schleife oder eine LINQ\-Abfrage.  Im folgenden Beispiel wird `StreamReaderEnumerable` in einer LINQ\-Abfrage gezeigt.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/VbVbalrIteratorWalkthrough/Module1.vb#10)]  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [For Each...Next\-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)