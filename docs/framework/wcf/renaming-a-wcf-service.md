---
title: Umbenennen eines WCF-Diensts
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 8cb86621972423f55bfa18c60c1d4eb60cacb205
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651042"
---
# <a name="renaming-a-wcf-service"></a>Umbenennen eines WCF-Diensts
In diesem Thema wird beschrieben, wie Sie einen Windows Communication Foundation (WCF)-Dienst umbenennen können.  
  
## <a name="renaming-a-wcf-service"></a>Umbenennen eines WCF-Diensts  
 Führen Sie die folgenden Schritte aus, um einen Dienst in einer Windows Communication Foundation (WCF)-Vorlage umzubenennen,  
  
- Ändern Sie den Namen der Klasse, die den Dienst implementiert.  
  
- Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Diensts in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt. Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- Handelt es sich um einen WebHosted-Dienst, verwendet er eine *.svc-Datei. Öffnen Sie die svc-Datei, und ändern Sie den Namen des Diensts, wie im folgenden Beispiel dargestellt. Dieser Schritt ist für selbst gehostete Anwendungen nicht erforderlich, da keine svc-Datei vorhanden ist.  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a>Umbenennen eines WCF-Dienstvertrags  
  
- Führen Sie die folgenden Schritte aus, um den Dienstvertrag umzubenennen:  
  
- Ändern Sie den Namen des Dienstvertrags.  
  
- Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Dienstvertrags in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt. Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
