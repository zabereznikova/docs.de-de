---
title: "Gewusst wie: Ausführen einer polymorphen Abfrage"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4c5ee1a815ed638bc8e775abbb1c0541aa70d746
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-execute-a-polymorphic-query"></a>Gewusst wie: Ausführen einer polymorphen Abfrage
In diesem Thema wird gezeigt, wie zum Ausführen einer polymorphen [!INCLUDE[esql](../../../../../includes/esql-md.md)] Abfragen mithilfe der [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) Operator.  
  
### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus  
  
1.  Hinzufügen der [Modell ' School '](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) zu Ihrem Projekt, und konfigurieren Sie das Projekt zur Verwendung von Entity Framework. Weitere Informationen finden Sie unter [wie: Verwenden des Entity Data Model-Assistenten](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Ändern Sie das konzeptionelle Modell, um eine Tabelle pro Hierrachy Vererbung verfügen, indem Sie die Schritte in [Exemplarische Vorgehensweise: Zuordnen von Vererbung - Tabelle pro Hierarchie](http://msdn.microsoft.com/en-us/49b685cf-9db8-4d6d-b885-8837ed238f55).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein OFTYPE-Operator verwendet, um eine Auflistung der `OnsiteCourses` aus einer Auflistung von `Courses` abzurufen und anzuzeigen.  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## <a name="see-also"></a>Siehe auch  
 [EntityClient-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
 [Entity SQL Language (Entity SQL-Sprache)](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
