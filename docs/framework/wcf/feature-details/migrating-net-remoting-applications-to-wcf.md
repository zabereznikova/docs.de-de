---
title: Migrieren von .NET-Remoteanwendungen nach WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 240901f4fa04a2468d5964821680506ea117bf7f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="37dad-102">Migrieren von .NET-Remoteanwendungen nach WCF</span><span class="sxs-lookup"><span data-stu-id="37dad-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="37dad-103">**Dieses Thema bezieht sich auf eine veraltete Technologie, die zum Zwecke der Abwärtskompatibilität mit vorhandenen Anwendungen beibehalten wird und nicht für die neue Entwicklung empfohlen wird. Verteilte Anwendungen sollten jetzt mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] entwickelt werden.**</span><span class="sxs-lookup"><span data-stu-id="37dad-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].**</span></span>  
  
 <span data-ttu-id="37dad-104">Es gibt zwei Möglichkeiten, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit vorhandenen .NET-Remoting-Anwendungen zu nutzen: Integration und Migration.</span><span class="sxs-lookup"><span data-stu-id="37dad-104">There are two ways to take advantage of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="37dad-105">Bei der Integration können .Net Remoting 2.0 und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nebeneinander ausgeführt werden. So können Sie dieselben Geschäftsobjekte über beide Technologien gleichzeitig verfügbar machen, ohne den vorhandenen .Net Remoting 2.0-Code ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="37dad-105">Integration allows you to have .Net Remoting 2.0 and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .Net Remoting 2.0 code.</span></span> <span data-ttu-id="37dad-106">Voraussetzung der Integration ist, dass [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="37dad-106">Integration requires that you are running on [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 or greater.</span></span> <span data-ttu-id="37dad-107">Wenn Sie die Funktionen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nutzen möchten und keine Übertragungskompatibilität mit Remoting 2.0-Systemen benötigen, können Sie eine Migration des gesamten Diensts nach [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] durchführen.</span><span class="sxs-lookup"><span data-stu-id="37dad-107">If you want to take advantage of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="37dad-108">Eine Migration von .NET Remoting 2.0 nach [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] setzt Änderungen an der Schnittstelle des Remoteobjekts und seinen Konfigurationseinstellungen voraus.</span><span class="sxs-lookup"><span data-stu-id="37dad-108">Migration from .NET Remoting 2.0 to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="37dad-109">Beide der folgenden Themen werden behandelt, [von Remoting zu Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).</span><span class="sxs-lookup"><span data-stu-id="37dad-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37dad-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37dad-110">See Also</span></span>  
 [<span data-ttu-id="37dad-111">Konzeptionelle Übersicht</span><span class="sxs-lookup"><span data-stu-id="37dad-111">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
