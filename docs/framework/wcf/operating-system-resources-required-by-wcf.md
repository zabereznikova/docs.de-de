---
title: "Für WCF erforderliche Betriebssystemressourcen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6cfe114e5e044a6aaa1e356194a46b4a46011aa0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="1afdd-102">Für WCF erforderliche Betriebssystemressourcen</span><span class="sxs-lookup"><span data-stu-id="1afdd-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="1afdd-103">Das Funktionieren von [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] hängt von mehreren Ressourcen ab, die vom Betriebssystem bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1afdd-103">[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="1afdd-104">In der folgenden Tabelle sind diese Ressourcen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1afdd-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="1afdd-105">Ressource</span><span class="sxs-lookup"><span data-stu-id="1afdd-105">Resource</span></span>|<span data-ttu-id="1afdd-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1afdd-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="1afdd-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="1afdd-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="1afdd-108">Zur Unterstützung von OleTx-Transaktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1afdd-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="1afdd-109">IIS (Internet Information Services)</span><span class="sxs-lookup"><span data-stu-id="1afdd-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="1afdd-110">Erforderlich, wenn Sie IIS zum Hosten der Anwendung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1afdd-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="1afdd-111">Windows Process Activation Service (WAS)</span><span class="sxs-lookup"><span data-stu-id="1afdd-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="1afdd-112">Erforderlich, wenn Sie WAS zum Hosten der Anwendung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1afdd-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1afdd-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1afdd-113">See Also</span></span>  
 [<span data-ttu-id="1afdd-114">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="1afdd-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
