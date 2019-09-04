---
title: 'Vorgehensweise: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von „EntityCommand“'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: a2196be1a5fb6b9c676542ab5bcc74b1824df9cc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251527"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a><span data-ttu-id="1b119-102">Vorgehensweise: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von „EntityCommand“</span><span class="sxs-lookup"><span data-stu-id="1b119-102">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>
<span data-ttu-id="1b119-103">In diesem Thema wird beschrieben, wie eine parametrisierte gespeicherte Prozedur mithilfe der <xref:System.Data.EntityClient.EntityCommand>-Klasse ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1b119-103">This topic shows how to execute a parameterized stored procedure by using the <xref:System.Data.EntityClient.EntityCommand> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="1b119-104">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="1b119-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="1b119-105">Fügen Sie dem Projekt das [Modell "School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) " hinzu, und konfigurieren Sie [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]das Projekt für die Verwendung von.</span><span class="sxs-lookup"><span data-stu-id="1b119-105">Add the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="1b119-106">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie den Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="1b119-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="1b119-107">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="1b119-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. <span data-ttu-id="1b119-108">Importieren Sie die gespeicherte `GetStudentGrades`-Prozedur, und geben Sie `CourseGrade`-Entitäten als Rückgabetyp an.</span><span class="sxs-lookup"><span data-stu-id="1b119-108">Import the `GetStudentGrades` stored procedure and specify `CourseGrade` entities as a return type.</span></span> <span data-ttu-id="1b119-109">Informationen zum Importieren einer gespeicherten Prozedur finden [Sie unter Gewusst wie: Importieren Sie eine gespeicherte](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100))Prozedur.</span><span class="sxs-lookup"><span data-stu-id="1b119-109">For information on how to import a stored procedure, see [How to: Import a Stored Procedure](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b119-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b119-110">Example</span></span>  
 <span data-ttu-id="1b119-111">Der folgenden Code führt die gespeicherte `GetStudentGrades`-Prozedur aus. Dabei ist `StudentId` ein erforderlicher Parameter.</span><span class="sxs-lookup"><span data-stu-id="1b119-111">The following code executes the `GetStudentGrades` stored procedure where `StudentId` is a required parameter.</span></span> <span data-ttu-id="1b119-112">Die Ergebnisse werden dann von einer <xref:System.Data.EntityClient.EntityDataReader> gelesen.</span><span class="sxs-lookup"><span data-stu-id="1b119-112">The results are then read by an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="1b119-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b119-113">See also</span></span>

- [<span data-ttu-id="1b119-114">EntityClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="1b119-114">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
