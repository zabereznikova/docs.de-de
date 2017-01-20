---
title: "Calling a Property or Method Using a String Name (Visual Basic) | Microsoft Docs"
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
  - "passing operators"
  - "strings [Visual Basic], passing new operators as"
  - "objects [Visual Basic], setting properties"
  - "setting properties, object properties at run time"
  - "method calls, strings"
  - "methods [Visual Basic], calling with string names"
  - "calling methods, string names"
  - "properties [Visual Basic], setting at run time"
  - "CallByName function"
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Calling a Property or Method Using a String Name (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In den meisten Fällen können Sie die Eigenschaften und Methoden eines Objekts in der Entwurfsphase ermitteln und dafür entsprechenden Code schreiben.  In seltenen Fällen kann es jedoch vorkommen, dass Sie die Eigenschaften und Methoden eines Objekts nicht im Voraus kennen. Vielleicht möchten Sie auch Endbenutzern die Möglichkeit geben, zur Laufzeit Eigenschaften festzulegen oder Methoden auszuführen.  
  
## CallByName\-Funktion  
 Stellen Sie sich beispielsweise eine Clientanwendung vor, die von Benutzern eingegebene Ausdrücke auswertet, indem ein Operator an eine COM\-Komponente übergeben wird.  Sie fügen der Komponente ununterbrochen neue Funktionen hinzu, die neue Operatoren benötigen.  Wenn Sie die Standardmethoden für den Objektzugriff verwenden, müssen Sie die Clientanwendung neu kompilieren und verteilen, damit die neuen Operatoren verwendet werden können.  Dies können Sie vermeiden, indem Sie die neuen Operatoren mit der `CallByName`\-Funktion als Zeichenfolge übergeben, ohne die Anwendung zu ändern.  
  
 Die `CallByName`\-Funktion ermöglicht Ihnen, zur Laufzeit eine Eigenschaft oder Methode anhand einer Zeichenfolge anzugeben.  Die Signatur für die `CallByName`\-Funktion sieht wie folgt aus:  
  
 *Ergebnis* \= `CallByName`\(*Objekt*, *Prozedurname*, *Aufruftyp*, *Argumente*\(\)\)  
  
 Das erste Argument, *Objekt*, erhält den Namen des betreffenden Objekts.  Das *ProcedureName*\-Argument erhält eine Zeichenfolge mit dem Namen der aufzurufenden Methode oder Eigenschaft.  Das *CallType*\-Argument erhält eine Konstante, die den Typ der aufzurufenden Prozedur darstellt: eine Methode \(`Microsoft.VisualBasic.CallType.Method`\), eine gelesene Eigenschaft \(`Microsoft.VisualBasic.CallType.Get`\) oder eine festgelegte Eigenschaft \(`Microsoft.VisualBasic.CallType.Set`\).  Das optionale *Arguments*\-Argument enthält ein Array des `Object`\-Typs mit allen Argumenten für die Prozedur.  
  
 Sie können `CallByName` in der aktuellen Projektmappe mit Klassen verwenden. In den meisten Fällen wird die Funktion jedoch dazu verwendet, auf COM\-Objekte oder Objekte aus [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Assemblys zuzugreifen.  
  
 Angenommen, Sie fügen einen Verweis auf eine Assembly hinzu, die eine Klasse mit der Bezeichnung `MathClass` enthält, welche wiederum eine neue Funktion mit der Bezeichnung `SquareRoot` beinhaltet. Beispiel:  
  
 [!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/VbVbalrOOP/OOP.vb#53)]  
  
 Mittels Textfeld\-Steuerelementen kann festgelegt werden, welche Methode mit welchen Argumenten aufgerufen wird.  Wenn z. B. `TextBox1` den auszuwertenden Ausdruck enthält und in `TextBox2` der Funktionsname eingegeben wird, können Sie anhand des folgenden Codes die `SquareRoot`\-Funktion für den Ausdruck in `TextBox1` aufrufen:  
  
 [!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/VbVbalrOOP/OOP.vb#54)]  
  
 Wenn Sie in `TextBox1` den Wert "64", in `TextBox2` "SquareRoot" eingeben und anschließend die `CallMath`\-Prozedur aufrufen, wird die Quadratwurzel der Zahl in `TextBox1` berechnet.  Der Beispielcode ruft die `SquareRoot`\-Funktion auf \(die als erforderliches Argument eine Zeichenfolge mit dem auszuwertenden Ausdruck enthält\) und gibt in `TextBox1` den Wert "8" \(die Quadratwurzel von 64\) zurück.  Wenn die Benutzer in `TextBox2` eine ungültige Zeichenfolge eingeben, die Zeichenfolge den Namen einer Eigenschaft anstelle einer Methode enthält oder die Methode ein weiteres erforderliches Argument aufweist, tritt ein Laufzeitfehler auf.  Um diese und andere Fehler bei der Arbeit mit `CallByName` zu vermeiden, müssen Sie einen zuverlässigen Fehlerbehandlungscode einfügen.  
  
> [!NOTE]
>  Die `CallByName`\-Funktion ist zwar in manchen Fällen hilfreich, Sie sollten jedoch berücksichtigen, dass Leistungseinbußen auftreten. Das Aufrufen einer Prozedur mit der `CallByName`\-Funktion dauert etwas länger als mit einem spät gebundenen Aufruf.  Wenn Sie eine Funktion aufrufen, die immer wieder ausgeführt wird, etwa in einer Schleife, kann die `CallByName`\-Funktion die Leistung stark beeinträchtigen.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>   
 [Determining Object Type](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)