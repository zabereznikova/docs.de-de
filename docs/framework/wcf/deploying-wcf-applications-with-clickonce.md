---
title: Bereitstellen von WCF-Anwendungen mit ClickOnce
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e87e01c39c5f50ff3f4d4e9479a68e19cceb90f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="ef2c5-102">Bereitstellen von WCF-Anwendungen mit ClickOnce</span><span class="sxs-lookup"><span data-stu-id="ef2c5-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="ef2c5-103">Clientanwendungen mit [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] werden möglicherweise mit ClickOnce-Technologie bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ef2c5-103">Client applications using [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="ef2c5-104">Diese Technologie ermöglicht es, den von der Codezugriffssicherheit bereitgestellten Laufzeitsicherheitsschutz zu nutzen, sofern die Clientanwendungen digital mit einem vertrauenswürdigen Zertifikat signiert sind.</span><span class="sxs-lookup"><span data-stu-id="ef2c5-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="ef2c5-105">Das Zertifikat, mit dem die ClickOnce-Anwendung signiert wird, muss sich im Speicher für vertrauenswürdige Herausgeber befinden. Die lokale Sicherheitsrichtlinie auf dem Clientcomputer muss so konfiguriert sein, dass signierte Anwendungen mit dem Zertifikat des Herausgebers Berechtigungen für volle Vertrauenswürdigkeit erhalten.</span><span class="sxs-lookup"><span data-stu-id="ef2c5-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="ef2c5-106">Informationen zum Konfigurieren von ClickOnce-Anwendungen und vertrauenswürdige Herausgeber finden Sie unter [vertrauenswürdige Herausgeber für die ClickOnce-Konfigurieren von](http://go.microsoft.com/fwlink/?LinkId=94774).</span><span class="sxs-lookup"><span data-stu-id="ef2c5-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](http://go.microsoft.com/fwlink/?LinkId=94774).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef2c5-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef2c5-107">See Also</span></span>  
 [<span data-ttu-id="ef2c5-108">Überblick über die Bereitstellung vertrauenswürdiger Anwendungen</span><span class="sxs-lookup"><span data-stu-id="ef2c5-108">Trusted Application Deployment Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=94775)  
 [<span data-ttu-id="ef2c5-109">ClickOnce-Bereitstellung für Windows Forms-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="ef2c5-109">ClickOnce Deployment for Windows Forms Applications</span></span>](http://go.microsoft.com/fwlink/?LinkId=94776)
