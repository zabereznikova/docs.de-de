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
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="6f501-102">Umbenennen eines WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="6f501-102">Renaming a WCF Service</span></span>
<span data-ttu-id="6f501-103">In diesem Thema wird beschrieben, wie Sie einen [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Dienst umbenennen.</span><span class="sxs-lookup"><span data-stu-id="6f501-103">This topic describes how you can rename a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="6f501-104">Umbenennen eines WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="6f501-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="6f501-105">Führen Sie die folgenden Schritte aus, um einen Dienst in einer [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Vorlage umzubenennen:</span><span class="sxs-lookup"><span data-stu-id="6f501-105">Perform the following steps to rename a service in a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] template,</span></span>  
  
-   <span data-ttu-id="6f501-106">Ändern Sie den Namen der Klasse, die den Dienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="6f501-106">Change the name of the class that implements the service.</span></span>  
  
-   <span data-ttu-id="6f501-107">Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Diensts in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6f501-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="6f501-108">Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.</span><span class="sxs-lookup"><span data-stu-id="6f501-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   <span data-ttu-id="6f501-109">Handelt es sich um einen WebHosted-Dienst, verwendet er eine \*.svc-Datei.</span><span class="sxs-lookup"><span data-stu-id="6f501-109">If your service is webhosted, it uses an \*.svc file.</span></span> <span data-ttu-id="6f501-110">Öffnen Sie die svc-Datei, und ändern Sie den Namen des Diensts, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6f501-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="6f501-111">Dieser Schritt ist für selbst gehostete Anwendungen nicht erforderlich, da keine svc-Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6f501-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="6f501-112">Umbenennen eines WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="6f501-112">Renaming a WCF Service Contract</span></span>  
  
-   <span data-ttu-id="6f501-113">Führen Sie die folgenden Schritte aus, um den Dienstvertrag umzubenennen:</span><span class="sxs-lookup"><span data-stu-id="6f501-113">Perform the following steps to rename the service contract,</span></span>  
  
-   <span data-ttu-id="6f501-114">Ändern Sie den Namen des Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="6f501-114">Change the name of the service contract.</span></span>  
  
-   <span data-ttu-id="6f501-115">Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Dienstvertrags in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6f501-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="6f501-116">Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.</span><span class="sxs-lookup"><span data-stu-id="6f501-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
