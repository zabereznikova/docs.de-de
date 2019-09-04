---
title: 'Vorgehensweise: Ausführen einer polymorphen Abfrage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 49e0a6b44af0729959fabf6278cc6d8ecf37a16b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251512"
---
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="a5777-102">Vorgehensweise: Ausführen einer polymorphen Abfrage</span><span class="sxs-lookup"><span data-stu-id="a5777-102">How to: Execute a Polymorphic Query</span></span>

<span data-ttu-id="a5777-103">In diesem Thema wird gezeigt, wie eine polymorphe [!INCLUDE[esql](../../../../../includes/esql-md.md)] Abfrage mithilfe des [OfType](./language-reference/oftype-entity-sql.md) -Operators ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a5777-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](./language-reference/oftype-entity-sql.md) operator.</span></span>

### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="a5777-104">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="a5777-104">To run the code in this example</span></span>

1. <span data-ttu-id="a5777-105">Fügen Sie dem Projekt das [Modell "School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) " hinzu, und konfigurieren Sie das Projekt für die Verwendung der Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="a5777-105">Add the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="a5777-106">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie den Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="a5777-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

2. <span data-ttu-id="a5777-107">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="a5777-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. <span data-ttu-id="a5777-108">Ändern Sie das konzeptionelle Modell so, dass es eine Tabelle pro Hierarchie-Vererbung durch [führt, indem Sie die Schritte in Exemplarische Vorgehensweise Zuordnung von "Vererbungs Tabelle pro hier](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100))Archie"</span><span class="sxs-lookup"><span data-stu-id="a5777-108">Modify the conceptual model to have a table-per-hierarchy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="a5777-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5777-109">Example</span></span>

<span data-ttu-id="a5777-110">Im folgenden Beispiel wird ein OFTYPE-Operator verwendet, um eine Auflistung der `OnsiteCourses` aus einer Auflistung von `Courses` abzurufen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a5777-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a><span data-ttu-id="a5777-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5777-111">See also</span></span>

- [<span data-ttu-id="a5777-112">EntityClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="a5777-112">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="a5777-113">Entity SQL Language (Entity SQL-Sprache)</span><span class="sxs-lookup"><span data-stu-id="a5777-113">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
