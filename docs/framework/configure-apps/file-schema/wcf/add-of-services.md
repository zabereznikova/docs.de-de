---
title: '&lt;add&gt; von &lt;services&gt;'
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 9a86b7549e0efef10cbeb16dcc427d04065e43d3
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145535"
---
# <a name="ltaddgt-of-ltservicesgt"></a>&lt;add&gt; von &lt;services&gt;
Gibt die Einstellungen für eine Instanz von <xref:System.Workflow.Runtime.WorkflowRuntime> zum Hosten workflowbasierter Windows Communication Foundation (WCF)-Diensten. Dieses Element ist vom Typ <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<Verhalten >  
\<Dienste >  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Eine Zeichenfolge, die den durch die Assembly bezeichneten Typnamen des zu initialisierenden Diensts angibt. Der angegebene Dienst muss bestimmten Regeln über die Signaturen ihrer Konstruktoren folgen. Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|Eine Auflistung von Diensten, die der <xref:System.Workflow.Runtime.WorkflowRuntime>-Engine hinzugefügt werden. Die Elemente sind vom Typ <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  Die in der Auflistung angegebenen Dienste werden vom Workflow-Laufzeitmodul initialisiert und den Diensten hinzugefügt, wenn der entsprechende <xref:System.Workflow.Runtime.WorkflowRuntime>-Konstruktor aufgerufen wird. Aus diesem Grund müssen die in der Auflistung angegebenen Dienste bestimmte Regeln bezüglich der Signaturen ihrer Konstruktoren erfüllen. Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.|  
  
## <a name="remarks"></a>Hinweise  
 Der in diesem Element angegebene Dienst wird von der Workflowruntime-Engine initialisiert und seinen Diensten hinzugefügt, wenn der entsprechende <xref:System.Workflow.Runtime.WorkflowRuntime>-Konstruktor aufgerufen wird. Deshalb muss der in der Auflistung angegebenen Dienst bestimmten Regeln über die Signaturen ihrer Konstruktoren folgen. Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<serviceBehaviors>
  <behavior name="ServiceBehavior">
    <workflowRuntime name="WorkflowServiceHostRuntime"
                     validateOnCreate="true"
                     enablePerformanceCounters="true">
      <services>
        <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common" />
      </services>
    </workflowRuntime>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))
