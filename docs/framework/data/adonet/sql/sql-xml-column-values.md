---
title: SQL-XML-Spaltenwerte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: b46c763e7cddfc7617c9a6a23428f83a54955ba0
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45516319"
---
# <a name="sql-xml-column-values"></a><span data-ttu-id="cfd2e-102">SQL-XML-Spaltenwerte</span><span class="sxs-lookup"><span data-stu-id="cfd2e-102">SQL XML Column Values</span></span>
<span data-ttu-id="cfd2e-103">SQL Server unterstützt die `xml` -Datentyp, und Entwickler können Abrufen von Resultsets, die diesen Typ mithilfe des Standardverhaltens der einschließen, die <xref:System.Data.SqlClient.SqlCommand> Klasse.</span><span class="sxs-lookup"><span data-stu-id="cfd2e-103">SQL Server supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="cfd2e-104">Eine `xml`-Spalte kann auf die gleiche Weise abgerufen werden wie jede andere Spalte auch (z. B. in einem <xref:System.Data.SqlClient.SqlDataReader>). Wenn Sie jedoch mit dem Inhalt der Spalte in Form von XML-Daten arbeiten möchten, müssen Sie einen <xref:System.Xml.XmlReader> verwenden.</span><span class="sxs-lookup"><span data-stu-id="cfd2e-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfd2e-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cfd2e-105">Example</span></span>  
 <span data-ttu-id="cfd2e-106">Die folgende Konsolenanwendung wählt zwei Zeilen mit jeweils einer `xml` Spalte aus der **Sales.Store** -Tabelle in der **AdventureWorks** -Datenbank in eine <xref:System.Data.SqlClient.SqlDataReader> Instanz.</span><span class="sxs-lookup"><span data-stu-id="cfd2e-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="cfd2e-107">Der Wert der `xml`-Spalte für jede Zeile wird mit der <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>-Methode des <xref:System.Data.SqlClient.SqlDataReader> gelesen.</span><span class="sxs-lookup"><span data-stu-id="cfd2e-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="cfd2e-108">Der Wert wird in einem <xref:System.Xml.XmlReader> gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cfd2e-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="cfd2e-109">Wenn Sie den Inhalt als <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>-Variable festlegen möchten, müssen Sie anstelle der <xref:System.Data.IDataRecord.GetValue%2A>-Methode die <xref:System.Data.SqlTypes.SqlXml>-Methode verwenden, denn <xref:System.Data.IDataRecord.GetValue%2A> gibt den Wert der `xml`-Spalte als Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="cfd2e-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfd2e-110">Die **AdventureWorks** Beispieldatenbank ist nicht standardmäßig installiert, bei der Installation von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cfd2e-110">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="cfd2e-111">Sie kann jedoch durch Ausführen des Setups von SQL Server installiert werden.</span><span class="sxs-lookup"><span data-stu-id="cfd2e-111">You can install it by running SQL Server Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cfd2e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfd2e-112">See Also</span></span>  
 <xref:System.Data.SqlTypes.SqlXml>  
 [<span data-ttu-id="cfd2e-113">XML-Daten in SQL Server</span><span class="sxs-lookup"><span data-stu-id="cfd2e-113">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 [<span data-ttu-id="cfd2e-114">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="cfd2e-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
