---
title: Umbenennen eines WCF-Diensts
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 1179e7b235130e1967c79843b7a11f55622a01fb
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052051"
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="e1a8d-102">Umbenennen eines WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="e1a8d-102">Renaming a WCF Service</span></span>
<span data-ttu-id="e1a8d-103">In diesem Thema wird beschrieben, wie Sie einen Windows Communication Foundation (WCF)-Dienst umbenennen können.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-103">This topic describes how you can rename a Windows Communication Foundation (WCF) service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="e1a8d-104">Umbenennen eines WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="e1a8d-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="e1a8d-105">Führen Sie die folgenden Schritte aus, um einen Dienst in einer Windows Communication Foundation (WCF)-Vorlage umzubenennen:</span><span class="sxs-lookup"><span data-stu-id="e1a8d-105">Perform the following steps to rename a service in a Windows Communication Foundation (WCF) template,</span></span>  
  
- <span data-ttu-id="e1a8d-106">Ändern Sie den Namen der Klasse, die den Dienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-106">Change the name of the class that implements the service.</span></span>  
  
- <span data-ttu-id="e1a8d-107">Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Diensts in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="e1a8d-108">Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- <span data-ttu-id="e1a8d-109">Wenn Ihr Dienst webgehostet ist, wird eine \* \* svc\* -Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-109">If your service is webhosted, it uses an *\*.svc* file.</span></span> <span data-ttu-id="e1a8d-110">Öffnen Sie die svc-Datei, und ändern Sie den Namen des Diensts, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="e1a8d-111">Dieser Schritt ist für selbst gehostete Anwendungen nicht erforderlich, da keine svc-Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```aspx-csharp
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="e1a8d-112">Umbenennen eines WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="e1a8d-112">Renaming a WCF Service Contract</span></span>  
  
- <span data-ttu-id="e1a8d-113">Führen Sie die folgenden Schritte aus, um den Dienstvertrag umzubenennen:</span><span class="sxs-lookup"><span data-stu-id="e1a8d-113">Perform the following steps to rename the service contract,</span></span>  
  
- <span data-ttu-id="e1a8d-114">Ändern Sie den Namen des Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-114">Change the name of the service contract.</span></span>  
  
- <span data-ttu-id="e1a8d-115">Ändern Sie in der Konfigurationsdatei des Diensts den Namen des Dienstvertrags in den neuen gewählten Namen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="e1a8d-116">Die Konfigurationsdatei ist je nach dem verwendeten Hostingmodell app.config oder web.config.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
