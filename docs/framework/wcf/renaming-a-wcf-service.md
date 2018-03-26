---
title: Umbenennen eines WCF-Diensts
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2ab3d780f85131fc7adf24c5f420bd5fe643d9e
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2018
---
# <a name="renaming-a-wcf-service"></a>Umbenennen eines WCF-Diensts
In diesem Thema wird beschrieben, wie Sie einen [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Dienst umbenennen.  
  
## <a name="renaming-a-wcf-service"></a>Umbenennen eines WCF-Diensts  
 Führen Sie die folgenden Schritte aus, um einen Dienst in einer [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Vorlage umzubenennen:  
  
-   Ändern Sie den Namen der Klasse, die den Dienst implementiert.  
  
-   Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Diensts in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt. Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   Handelt es sich um einen WebHosted-Dienst, verwendet er eine *.svc-Datei. Öffnen Sie die svc-Datei, und ändern Sie den Namen des Diensts, wie im folgenden Beispiel dargestellt. Dieser Schritt ist für selbst gehostete Anwendungen nicht erforderlich, da keine svc-Datei vorhanden ist.  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a>Umbenennen eines WCF-Dienstvertrags  
  
-   Führen Sie die folgenden Schritte aus, um den Dienstvertrag umzubenennen:  
  
-   Ändern Sie den Namen des Dienstvertrags.  
  
-   Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Dienstvertrags in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt. Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
