---
title: Unterstützung für Abfragen
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: 350644de4a5deb7b8dcb5133c9cc2edb477fd355
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258438"
---
# <a name="support-for-queries"></a>Unterstützung für Abfragen

Der SQL-Workflowinstanzspeicher zeichnet einen Satz bekannter Eigenschaften im Speicher auf. Benutzer können Instanzen auf Grundlage dieser Eigenschaften abfragen. Die folgende Liste enthält einige dieser bekannten Eigenschaften:  
  
- **Der Name der Website.** Der Name der Website, die den Dienst enthält.  
  
- **Relative Application Path.** Der Pfad der Anwendung relativ zur Website.  
  
- **Relative Service Path.** Der Pfad des Diensts relativ zur Anwendung.  
  
- **Der Dienst Name.** Der Name des Diensts.  
  
- **Dienst Namespace.** Der Name des vom Dienst verwendeten Namespaces.  
  
- **Current Machine.**  
  
- **Letzter Computer**. Der Computer, auf dem die Workflowdienstinstanz das letzte Mal ausgeführt wurde.  
  
> [!NOTE]
> Für selbst gehostete Szenarios mit dem Workflowdiensthost werden nur die letzten vier Eigenschaften aufgefüllt. Für Workflowanwendungsszenarios wird nur die letzte Eigenschaft aufgefüllt.  
  
 Die Workflowlaufzeit stellt Werte für die ersten drei Eigenschaften bereit. Der Workflow Dienst Host gibt den Wert für die Eigenschaft " **Suspend Reason** " an. Der SQL-workflowinstanzspeicher selbst stellt Werte für die **zuletzt aktualisierte Computer** Eigenschaft bereit.  
  
 Der SQL-Workflowinstanzspeicher lässt Sie darüber hinaus die benutzerdefinierten Eigenschaften angeben, für die Sie die Werte in der Persistenzdatenbank speichern und die Sie in Abfragen verwenden möchten. Weitere Informationen zu benutzerdefinierten Aktionen finden Sie unter [Store-Erweiterbarkeit](store-extensibility.md).  
  
## <a name="views"></a>Sichten  

 Der Instanzspeicher enthält die folgenden Ansichten. Weitere Informationen finden Sie unter [persistenzdatenbankschema](persistence-database-schema.md) .  
  
### <a name="the-instances-view"></a>Die Ansicht "Instances"  

 Die Ansicht "Instances" enthält die folgenden Felder:  
  
1. **Id**  
  
2. **PendingTimer**  
  
3. **CreationTime**  
  
4. **LastUpdatedTime**  
  
5. **ServiceDeploymentId**  
  
6. **SuspensionExceptionName**  
  
7. **SuspensionReason**  
  
8. **ActiveBookmarks**  
  
9. **CurrentMachine**  
  
10. **LastMachine**  
  
11. **ExecutionStatus**  
  
12. **IsInitialized**  
  
13. **IsSuspended**  
  
14. **IsCompleted**  
  
15. **EncodingOption**  
  
16. **ReadWritePrimitiveDataProperties**  
  
17. **WriteOnlyPrimitiveDataProperties**  
  
18. **ReadWriteComplexDataProperties**  
  
19. **WriteOnlyComplexDataProperties**  
  
### <a name="the-servicedeployments-view"></a>Die Ansicht "ServiceDeployments"  

 Die Ansicht "ServiceDeployments" enthält die folgenden Felder:  
  
1. **Sitename**  
  
2. **RelativeServicePath**  
  
3. **RelativeApplicationPath**  
  
4. **Service Name**  
  
5. **ServiceNamespace**  
  
### <a name="the-instancepromotedproperties-view"></a>Die Ansicht "InstancePromotedProperties"  

 Die Ansicht "InstancePromotedProperties" enthält die folgenden Felder. Ausführliche Informationen zu höher gestuften Eigenschaften finden Sie im Thema [Store-Erweiterbarkeit](store-extensibility.md) .  
  
1. **InstanceId**  
  
2. **EncodingOption**  
  
3. **PromotionName**  
  
4. **Wert #** (ein Bereich von Feldern von **value1** bis **Value64**).
