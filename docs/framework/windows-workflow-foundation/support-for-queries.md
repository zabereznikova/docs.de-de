---
title: Unterstützung für Abfragen
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: e281b5ae7a41bd282f8e7c7eb9db6f99ef5487f3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948938"
---
# <a name="support-for-queries"></a>Unterstützung für Abfragen
Der SQL-Workflowinstanzspeicher zeichnet einen Satz bekannter Eigenschaften im Speicher auf. Benutzer können Instanzen auf Grundlage dieser Eigenschaften abfragen. Die folgende Liste enthält einige dieser bekannten Eigenschaften:  
  
- **Der Name der Website.** Der Name der Website, die den Dienst enthält.  
  
- **Relativer Anwendungspfad.** Der Pfad der Anwendung relativ zur Website.  
  
- **Relativer Dienst Pfad.** Der Pfad des Diensts relativ zur Anwendung.  
  
- **Der Dienst Name.** Name des Diensts.  
  
- **Dienst Namespace.** Der Name des vom Dienst verwendeten Namespaces.  
  
- **Aktueller Computer.**  
  
- **Letzter Computer**. Der Computer, auf dem die Workflowdienstinstanz das letzte Mal ausgeführt wurde.  
  
> [!NOTE]
> Für selbst gehostete Szenarios mit dem Workflowdiensthost werden nur die letzten vier Eigenschaften aufgefüllt. Für Workflowanwendungsszenarios wird nur die letzte Eigenschaft aufgefüllt.  
  
 Die Workflowlaufzeit stellt Werte für die ersten drei Eigenschaften bereit. Der Workflow Dienst Host gibt den Wert für die Eigenschaft " **Suspend Reason** " an. Der SQL-workflowinstanzspeicher selbst stellt Werte für die **zuletzt aktualisierte Computer** Eigenschaft bereit.  
  
 Der SQL-Workflowinstanzspeicher lässt Sie darüber hinaus die benutzerdefinierten Eigenschaften angeben, für die Sie die Werte in der Persistenzdatenbank speichern und die Sie in Abfragen verwenden möchten. Weitere Informationen zu benutzerdefinierten Aktionen finden Sie unter [Store-Erweiterbarkeit](store-extensibility.md).  
  
## <a name="views"></a>Ansichten  
 Der Instanzspeicher enthält die folgenden Ansichten. Weitere Informationen finden Sie unter [persistenzdatenbankschema](persistence-database-schema.md) .  
  
### <a name="the-instances-view"></a>Die Ansicht "Instances"  
 Die Ansicht "Instances" enthält die folgenden Felder:  
  
1. **Id**  
  
2. **"Pdingtimer"**  
  
3. **CreationTime**  
  
4. **LastUpdatedTime**  
  
5. **ServiceDeploymentId**  
  
6. **SuspensionExceptionName**  
  
7. **SuspensionReason**  
  
8. **Activebookmarks**  
  
9. **Currentmachine**  
  
10. **Lastmachine**  
  
11. **ExecutionStatus**  
  
12. **IsInitialized**  
  
13. **Issuout**  
  
14. **IsCompleted**  
  
15. **EncodingOption**  
  
16. **ReadWritePrimitiveDataProperties**  
  
17. **WriteOnlyPrimitiveDataProperties**  
  
18. **"Read Write Items complexdataproperties"**  
  
19. **"Schreibonlycomplexdataproperties"**  
  
### <a name="the-servicedeployments-view"></a>Die Ansicht "ServiceDeployments"  
 Die Ansicht "ServiceDeployments" enthält die folgenden Felder:  
  
1. **Sitename**  
  
2. **RelativeServicePath**  
  
3. **RelativeApplicationPath**  
  
4. **ServiceName**  
  
5. **ServiceNamespace**  
  
### <a name="the-instancepromotedproperties-view"></a>Die Ansicht "InstancePromotedProperties"  
 Die Ansicht "InstancePromotedProperties" enthält die folgenden Felder. Ausführliche Informationen zu höher gestuften Eigenschaften finden Sie im Thema [Store-Erweiterbarkeit](store-extensibility.md) .  
  
1. **InstanceId**  
  
2. **EncodingOption**  
  
3. **PromotionName**  
  
4. **Wert #** (ein Bereich von Feldern von **value1** bis **Value64**).
