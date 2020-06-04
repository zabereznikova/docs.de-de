---
title: 'Vorgehensweise: Freigeben einer Systemressource'
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
ms.openlocfilehash: dd15c6746628f45b072d46eea40051ed9afb7921
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403497"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Gewusst wie: Freigeben einer Systemressource (Visual Basic)
Sie können einen- `Using` Block verwenden, um sicherzustellen, dass das System eine Ressource freigibt, wenn der Code den Block verlässt. Dies ist nützlich, wenn Sie eine System Ressource verwenden, die eine große Menge an Arbeitsspeicher beansprucht oder die andere Komponenten verwenden möchten.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>So löschen Sie eine Datenbankverbindung, wenn Ihr Code abgeschlossen ist  
  
1. Stellen Sie sicher, dass Sie die entsprechende [Imports-Anweisung (.NET-Namespace und-Typ)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) für die Datenbankverbindung am Anfang der Quelldatei (in diesem Fall <xref:System.Data.SqlClient> ) einschließen.  
  
2. Erstellen Sie einen `Using` -Block mit den `Using` `End Using` Anweisungen und. Fügen Sie innerhalb des-Blocks den Code ein, der die Datenbankverbindung behandelt.  
  
3. Deklarieren Sie die Verbindung, und erstellen Sie eine Instanz davon als Teil der- `Using` Anweisung.  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     Das System löscht die Ressource unabhängig davon, wie Sie den Block beenden, einschließlich der Groß-/Kleinschreibung einer nicht behandelten Ausnahme.  
  
     Beachten Sie, dass Sie nicht `sqc` von außerhalb des-Blocks auf zugreifen können, da der zugehörige `Using` Bereich auf den-Block beschränkt ist.  
  
     Sie können dieselbe Technik für eine System Ressource wie ein Datei Handle oder einen COM-Wrapper verwenden. Sie verwenden einen- `Using` Block, wenn Sie sicher sein möchten, dass die Ressource für andere Komponenten verfügbar ist, nachdem Sie den-Block verlassen haben `Using` .  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.SqlClient.SqlConnection>
- [Ablauf Steuerung](index.md)
- [Entscheidungsstrukturen](decision-structures.md)
- [Schleifenstrukturen](loop-structures.md)
- [Weitere Steuerungsstrukturen](other-control-structures.md)
- [Geschachtelte Steuerungsstrukturen](nested-control-structures.md)
- [Using-Anweisung](../../../language-reference/statements/using-statement.md)
