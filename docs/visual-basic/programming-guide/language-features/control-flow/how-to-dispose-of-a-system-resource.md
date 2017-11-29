---
title: 'Gewusst wie: Freigeben einer Systemressource (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5b5c65c9d123c6f481852eb249cb4d479a180c5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Gewusst wie: Freigeben einer Systemressource (Visual Basic)
Sie können eine `Using` Block, um sicherzustellen, dass das System eine Ressource freigibt, wenn der Code den Block verlässt. Dies ist hilfreich, wenn Sie eine Systemressource, die eine große Menge an Arbeitsspeicher beansprucht oder andere Komponenten auch verwenden möchten.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>Um eine Verbindung mit Datenbank freigeben, wenn der Code beendet wurde  
  
1.  Stellen Sie sicher, dass Sie die entsprechende [Imports-Anweisung (.NET Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) für eine Verbindung mit der Datenbank am Anfang der Quelldatei (in diesem Fall <xref:System.Data.SqlClient>).  
  
2.  Erstellen einer `Using` -block mit der `Using` und `End Using` Anweisungen. Platzieren Sie den Code, der Verbindung mit der Datenbank behandelt, innerhalb des Blocks.  
  
3.  Deklarieren Sie die Verbindung, und erstellen Sie eine Instanz als Teil der `Using` Anweisung.  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     Das System, verwirft der Ressource unabhängig davon, wie Sie den Block, einschließlich der Groß-/Kleinschreibung eine nicht behandelte Ausnahme beenden.  
  
     Beachten Sie, die Sie nicht zugreifen können `sqc` von außerhalb der `Using` blockiert werden, da der Gültigkeitsbereich auf den Block beschränkt ist.  
  
     Sie können auf die gleiche Weise auf eine Systemressource, z. B. ein Dateihandle oder einen COM-Wrapper verwenden. Sie verwenden eine `Using` blockieren, wenn Sie möchten sicherstellen, dass die Ressource für andere Komponenten lassen, nachdem Sie geschlossen haben die `Using` Block.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.SqlClient.SqlConnection>  
 [Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Entscheidungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Weitere Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [Geschachtelte Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md)
