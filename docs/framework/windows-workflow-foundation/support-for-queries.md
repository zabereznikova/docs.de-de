---
title: "Unterstützung für Abfragen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d4f338f9ae5cc6967885d0518eb573d9f9535fc2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="support-for-queries"></a>Unterstützung für Abfragen
Der SQL-Workflowinstanzspeicher zeichnet einen Satz bekannter Eigenschaften im Speicher auf. Benutzer können Instanzen auf Grundlage dieser Eigenschaften abfragen. Die folgende Liste enthält einige dieser bekannten Eigenschaften:  
  
-   **Name der Website.** Der Name der Website, die den Dienst enthält.  
  
-   **Relativen Pfad.** Der Pfad der Anwendung relativ zur Website.  
  
-   **Relativen Pfad.** Der Pfad des Diensts relativ zur Anwendung.  
  
-   **Service Name.** Name des Diensts.  
  
-   **Dienst-Namespace.** Der Name des vom Dienst verwendeten Namespaces.  
  
-   **Aktuellen Computer.**  
  
-   **Letzte Computer**. Der Computer, auf dem die Workflowdienstinstanz das letzte Mal ausgeführt wurde.  
  
> [!NOTE]
>  Für selbst gehostete Szenarios mit dem Workflowdiensthost werden nur die letzten vier Eigenschaften aufgefüllt. Für Workflowanwendungsszenarios wird nur die letzte Eigenschaft aufgefüllt.  
  
 Die Workflowlaufzeit stellt Werte für die ersten drei Eigenschaften bereit. Der Workflowdiensthost gibt den Wert für die **Suspend Reason** Eigenschaft. Der SQL-Workflowinstanzspeicher selbst gibt Werte für die **Last Updated Machine** Eigenschaft.  
  
 Der SQL-Workflowinstanzspeicher lässt Sie darüber hinaus die benutzerdefinierten Eigenschaften angeben, für die Sie die Werte in der Persistenzdatenbank speichern und die Sie in Abfragen verwenden möchten. Weitere Informationen zu benutzerdefinierten Werbeaktionen, finden Sie unter [Store Erweiterbarkeit](../../../docs/framework/windows-workflow-foundation/store-extensibility.md).  
  
## <a name="views"></a>Ansichten  
 Der Instanzspeicher enthält die folgenden Ansichten. Finden Sie unter [Persistenzdatenbankschema](../../../docs/framework/windows-workflow-foundation/persistence-database-schema.md) Weitere Details.  
  
### <a name="the-instances-view"></a>Die Ansicht "Instances"  
 Die Ansicht "Instances" enthält die folgenden Felder:  
  
1.  **Id**  
  
2.  **PendingTimer**  
  
3.  **CreationTime**  
  
4.  **LastUpdatedTime**  
  
5.  **ServiceDeploymentId**  
  
6.  **SuspensionExceptionName**  
  
7.  **SuspensionReason**  
  
8.  **ActiveBookmarks**  
  
9. **CurrentMachine**  
  
10. **LastMachine**  
  
11. **ExecutionStatus**  
  
12. **IsInitialized**  
  
13. **IsSuspended**  
  
14. **IsCompleted**  
  
15. **EncodingOption**  
  
16. **"Readwriteprimitivedataproperties"-Spalte**  
  
17. **WriteOnlyPrimitiveDataProperties**  
  
18. **ReadWriteComplexDataProperties**  
  
19. **WriteOnlyComplexDataProperties**  
  
### <a name="the-servicedeployments-view"></a>Die Ansicht "ServiceDeployments"  
 Die Ansicht "ServiceDeployments" enthält die folgenden Felder:  
  
1.  **SiteName**  
  
2.  **RelativeServicePath**  
  
3.  **RelativeApplicationPath**  
  
4.  **Dienstname**  
  
5.  **ServiceNamespace**  
  
### <a name="the-instancepromotedproperties-view"></a>Die Ansicht "InstancePromotedProperties"  
 Die Ansicht "InstancePromotedProperties" enthält die folgenden Felder. Ausführliche Informationen zum höher gestuften Eigenschaften finden Sie unter der [Store Erweiterbarkeit](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) Thema.  
  
1.  **Instanz-ID**  
  
2.  **EncodingOption**  
  
3.  **Mit dem PromotionName**  
  
4.  **Value#** (ein Wertebereich von **Value1** auf **Value64**).
