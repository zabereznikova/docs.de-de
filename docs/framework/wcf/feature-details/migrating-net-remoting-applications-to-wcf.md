---
title: Migrieren von .NET-Remoteanwendungen nach WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 4040fb0ac223f91705a49b733f6a1f42d144068e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091115"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="2b50f-102">Migrieren von .NET-Remoteanwendungen nach WCF</span><span class="sxs-lookup"><span data-stu-id="2b50f-102">Migrating .NET Remoting Applications to WCF</span></span>
**<span data-ttu-id="2b50f-103">Dieses Thema bezieht sich auf eine veraltete Technologie, die zum Zwecke der Abwärtskompatibilität mit vorhandenen Anwendungen beibehalten wird und nicht für die neue Entwicklung empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="2b50f-103">This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development.</span></span> <span data-ttu-id="2b50f-104">Verteilte Anwendungen sollten jetzt mithilfe von WCF entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="2b50f-104">Distributed applications should now be developed using WCF.</span></span>**  
  
 <span data-ttu-id="2b50f-105">Es gibt zwei Möglichkeiten von WCF mit vorhandenen .NET Remoting-Anwendungen nutzen: Integration und Migration.</span><span class="sxs-lookup"><span data-stu-id="2b50f-105">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="2b50f-106">Integration können Sie .NET Remoting 2.0 "und" WCF parallel ausgeführt wird, können Sie dieselben Geschäftsobjekte über beide Technologien gleichzeitig verfügbar zu machen ohne den vorhandenen .NET Remoting 2.0-Code ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="2b50f-106">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="2b50f-107">Voraussetzung der Integration ist, dass [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2b50f-107">Integration requires that you are running on [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 or greater.</span></span> <span data-ttu-id="2b50f-108">Wenn Sie WCF-Features nutzen möchten, und netzwerkkompatibilität mit Remoting 2.0-Systemen ist nicht erforderlich, können Sie Ihre gesamten Dienst zu WCF migrieren.</span><span class="sxs-lookup"><span data-stu-id="2b50f-108">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="2b50f-109">Migration von .NET Remoting 2.0 nach WCF erfordert Änderungen am-Schnittstelle des Remoteobjekts und ihre Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="2b50f-109">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="2b50f-110">Beide der folgenden Themen finden Sie im [von Remoting zu Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).</span><span class="sxs-lookup"><span data-stu-id="2b50f-110">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b50f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b50f-111">See also</span></span>

- [<span data-ttu-id="2b50f-112">Konzeptionelle Übersicht</span><span class="sxs-lookup"><span data-stu-id="2b50f-112">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
