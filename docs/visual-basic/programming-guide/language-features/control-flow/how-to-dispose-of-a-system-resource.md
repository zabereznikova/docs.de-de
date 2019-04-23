---
title: 'Vorgehensweise: Freigeben einer Systemressource (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: e3594db036edc3a6288b0373737c1ee26a691a57
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59341906"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Vorgehensweise: Freigeben einer Systemressource (Visual Basic)
Sie können eine `Using` Block, um sicherzustellen, dass das System eine Ressource freigibt, wenn der Code den Block beendet. Dies ist hilfreich, wenn Sie eine Systemressource, die eine große Menge an Arbeitsspeicher beansprucht oder andere Komponenten auch verwenden möchten.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>Um eine Verbindung mit Datenbank freigeben, wenn Ihr Code beendet wurde  
  
1. Stellen Sie sicher, Sie fügen Sie die entsprechenden [Imports-Anweisung (.NET-Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) für eine Verbindung mit der Datenbank am Anfang der Quelldatei (in diesem Fall <xref:System.Data.SqlClient>).  
  
2. Erstellen Sie eine `Using` -block mit der `Using` und `End Using` Anweisungen. Platzieren Sie den Code, der mit der datenbankverbindung behandelt, innerhalb des Blocks.  
  
3. Deklarieren Sie die Verbindung, und erstellen Sie eine Instanz davon als Teil der `Using` Anweisung.  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     Das System löscht der Ressource unabhängig davon, wie Sie den Block, einschließlich den Fall einer nicht behandelten Ausnahme beenden.  
  
     Beachten Sie, die Sie nicht zugreifen können `sqc` von außerhalb der `Using` blockieren, da der Gültigkeitsbereich auf den Block beschränkt ist.  
  
     Sie können auf die gleiche Weise auf eine Systemressource, z. B. ein Dateihandle oder einen COM-Wrapper verwenden. Sie verwenden eine `Using` blockieren, wenn Sie sicher sein wollen, dass die Ressource, die für andere Komponenten verfügbar, nachdem Sie beendet haben die `Using` Block.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.SqlClient.SqlConnection>
- [Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Entscheidungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Weitere Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Geschachtelte Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md)
