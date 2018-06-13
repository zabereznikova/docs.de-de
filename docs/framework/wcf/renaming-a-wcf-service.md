---
title: Umbenennen eines WCF-Diensts
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: a215523b92757e3bde1dae2e50de22169020e870
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498986"
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="05cbe-102">Umbenennen eines WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="05cbe-102">Renaming a WCF Service</span></span>
<span data-ttu-id="05cbe-103">In diesem Thema wird beschrieben, wie Sie einen Windows Communication Foundation (WCF)-Dienst umbenennen können.</span><span class="sxs-lookup"><span data-stu-id="05cbe-103">This topic describes how you can rename a Windows Communication Foundation (WCF) service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="05cbe-104">Umbenennen eines WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="05cbe-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="05cbe-105">Führen Sie die folgenden Schritte aus, um einen Dienst in einer Vorlage für Windows Communication Foundation (WCF) umzubenennen,</span><span class="sxs-lookup"><span data-stu-id="05cbe-105">Perform the following steps to rename a service in a Windows Communication Foundation (WCF) template,</span></span>  
  
-   <span data-ttu-id="05cbe-106">Ändern Sie den Namen der Klasse, die den Dienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="05cbe-106">Change the name of the class that implements the service.</span></span>  
  
-   <span data-ttu-id="05cbe-107">Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Diensts in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="05cbe-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="05cbe-108">Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.</span><span class="sxs-lookup"><span data-stu-id="05cbe-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   <span data-ttu-id="05cbe-109">Handelt es sich um einen WebHosted-Dienst, verwendet er eine \*.svc-Datei.</span><span class="sxs-lookup"><span data-stu-id="05cbe-109">If your service is webhosted, it uses an \*.svc file.</span></span> <span data-ttu-id="05cbe-110">Öffnen Sie die svc-Datei, und ändern Sie den Namen des Diensts, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="05cbe-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="05cbe-111">Dieser Schritt ist für selbst gehostete Anwendungen nicht erforderlich, da keine svc-Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="05cbe-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="05cbe-112">Umbenennen eines WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="05cbe-112">Renaming a WCF Service Contract</span></span>  
  
-   <span data-ttu-id="05cbe-113">Führen Sie die folgenden Schritte aus, um den Dienstvertrag umzubenennen:</span><span class="sxs-lookup"><span data-stu-id="05cbe-113">Perform the following steps to rename the service contract,</span></span>  
  
-   <span data-ttu-id="05cbe-114">Ändern Sie den Namen des Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="05cbe-114">Change the name of the service contract.</span></span>  
  
-   <span data-ttu-id="05cbe-115">Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Dienstvertrags in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="05cbe-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="05cbe-116">Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.</span><span class="sxs-lookup"><span data-stu-id="05cbe-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
