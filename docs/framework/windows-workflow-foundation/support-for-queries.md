---
title: Unterstützung für Abfragen
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: 30695fcd791a0d69c31a897068d69838c80c3957
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307950"
---
# <a name="support-for-queries"></a>Unterstützung für Abfragen
Der SQL-Workflowinstanzspeicher zeichnet einen Satz bekannter Eigenschaften im Speicher auf. Benutzer können Instanzen auf Grundlage dieser Eigenschaften abfragen. Die folgende Liste enthält einige dieser bekannten Eigenschaften:  
  
-   **Websitename.** Der Name der Website, die den Dienst enthält.  
  
-   **Relative Anwendungspfad.** Der Pfad der Anwendung relativ zur Website.  
  
-   **Relativer Pfad.** Der Pfad des Diensts relativ zur Anwendung.  
  
-   **Dienstname.** Name des Diensts.  
  
-   **Dienst-Namespace.** Der Name des vom Dienst verwendeten Namespaces.  
  
-   **Aktuellen Computer.**  
  
-   **Letzte Computer**. Der Computer, auf dem die Workflowdienstinstanz das letzte Mal ausgeführt wurde.  
  
> [!NOTE]
>  Für selbst gehostete Szenarios mit dem Workflowdiensthost werden nur die letzten vier Eigenschaften aufgefüllt. Für Workflowanwendungsszenarios wird nur die letzte Eigenschaft aufgefüllt.  
  
 Die Workflowlaufzeit stellt Werte für die ersten drei Eigenschaften bereit. Der Workflowdiensthost gibt den Wert für die **Suspend Reason** Eigenschaft. Die SQL-Workflow-Instanz Store selbst gibt Werte für die **Last Updated Machine** Eigenschaft.  
  
 Der SQL-Workflowinstanzspeicher lässt Sie darüber hinaus die benutzerdefinierten Eigenschaften angeben, für die Sie die Werte in der Persistenzdatenbank speichern und die Sie in Abfragen verwenden möchten. Weitere Informationen zu benutzerdefinierten heraufstufungen finden Sie unter [Store Erweiterbarkeit](store-extensibility.md).  
  
## <a name="views"></a>Ansichten  
 Der Instanzspeicher enthält die folgenden Ansichten. Finden Sie unter [Persistenzdatenbankschema](persistence-database-schema.md) Weitere Details.  
  
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
  
1. **SiteName**  
  
2. **RelativeServicePath**  
  
3. **RelativeApplicationPath**  
  
4. **ServiceName**  
  
5. **ServiceNamespace**  
  
### <a name="the-instancepromotedproperties-view"></a>Die Ansicht "InstancePromotedProperties"  
 Die Ansicht "InstancePromotedProperties" enthält die folgenden Felder. Weitere Informationen zu höher gestuften Eigenschaften finden Sie unter den [Store Erweiterbarkeit](store-extensibility.md) Thema.  
  
1. **InstanceId**  
  
2. **EncodingOption**  
  
3. **PromotionName**  
  
4. **Value#** (eine Reihe von Feldern aus **Value1** zu **Value64**).
