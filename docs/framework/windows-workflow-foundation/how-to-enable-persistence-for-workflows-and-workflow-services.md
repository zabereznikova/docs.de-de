---
title: 'Vorgehensweise: Aktivieren der Persistenz für Workflows und Workflowdienste'
description: Erfahren Sie, wie Sie den SQL-workflowinstanzspeicher konfigurieren, um die Persistenz für Workflows und Workflow Dienste Programm gesteuert und mithilfe einer Konfigurationsdatei zu aktivieren
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 31fe6e3f06989e9a42254747565342cf97e4b9f1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421513"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a>Vorgehensweise: Aktivieren der Persistenz für Workflows und Workflowdienste

In diesem Thema wird beschrieben, wie die Persistenz für Workflows und Workflowdienste aktiviert wird.

## <a name="enable-persistence-for-workflows"></a>Aktivieren der Persistenz für Workflows

Sie können einen Instanzspeicher mithilfe der-Eigenschaft der-Klasse mit einer **Workflow Anwendung** verknüpfen <xref:System.Activities.WorkflowApplication.InstanceStore%2A> <xref:System.Activities.WorkflowApplication> . Die <xref:System.Activities.WorkflowApplication.Persist%2A>-Methode speichert einen Workflow im Instanzspeicher, der der Anwendung zugeordnet ist, oder behält ihn darin bei. Die <xref:System.Activities.WorkflowApplication.Unload%2A>-Methode speichert einen Workflow im Instanzspeicher und entlädt die Instanz daraufhin aus dem Arbeitsspeicher. Die **Load** -Methode lädt einen Workflow mithilfe der im instanzpersistenzspeicher gespeicherten Workflow Daten in den Arbeitsspeicher.

Die **Persistenzmethode** führt die folgenden Schritte aus:

1. Anhalten des Workflowplaners und Warten, bis der Workflow in den Leerlauf wechselt

2. Beibehalten oder Speichern des Workflows im persistenten Speicher

3. Fortsetzen des Workflowplaners

 Die **Entlade** Methode führt die folgenden Schritte aus:

1. Anhalten des Workflowplaners und Warten, bis der Workflow in den Leerlauf wechselt

2. Beibehalten oder Speichern des Workflows im persistenten Speicher

3. Löschen der Workflowinstanz aus dem Arbeitsspeicher

Die **Persistenzmethode** und die **Entlade** Methode werden blockiert, während sich ein Workflow in einer Zone ohne Persistenz befindet, bis der Workflow die Zone ohne Persistenz verlässt. Die Methode setzt den Beibehaltungs- bzw. Entladungsvorgang fort, nachdem die Zone ohne Persistenz beendet wurde. Wenn die Zone ohne Persistenz nicht beendet wird, bevor das Timeout verstreicht, oder wenn der Persistenzprozess zu lange dauert, wird eine TimeoutException ausgelöst.

## <a name="enable-persistence-for-workflow-services-in-code"></a>Aktivieren der Persistenz für Workflowdienste im Code

Der **durableinstancingoptions** -Member der- <xref:System.ServiceModel.WorkflowServiceHost> Klasse verfügt über eine Eigenschaft mit dem Namen **InstanceStore** , die Sie verwenden können, um dem **Workflow Service Host**einen Instanzspeicher zuzuordnen.

```csharp
// wsh is an instance of WorkflowServiceHost class
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();
```

Wenn **Workflow Service Host** geöffnet wird, wird die Persistenz automatisch aktiviert, wenn **durableinstancingoptions. InstanceStore** nicht NULL ist.

In der Regel stellt ein Dienst Verhalten den konkreten Instanzspeicher bereit, der mit einem Workflow Dienst Host verwendet werden soll, indem die **InstanceStore** -Eigenschaft verwendet wird. Beispielsweise erstellt SqlWorkflowInstanceStoreBehavior eine Instanz von **SqlWorkflowInstanceStore**, konfiguriert Sie und weist Sie der **durableinstancingoptions. InstanceStore**zu.

## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a>Aktivieren der Persistenz für Workflowdienste mithilfe einer Anwendungskonfigurationsdatei

Persistenz kann mithilfe einer Anwendungskonfigurationsdatei aktiviert werden, indem Sie der Datei "web.config" oder "app.config" folgenden Code hinzufügen:

```xml
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="myBehavior">
          <sqlWorkflowInstanceStore connectionString="Data Source=myDatabaseServer;Initial Catalog=myPersistenceDatabase" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```
