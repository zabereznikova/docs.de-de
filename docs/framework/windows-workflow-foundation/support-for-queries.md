---
title: "Unterst&#252;tzung f&#252;r Abfragen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Unterst&#252;tzung f&#252;r Abfragen
Der SQL\-Workflowinstanzspeicher zeichnet einen Satz bekannter Eigenschaften im Speicher auf.Benutzer können Instanzen auf Grundlage dieser Eigenschaften abfragen.Die folgende Liste enthält einige dieser bekannten Eigenschaften:  
  
-   **Site Name.** Der Name der Website, die den Dienst enthält.  
  
-   **Relative Application Path.** Der Pfad der Anwendung relativ zur Website.  
  
-   **Relative Service Path.** Der Pfad des Diensts relativ zur Anwendung.  
  
-   **Service Name.** Der Name des Diensts.  
  
-   **Service Namespace.** Der Name des vom Dienst verwendeten Namespaces.  
  
-   **Current Machine.**  
  
-   **Last Machine**.Der Computer, auf dem die Workflowdienstinstanz das letzte Mal ausgeführt wurde.  
  
> [!NOTE]
>  Für selbst gehostete Szenarios mit dem Workflowdiensthost werden nur die letzten vier Eigenschaften aufgefüllt.Für Workflowanwendungsszenarios wird nur die letzte Eigenschaft aufgefüllt.  
  
 Die Workflowlaufzeit stellt Werte für die ersten drei Eigenschaften bereit.Der Workflowdiensthost gibt den Wert für die Eigenschaft **Suspend Reason** an.Der SQL\-Workflowinstanzspeicher selbst gibt Werte für die Eigenschaft **Last Updated Machine** an.  
  
 Der SQL\-Workflowinstanzspeicher lässt Sie darüber hinaus die benutzerdefinierten Eigenschaften angeben, für die Sie die Werte in der Persistenzdatenbank speichern und die Sie in Abfragen verwenden möchten.Weitere Informationen zu benutzerdefinierten Heraufstufungen finden Sie unter [Erweiterbarkeit des Speichers](../../../docs/framework/windows-workflow-foundation//store-extensibility.md).  
  
## Ansichten  
 Der Instanzspeicher enthält die folgenden Ansichten.Weitere Informationen finden Sie unter [Persistenzdatenbankschema](../../../docs/framework/windows-workflow-foundation//persistence-database-schema.md).  
  
### Die Ansicht "Instances"  
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
  
16. **ReadWritePrimitiveDataProperties**  
  
17. **WriteOnlyPrimitiveDataProperties**  
  
18. **ReadWriteComplexDataProperties**  
  
19. **WriteOnlyComplexDataProperties**  
  
### Die Ansicht "ServiceDeployments"  
 Die Ansicht "ServiceDeployments" enthält die folgenden Felder:  
  
1.  **SiteName**  
  
2.  **RelativeServicePath**  
  
3.  **RelativeApplicationPath**  
  
4.  **ServiceName**  
  
5.  **ServiceNamespace**  
  
### Die Ansicht "InstancePromotedProperties"  
 Die Ansicht "InstancePromotedProperties" enthält die folgenden Felder.Nähere Informationen zu höher gestuften Eigenschaften finden Sie im Thema [Erweiterbarkeit des Speichers](../../../docs/framework/windows-workflow-foundation//store-extensibility.md).  
  
1.  **InstanceId**  
  
2.  **EncodingOption**  
  
3.  **PromotionName**  
  
4.  **Value\#** \(ein Wertebereich von **Value1** bis **Value64**\).