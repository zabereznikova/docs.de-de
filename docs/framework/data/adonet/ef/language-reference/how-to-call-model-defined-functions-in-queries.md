---
title: 'Gewusst wie: Aufrufen modelldefinierter Funktionen in Abfragen'
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
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d639297764333b99675cb9e076e816314f3567c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-call-model-defined-functions-in-queries"></a>Gewusst wie: Aufrufen modelldefinierter Funktionen in Abfragen
In diesem Thema wird beschrieben, wie Funktionen, die im konzeptionellen Modell definiert sind, aus [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfragen heraus aufgerufen werden.  
  
 Das nachfolgende Verfahren bietet einen allgemeinen Überblick über den Aufruf einer im Modell definierten Funktion aus einer [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfrage heraus. Das folgende Beispiel enthält weitere Details zu den Schritten in der Prozedur. In dem Verfahren wird davon ausgegangen, dass eine Funktion im konzeptionellen Modell definiert wurde. Weitere Informationen finden Sie unter [wie: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a>So rufen Sie eine im konzeptionellen Modell definierte Funktion auf  
  
1.  Fügen Sie der Anwendung, die der im konzeptionellen Modell definierten Funktion zugeordnet ist, eine Common Language Runtime (CLR)-Methode hinzu. Zum Zuordnen der Methode müssen Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> für die Methode übernehmen. Beachten Sie, dass der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A>-Parameter und der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A>-Parameter des Attributs den Namespacenamen bzw. den Funktionsnamen im konzeptionellen Modell darstellen. Bei der Funktionsnamenauflösung für LINQ wird die Groß-/Kleinschreibung berücksichtigt.  
  
2.  Rufen Sie die Funktion in einer [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfrage auf.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine Funktion, die im konzeptionellen Modell definiert wird, aus einer [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfrage heraus aufgerufen wird. Im Beispiel wird das Modell "School" verwendet. Informationen über das Modell "School" finden Sie unter [Erstellen der Beispieldatenbank "School"](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) und [der Schule EDMX-Datei generieren](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758).  
  
 Die folgende konzeptionelle Modellfunktion gibt die Anzahl der Jahre zurück, die seit der Einstellung einer Lehrkraft vergangen sind. Informationen zum Hinzufügen von der Funktion mit einem konzeptionellen Modell finden Sie unter [wie: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).)  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a>Beispiel  
 Fügen Sie der Anwendung danach die folgende Methode hinzu, und verwenden Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>, um sie der Funktion im konzeptionellen Modell zuzuordnen:  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a>Beispiel  
 Jetzt können Sie die im konzeptionellen Modell definierte Funktion aus einer [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfrage heraus aufrufen. Im folgenden Code wird die Methode aufgerufen, um alle Lehrkräfte anzuzeigen, die vor mehr als zehn Jahren eingestellt wurden:  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die EDMX-Datei](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [Aufrufen von Funktionen in LINQ to Entities-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [Vorgehensweise: Aufrufen modelldefinierter Funktionen als Objektmethoden](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)
