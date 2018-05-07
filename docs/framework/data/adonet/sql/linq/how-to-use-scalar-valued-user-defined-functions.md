---
title: 'Gewusst wie: Verwenden von benutzerdefinierten Skalarwertfunktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: 3748f7b865de22353c8c0a91aaf52e672455ed38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a>Gewusst wie: Verwenden von benutzerdefinierten Skalarwertfunktionen
Sie können eine Clientmethode für eine Klasse einer benutzerdefinierten Funktion zuweisen. Verwenden Sie hierfür das <xref:System.Data.Linq.Mapping.FunctionAttribute>-Attribut. Beachten Sie, dass der Hauptteil der Methode einen Ausdruck erstellt, der die Absicht des Methodenaufrufs erfasst und diesen Ausdruck zur Übersetzung und Ausführung an den <xref:System.Data.Linq.DataContext> weiterleitet.  
  
> [!NOTE]
>  Die direkte Ausführung tritt nur auf, wenn die Funktion außerhalb einer Abfrage aufgerufen wird. Weitere Informationen finden Sie unter [Vorgehensweise: Call User-Defined Functions Inline](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende SQL-Code zeigt eine benutzerdefinierte Skalarwertfunktion: `ReverseCustName()`.  
  
```  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 Sie würden beispielsweise die folgende Clientmethode für diesen Code zuordnen:  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzerdefinierte Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
