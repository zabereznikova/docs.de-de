---
ms.openlocfilehash: ab9431780422dfece5dcf8007d13e6d584f5118f
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96478099"
---
### <a name="avoiding-endless-recursion-for-iworkflowinstancemanagementtransactedcancel-and-iworkflowinstancemanagementtransactedterminate"></a>Vermeiden von Endlosrekursion für IWorkflowInstanceManagement.TransactedCancel und IWorkflowInstanceManagement.TransactedTerminate

#### <a name="details"></a>Details

Wenn Sie <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedCancel%2A?displayProperty=nameWithType>- oder <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedTerminate%2A?displayProperty=nameWithType>-APIs verwenden, um eine Worklowdienstinstanz abzubrechen oder zu beenden, kann für die Workflowinstanz unter bestimmten Umständen aufgrund von Endlosrekursion ein Stapelüberlauf auftreten, wenn die `Workflow`-Laufzeit versucht, die Dienstinstanz als Teil der Verarbeitung der Anforderung persistent zu speichern. Das Problem tritt auf, wenn sich die Workflowinstanz in einem Zustand befindet, in dem sie auf den Abschluss einer anderen ausstehenden WCF-Anforderung an einen anderen Dienst wartet. Die Vorgänge `TransactedCancel` und `TransactedTerminate` erstellen Arbeitselemente, die für die Workflowdienstinstanz in die Warteschlange eingereiht werden. Diese Arbeitselemente werden nicht im Rahmen der Verarbeitung der `TransactedCancel/TransactedTerminate`-Anforderung ausgeführt. Da die Workflowdienstinstanz damit ausgelastet ist, auf den Abschluss der anderen ausstehenden WCF-Anforderung zu warten, verbleibt das erstellte Arbeitselement in der Warteschlange. Der `TransactedCancel/TransactedTerminate`-Vorgang wird abgeschlossen, und die Steuerung wird zurück an den Client übergeben. Wenn die dem `TransactedCancel/TransactedTerminate`-Vorgang zugeordnete Transaktion den Commit versucht, muss sie den Zustand der Workflowdienstinstanz persistent speichern. Da aber für die Instanz eine ausstehende `WCF`-Anforderung vorliegt, kann die Workflowruntime die Workflowdienstinstanz nicht persistent speichern, und eine Endlosrekursionsschleife führt zum Stapelüberlauf. Da `TransactedCancel` und `TransactedTerminate` nur ein Arbeitselement im Speicher erstellen, besitzt die Tatsache, dass eine Transaktion vorhanden ist, keinerlei Auswirkung. Durch ein Rollback der Transaktion wird das Arbeitselement nicht verworfen. Zur Lösung dieses Problems wurde ab .NET Framework 4.7.2 eine `AppSetting` eingeführt, die `web.config/app.config` des Workflowdiensts hinzugefügt werden kann und angibt, dass Transaktionen für `TransactedCancel` und `TransactedTerminate` ignoriert werden sollen. Auf diese Weise kann die Transaktion einen Commit ausführen, ohne warten zu müssen, bis die Workflowinstanz dauerhaft gespeichert wurde. Das AppSetting-Element für dieses Feature hat den Namen `microsoft:WorkflowServices:IgnoreTransactionsForTransactedCancelAndTransactedTerminate`. Der Wert `true` gibt an, dass die Transaktion ignoriert werden soll, um so den Stapelüberlauf zu vermeiden. Der Standardwert dieser AppSetting ist `false`. Vorhandene Workflowdienstinstanzen sind daher nicht betroffen.

#### <a name="suggestion"></a>Vorschlag

Wenn Sie AppFabric oder einen anderen <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement>-Client verwenden und beim Versuch, eine Workflowinstanz abzubrechen oder zu beenden, ein Stapelüberlauf in der Workflowdienstinstanz auftritt, können Sie Folgendes zum Abschnitt `<appSettings>` der Datei „web.config/app.config“ für den Workflowdienst hinzufügen:

<pre><code class="lang-xml">&lt;add key=&quot;microsoft:WorkflowServices:IgnoreTransactionsForTransactedCancelAndTransactedTerminate&quot; value=&quot;true&quot;/&gt;&#13;&#10;</code></pre>

Wenn dieses Problem nicht auftritt, müssen Sie diese Aktion nicht ausführen.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |
