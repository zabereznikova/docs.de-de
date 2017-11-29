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
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="427c0-102">Gewusst wie: Freigeben einer Systemressource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="427c0-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="427c0-103">Sie können eine `Using` Block, um sicherzustellen, dass das System eine Ressource freigibt, wenn der Code den Block verlässt.</span><span class="sxs-lookup"><span data-stu-id="427c0-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="427c0-104">Dies ist hilfreich, wenn Sie eine Systemressource, die eine große Menge an Arbeitsspeicher beansprucht oder andere Komponenten auch verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="427c0-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="427c0-105">Um eine Verbindung mit Datenbank freigeben, wenn der Code beendet wurde</span><span class="sxs-lookup"><span data-stu-id="427c0-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1.  <span data-ttu-id="427c0-106">Stellen Sie sicher, dass Sie die entsprechende [Imports-Anweisung (.NET Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) für eine Verbindung mit der Datenbank am Anfang der Quelldatei (in diesem Fall <xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="427c0-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2.  <span data-ttu-id="427c0-107">Erstellen einer `Using` -block mit der `Using` und `End Using` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="427c0-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="427c0-108">Platzieren Sie den Code, der Verbindung mit der Datenbank behandelt, innerhalb des Blocks.</span><span class="sxs-lookup"><span data-stu-id="427c0-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3.  <span data-ttu-id="427c0-109">Deklarieren Sie die Verbindung, und erstellen Sie eine Instanz als Teil der `Using` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="427c0-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="427c0-110">Das System, verwirft der Ressource unabhängig davon, wie Sie den Block, einschließlich der Groß-/Kleinschreibung eine nicht behandelte Ausnahme beenden.</span><span class="sxs-lookup"><span data-stu-id="427c0-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="427c0-111">Beachten Sie, die Sie nicht zugreifen können `sqc` von außerhalb der `Using` blockiert werden, da der Gültigkeitsbereich auf den Block beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="427c0-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="427c0-112">Sie können auf die gleiche Weise auf eine Systemressource, z. B. ein Dateihandle oder einen COM-Wrapper verwenden.</span><span class="sxs-lookup"><span data-stu-id="427c0-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="427c0-113">Sie verwenden eine `Using` blockieren, wenn Sie möchten sicherstellen, dass die Ressource für andere Komponenten lassen, nachdem Sie geschlossen haben die `Using` Block.</span><span class="sxs-lookup"><span data-stu-id="427c0-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="427c0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="427c0-114">See Also</span></span>  
 <xref:System.Data.SqlClient.SqlConnection>  
 [<span data-ttu-id="427c0-115">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="427c0-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="427c0-116">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="427c0-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="427c0-117">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="427c0-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="427c0-118">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="427c0-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="427c0-119">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="427c0-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="427c0-120">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="427c0-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
