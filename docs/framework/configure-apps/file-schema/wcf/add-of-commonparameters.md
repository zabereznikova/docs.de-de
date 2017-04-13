---
title: "&lt;add&gt; von &lt;commonParameters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;add&gt; von &lt;commonParameters&gt;
Gibt ein Name\-Wert\-Paar von Parametern an, die global in mehreren Diensten verwendet werden.  In der Regel umfasst dieser Parameter die Datenbank\-Verbindungszeichenfolge, die von permanenten Diensten freigegeben werden könnte.  
  
## Syntax  
  
```  
  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Name|Der Name des für einen Dienst angegebenen Parameters.|  
|Wert|Der Wert des für einen Dienst angegebenen Parameters.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<commonParameters\>](http://msdn.microsoft.com/de-de/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|Eine Auflistung der allgemeinen, von Diensten verwendeten Parameter.  Diese Auflistung schließt in der Regel die Datenbankverbindungszeichenfolge ein, die ggf. von permanenten Diensten gemeinsam genutzt wird.|  
  
## Hinweise  
 Mit dem `<commonParameters>`\-Element werden alle Parameter definiert, die global in mehreren Diensten verwendet werden, beispielsweise `ConnectionString` bei der Verwendung von <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.  
  
 Dienste, die Commits für Arbeitsbatches in Persistenzspeichern ausführen, z. B. <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> und <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, können mit dem `EnableRetries`\-Parameter so konfiguriert werden, dass sie ihre Transaktion wiederholen, wie im folgenden Beispiel veranschaulicht.  
  
```  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 Der `EnableRetries`\-Parameter kann entweder global \(siehe Abschnitt *CommonParameters*\) oder für einzelne Dienste, die `EnableRetries` unterstützen \(siehe Abschnitt *Dienste*\), festgelegt werden.  
  
 Weitere Informationen über die Verwendung einer Konfigurationsdatei zum Steuern des Verhaltens eines <xref:System.Workflow.Runtime.WorkflowRuntime>\-Objekts einer Hostanwendung von Windows Workflow Foundation finden Sie unter [Workflow Configuration Files](http://msdn.microsoft.com/de-de/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).  
  
## Beispiel  
  
```  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>   
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>   
 <xref:System.Workflow.Runtime.WorkflowRuntime>   
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>   
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>   
 [Workflow Configuration Files](http://msdn.microsoft.com/de-de/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)   
 [\<commonParameters\>](http://msdn.microsoft.com/de-de/d0e1e6fc-985a-4713-b7da-194e30dfab4c)