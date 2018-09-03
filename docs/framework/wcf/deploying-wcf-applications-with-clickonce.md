---
title: Bereitstellen von WCF-Anwendungen mit ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: d733c6f523393737418c6394707c1d4e6e9c1710
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467458"
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="f517a-102">Bereitstellen von WCF-Anwendungen mit ClickOnce</span><span class="sxs-lookup"><span data-stu-id="f517a-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="f517a-103">Mit Windows Communication Foundation (WCF) Client-Anwendungen können mithilfe von ClickOnce-Technologie bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f517a-103">Client applications using Windows Communication Foundation (WCF) may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="f517a-104">Diese Technologie ermöglicht es, den von der Codezugriffssicherheit bereitgestellten Laufzeitsicherheitsschutz zu nutzen, sofern die Clientanwendungen digital mit einem vertrauenswürdigen Zertifikat signiert sind.</span><span class="sxs-lookup"><span data-stu-id="f517a-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="f517a-105">Das Zertifikat, mit dem die ClickOnce-Anwendung signiert wird, muss sich im Speicher für vertrauenswürdige Herausgeber befinden. Die lokale Sicherheitsrichtlinie auf dem Clientcomputer muss so konfiguriert sein, dass signierte Anwendungen mit dem Zertifikat des Herausgebers Berechtigungen für volle Vertrauenswürdigkeit erhalten.</span><span class="sxs-lookup"><span data-stu-id="f517a-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="f517a-106">Informationen zum Konfigurieren von ClickOnce-Anwendungen und vertrauenswürdigen Herausgebern finden Sie unter [Konfigurieren von vertrauenswürdigen ClickOnce-Herausgebern](https://go.microsoft.com/fwlink/?LinkId=94774).</span><span class="sxs-lookup"><span data-stu-id="f517a-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](https://go.microsoft.com/fwlink/?LinkId=94774).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f517a-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f517a-107">See Also</span></span>  
 [<span data-ttu-id="f517a-108">Überblick über die Bereitstellung vertrauenswürdiger Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f517a-108">Trusted Application Deployment Overview</span></span>](https://go.microsoft.com/fwlink/?LinkId=94775)  
 [<span data-ttu-id="f517a-109">ClickOnce-Bereitstellung für Windows Forms-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f517a-109">ClickOnce Deployment for Windows Forms Applications</span></span>](https://go.microsoft.com/fwlink/?LinkId=94776)
