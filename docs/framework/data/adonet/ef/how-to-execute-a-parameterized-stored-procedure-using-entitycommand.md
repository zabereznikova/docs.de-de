---
title: 'Vorgehensweise: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von EntityCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: 11894decbb81192eb68c680149bbe9f7398f0203
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587809"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a><span data-ttu-id="d5fd3-102">Vorgehensweise: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von EntityCommand</span><span class="sxs-lookup"><span data-stu-id="d5fd3-102">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>
<span data-ttu-id="d5fd3-103">In diesem Thema wird beschrieben, wie eine parametrisierte gespeicherte Prozedur mithilfe der <xref:System.Data.EntityClient.EntityCommand>-Klasse ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d5fd3-103">This topic shows how to execute a parameterized stored procedure by using the <xref:System.Data.EntityClient.EntityCommand> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="d5fd3-104">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="d5fd3-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="d5fd3-105">Hinzufügen der [Modell "School"](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) zu Ihrem Projekt und Konfigurieren Ihres Projekts zur Verwendung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5fd3-105">Add the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="d5fd3-106">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="d5fd3-106">For more information, see [How to: Use the Entity Data Model Wizard](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="d5fd3-107">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="d5fd3-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="d5fd3-108">Importieren Sie die gespeicherte `GetStudentGrades`-Prozedur, und geben Sie `CourseGrade`-Entitäten als Rückgabetyp an.</span><span class="sxs-lookup"><span data-stu-id="d5fd3-108">Import the `GetStudentGrades` stored procedure and specify `CourseGrade` entities as a return type.</span></span> <span data-ttu-id="d5fd3-109">Informationen zum Importieren einer gespeicherten Prozedur finden Sie unter [Vorgehensweise: Importieren einer gespeicherten Prozedur](https://msdn.microsoft.com/library/24e68bf4-bd6d-428d-bc35-92d7b8e3736d).</span><span class="sxs-lookup"><span data-stu-id="d5fd3-109">For information on how to import a stored procedure, see [How to: Import a Stored Procedure](https://msdn.microsoft.com/library/24e68bf4-bd6d-428d-bc35-92d7b8e3736d).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5fd3-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d5fd3-110">Example</span></span>  
 <span data-ttu-id="d5fd3-111">Der folgenden Code führt die gespeicherte `GetStudentGrades`-Prozedur aus. Dabei ist `StudentId` ein erforderlicher Parameter.</span><span class="sxs-lookup"><span data-stu-id="d5fd3-111">The following code executes the `GetStudentGrades` stored procedure where `StudentId` is a required parameter.</span></span> <span data-ttu-id="d5fd3-112">Die Ergebnisse werden dann von einer <xref:System.Data.EntityClient.EntityDataReader> gelesen.</span><span class="sxs-lookup"><span data-stu-id="d5fd3-112">The results are then read by an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="d5fd3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5fd3-113">See also</span></span>
- [<span data-ttu-id="d5fd3-114">EntityClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="d5fd3-114">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
