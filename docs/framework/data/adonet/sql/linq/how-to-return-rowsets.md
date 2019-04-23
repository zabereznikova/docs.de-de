---
title: 'Vorgehensweise: Rückgabe von Rowsets'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: 599ad6f722251003ab56547ce050cbd0e8da831d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168713"
---
# <a name="how-to-return-rowsets"></a>Vorgehensweise: Rückgabe von Rowsets
In diesem Beispiel wird ein Rowset von der Datenbank zurückgegeben. Er enthält einen Eingabeparameter, um das Ergebnis zu filtern.  
  
 Wenn Sie eine gespeicherte Prozedur, die ein Rowset zurückgibt ausführen, verwenden Sie eine *Ergebnis* -Klasse, die die Rückgabe aus der gespeicherten Prozedur speichert. Weitere Informationen finden Sie unter [Analysieren von LINQ to SQL-Quellcode](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine gespeicherte Prozedur dargestellt, die Zeilen mit Kunden zurückgibt und anhand eines Eingabeparameters nur die Zeilen zurückgibt, die „London“ als Ort für den Kunden enthalten. Dieses Beispiel setzt eine zählbare `CustomersByCityResult`-Klasse voraus.  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
