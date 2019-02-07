---
title: 'Vorgehensweise: Ausführen einer polymorphen Abfrage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 01619e556750a93910afefed4b5647818f6a9d92
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826238"
---
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="1d714-102">Vorgehensweise: Ausführen einer polymorphen Abfrage</span><span class="sxs-lookup"><span data-stu-id="1d714-102">How to: Execute a Polymorphic Query</span></span>
<span data-ttu-id="1d714-103">In diesem Thema wird gezeigt, wie eine polymorphe [!INCLUDE[esql](../../../../../includes/esql-md.md)] Abfragen mit der [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) Operator.</span><span class="sxs-lookup"><span data-stu-id="1d714-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="1d714-104">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="1d714-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="1d714-105">Hinzufügen der [Modell "School"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) zu Ihrem Projekt und konfigurieren Sie das Projekt zur Verwendung von Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="1d714-105">Add the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="1d714-106">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="1d714-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="1d714-107">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="1d714-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="1d714-108">Ändern Sie das konzeptionelle Modell, um eine Tabelle-pro-Hierarchie-Vererbung verfügen, indem Sie die Schritte in [Exemplarische Vorgehensweise: Zuordnen von Vererbung - ' Tabelle pro Hierarchie](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="1d714-108">Modify the conceptual model to have a table-per-hierrachy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d714-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d714-109">Example</span></span>  
 <span data-ttu-id="1d714-110">Im folgenden Beispiel wird ein OFTYPE-Operator verwendet, um eine Auflistung der `OnsiteCourses` aus einer Auflistung von `Courses` abzurufen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1d714-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## <a name="see-also"></a><span data-ttu-id="1d714-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d714-111">See also</span></span>
- [<span data-ttu-id="1d714-112">EntityClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="1d714-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="1d714-113">Entity SQL Language (Entity SQL-Sprache)</span><span class="sxs-lookup"><span data-stu-id="1d714-113">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
