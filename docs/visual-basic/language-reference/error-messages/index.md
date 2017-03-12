---
title: "Error Messages (Visual Basic) | Microsoft Docs"
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
  - "errors [Visual Basic]"
  - "error messages"
  - "trappable errors"
  - "errors [Visual Basic], trappable"
ms.assetid: f2dda05b-baef-41f5-8bb1-598bd7cf239f
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Error Messages (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Wenn Sie einer Visual Basic\-Anwendung schreiben, kompilieren oder ausführen, können die folgenden Arten von Fehlern auftreten:  
  
1.  Entwurfszeitfehler, die auftreten, wenn Sie eine Anwendung in Visual Studio schreiben.  
  
2.  Kompilierungsfehler, die auftreten, wenn Sie eine Anwendung in Visual Studio oder eine Eingabeaufforderung kompilieren.  
  
3.  Laufzeitfehler, die auftreten, wenn Sie eine Anwendung in Visual Studio oder als eigenständige ausführbare Datei ausführen.  
  
 Informationen dazu, wie Sie einen bestimmten Fehler, finden Sie unter [Additional Resources for Visual Basic Programmers](../../../visual-basic/getting-started/additional-resources.md) enthalten.  
  
## Laufzeitfehler  
 Wenn eine Visual Basic\-Anwendung versucht, eine Aktion auszuführen, die das System nicht ausgeführt werden kann, tritt ein Laufzeitfehler und [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] löst ein `Exception`\-Objekt auf.  Mithilfe der `Throw`\-Anweisung können benutzerdefinierte Fehler jeden Datentyps von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] generiert werden, darunter auch `Exception`\-Objekte.  Eine Anwendung kann den Fehler identifizieren, indem sie die Fehlernummer und \- meldung einer abgefangenen Ausnahme anzeigt.  Wenn ein Fehler nicht abgefangen wird, beendet die Anwendung.  
  
 Der Code kann Laufzeitfehler erfasst und überprüfen.  Wenn Sie den Code hinzufügen, der den Fehler in einem `Try`\-Block erzeugt, können Sie jeden ausgelösten Fehler mit einem entsprechenden `Catch`\-Block abfangen.  Informationen darüber, wie Fehler zur Laufzeit Felder und auf sie im Code, finden Sie unter [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) reagiert.  
  
## Kompilierungszeitfehler  
 Wenn der Visual Basic\-Compiler auf ein Problem im Code stößt, tritt ein Kompilierungsfehler auf.  Im Code\-Editor können Sie leichter ermitteln, welche Codezeile den Fehler verursacht hat, da eine Wellenlinie Zeile unter diese Codezeile wird angezeigt.  Die Fehlermeldung wird angezeigt, wenn Sie entweder zur wellenförmigen Unterstreichung zeigen oder **Fehlerliste** öffnen, die auch andere Meldungen angezeigt werden.  
  
 Wenn ein Bezeichner eine wellenförmige Unterstreichung hat und ein kurzer Unterstrich unter dem Zeichen ganz rechts eine angezeigt wird, können Sie einen Stub für die Klasse, den Konstruktor, die Methode, die Eigenschaft, das Feld oder die Enumeration generieren.  Weitere Informationen finden Sie unter [Generate From Usage](/visual-cpp/misc/generate-from-usage).  
  
 Indem Sie Warnungen aus dem Visual Basic\-Compiler gelöst, können Sie möglicherweise, Code zu schreiben, dem ausgeführt schneller und weniger Fehler aufweist.  Diese Warnungen bezeichnen Code, der möglicherweise Fehler verursacht, wenn die Anwendung ausgeführt wird.  Beispielsweise gibt der Compiler Sie, wenn Sie, einen Member einer nicht zugewiesenen Objektvariablen aufzurufen, einer Funktion zurückzugeben versuchen, ohne den Rückgabewert festzulegen, oder einen `Try`\-Block auszuführen, um Ausnahmen abzufangen.  Weitere Informationen zu Warnungen, enthalten, wie sie aktiviert und, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic) veranschaulicht.