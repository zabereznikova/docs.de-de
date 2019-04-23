---
title: Initialisierungsausdrücke
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98daef1f-15d4-483e-985c-d78ea3abe8c8
ms.openlocfilehash: 6f6f27eaecd760e565eeb98a286252981d6df0bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129141"
---
# <a name="initialization-expressions"></a><span data-ttu-id="6c0dd-102">Initialisierungsausdrücke</span><span class="sxs-lookup"><span data-stu-id="6c0dd-102">Initialization Expressions</span></span>
<span data-ttu-id="6c0dd-103">Ein Initialisierungsausdruck initialisiert ein neues Objekt.</span><span class="sxs-lookup"><span data-stu-id="6c0dd-103">An initialization expression initializes a new object.</span></span> <span data-ttu-id="6c0dd-104">Die meisten Initialisierungsausdrücke werden unterstützt, einschließlich der meisten neuen C# 3.0- und Visual Basic 9.0-Initialisierungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="6c0dd-104">Most initialization expressions are supported, including most new C# 3.0 and Visual Basic 9.0 initialization expressions.</span></span> <span data-ttu-id="6c0dd-105">Die folgenden Typen können von einer LINQ to Entities-Abfrage initialisiert und zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="6c0dd-105">The following types can be initialized and returned by a LINQ to Entities query:</span></span>  
  
-   <span data-ttu-id="6c0dd-106">Eine Auflistung von 0 (null) oder mehreren typisierten Entitätsobjekten oder einer Projektion komplexer Typen, die im konzeptionellen Modell definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6c0dd-106">A collection of zero or more typed entity objects or a projection of complex types that are defined in the conceptual model.</span></span>  
  
-   <span data-ttu-id="6c0dd-107">Von [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] unterstütze CLR-Typen.</span><span class="sxs-lookup"><span data-stu-id="6c0dd-107">CLR types supported by the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="6c0dd-108">Inlineauflistungen</span><span class="sxs-lookup"><span data-stu-id="6c0dd-108">Inline collections.</span></span>  
  
-   <span data-ttu-id="6c0dd-109">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="6c0dd-109">Anonymous types.</span></span>  
  
 <span data-ttu-id="6c0dd-110">Im folgenden Beispiel wird die anonyme Typinitialisierung in der Abfrageausdruckssyntax dargestellt:</span><span class="sxs-lookup"><span data-stu-id="6c0dd-110">Anonymous type initialization is shown in the following example in query expression syntax:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization)]  
  
 <span data-ttu-id="6c0dd-111">Im folgenden Beispiel methodenbasierter Abfragesyntax wird die anonyme Typinitialisierung veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6c0dd-111">The following example in method-based query syntax shows anonymous type initialization:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization_mq)]  
  
 <span data-ttu-id="6c0dd-112">Die benutzerdefinierte Klasseninitialisierung wird ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6c0dd-112">User-defined class initialization is also supported.</span></span> <span data-ttu-id="6c0dd-113">Die Initialisierungsmuster von C# 3.0 und Visual Basic 9.0 werden unterstützt. Dabei wird angenommen, dass die Getter und Setter für die Eigenschaften symmetrisch sind.</span><span class="sxs-lookup"><span data-stu-id="6c0dd-113">The C# 3.0 and Visual Basic 9.0 initialization pattern is supported and assumes that the property getter and setter are symmetric.</span></span> <span data-ttu-id="6c0dd-114">Das folgende Beispiel von Abfrageausdruckssyntax zeigt die Initialisierung einer benutzerdefinierten Klasse in einer Abfrage:</span><span class="sxs-lookup"><span data-stu-id="6c0dd-114">The following example in query expression syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myorder)]
 [!code-vb[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myorder)]  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization)]  
  
 <span data-ttu-id="6c0dd-115">Das folgende Beispiel methodenbasierter Abfragesyntax zeigt die Initialisierung einer benutzerdefinierten Klasse in einer Abfrage:</span><span class="sxs-lookup"><span data-stu-id="6c0dd-115">The following example in method-based query syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="6c0dd-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c0dd-116">See also</span></span>

- [<span data-ttu-id="6c0dd-117">Ausdrücke in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="6c0dd-117">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
