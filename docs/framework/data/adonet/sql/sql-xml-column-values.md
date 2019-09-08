---
title: SQL-XML-Spaltenwerte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: 03b09d3a53c725bb0e84ba6b5d98944267bc564c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780801"
---
# <a name="sql-xml-column-values"></a><span data-ttu-id="79e1d-102">SQL-XML-Spaltenwerte</span><span class="sxs-lookup"><span data-stu-id="79e1d-102">SQL XML Column Values</span></span>
<span data-ttu-id="79e1d-103">SQL Server unterstützt `xml` den-Datentyp, und Entwickler können Resultsets, einschließlich dieses Typs, mithilfe <xref:System.Data.SqlClient.SqlCommand> des Standard Verhaltens der-Klasse abrufen.</span><span class="sxs-lookup"><span data-stu-id="79e1d-103">SQL Server supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="79e1d-104">Eine `xml`-Spalte kann auf die gleiche Weise abgerufen werden wie jede andere Spalte auch (z. B. in einem <xref:System.Data.SqlClient.SqlDataReader>). Wenn Sie jedoch mit dem Inhalt der Spalte in Form von XML-Daten arbeiten möchten, müssen Sie einen <xref:System.Xml.XmlReader> verwenden.</span><span class="sxs-lookup"><span data-stu-id="79e1d-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79e1d-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79e1d-105">Example</span></span>  
 <span data-ttu-id="79e1d-106">Mit der folgenden Konsolenanwendung werden zwei Zeilen, von denen `xml` jede eine-Spalte enthält, aus der **Sales. Store** -Tabelle der **AdventureWorks** -Datenbank in eine <xref:System.Data.SqlClient.SqlDataReader> -Instanz ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="79e1d-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="79e1d-107">Der Wert der `xml`-Spalte für jede Zeile wird mit der <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>-Methode des <xref:System.Data.SqlClient.SqlDataReader> gelesen.</span><span class="sxs-lookup"><span data-stu-id="79e1d-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="79e1d-108">Der Wert wird in einem <xref:System.Xml.XmlReader> gespeichert.</span><span class="sxs-lookup"><span data-stu-id="79e1d-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="79e1d-109">Wenn Sie den Inhalt als <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>-Variable festlegen möchten, müssen Sie anstelle der <xref:System.Data.IDataRecord.GetValue%2A>-Methode die <xref:System.Data.SqlTypes.SqlXml>-Methode verwenden, denn <xref:System.Data.IDataRecord.GetValue%2A> gibt den Wert der `xml`-Spalte als Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="79e1d-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="79e1d-110">Die **AdventureWorks** -Beispieldatenbank wird nicht standardmäßig installiert, wenn Sie SQL Server installieren.</span><span class="sxs-lookup"><span data-stu-id="79e1d-110">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="79e1d-111">Sie kann jedoch durch Ausführen des Setups von SQL Server installiert werden.</span><span class="sxs-lookup"><span data-stu-id="79e1d-111">You can install it by running SQL Server Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="79e1d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79e1d-112">See also</span></span>

- <xref:System.Data.SqlTypes.SqlXml>
- [<span data-ttu-id="79e1d-113">XML-Daten in SQL Server</span><span class="sxs-lookup"><span data-stu-id="79e1d-113">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)
- [<span data-ttu-id="79e1d-114">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="79e1d-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
