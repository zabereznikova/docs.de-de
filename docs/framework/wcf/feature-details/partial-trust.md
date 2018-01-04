---
title: "Teilweise Vertrauenswürdigkeit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489b1587-9909-4d0e-8c1a-5e83c8f8292b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac76f092d5583519220d2d1b7a8d6d1bbb665632
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="partial-trust"></a><span data-ttu-id="9c6e2-102">Teilweise Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="9c6e2-102">Partial Trust</span></span>
<span data-ttu-id="9c6e2-103">Ab [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] können teilweise vertrauenswürdige Aufrufer auf öffentliche Typen und Methoden zugreifen, die in <xref:System.ServiceModel>, <xref:System.Runtime.Serialization> und <xref:System.ServiceModel.Web> implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="9c6e2-103">Starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)], partially trusted callers can access public types and methods implemented in <xref:System.ServiceModel>, <xref:System.Runtime.Serialization>, and <xref:System.ServiceModel.Web>.</span></span> <span data-ttu-id="9c6e2-104">In diesem Abschnitt werden die für die Verwendung von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in teilweise vertrauenswürdigen Anwendungen unterstützten Szenarien sowie die eingeschränkte Teilmenge an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Funktionen beschrieben, die für Anwendungen verfügbar sind, die mit reduzierten Berechtigungen für die Codezugriffssicherheit (CAS) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9c6e2-104">This section describes supported scenarios for using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] within a partially trusted application as well as the limited subset of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] functionality available to applications running with reduced code access security (CAS) permissions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9c6e2-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9c6e2-105">In This Section</span></span>  
 [<span data-ttu-id="9c6e2-106">Unterstützte Bereitstellungsszenarien</span><span class="sxs-lookup"><span data-stu-id="9c6e2-106">Supported Deployment Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md)  
 <span data-ttu-id="9c6e2-107">Beschreibt die Hauptszenarien für die Ausführung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in teilweise vertrauenswürdigen Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="9c6e2-107">Describes the main partial trust scenarios for running [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="9c6e2-108">Featurekompatibilität für teilweise Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="9c6e2-108">Partial Trust Feature Compatibility</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md)  
 <span data-ttu-id="9c6e2-109">Beschreibt die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Funktionen, die nicht mit teilweiser Vertrauenswürdigkeit verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9c6e2-109">Describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] features that cannot be used with partial trust.</span></span>  
  
 [<span data-ttu-id="9c6e2-110">Bewährte Methoden für teilweise Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="9c6e2-110">Partial Trust Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md)  
 <span data-ttu-id="9c6e2-111">Enthält Best Practices zur Verwendung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in teilweise vertrauenswürdigen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="9c6e2-111">Contains best practices for using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in partially trusted applications.</span></span>
