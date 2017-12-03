---
title: '&lt;add&gt; von &lt;services&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d7e58638ba4a964a1780606e2f75c0fd453638eb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltservicesgt"></a>&lt;add&gt; von &lt;services&gt;
Legt Einstellungen für eine Instanz von <xref:System.Workflow.Runtime.WorkflowRuntime> zum Hosten workflowbasierter [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienste fest. Dieses Element ist vom Typ <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  
  
 \<System. ServiceModel >  
\<Verhalten >  
\<ServiceBehaviors >  
\<Verhalten >  
\<Services >  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<workflowRuntime>  
   <services>  
      <add type="String"/>  
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
|[\<Services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|Eine Auflistung von Diensten, die dem <xref:System.Workflow.Runtime.WorkflowRuntime>-Modul hinzugefügt werden. Die Elemente sind vom Typ <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  Die in der Auflistung angegebenen Dienste werden vom Workflow-Laufzeitmodul initialisiert und den Diensten hinzugefügt, wenn der entsprechende <xref:System.Workflow.Runtime.WorkflowRuntime>-Konstruktor aufgerufen wird. Aus diesem Grund müssen die in der Auflistung angegebenen Dienste bestimmte Regeln bezüglich der Signaturen ihrer Konstruktoren erfüllen. Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.|  
  
## <a name="remarks"></a>Hinweise  
 Der in diesem Element angegebene Dienst wird vom Workflow-Lauftzeitmodul initialisiert und seinen Diensten hinzugefügt, wenn der entsprechende <xref:System.Workflow.Runtime.WorkflowRuntime>-Konstruktor aufgerufen wird. Deshalb muss der in der Auflistung angegebenen Dienst bestimmten Regeln über die Signaturen ihrer Konstruktoren folgen. Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [Workflow-Konfigurationsdateien](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)
