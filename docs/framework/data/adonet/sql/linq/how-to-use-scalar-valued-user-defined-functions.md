---
title: "Vorgehensweise: Verwenden von benutzerdefinierten Skalarwertfunktionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Verwenden von benutzerdefinierten Skalarwertfunktionen
Sie können eine Clientmethode für eine Klasse einer benutzerdefinierten Funktion zuweisen. Verwenden Sie hierfür das <xref:System.Data.Linq.Mapping.FunctionAttribute>\-Attribut.  Beachten Sie, dass der Hauptteil der Methode einen Ausdruck erstellt, der die Absicht des Methodenaufrufs erfasst und diesen Ausdruck zur Übersetzung und Ausführung an den <xref:System.Data.Linq.DataContext> weiterleitet.  
  
> [!NOTE]
>  Die direkte Ausführung tritt nur auf, wenn die Funktion außerhalb einer Abfrage aufgerufen wird.  Weitere Informationen finden Sie unter [Vorgehensweise: Inline\-Aufrufen von benutzerdefinierten Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md).  
  
## Beispiel  
 Der folgende SQL\-Code zeigt eine benutzerdefinierte Skalarwertfunktion: `ReverseCustName()`.  
  
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
  
## Siehe auch  
 [Benutzerdefinierte Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)