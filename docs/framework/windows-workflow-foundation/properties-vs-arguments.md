---
title: Eigenschaften im Vergleich zu Argumente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14651389-4a49-4cbb-9ddf-c83fdc155df1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4fcb38322d6b068095238add9334aa2d081c4a5d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="properties-vs-arguments"></a>Eigenschaften im Vergleich zu Argumente
Es gibt mehrere Möglichkeiten für die Übergabe von Daten an eine Aktivität. Neben dem Verwenden von <xref:System.Activities.InArgument> können auch Aktivitäten entwickelt werden, um Daten entweder mit CLR-Standardeigenschaften oder öffentlichen <xref:System.Activities.ActivityAction>-Eigenschaften zu empfangen. In diesem Thema wird erläutert, wie der richtige Methodentyp ausgewählt wird.  
  
## <a name="using-clr-properties"></a>Verwenden von CLR-Eigenschaften  
 Bei der Übergabe von Daten an eine Aktivität bestehen bei CLR-Eigenschaften (d. h. öffentliche Methoden, die Get- und Set-Routinen zum Verfügbarmachen von Daten verwenden) die meisten Einschränkungen. Der Wert eines Parameters, der an eine CLR-Eigenschaft übergeben wird, muss zur Kompilierungszeit der Lösung bekannt sein. Dieser Wert ist für jede Instanz des Workflows identisch. Ein an eine CLR-Eigenschaft übergebener Wert ist also mit einer Konstante vergleichbar, die im Code definiert wird. Der Wert kann weder für die Lebensdauer der Aktivität noch für verschiedene Instanzen der Aktivität geändert werden. <xref:System.Activities.Expressions.InvokeMethod%601.MethodName%2A> ist ein Beispiel für eine CLR-Eigenschaft, die von einer Aktivität verfügbar gemacht wird. Der Methodenname, den die Aktivität aufruft, kann nicht basierend auf den Laufzeitbedingungen geändert werden und ist für jede Instanz der Aktivität identisch.  
  
## <a name="using-arguments"></a>Verwenden von Argumenten  
 Argumente sollten verwendet werden, wenn Daten nur einmal während der Lebensdauer der Aktivität ausgewertet werden. Das heißt, der Wert bleibt zwar während der Lebensdauer der Aktivität unverändert, kann aber für verschiedene Instanzen der Aktivität anders lauten. <xref:System.Activities.Statements.If.Condition%2A> ist ein Beispiel für einen Wert, der einmal ausgewertet wird und daher als Argument definiert ist. <xref:System.Activities.Statements.WriteLine.Text%2A> ist ein weiteres Beispiel für eine Methode, die als Argument definiert werden sollte, da sie nur einmal während der Ausführung der Aktivität ausgewertet wird, aber für verschiedene Instanzen der Aktivität anders lauten kann.  
  
## <a name="using-activityaction"></a>Verwenden von ActivityAction  
 Wenn Daten während der Lebensdauer der Ausführung einer Aktivität mehrmals ausgewertet werden müssen, sollte ein <xref:System.Activities.ActivityAction> verwendet werden. Die <xref:System.Activities.Statements.While.Condition%2A>-Eigenschaft wird z. B. für jede Iteration der <xref:System.Activities.Statements.While>-Schleife ausgewertet. Wenn zu diesem Zweck ein <xref:System.Activities.InArgument> verwendet wird, wird die Schleife nie beendet, da das Argument nicht für jede Iteration erneut ausgewertet wird und immer das gleiche Ergebnis zurückgibt.
