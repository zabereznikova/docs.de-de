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
# <a name="how-to-connect-to-a-database"></a>Gewusst wie: Verbinden mit einer Datenbank
Der <xref:System.Data.Linq.DataContext> ist die "Hauptleitung" für die Verbindung zu einer Datenbank, für das Abrufen von Objekten und für das Übergeben von Änderungen. Sie verwenden die <xref:System.Data.Linq.DataContext> wie eine ADO.net-<xref:System.Data.SqlClient.SqlConnection>. Tatsächlich wird der <xref:System.Data.Linq.DataContext> mit einer von Ihnen angegebenen Verbindung oder Verbindungszeichenfolge initialisiert. Weitere Informationen finden Sie unter [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).  
  
 Der Zweck des <xref:System.Data.Linq.DataContext> besteht in der Übersetzung Ihrer Objektanforderungen in SQL-Abfragen für die Datenbank und in der anschließenden Zusammenstellung von Objekten aus den Ergebnissen. Der <xref:System.Data.Linq.DataContext> ermöglicht die sprach integrierte Abfrage (Language-Integrated Query, LINQ), indem das gleiche Operator Muster wie die Standard Abfrage Operatoren wie `Where` und `Select`implementiert wird.  
  
> [!IMPORTANT]
> Der Erhalt einer sicheren Verbindung ist von grundlegender Bedeutung. Weitere Informationen finden Sie unter [Security in LINQ to SQL](security-in-linq-to-sql.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der <xref:System.Data.Linq.DataContext> zum Herstellen einer Verbindung zur Beispieldatenbank Nordwind und zum Abrufen von Zeilen mit Kunden aus London verwendet.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 Jede Datenbanktabelle wird als `Table`-Auflistung dargestellt, die über die <xref:System.Data.Linq.DataContext.GetTable%2A>-Methode zur Verfügung steht. Zur Identifikation wird hierbei die Entitätsklasse verwendet.  
  
## <a name="example"></a>Beispiel  
 Die bewährte Methode besteht in der Deklaration eines starken <xref:System.Data.Linq.DataContext> anstelle der grundlegenden <xref:System.Data.Linq.DataContext>-Klasse und der <xref:System.Data.Linq.DataContext.GetTable%2A>-Methode. Ein starker <xref:System.Data.Linq.DataContext> deklariert alle `Table`-Auflistungen wie im folgenden Beispiel als Kontextmember.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 Sie können dann die Abfrage von Kunden aus London wie folgt einfacher ausdrücken:  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- [Kommunizieren mit der Datenbank](communicating-with-the-database.md)
