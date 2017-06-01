---
title: "Umbenennen eines WCF-Diensts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Umbenennen eines WCF-Diensts
In diesem Thema wird beschrieben, wie Sie einen [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Dienst umbenennen.  
  
## Umbenennen eines WCF\-Diensts  
 Führen Sie die folgenden Schritte aus, um einen Dienst in einer [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Vorlage umzubenennen:  
  
-   Ändern Sie den Namen der Klasse, die den Dienst implementiert.  
  
-   Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Diensts in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt.Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.  
  
```  
<system.servicemodel>  
   <services>  
      <service name=”WcfService.NewName”>  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   Handelt es sich um einen WebHosted\-Dienst, verwendet er eine \*.svc\-Datei.Öffnen Sie die svc\-Datei, und ändern Sie den Namen des Diensts, wie im folgenden Beispiel dargestellt.Dieser Schritt ist für selbst gehostete Anwendungen nicht erforderlich, da keine svc\-Datei vorhanden ist.  
  
```  
<%@ ServiceHost Service=”WcfService.NewName”>  
```  
  
## Umbenennen eines WCF\-Dienstvertrags  
  
-   Führen Sie die folgenden Schritte aus, um den Dienstvertrag umzubenennen:  
  
-   Ändern Sie den Namen des Dienstvertrags.  
  
-   Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Dienstvertrags in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt.Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.  
  
```  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract=”WcfService.NewContractName” />  
      </service>  
   </services>  
</system.servicemodel>  
```