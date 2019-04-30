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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906736"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="d143f-102">Vorgehensweise: Freigeben einer Systemressource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d143f-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="d143f-103">Sie können eine `Using` Block, um sicherzustellen, dass das System eine Ressource freigibt, wenn der Code den Block beendet.</span><span class="sxs-lookup"><span data-stu-id="d143f-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="d143f-104">Dies ist hilfreich, wenn Sie eine Systemressource, die eine große Menge an Arbeitsspeicher beansprucht oder andere Komponenten auch verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d143f-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="d143f-105">Um eine Verbindung mit Datenbank freigeben, wenn Ihr Code beendet wurde</span><span class="sxs-lookup"><span data-stu-id="d143f-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1. <span data-ttu-id="d143f-106">Stellen Sie sicher, Sie fügen Sie die entsprechenden [Imports-Anweisung (.NET-Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) für eine Verbindung mit der Datenbank am Anfang der Quelldatei (in diesem Fall <xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="d143f-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2. <span data-ttu-id="d143f-107">Erstellen Sie eine `Using` -block mit der `Using` und `End Using` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="d143f-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="d143f-108">Platzieren Sie den Code, der mit der datenbankverbindung behandelt, innerhalb des Blocks.</span><span class="sxs-lookup"><span data-stu-id="d143f-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3. <span data-ttu-id="d143f-109">Deklarieren Sie die Verbindung, und erstellen Sie eine Instanz davon als Teil der `Using` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d143f-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="d143f-110">Das System löscht der Ressource unabhängig davon, wie Sie den Block, einschließlich den Fall einer nicht behandelten Ausnahme beenden.</span><span class="sxs-lookup"><span data-stu-id="d143f-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="d143f-111">Beachten Sie, die Sie nicht zugreifen können `sqc` von außerhalb der `Using` blockieren, da der Gültigkeitsbereich auf den Block beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="d143f-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="d143f-112">Sie können auf die gleiche Weise auf eine Systemressource, z. B. ein Dateihandle oder einen COM-Wrapper verwenden.</span><span class="sxs-lookup"><span data-stu-id="d143f-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="d143f-113">Sie verwenden eine `Using` blockieren, wenn Sie sicher sein wollen, dass die Ressource, die für andere Komponenten verfügbar, nachdem Sie beendet haben die `Using` Block.</span><span class="sxs-lookup"><span data-stu-id="d143f-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d143f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d143f-114">See also</span></span>

- <xref:System.Data.SqlClient.SqlConnection>
- [<span data-ttu-id="d143f-115">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="d143f-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="d143f-116">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="d143f-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="d143f-117">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="d143f-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="d143f-118">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="d143f-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="d143f-119">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="d143f-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="d143f-120">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d143f-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
