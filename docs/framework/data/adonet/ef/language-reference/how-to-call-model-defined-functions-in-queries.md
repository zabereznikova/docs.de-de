---
title: 'Vorgehensweise: Aufrufen modelldefinierter Funktionen in Abfragen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
ms.openlocfilehash: 32cdb5b0f27817856ab586eb38f89df63c1c4d3b
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539859"
---
# <a name="how-to-call-model-defined-functions-in-queries"></a>Vorgehensweise: Aufrufen modelldefinierter Funktionen in Abfragen
In diesem Thema wird beschrieben, wie Funktionen aufgerufen werden, die im konzeptionellen Modell von in LINQ to Entities-Abfragen definiert werden.  
  
 Das folgende Verfahren bietet einen Überblick über das für das Aufrufen einer modelldefinierten Funktion von innerhalb einer LINQ to Entities-Abfrage an. Das folgende Beispiel enthält weitere Details zu den Schritten in der Prozedur. In dem Verfahren wird davon ausgegangen, dass eine Funktion im konzeptionellen Modell definiert wurde. Weitere Informationen finden Sie unter [Vorgehensweise: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a>So rufen Sie eine im konzeptionellen Modell definierte Funktion auf  
  
1. Fügen Sie der Anwendung, die der im konzeptionellen Modell definierten Funktion zugeordnet ist, eine Common Language Runtime (CLR)-Methode hinzu. Zum Zuordnen der Methode müssen Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> für die Methode übernehmen. Beachten Sie, dass der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A>-Parameter und der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A>-Parameter des Attributs den Namespacenamen bzw. den Funktionsnamen im konzeptionellen Modell darstellen. Bei der Funktionsnamenauflösung für LINQ wird die Groß-/Kleinschreibung berücksichtigt.  
  
2. Rufen Sie die Funktion in einer LINQ to Entities-Abfrage auf.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie eine Funktion aufrufen, die im konzeptionellen Modell von innerhalb einer LINQ to Entities-Abfrage definiert ist. Im Beispiel wird das Modell "School" verwendet. Weitere Informationen über das Modell "School" finden Sie unter [Erstellen der Beispieldatenbank "School"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) und [Generieren der EDMX-Datei des "School"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).  
  
 Die folgende konzeptionelle Modellfunktion gibt die Anzahl der Jahre zurück, die seit der Einstellung einer Lehrkraft vergangen sind. Informationen zum Hinzufügen der Funktion zu einem konzeptionellen Modell finden Sie unter [Vorgehensweise: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a>Beispiel  
 Fügen Sie der Anwendung danach die folgende Methode hinzu, und verwenden Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>, um sie der Funktion im konzeptionellen Modell zuzuordnen:  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a>Beispiel  
 Jetzt können Sie die Funktion im konzeptionellen Modell von innerhalb einer LINQ to Entities-Abfrage aufrufen. Im folgenden Code wird die Methode aufgerufen, um alle Lehrkräfte anzuzeigen, die vor mehr als zehn Jahren eingestellt wurden:  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
- [Aufrufen von Funktionen in LINQ to Entities-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)
- [Vorgehensweise: Rufen Sie Modelldefinierter Funktionen als Objektmethoden auf](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)
