---
title: SQL-XML-Spaltenwerte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: cd55e2263d4b71fe62910ac918e331ebe37833eb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177279"
---
# <a name="sql-xml-column-values"></a><span data-ttu-id="e1531-102">SQL-XML-Spaltenwerte</span><span class="sxs-lookup"><span data-stu-id="e1531-102">SQL XML Column Values</span></span>

<span data-ttu-id="e1531-103">SQL Server unterstützt den `xml`-Datentyp. Daher können Entwickler Resultsets, die diesen Typ einschließen, mithilfe des Standardverhaltens der <xref:System.Data.SqlClient.SqlCommand>-Klasse abrufen.</span><span class="sxs-lookup"><span data-stu-id="e1531-103">SQL Server supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="e1531-104">Eine `xml`-Spalte kann wie jede andere Spalte abgerufen werden (beispielsweise in eine <xref:System.Data.SqlClient.SqlDataReader>-Instanz), wenn Sie den Inhalt der Spalte jedoch als XML verwenden möchten, müssen Sie <xref:System.Xml.XmlReader> verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1531-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1531-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1531-105">Example</span></span>  

 <span data-ttu-id="e1531-106">Die folgende Konsolenanwendung ruft zwei Zeilen mit jeweils einer `xml`-Spalte aus der **Sales.Store**-Tabelle in der **AdventureWorks**-Datenbank ab und übermittelt sie an eine <xref:System.Data.SqlClient.SqlDataReader>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="e1531-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="e1531-107">Für jede Zeile wird der Wert der `xml`-Spalte mithilfe der <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>-Methode von <xref:System.Data.SqlClient.SqlDataReader> gelesen.</span><span class="sxs-lookup"><span data-stu-id="e1531-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="e1531-108">Der Wert wird in einer <xref:System.Xml.XmlReader>-Instanz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e1531-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="e1531-109">Beachten Sie, dass Sie <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> anstelle der <xref:System.Data.IDataRecord.GetValue%2A>-Methode verwenden müssen, wenn Sie eine <xref:System.Data.SqlTypes.SqlXml>-Variable als Inhalt festlegen möchten. <xref:System.Data.IDataRecord.GetValue%2A> gibt den Wert der `xml`-Spalte als Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="e1531-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1531-110">Beim Installieren von SQL Server wird die Beispieldatenbank **AdventureWorks** in der Standardeinstellung nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="e1531-110">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="e1531-111">Sie kann jedoch über das SQL Server-Setup installiert werden.</span><span class="sxs-lookup"><span data-stu-id="e1531-111">You can install it by running SQL Server Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e1531-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1531-112">See also</span></span>

- <xref:System.Data.SqlTypes.SqlXml>
- [<span data-ttu-id="e1531-113">XML-Daten in SQL Server</span><span class="sxs-lookup"><span data-stu-id="e1531-113">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)
- [<span data-ttu-id="e1531-114">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e1531-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
