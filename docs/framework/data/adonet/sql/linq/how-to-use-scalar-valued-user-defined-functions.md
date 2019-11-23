---
title: 'Gewusst wie: Verwenden von benutzerdefinierten Skalarwertfunktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: dfe82fd50eb3eedeaff9082a4288901f72197795
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003238"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a>Gewusst wie: Verwenden von benutzerdefinierten Skalarwertfunktionen
Sie können eine Clientmethode für eine Klasse einer benutzerdefinierten Funktion zuweisen. Verwenden Sie hierfür das <xref:System.Data.Linq.Mapping.FunctionAttribute>-Attribut. Beachten Sie, dass der Hauptteil der Methode einen Ausdruck erstellt, der die Absicht des Methodenaufrufs erfasst und diesen Ausdruck zur Übersetzung und Ausführung an den <xref:System.Data.Linq.DataContext> weiterleitet.  
  
> [!NOTE]
> Die direkte Ausführung tritt nur auf, wenn die Funktion außerhalb einer Abfrage aufgerufen wird. Weitere Informationen finden Sie unter Gewusst [wie: Inline-aufzurufen von benutzerdefinierten Funktionen](how-to-call-user-defined-functions-inline.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende SQL-Code zeigt eine benutzerdefinierte Skalarwertfunktion: `ReverseCustName()`.  
  
```sql  
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

- [Benutzerdefinierte Funktionen](user-defined-functions.md)
