---
title: "Vorgehensweise: Aktivieren der Persistenz f&#252;r Workflows und Workflowdienste | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Vorgehensweise: Aktivieren der Persistenz f&#252;r Workflows und Workflowdienste
In diesem Thema wird beschrieben, wie die Persistenz für Workflows und Workflowdienste aktiviert wird.  
  
## Aktivieren der Persistenz für Workflows  
 Mit der <xref:System.Activities.WorkflowApplication.InstanceStore%2A>\-Eigenschaft der <xref:System.Activities.WorkflowApplication>\-Klasse können Sie einen Instanzspeicher einer **WorkflowApplication** zuordnen.Die <xref:System.Activities.WorkflowApplication.Persist%2A>\-Methode speichert einen Workflow im Instanzspeicher, der der Anwendung zugeordnet ist, oder behält ihn darin bei.Die <xref:System.Activities.WorkflowApplication.Unload%2A>\-Methode speichert einen Workflow im Instanzspeicher und entlädt die Instanz daraufhin aus dem Arbeitsspeicher.Die **Load**\-Methode lädt einen Workflow mithilfe der im Instanzpersistenzspeicher gespeicherten Workflowdaten in den Arbeitsspeicher.  
  
 Die **Persist**\-Methode führt die folgenden Schritte aus:  
  
1.  Anhalten des Workflowplaners und Warten, bis der Workflow in den Leerlauf wechselt  
  
2.  Beibehalten oder Speichern des Workflows im persistenten Speicher  
  
3.  Fortsetzen des Workflowplaners  
  
 Die **Unload**\-Methode führt die folgenden Schritte aus:  
  
1.  Anhalten des Workflowplaners und Warten, bis der Workflow in den Leerlauf wechselt  
  
2.  Beibehalten oder Speichern des Workflows im persistenten Speicher  
  
3.  Löschen der Workflowinstanz aus dem Arbeitsspeicher  
  
 Die **Persist**\-Methode und die **Unload**\-Methode führen beide zu einer Blockierung, während ein Workflow sich in einer Zone ohne Persistenz befindet, bis der Workflow sich nicht mehr in dieser Zone befindet.Die Methode setzt den Beibehaltungs\- bzw. Entladungsvorgang fort, nachdem die Zone ohne Persistenz beendet wurde.Wenn die Zone ohne Persistenz nicht beendet wird, bevor das Timeout verstreicht, oder wenn der Persistenzprozess zu lange dauert, wird eine TimeoutException ausgelöst.  
  
## Aktivieren der Persistenz für Workflowdienste im Code  
 Der **DurableInstancingOptions**\-Member der <xref:System.ServiceModel.WorkflowServiceHost>\-Klasse verfügt über eine Eigenschaft namens **InstanceStore**, mit der Sie **WorkflowServiceHost** einen Instanzspeicher zuordnen können.  
  
```  
  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
  
```  
  
 Beim Öffnen des **WorkflowServiceHost** wird die Persistenz automatisch aktiviert, wenn der **DurableInstancingOptions.InstanceStore** nicht NULL ist.  
  
 In der Regel wird über das Dienstverhalten mithilfe der **InstanceStore**\-Eigenschaft der konkrete Instanzspeicher bereitgestellt, der mit einem Workflowdiensthost verwendet werden soll.SqlWorkflowInstanceStoreBehavior erstellt z. B. eine Instanz des **SqlWorkflowInstanceStore**, konfiguriert sie und weist sie dem **DurableInstancingOptions.InstanceStore** zu.  
  
## Aktivieren der Persistenz für Workflowdienste mithilfe einer Anwendungskonfigurationsdatei  
 Persistenz kann mithilfe einer Anwendungskonfigurationsdatei aktiviert werden, indem Sie der Datei "web.config" oder "app.config" folgenden Code hinzufügen:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name=”myBehavior”>  
          <SqlWorkflowInstanceStore connectionString=”Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase”>  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
  
```