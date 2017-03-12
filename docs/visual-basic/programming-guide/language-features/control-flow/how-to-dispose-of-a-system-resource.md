---
title: "How to: Dispose of a System Resource (Visual Basic) | Microsoft Docs"
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
  - "Using statement, disposing of system resources"
  - "Visual Basic code, control flow"
  - "system resources, disposing of"
  - "resources [Visual Basic], disposing of system"
  - "system resources"
  - "Using statement, Using...End Using"
  - "Using block"
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Dispose of a System Resource (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Mit einem `Using`\-Block können Sie sicherstellen, dass das System eine Ressource freigibt, wenn der Code den Block beendet.  Dies ist hilfreich, wenn Sie eine Systemressource verwenden, die sehr viel Speicher beansprucht oder auf die auch andere Komponenten zugreifen.  
  
### So geben Sie eine Datenbankverbindung frei, wenn sie vom Code nicht mehr benötigt wird  
  
1.  Fügen Sie am Anfang der Quelldatei die entsprechende [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) für die Datenbankverbindung ein \(in diesem Fall <xref:System.Data.SqlClient>\).  
  
2.  Erstellen Sie einen `Using`\-Block mit der `Using`\-Anweisung und der `End Using`\-Anweisung.  Fügen Sie in den Block den Code ein, der die Datenbankverbindung definiert.  
  
3.  Deklarieren Sie die Verbindung, und erstellen Sie eine Instanz davon als Teil der `Using`\-Anweisung.  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     Das System gibt die Ressource frei. Dies gilt unabhängig davon, wie der Block beendet wird, beispielsweise auch bei Auftreten einer nicht behandelten Ausnahme.  
  
     Sie können nur innerhalb des `Using`\-Blocks auf `sqc` zugreifen, da der Gültigkeitsbereich auf den Block beschränkt ist.  
  
     Das gleiche Verfahren kann auch auf andere Systemressourcen wie ein Dateihandle oder einen COM\-Wrapper angewendet werden.  Sie verwenden einen `Using`\-Block, wenn Sie sicher sein möchten, dass die Ressource auch anderen Komponenten zur Verfügung steht, nachdem Sie den `Using`\-Block beendet haben.  
  
## Siehe auch  
 <xref:System.Data.SqlClient.SqlConnection>   
 [Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md)