---
title: 'Gewusst wie: Verbinden mit einer Datenbank'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
ms.openlocfilehash: 837919b1cfcdf46026ccfb37cbbec951c0ae41b8
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634676"
---
# <a name="how-to-connect-to-a-database"></a><span data-ttu-id="00c88-102">Gewusst wie: Verbinden mit einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="00c88-102">How to: Connect to a Database</span></span>
<span data-ttu-id="00c88-103">Der <xref:System.Data.Linq.DataContext> ist die "Hauptleitung" für die Verbindung zu einer Datenbank, für das Abrufen von Objekten und für das Übergeben von Änderungen.</span><span class="sxs-lookup"><span data-stu-id="00c88-103">The <xref:System.Data.Linq.DataContext> is the main conduit by which you connect to a database, retrieve objects from it, and submit changes back to it.</span></span> <span data-ttu-id="00c88-104">Sie verwenden die <xref:System.Data.Linq.DataContext> wie eine ADO.net-<xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="00c88-104">You use the <xref:System.Data.Linq.DataContext> just as you would use an ADO.NET <xref:System.Data.SqlClient.SqlConnection>.</span></span> <span data-ttu-id="00c88-105">Tatsächlich wird der <xref:System.Data.Linq.DataContext> mit einer von Ihnen angegebenen Verbindung oder Verbindungszeichenfolge initialisiert.</span><span class="sxs-lookup"><span data-stu-id="00c88-105">In fact, the <xref:System.Data.Linq.DataContext> is initialized with a connection or connection string that you supply.</span></span> <span data-ttu-id="00c88-106">Weitere Informationen finden Sie unter [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span><span class="sxs-lookup"><span data-stu-id="00c88-106">For more information, see [DataContext Methods (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span></span>  
  
 <span data-ttu-id="00c88-107">Der Zweck des <xref:System.Data.Linq.DataContext> besteht in der Übersetzung Ihrer Objektanforderungen in SQL-Abfragen für die Datenbank und in der anschließenden Zusammenstellung von Objekten aus den Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="00c88-107">The purpose of the <xref:System.Data.Linq.DataContext> is to translate your requests for objects into SQL queries to be made against the database, and then to assemble objects out of the results.</span></span> <span data-ttu-id="00c88-108">Der <xref:System.Data.Linq.DataContext> ermöglicht die sprach integrierte Abfrage (Language-Integrated Query, LINQ), indem das gleiche Operator Muster wie die Standard Abfrage Operatoren wie `Where` und `Select`implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="00c88-108">The <xref:System.Data.Linq.DataContext> enables Language-Integrated Query (LINQ) by implementing the same operator pattern as the Standard Query Operators, such as `Where` and `Select`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="00c88-109">Der Erhalt einer sicheren Verbindung ist von grundlegender Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="00c88-109">Maintaining a secure connection is of the highest importance.</span></span> <span data-ttu-id="00c88-110">Weitere Informationen finden Sie unter [Security in LINQ to SQL](security-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="00c88-110">For more information, see [Security in LINQ to SQL](security-in-linq-to-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00c88-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00c88-111">Example</span></span>  
 <span data-ttu-id="00c88-112">Im folgenden Beispiel wird der <xref:System.Data.Linq.DataContext> zum Herstellen einer Verbindung zur Beispieldatenbank Nordwind und zum Abrufen von Zeilen mit Kunden aus London verwendet.</span><span class="sxs-lookup"><span data-stu-id="00c88-112">In the following example, the <xref:System.Data.Linq.DataContext> is used to connect to the Northwind sample database and to retrieve rows of customers whose city is London.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 <span data-ttu-id="00c88-113">Jede Datenbanktabelle wird als `Table`-Auflistung dargestellt, die über die <xref:System.Data.Linq.DataContext.GetTable%2A>-Methode zur Verfügung steht. Zur Identifikation wird hierbei die Entitätsklasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="00c88-113">Each database table is represented as a `Table` collection available by way of the <xref:System.Data.Linq.DataContext.GetTable%2A> method, by using the entity class to identify it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00c88-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00c88-114">Example</span></span>  
 <span data-ttu-id="00c88-115">Die bewährte Methode besteht in der Deklaration eines starken <xref:System.Data.Linq.DataContext> anstelle der grundlegenden <xref:System.Data.Linq.DataContext>-Klasse und der <xref:System.Data.Linq.DataContext.GetTable%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="00c88-115">Best practice is to declare a strongly typed <xref:System.Data.Linq.DataContext> instead of relying on the basic <xref:System.Data.Linq.DataContext> class and the <xref:System.Data.Linq.DataContext.GetTable%2A> method.</span></span> <span data-ttu-id="00c88-116">Ein starker <xref:System.Data.Linq.DataContext> deklariert alle `Table`-Auflistungen wie im folgenden Beispiel als Kontextmember.</span><span class="sxs-lookup"><span data-stu-id="00c88-116">A strongly typed <xref:System.Data.Linq.DataContext> declares all `Table` collections as members of the context, as in the following example.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 <span data-ttu-id="00c88-117">Sie können dann die Abfrage von Kunden aus London wie folgt einfacher ausdrücken:</span><span class="sxs-lookup"><span data-stu-id="00c88-117">You can then express the query for customers from London more simply as:</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="00c88-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00c88-118">See also</span></span>

- [<span data-ttu-id="00c88-119">Kommunizieren mit der Datenbank</span><span class="sxs-lookup"><span data-stu-id="00c88-119">Communicating with the Database</span></span>](communicating-with-the-database.md)
