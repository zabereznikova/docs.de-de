---
title: "End Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.End"
  - "End"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "execution, ending"
  - "files, closing"
  - "End keyword, End statements"
  - "programs, quitting"
  - "code, exiting"
  - "program termination"
  - "End statement"
  - "execution, stopping"
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# End Statement
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Beendet die Ausführung mit sofortiger Wirkung.  
  
## Syntax  
  
```  
End  
```  
  
## Hinweise  
 Sie können die `End`\-Anweisung irgendwo in einer Prozedur einfügen, um die Ausführung der ganzen Anwendung zum Beenden zu zwingen.  `End` schließt alle mit einer `Open`\-Anweisung geöffnete Dateien und löscht alle Variablen der Anwendung.  Die Anwendung wird geschlossen, sobald keine anderen Programme mehr auf ihre Objekte verweisen und kein Code der Anwendung mehr ausgeführt wird.  
  
> [!NOTE]
>  Die `End`\-Anweisung beendet die Ausführung von Code mit sofortiger Wirkung, ohne die `Dispose`\-Methode, die `Finalize`\-Methode oder anderen Visual Basic\-Code aufzurufen.  Objektverweise, die von anderen Programmen verwendet werden, werden ungültig.  Wenn sich eine `End`\-Anweisung in einem `Try`\-Block oder einem `Catch`\-Block befindet, wird die Steuerung nicht an den entsprechenden `Finally`\-Block übergeben.  
  
 Die `Stop`\-Anweisung unterbricht die Ausführung, schließt aber im Gegensatz zu `End` keine Dateien und setzt auch keine Variablen zurück, es sei denn, die Anweisung befindet sich in einer kompilierten ausführbaren Datei \(EXE\-Datei\).  
  
 Da `End` die Anwendung beendet, ohne möglicherweise geöffnete Ressourcen zu berücksichtigen, sollten Sie versuchen, die Anwendung ordnungsgemäß zu beenden, bevor Sie diese Anweisung verwenden.  Wenn beispielsweise Formulare für die Anwendung geöffnet sind, schließen Sie die Formulare, bevor die Steuerung an die `End`\-Anweisung übergeben wird.  
  
 Verwenden Sie `End` sparsam und nur, wenn Sie die Anwendung sofort beenden müssen.  Mit den normalen Verfahren zum Beenden einer Prozedur \([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) und [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)\) wird nicht nur die Prozedur ordnungsgemäß beendet, sondern auch das ordnungsgemäße Beenden des aufrufenden Codes ermöglicht.  Beispielsweise kann für eine Konsolenwendung einfach `Return` aus der `Main`\-Prozedur ausgeführt werden.  
  
> [!IMPORTANT]
>  Die `End`\-Anweisung ruft die <xref:System.Environment.Exit%2A> \-Methode der <xref:System.Environment>\-Klasse im <xref:System>\-Namespace auf.  <xref:System.Environment.Exit%2A> erfordert, dass Sie über die `UnmanagedCode`\-Berechtigung verfügen.  Wenn Sie diese Berechtigung nicht besitzen, tritt ein <xref:System.Security.SecurityException>\-Fehler auf.  
  
 Wenn auf [End \<keyword\> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) ein zusätzliches Schlüsselwort folgt, wird mit der Anweisung die Definition der entsprechenden Prozedur oder des entsprechenden Blocks beendet.  Beispielsweise beendet `End Function` die Definition einer `Function`\-Prozedur.  
  
## Beispiel  
 Im folgenden Beispiel wird mit der `End`\-Anweisung die Codeausführung beendet, wenn der Benutzer dies anfordert.  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVersHelp60Controls/Form1.vb#64)]  
  
## Hinweise für Entwickler intelligenter Geräte  
 Diese Anweisung wird nicht unterstützt.  
  
## Siehe auch  
 <xref:System.Security.Permissions.SecurityPermissionFlag>   
 [Stop Statement](../../../visual-basic/language-reference/statements/stop-statement.md)   
 [End \<keyword\> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md)