---
title: 'Vorgehensweise: Aktivieren der Persistenz für Workflows und Workflowdienste'
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 9357098318342d15ad7eead32cbc7218af095f6e
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425342"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a>Vorgehensweise: Aktivieren der Persistenz für Workflows und Workflowdienste

In diesem Thema wird beschrieben, wie die Persistenz für Workflows und Workflowdienste aktiviert wird.

## <a name="enable-persistence-for-workflows"></a>Aktivieren der Persistenz für Workflows

Sie können einen Instanzspeicher zuordnen eine **WorkflowApplication** mithilfe der <xref:System.Activities.WorkflowApplication.InstanceStore%2A> Eigenschaft der <xref:System.Activities.WorkflowApplication> Klasse. Die <xref:System.Activities.WorkflowApplication.Persist%2A>-Methode speichert einen Workflow im Instanzspeicher, der der Anwendung zugeordnet ist, oder behält ihn darin bei. Die <xref:System.Activities.WorkflowApplication.Unload%2A>-Methode speichert einen Workflow im Instanzspeicher und entlädt die Instanz daraufhin aus dem Arbeitsspeicher. Die **Load** Methode lädt einen Workflow in den Arbeitsspeicher mit der im instanzpersistenzspeicher gespeicherten Instanz persistenten Speicher.

Die **Persist** Methode führt die folgenden Schritte aus:

1. Anhalten des Workflowplaners und Warten, bis der Workflow in den Leerlauf wechselt

2. Beibehalten oder Speichern des Workflows im persistenten Speicher

3. Fortsetzen des Workflowplaners

 Die **entladen** Methode führt die folgenden Schritte aus:

1. Anhalten des Workflowplaners und Warten, bis der Workflow in den Leerlauf wechselt

2. Beibehalten oder Speichern des Workflows im persistenten Speicher

3. Löschen der Workflowinstanz aus dem Arbeitsspeicher

Sowohl die **Persist** und **entladen** Methoden blockiert, während ein Workflows in einer Zone ohne Persistenz befindet, bis der Workflow die Zone ohne Persistenz beendet wird. Die Methode setzt den Beibehaltungs- bzw. Entladungsvorgang fort, nachdem die Zone ohne Persistenz beendet wurde. Wenn die Zone ohne Persistenz nicht beendet wird, bevor das Timeout verstreicht, oder wenn der Persistenzprozess zu lange dauert, wird eine TimeoutException ausgelöst.

## <a name="enable-persistence-for-workflow-services-in-code"></a>Aktivieren der Persistenz für Workflowdienste im Code

Die **DurableInstancingOptions** Mitglied der <xref:System.ServiceModel.WorkflowServiceHost> -Klasse verfügt über eine Eigenschaft namens **InstanceStore** , Sie verwenden können, um einen Instanzspeicher Zuordnen der **WorkflowServiceHost** .

```csharp
// wsh is an instance of WorkflowServiceHost class
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();
```

Wenn die **WorkflowServiceHost** wird geöffnet, Persistenz automatisch aktiviert, wenn die **DurableInstancingOptions.InstanceStore** nicht null ist.

In der Regel ein Dienstverhalten mit einem Workflowdiensthost verwendet werden, mithilfe der konkrete Instanzspeicher enthält die **InstanceStore** Eigenschaft. SqlWorkflowInstanceStoreBehavior erstellt z. B. eine Instanz der **SqlWorkflowInstanceStore**konfiguriert, und weist sie der **DurableInstancingOptions.InstanceStore**.

## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a>Aktivieren der Persistenz für Workflowdienste mithilfe einer Anwendungskonfigurationsdatei

Persistenz kann mithilfe einer Anwendungskonfigurationsdatei aktiviert werden, indem Sie der Datei "web.config" oder "app.config" folgenden Code hinzufügen:

```xml
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="myBehavior">
          <SqlWorkflowInstanceStore connectionString="Data Source=myDatabaseServer;Initial Catalog=myPersistenceDatabase">
        </behavior>
      </serviceBehaviors>
    <behaviors>
  </system.serviceModel>
</configuration>
```
