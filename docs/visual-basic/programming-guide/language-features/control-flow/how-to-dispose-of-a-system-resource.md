---
title: 'Gewusst wie: Freigeben einer Systemressource'
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
ms.openlocfilehash: c493051050442597196ba484fb9ce8e99249dbb7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353941"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="18d8c-102">Gewusst wie: Freigeben einer Systemressource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18d8c-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="18d8c-103">Sie können einen `Using`-Block verwenden, um sicherzustellen, dass das System eine Ressource freigibt, wenn der Code den Block verlässt.</span><span class="sxs-lookup"><span data-stu-id="18d8c-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="18d8c-104">Dies ist nützlich, wenn Sie eine System Ressource verwenden, die eine große Menge an Arbeitsspeicher beansprucht oder die andere Komponenten verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="18d8c-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="18d8c-105">So löschen Sie eine Datenbankverbindung, wenn Ihr Code abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="18d8c-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1. <span data-ttu-id="18d8c-106">Stellen Sie sicher, dass Sie die entsprechende [Imports-Anweisung (.NET-Namespace und-Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) für die Datenbankverbindung am Anfang der Quelldatei (in diesem Fall <xref:System.Data.SqlClient>) einschließen.</span><span class="sxs-lookup"><span data-stu-id="18d8c-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2. <span data-ttu-id="18d8c-107">Erstellen Sie einen `Using`-Block mit den Anweisungen `Using` und `End Using`.</span><span class="sxs-lookup"><span data-stu-id="18d8c-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="18d8c-108">Fügen Sie innerhalb des-Blocks den Code ein, der die Datenbankverbindung behandelt.</span><span class="sxs-lookup"><span data-stu-id="18d8c-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3. <span data-ttu-id="18d8c-109">Deklarieren Sie die Verbindung, und erstellen Sie eine Instanz davon als Teil der `Using`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="18d8c-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="18d8c-110">Das System löscht die Ressource unabhängig davon, wie Sie den Block beenden, einschließlich der Groß-/Kleinschreibung einer nicht behandelten Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="18d8c-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="18d8c-111">Beachten Sie, dass Sie nicht von außerhalb des `Using` Blocks auf `sqc` zugreifen können, da der zugehörige Bereich auf den Block beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="18d8c-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="18d8c-112">Sie können dieselbe Technik für eine System Ressource wie ein Datei Handle oder einen COM-Wrapper verwenden.</span><span class="sxs-lookup"><span data-stu-id="18d8c-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="18d8c-113">Sie verwenden einen `Using` Block, wenn Sie sicher gehen möchten, dass die Ressource für andere Komponenten verfügbar ist, nachdem Sie den `Using`-Block verlassen haben.</span><span class="sxs-lookup"><span data-stu-id="18d8c-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18d8c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18d8c-114">See also</span></span>

- <xref:System.Data.SqlClient.SqlConnection>
- [<span data-ttu-id="18d8c-115">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="18d8c-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="18d8c-116">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="18d8c-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="18d8c-117">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="18d8c-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="18d8c-118">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="18d8c-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="18d8c-119">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="18d8c-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="18d8c-120">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="18d8c-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
