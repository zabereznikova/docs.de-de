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
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="351da-102">Gewusst wie: Freigeben einer Systemressource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="351da-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="351da-103">Sie können einen- `Using` Block verwenden, um sicherzustellen, dass das System eine Ressource freigibt, wenn der Code den Block verlässt.</span><span class="sxs-lookup"><span data-stu-id="351da-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="351da-104">Dies ist nützlich, wenn Sie eine System Ressource verwenden, die eine große Menge an Arbeitsspeicher beansprucht oder die andere Komponenten verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="351da-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="351da-105">So löschen Sie eine Datenbankverbindung, wenn Ihr Code abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="351da-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1. <span data-ttu-id="351da-106">Stellen Sie sicher, dass Sie die entsprechende [Imports-Anweisung (.NET-Namespace und-Typ)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) für die Datenbankverbindung am Anfang der Quelldatei (in diesem Fall <xref:System.Data.SqlClient> ) einschließen.</span><span class="sxs-lookup"><span data-stu-id="351da-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2. <span data-ttu-id="351da-107">Erstellen Sie einen `Using` -Block mit den `Using` `End Using` Anweisungen und.</span><span class="sxs-lookup"><span data-stu-id="351da-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="351da-108">Fügen Sie innerhalb des-Blocks den Code ein, der die Datenbankverbindung behandelt.</span><span class="sxs-lookup"><span data-stu-id="351da-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3. <span data-ttu-id="351da-109">Deklarieren Sie die Verbindung, und erstellen Sie eine Instanz davon als Teil der- `Using` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="351da-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="351da-110">Das System löscht die Ressource unabhängig davon, wie Sie den Block beenden, einschließlich der Groß-/Kleinschreibung einer nicht behandelten Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="351da-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="351da-111">Beachten Sie, dass Sie nicht `sqc` von außerhalb des-Blocks auf zugreifen können, da der zugehörige `Using` Bereich auf den-Block beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="351da-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="351da-112">Sie können dieselbe Technik für eine System Ressource wie ein Datei Handle oder einen COM-Wrapper verwenden.</span><span class="sxs-lookup"><span data-stu-id="351da-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="351da-113">Sie verwenden einen- `Using` Block, wenn Sie sicher sein möchten, dass die Ressource für andere Komponenten verfügbar ist, nachdem Sie den-Block verlassen haben `Using` .</span><span class="sxs-lookup"><span data-stu-id="351da-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="351da-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="351da-114">See also</span></span>

- <xref:System.Data.SqlClient.SqlConnection>
- [<span data-ttu-id="351da-115">Ablauf Steuerung</span><span class="sxs-lookup"><span data-stu-id="351da-115">Control Flow</span></span>](index.md)
- [<span data-ttu-id="351da-116">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="351da-116">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="351da-117">Schleifenstrukturen</span><span class="sxs-lookup"><span data-stu-id="351da-117">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="351da-118">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="351da-118">Other Control Structures</span></span>](other-control-structures.md)
- [<span data-ttu-id="351da-119">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="351da-119">Nested Control Structures</span></span>](nested-control-structures.md)
- [<span data-ttu-id="351da-120">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="351da-120">Using Statement</span></span>](../../../language-reference/statements/using-statement.md)
