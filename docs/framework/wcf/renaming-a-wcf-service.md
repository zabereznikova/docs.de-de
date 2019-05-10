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
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="2fa4a-102">Umbenennen eines WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="2fa4a-102">Renaming a WCF Service</span></span>
<span data-ttu-id="2fa4a-103">In diesem Thema wird beschrieben, wie Sie einen Windows Communication Foundation (WCF)-Dienst umbenennen können.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-103">This topic describes how you can rename a Windows Communication Foundation (WCF) service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="2fa4a-104">Umbenennen eines WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="2fa4a-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="2fa4a-105">Führen Sie die folgenden Schritte aus, um einen Dienst in einer Windows Communication Foundation (WCF)-Vorlage umzubenennen,</span><span class="sxs-lookup"><span data-stu-id="2fa4a-105">Perform the following steps to rename a service in a Windows Communication Foundation (WCF) template,</span></span>  
  
- <span data-ttu-id="2fa4a-106">Ändern Sie den Namen der Klasse, die den Dienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-106">Change the name of the class that implements the service.</span></span>  
  
- <span data-ttu-id="2fa4a-107">Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Diensts in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="2fa4a-108">Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- <span data-ttu-id="2fa4a-109">Handelt es sich um einen WebHosted-Dienst, verwendet er eine \*.svc-Datei.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-109">If your service is webhosted, it uses an \*.svc file.</span></span> <span data-ttu-id="2fa4a-110">Öffnen Sie die svc-Datei, und ändern Sie den Namen des Diensts, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="2fa4a-111">Dieser Schritt ist für selbst gehostete Anwendungen nicht erforderlich, da keine svc-Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="2fa4a-112">Umbenennen eines WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="2fa4a-112">Renaming a WCF Service Contract</span></span>  
  
- <span data-ttu-id="2fa4a-113">Führen Sie die folgenden Schritte aus, um den Dienstvertrag umzubenennen:</span><span class="sxs-lookup"><span data-stu-id="2fa4a-113">Perform the following steps to rename the service contract,</span></span>  
  
- <span data-ttu-id="2fa4a-114">Ändern Sie den Namen des Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-114">Change the name of the service contract.</span></span>  
  
- <span data-ttu-id="2fa4a-115">Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Dienstvertrags in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="2fa4a-116">Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
