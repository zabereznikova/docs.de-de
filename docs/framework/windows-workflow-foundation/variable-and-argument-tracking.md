---
title: Nachverfolgung von Variablen und Argumenten
ms.date: 03/30/2017
ms.assetid: 8f3d9d30-d899-49aa-b7ce-a8d0d32c4ff0
ms.openlocfilehash: c5d3fe6626c22184edd83de6aedad8589ab2ef35
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837544"
---
# <a name="variable-and-argument-tracking"></a>Nachverfolgung von Variablen und Argumenten
Bei der Nachverfolgung der Workflowausführung kann sich das Extrahieren von Daten oft als nützlich erweisen. Sie stellt zusätzlichen Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird. In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] können Sie alle sichtbaren Variablen oder Argumente innerhalb des Bereichs einer Aktivität in einem Workflow mithilfe der Nachverfolgung extrahieren. Überwachungsprofile vereinfachen das Extrahieren von Daten.  
  
## <a name="variables-and-arguments"></a>Variablen und Argumente  
 Variablen und Argumente werden extrahiert, wenn eine Aktivität einen ActivityStateRecord ausgibt.  Eine Variable kann nur extrahiert werden, wenn sie innerhalb des Bereichs der Aktivität liegt. Eine Variable, die in einer Aktivität extrahiert werden soll, wird wie folgt angegeben:  
  
- Wenn eine Variable über den Variablennamen angegeben wird, sucht die Nachverfolgung in der aktuellen Aktivität, die nachverfolgt wird, und in den übergeordneten Aktivitäten nach der Variable. Es wird im aktuellen Aktivitätsbereich und im übergeordneten Bereich nach der Variablen gesucht.  
  
- Wenn Variablen, die extrahiert werden sollen, mit Name = "\*" angegeben werden, werden alle Variablen innerhalb der aktuellen Aktivität, die nachverfolgt werden, extrahiert. In diesem Fall werden keine Variablen extrahiert, die innerhalb des Bereichs liegen, jedoch in übergeordneten Aktivitäten definiert sind.  
  
 Beim Extrahieren von Argumenten sind die extrahierten Argumente vom Zustand der Aktivität abhängig. Wenn der Zustand einer Aktivität Executing ist, können nur `InArguments` extrahiert werden. Bei jedem anderen Aktivitätszustand (Closed, Faulted, Canceled) können alle Argumente, InArguments und OutArguments, extrahiert werden.  
  
 Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird. Variablen und Argumente können nur mit einem <xref:System.Activities.Tracking.ActivityStateRecord>-Objekt extrahiert und so innerhalb eines Überwachungsprofils mit <xref:System.Activities.Tracking.ActivityStateQuery> abonniert werden.  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="protecting-information-stored-within-variables-and-arguments"></a>Schützen von Informationen in Variablen und Argumenten  
 Eine nachverfolgte Variable oder ein nachverfolgtes Argument wird standardmäßig von der WF-Laufzeit sichtbar gemacht. Workflowentwickler können mit folgenden Schritten einen Schutz vor Zugriffen erreichen:  
  
1. Verschlüsseln Sie den Wert einer Variablen.  
  
2. Steuern Sie die Erstellung eines Überwachungsprofils, um das Extrahieren von Variablen oder Argumenten zu verhindern.  
  
3. Stellen Sie bei benutzerdefinierten Überwachungsteilnehmern sicher, dass im WF-Code keine vertraulichen Informationen angegeben sind, die in Variablen oder Argumenten gespeichert werden.  
  
## <a name="see-also"></a>Siehe auch

- [Windows Server-App-Fabric-Überwachung](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [Überwachen von Anwendungen mit App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
