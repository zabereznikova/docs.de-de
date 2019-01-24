---
title: '&lt;commonParameters&gt;'
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: 2b8a6e5ba670657afda6fd8c64024a330650a9b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626835"
---
# <a name="ltcommonparametersgt"></a>&lt;commonParameters&gt;
Stellt eine Auflistung von Parametern dar, die global in mehreren Diensten verwendet werden. Diese Auflistung schließt in der Regel die Datenbankverbindungszeichenfolge ein, die ggf. von permanenten Diensten gemeinsam genutzt wird.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<workflowRuntime>  
\<commonParameters>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|Fügt ein Name-Wert-Paar von allgemeinen von Diensten verwendeten Parametern zur Auflistung hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<workflowRuntime>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|Gibt die Einstellungen für eine Instanz von <xref:System.Workflow.Runtime.WorkflowRuntime> zum Hosten workflowbasierter Windows Communication Foundation (WCF)-Diensten.|  
  
## <a name="remarks"></a>Hinweise  
 Mit dem `<commonParameters>`-Element werden alle Parameter definiert, die global in mehreren Diensten verwendet werden, beispielsweise `ConnectionString` bei der Verwendung von <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.  
  
> [!NOTE]
>  Der SQL-Überwachungsdienst verwendet den `ConnectionString`-Wert nicht auf einheitliche Weise, wenn er im `<commonParameters>`-Abschnitt angegeben ist. Einige der Vorgänge wie das Abrufen der `StateMachineWorkflowInstance.StateHistory`-Eigenschaft schlagen möglicherweise fehl. Um dies zu umgehen, geben Sie das `ConnectionString`-Attribut im Konfigurationsabschnitt für Überwachungsprovider an, wie im folgenden Beispiel dargestellt.  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 Dienste, die Commits für Arbeitsbatches in Persistenzspeichern ausführen, z. B. <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> und <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, können mit dem `EnableRetries`-Parameter so konfiguriert werden, dass sie ihre Transaktion wiederholen, wie im folgenden Beispiel veranschaulicht.  
  
```xml  
<workflowRuntime name="SampleApplication"
                 unloadOnIdle="false">
  <commonParameters>
    <add name="ConnectionString"
         value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
    <add name="EnableRetries"
         value="True" />
  </commonParameters>
  <services>
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime,
               Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 Beachten Sie, dass die `EnableRetries` Parameter kann festgelegt werden, entweder auf globaler Ebene (siehe die *CommonParameters* Abschnitt) oder für einzelne Dienste, die unterstützen `EnableRetries` (siehe die *Services*Abschnitt).  
  
 Im folgenden Beispielcode wird veranschaulicht, wie die allgemeinen Parameter programmgesteuert geändert werden.  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 Weitere Informationen zur Verwendung einer Konfigurationsdatei zum Steuern des Verhaltens von einem <xref:System.Workflow.Runtime.WorkflowRuntime> Objekt einer hostanwendung von Windows Workflow Foundation finden Sie unter [Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).  
  
## <a name="example"></a>Beispiel  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- [Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))
- [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)
